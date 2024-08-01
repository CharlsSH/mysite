---
title: "Introducción al DOM y su Manipulación"
description: "El Document Object Model (DOM) es una interfaz de programación para documentos HTML y XML."
pubDate: "Feb 18 2024"
heroImage: "../img/img_blog/ckteam_funko.webp"
---

ドキュメント オブジェクト モデル (DOM) は、HTML および XML ドキュメントのプログラミング インターフェイスです。これはドキュメント構造をノードのツリーとして表し、開発者が JavaScript またはその他のブラウザベースのテクノロジを使用して Web ページの要素とコンテンツに動的にアクセス、操作、および更新できるようにします。
![C & K Team](/img/img_blog/ckteam_funko.webp)


## **重要な概念**


1. **ノード**: DOM では、HTML 要素、属性、テキスト、コメントなどのドキュメントの各部分がノードとして表されます。ノードは親子関係を持つことができ、プログラムからアクセス、変更、削除できます。



2. **ノード ツリー**: DOM はノードをツリー構造に編成します。ルート ノードはドキュメント全体であり、他のノードはその子孫です。この階層構造により、ドキュメント要素の移動と操作が容易になります。

3. **要素**: これらは、`<div>`、`<p>`、`<h1>` など、ドキュメント内の HTML タグを表すノードです。各要素には属性と関連するコンテンツを含めることができます。

4. **属性**: これらは、`id`、`class`、`src` など、開始タグで指定される要素の追加の特性です。 JavaScript を使用して属性にアクセスして変更し、要素の動作やスタイルを変更できます。

5. **イベント**: DOM では、マウスのクリック、キーストローク、フォームの変更などのイベントを通じてユーザーと対話できます。イベントをリッスンして JavaScript で処理し、ユーザーのアクションに応じて特定のアクションを実行できます。

6. **要素の選択**: 開発者は、`getElementById()`、`querySelector()`、`getElementsByClassName()` などのさまざまなメソッドを使用して DOM から要素を選択できます。これらのメソッドを使用すると、ID、クラス、ラベル、またはその他の選択基準に基づいて特定の要素にアクセスできます。

![tipos de Nodos](/img/img_blog/tipos_nodos.webp)

## **JavaScript を使用して DOM を変更する方法**

1. **getElementById()**: 指定された `id` 属性の値を持つ最初の要素を返します。

2. **querySelector()**: ドキュメント内で指定された CSS セレクターに一致する最初の要素を返します。

3. **createElement()**: 指定されたタグ名で新しい要素を作成します。

4. **appendChild()**: 指定された親ノードの最後の子としてノードを追加します。

5. **innerHTML**: 要素の HTML コンテンツを提供または返し、要素の HTML コンテンツを変更できるようにします。

6. **classList**: 要素の CSS クラスを追加、削除、切り替えするメソッドを提供し、スタイルを動的に簡単に操作できるようにします。

## **メソッドの使用例**



## **要素の子/親へのアクセス**

要素の子を直接操作することに加えて、DOM 内の要素の親要素と子要素にアクセスできると便利なことがよくあります。その方法の例をいくつか示します。

1. **要素の親にアクセスします**

段落をクリックしたときにその背景を強調表示したいが、段落コンテナの背景も変更したいとします。これは、段落の親にアクセスすることで実現できます。

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM の親/子へのアクセス</title>
    <style>
        .resaltado {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <div id="contenedor">
        <p onclick="resaltarElemento(this)">Haz clic aquí</p>
    </div>
    <script>
        function resaltarElemento(elemento) {
            elemento.classList.add('resaltado');
            const padre = elemento.parentNode;
            padre.style.backgroundColor = 'lightblue';
        }
    </script>
</body>
</html>
```

この例では、段落をクリックすると `highlightElement()` 関数が実行され、段落が引数として渡されます。この関数内で、段落に「ハイライト」クラスを追加して、その背景を強調表示します。次に、`parentNode`で段落の親にアクセスし、コンテナの背景色を変更します。

2. **要素の子にアクセスします**

コンテナの子要素の数をカウントし、その数をメッセージに表示したいとします。これは、コンテナーの子のリストにアクセスすることで実現できます。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Accediendo a Padres/Hijos del DOM</title>
</head>
<body>
    <div id="contenedor">
        <p>Primer párrafo</p>
        <p>Segundo párrafo</p>
        <p>Tercer párrafo</p>
    </div>
    <button onclick="contarHijos()">Contar Hijos</button>
    <script>
        function contarHijos() {
            const contenedor = document.getElementById('contenedor');
            const cantidadHijos = contenedor.children.length;
            alert('El contenedor tiene ' + cantidadHijos + ' hijos.');
        }
    </script>
</body>
</html>
```

この例では、「CountChildren」ボタンをクリックすると、「countChildren()」関数が実行されます。この関数内では、`getElementById('container')` を使用してコンテナー `<div>` を選択し、`children` を使用してその子のリストにアクセスします。このリストの長さを計算して子の数を取得し、この数を警告メッセージに表示します。



## **新しい要素の作成**

DOM 内の既存の要素にアクセスして変更することに加えて、新しい要素を動的に作成し、必要に応じて Web ページに追加するのが一般的です。新しい要素を作成して DOM に追加する方法の例をいくつか示します。

1. **新しい要素を作成し、別の要素の子として追加します**

ユーザーがボタンをクリックするたびに、新しいリスト項目 `<li>` を順序なしリスト `<ul>` に追加するとします。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Creación de Nuevos Elementos en el DOM</title>
</head>
<body>
    <ul id="miLista">
        <li>Elemento 1</li>
        <li>Elemento 2</li>
        <li>Elemento 3</li>
    </ul>
    <button onclick="agregarElemento()">Agregar Elemento</button>
    <script>
        function agregarElemento() {
            const lista = document.getElementById('miLista');
            const nuevoElemento = document.createElement('li');
            nuevoElemento.textContent = 'Nuevo elemento';
            lista.appendChild(nuevoElemento);
        }
    </script>
</body>
</html>
```

En este ejemplo, al hacer clic en el botón "Agregar Elemento", se ejecuta la función `agregarElemento()`. Dentro de esta función, creamos un nuevo elemento `<li>` con `createElement('li')` y le asignamos el texto 'Nuevo elemento' con `textContent`. Luego, utilizamos `appendChild(nuevoElemento)` para agregar este nuevo elemento como el último hijo de la lista desordenada.

2. **Crear un nuevo elemento con atributos y estilos**

Supongamos que queremos crear un nuevo botón con un texto personalizado y un estilo específico:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Creación de Nuevos Elementos en el DOM</title>
    <style>
        .botonPersonalizado {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="contenedorBoton"></div>
    <script>
        const contenedor = document.getElementById('contenedorBoton');
        const nuevoBoton = document.createElement('button');
        nuevoBoton.textContent = 'Haz clic aquí';
        nuevoBoton.classList.add('botonPersonalizado');
        contenedor.appendChild(nuevoBoton);
    </script>
</body>
</html>
```

En este ejemplo, creamos un nuevo botón utilizando `createElement('button')` y le asignamos el texto 'Haz clic aquí' con `textContent`. Luego, agregamos la clase 'botonPersonalizado' al botón con `classList.add('botonPersonalizado')` para aplicar estilos CSS personalizados. Finalmente, utilizamos `appendChild(nuevoBoton)` para agregar este nuevo botón como hijo del contenedor.

**Añadiendo Elementos al DOM**

Una de las capacidades fundamentales de JavaScript en la manipulación del DOM es la capacidad de agregar nuevos elementos al árbol de documentos de manera dinámica. Aquí hay algunos ejemplos de cómo puedes hacerlo:

1. **Añadir un nuevo párrafo al final del cuerpo del documento:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Añadir elementos al DOM</title>
</head>
<body>
    <script>
        // Crear un nuevo elemento de párrafo
        const nuevoParrafo = document.createElement('p');
        // Asignar texto al párrafo
        nuevoParrafo.textContent = 'Este es un nuevo párrafo añadido dinámicamente.';
        // Agregar el párrafo al final del cuerpo del documento
        document.body.appendChild(nuevoParrafo);
    </script>
</body>
</html>
```

En este ejemplo, se crea un nuevo elemento de párrafo utilizando `document.createElement('p')`, se le asigna texto utilizando la propiedad `textContent`, y luego se agrega al final del cuerpo del documento utilizando `document.body.appendChild(nuevoParrafo)`.
```html
<!DOCTYPE html>
<html>
<head>
    <title>Manipulación del DOM</title>
    <style>
        .resaltado {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div id="contenedor"></div>
    <button onclick="agregarElemento()">Agregar Elemento</button>
    <script>
        function agregarElemento() {
            const padre = document.getElementById('contenedor');
            const nuevoElemento = document.createElement('p');
            nuevoElemento.innerHTML = 'Nuevo elemento';
            nuevoElemento.classList.add('resaltado');
            padre.appendChild(nuevoElemento);
        }
    </script>
</body>
</html>

```

Este código crea un nuevo párrafo cuando se hace clic en el botón "Agregar Elemento", le asigna contenido y una clase, y lo agrega como hijo del div con el id 'contenedor'.

2. **Añadir un nuevo elemento a un contenedor específico:**


```html
<!DOCTYPE html>
<html>
<head>
    <title>Añadir elementos al DOM</title>
</head>
<body>
    <div id="contenedor">
        <!-- Este es el contenedor donde se añadirá el nuevo elemento -->
    </div>
    <script>
        // Obtener el contenedor
        const contenedor = document.getElementById('contenedor');
        // Crear un nuevo elemento de enlace
        const nuevoEnlace = document.createElement('a');
        // Asignar atributos al enlace
        nuevoEnlace.href = 'https://myportfoliosite-eosin.vercel.app/';
        nuevoEnlace.textContent = 'Mi portfolio';
        // Agregar el enlace al contenedor
        contenedor.appendChild(nuevoEnlace);
    </script>
</body>
</html>
```

En este ejemplo, se obtiene el contenedor mediante `document.getElementById('contenedor')`, se crea un nuevo elemento de enlace con `document.createElement('a')`, se le asignan atributos como `href` y `textContent`, y luego se agrega al contenedor utilizando `contenedor.appendChild(nuevoEnlace)`.



## **Recap: Más Ejemplos de Manipulación del DOM**

1. Cambiar el contenido de un elemento existente:

```javascript
const elemento = document.getElementById('miElemento');
elemento.innerHTML = 'Nuevo contenido';
```

2. Eliminar un elemento del DOM:

```javascript
const elemento = document.getElementById('elementoAEliminar');
elemento.parentNode.removeChild(elemento);
```

3. Agregar un manejador de eventos a un elemento:

```javascript
const boton = document.getElementById('miBoton');
boton.addEventListener('click', function() {
    alert('¡Haz hecho clic en el botón!');
});
```
