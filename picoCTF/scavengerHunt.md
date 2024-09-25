# Retos picoCTF

# Level Scavenger Hunt

## Objetivo
There is some interesting information hidden around this site http://mercury.picoctf.net:5080/. Can you find it?

## Solucion

**Bandera:** picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

La primer parte de la bandera esta en **http://mercury.picoctf.net:5080/**

```
<!doctype html>
<html>
  <head>
    <title>Scavenger Hunt</title>
    <link href="https://fonts.googleapis.com/css?family=Open+Sans|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="mycss.css">
    <script type="application/javascript" src="myjs.js"></script>
  </head>

  <body>
    <div class="container">
      <header>
		<h1>Just some boring HTML</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

      <div id="tabintro" class="tabcontent">
		<h3>How</h3>
		<p>How do you like my website?</p>
      </div>

      <div id="tababout" class="tabcontent">
		<h3>What</h3>
		<p>I used these to make this site: <br/>
		  HTML <br/>
		  CSS <br/>
		  JS (JavaScript)
		</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      </div>

    </div>

  </body>
</html>

```
La segunda parte esta en el .css

```
div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```

La tercera parte esta en **http://mercury.picoctf.net:5080/robots.txt**
```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
La cuarta parte esta en **http://mercury.picoctf.net:5080/.htaccess**
El archivo: .htaccess, maneja los permisos del servidor Apache

```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
El Store en mayusculas es pista para .DS_Store en una mac,al ingresar el archivo nos da lo que falta de la bandera.

```
Congrats! You completed the scavenger hunt. Part 5: _35844447}
```

## Referencias


