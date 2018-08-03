#  CSS Básico - Atualização 2  

https://www.schoolofnet.com/curso-css-basico-rev2/

---

## <a name="indice">Índice</a>

- [Introdução](#parte1)   
- [Entendendo CSS na prática](#parte2)   
- [Seletores CSS](#parte3)   
- [Relacionamento de seletores](#parte4)   
- [Prioridade de substituição](#parte5)   
- [Pseudo-seletores](#parte6)   
- [Exemplo prático links](#parte7)   
- [Outros seletores interessantes](#parte8)   
- [Folhas de estilos externas](#parte9)   
- [Fontes](#parte10)   
- [Margem e borda](#parte11)   
- [Display e visibilidade](#parte12)   
- [Posicionamento](#parte13)   
- [Exemplo prático menu](#parte14)   
- [Exemplo prático formulário](#parte15)   



---

## <a name="parte1">Introdução</a>


[Voltar ao Índice](#indice)

---

## <a name="parte2">Entendendo CSS na prática</a>

```html
<!doctype html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        header{
            background-color: red ;
        }
        footer{
            background-color: green;
        }
    </style>
</head>
<body>
<header>
    <div>
        <div><a href="">LogoMarca</a></div>
    </div>
</header>
<main>
    <section>
        <h1>Conteúdo</h1>
        <p>Um texto qualquer</p>
    </section>
</main>
<footer>
    <div>
        <p>&copy; Todos os direitos reservados</p>
    </div>
</footer>
</body>
</html>
```

[Voltar ao Índice](#indice)

---

## <a name="parte3">Seletores CSS</a>

```html
<!doctype html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        #header{
            background-color: red ;
        }
        #footer{
            background-color: green;
        }
        .logomarca{
            background-color: blue;
        }
    </style>
</head>
<body>
<header id="header">
    <div>
        <div class="logomarca">
            <a href="">LogoMarca</a>
        </div>
    </div>
</header>
<main id="main">
    <section>
        <h1>Conteúdo</h1>
        <p>Um texto qualquer</p>
    </section>
</main>
<footer id="footer">
    <div>
        <p>&copy; Todos os direitos reservados</p>
    </div>
</footer>
</body>
</html>
```

[Voltar ao Índice](#indice)

---

## <a name="parte4">Relacionamento de seletores</a>

```css
        #footer > .logomarca {
            color: white;
        }
```

```html
<footer id="footer">
    <section>
        <p class="logomarca">&copy; Todos os direitos reservados</p>
    </section>
    <a class="logomarca">&copy; Todos os direitos reservados</a>
</footer>
```


[Voltar ao Índice](#indice)

---

## <a name="parte5">Prioridade de substituição</a>

```css
 /*
            tag
            classe
            id      <- Mais específico
        */
        .header a{
            color: blue;
        }
        header a{
            color:red;
        }
        #header div div a{
            background-color: blueviolet;
            color: gray;
        }
        #header div div a{
            background-color: white;
            color: green;
        }
        #header a{
            color: yellow;
        }
```

```html
<header class="header" id="header">
    <div>
        <div>
            <a href="" class="logomarca">LogoMarca</a>
        </div>
    </div>
</header>
```

[Voltar ao Índice](#indice)

---

## <a name="parte6">Pseudo-seletores</a>

```css
  a {
            color: green;
        }

        a:hover {
            color: red;
        }
        a:active {
            color: yellow;
        }
        a:focus {
            color: blue;
        }
        input:focus{

        }
        div:focus-within{
            background-color: darkred;
        }
```

```html
<header class="header" id="header">
    <div>
        <div>
            <a href="" class="logomarca">LogoMarca</a>
            <input type="text">
        </div>
    </div>
</header>
```

[Voltar ao Índice](#indice)

---

## <a name="parte7">Exemplo prático links</a>

```html
<!doctype html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body{
            padding: 10px;
        }

        .btn{
            background-color: darkgray;
            color: #fff;
            text-decoration: none;
            padding: 10px 20px;
            border-radius: 10px;
        }
        .btn:hover{
            background-color: gray;
        }
        .btn.btn-red{
            background-color: darkred;
            color: #fff;
        }
        .btn-red:hover{
            background-color: red;
        }

        .btn.btn-blue{
            background-color: blue;
            color: #fff;
        }
        .btn-blue:hover{
            background-color: #2980b9;
        }

    </style>
</head>
<body>

    <a class="btn btn-red" href="">item 1</a>
    <a class="btn btn-blue" href="">item 2</a>
    <a class="btn" href="">item 3</a>
    <a class="btn" href="">item 5</a>

</body>
</html>
```


[Voltar ao Índice](#indice)

---

## <a name="parte8">Outros seletores interessantes</a>

```css
  * {
            border: 1px solid red;
        }


        header + main{
            border: 5px solid blue;
        }

        header ~ main{ /* menos restritivo */
            border: 5px solid blue;
        }
        a[title]{
            color: red;
        }
        a[title='item 1']{
            color: lime;
        }
        a[class*="btn"]{

        }

```

[Voltar ao Índice](#indice)

---

## <a name="parte9">Folhas de estilos externas</a>

```html
    <link rel="stylesheet" href="style.css">
```
```css
@import "botoes.css";
/*reset*/
* {
    border: 1px solid red;
}


header + main{
    border: 5px solid blue;
}

header ~ main{ /* menos restritivo */
    border: 5px solid blue;
}

```

[Voltar ao Índice](#indice)

---

## <a name="parte10">Fontes</a>

- https://fonts.google.com/

```css
@import url('https://fonts.googleapis.com/css?family=Encode+Sans+Semi+Condensed');
body{
    padding: 10px;
    background-color: white;
    font-family: 'Encode Sans Semi Condensed', sans-serif;
    font-size: 16px;
    font-weight: bold;
}
```


[Voltar ao Índice](#indice)

---

## <a name="parte11">Margem e borda</a>


[Voltar ao Índice](#indice)

---

## <a name="parte12">Display e visibilidade</a>


[Voltar ao Índice](#indice)

---

## <a name="parte13">Posicionamento</a>


[Voltar ao Índice](#indice)

---

## <a name="parte14">Exemplo prático menu</a>


[Voltar ao Índice](#indice)

---

## <a name="parte15">Exemplo prático formulário</a>


[Voltar ao Índice](#indice)

---