---
title: "Javascript: Condicionales"
description: "Aprenderemos sobre condiciones en Javascript así como su implementación"
pubDate: "Jan 18 2024"
heroImage: "../img/img_blog/ckteamRed.webp"
---
**Tomando Decisiones en JavaScript: El Poder de las Estructuras de Control de Flujo**

プログラミングの世界では、動的で適応的なコードを作成するには、意思決定を行う能力が不可欠です。 JavaScript では、この目的のための重要なツールの 1 つは「if」制御フロー構造です。 「if」とそのバリエーションの使用法を探求してみましょう。

![ckteam](/img/img_blog/ckteamRed.webp)

### 1. if-else: 異なるルートを選択する

「if-else」構造を使用すると、条件が true か false に応じて、異なるコード ブロックを実行できます。実際の例を見てみましょう。

```javascript
let edad = 18;

if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad");
}
```

ここで、プログラムは人が成人か未成年かを判断し、対応するメッセージを出力します。それは、交差点で 2 つの可能な道があるようなものです。


### 2. if-else if-else: オプション間の移動

複数の条件があるより複雑な状況の場合は、「else if」を使用して追加のケースを評価できます。

```javascript
let hora = 14;

if (hora < 12) {
  console.log("Buenos días");
} else if (hora < 18) {
  console.log("Buenas tardes");
} else {
  console.log("Buenas noches");
}
```

ここでは、プログラムが一日の時間帯に基づいてあなたを迎え、朝、午後、夕方にパーソナライズされたメッセージを提供します。

### 3. 三項演算子: エレガントなライン

三項演算子は、「if-else」構造を 1 行で表現する簡潔な方法です。

```javascript
let esMayor = edad >= 18 ? "Mayor de edad" : "Menor de edad";
console.log(esMayor);
```

このアプローチは、条件に基づいて効率的に値を割り当てたい場合に特に便利です。

### 4. スイッチ: 構造化された代替手段

「switch」は、複数のケースがあり、式の値に基づいてコードの異なるブロックを実行したい場合に最適です。

```javascript
let diaDeLaSemana = "Lunes";

switch (diaDeLaSemana) {
  case "Lunes":
    console.log("Comienzo de la semana");
    break;
  case "Viernes":
    console.log("¡Viernes, por fin!");
    break;
  default:
    console.log("Es otro día de la semana");
}
```

この構造はオプション メニューに似ており、コードが対応するケースに誘導されます。

### 5. 真実と虚偽: 厳密な真偽を超えて

ブール値のコンテキストでは、値は「真実」または「偽」に評価されます。これは、次のように「if」ステートメントで利用できます。

```javascript
let nombre = "";

if (nombre) {
  console.log("El nombre es truthy");
} else {
  console.log("El nombre es falsy");
}
```

ここで、プログラムは、名前がブール値のコンテキストで「真実」と見なされるか「偽」と見なされるかを決定します。

JavaScript のこれらの制御フロー構造を理解することで、コードの動作をガイドする強力なツールを備えることができます。プログラムを探索、実験し、情報に基づいた意思決定を行ってください。