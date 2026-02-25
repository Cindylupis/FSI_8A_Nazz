## Descripción

There is some interesting information hidden around this site. Can you find it?http://wily-courier.picoctf.net:63835/
## Solución

**Solución 1
```
---------------PARTE 1--------------------------------------------
INDEX 
|
|
V   
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
<!-- Here's the first part of the flag: picoCTF{t -->

------------PARTE 2---------------------------------------------------
mycss.css
|
|
v
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

--------------PARTE 3-------------------------------------------------
http://wily-courier.picoctf.net:63835/robots.txt
|
|
V
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

-------------PARTE 4-------------------------------------------------
http://wily-courier.picoctf.net:63835/.htaccess
|
|
V
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

-------------PARTE 5--------------------------------------------------
http://wily-courier.picoctf.net:63835/.DS_Store
|
|
V
Congrats! You've completed the scavenger hunt! Part 5: _9588550}

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}

```

#### NOTAS
- La pista en `robots.txt` mencionará que el sitio usa **Apache**. En este tipo de servidores, existe un archivo oculto llamado `.htaccess` que controla la configuración de las carpetas.
- Si la pista menciona algo sobre archivos almacenados en una Mac, se refiere a los archivos de metadatos llamados `.DS_Store`.