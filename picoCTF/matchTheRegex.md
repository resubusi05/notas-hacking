# Retos picoCTF

# Level Match The Regex

## Objetivo
How about trying to match a regular expression The website is running here.

## Solucion
e inspecciona el codigo fuente de la pagina y dentro de este se encuentra el comatario: // ^p.....F!? eso nos indica que la contraseña va desde la letra p y avanza cinco caracteres mas y termina en F eso nos puede dar pistas de la bandera, as`i que intentamos con "picoCTF" y nos da la bandera.

```
<!DOCTYPE html>
<html>

<head>
	<!-- <link rel="stylesheet" href="./index.css" /> -->
	<style>
		.heading {
			width: 100%;
			height: 40px;
			background-color: coral;
			padding-left: 10px;
			font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		}

		.normal-form {
			text-align: center;
			margin-top: 5%;
		}

		#submit-but {
			border-radius: 0;
			width: 250px;
			height: 25px;

		}

		#name {
			width: 250px;
			height: 25px;
			background-color: rgb(241, 226, 206);
		}

		#sub-heading {
			color: brown;
		}
	</style>
</head>

<body>

	<h1 class="heading">PicoCTF</h1>
	<p></p>

	<div class="normal-form">
		<h2 id="sub-heading">Valid Input</h2>
		<form action="#" onsubmit="return send_request()">
			<input type="text" id="name" name="input" placeholder="Input text">
			<br>
			<br>
			<button id="submit-but" type="submit" id="submit-button">SUBMIT</button>
		</form>
	</div>
</body>
<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>

</html>
```

picoCTF{succ3ssfully_matchtheregex_08c310c6}

## Referencias


