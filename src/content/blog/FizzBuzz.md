---
title: "Aprende a resolver el desafío de FizzBuzz"
description: "Resolviendo pruebas técnicas: FizzBuzz"
pubDate: "Mar 06 2024"
heroImage: "../img/img_blog/ckteam_code.webp"

---
### FizzBu​​zz の課題を解決するためのステップバイステップ ガイド

FizzBu​​zz チャレンジは、就職面接で最も一般的なチャレンジの 1 つです。目標は、受験者の基本的なコードを記述し、ループ、条件、算術演算などの基本的な概念を理解する能力をテストすることです。このガイドでは、問題を段階的に分解し、その解決方法を説明します。

![C & K Team image IA, coding](/img/img_blog/ckteam_code.webp)

### 数学における倍数の紹介

FizzBu​​zz のソリューションを見始める前に、数学における倍数とは何かを理解することが重要です。これが重要な点だからです。
そして、結局のところ、自分が書いていることを理解していなければ、その方法を覚えても意味がありません。したがって、倍数とは何か、またその取得方法についてすでに理解している場合は、この部分を飛ばしてください。

数値の倍数は、その数値を整数で乗算した結果として得られる別の数値です。たとえば、3 の最初の倍数は、それぞれ 3 に 1、2、3、4 などを乗じることによって得られるため、3、6、9、12 などになります。
```javascript
Para encontrar los múltiplos de 3:
- Multiplicamos el número base (3) por los enteros sucesivos:
   3 * 1 = 3
   3 * 2 = 6
   3 * 3 = 9
   3 * 4 = 12
   y así sucesivamente
```
#### El múltiplo común

公倍数とは、同時に 2 つ以上の数値の倍数である数値のことを指します。たとえば、3 と 5 の公倍数は、3 と 5 の両方で割り切れる数値です。数学では、最小公倍数 (lcm) の概念を使用して 2 つの数値の最小公倍数を見つけることができます。

```javascript
2 つの数値 (a と b) の公倍数を見つけるには:
- 各数値の倍数を個別に識別します。
- 両方の倍数セットに現れる最初の数字を探します。

たとえば、3 と 5 の公倍数を見つけるには、次のようにします。
- 各基数 (3 と 5) に連続する整数を掛けます。
 3 の倍数: 3、6、9、12、13、14、15...
 5 の倍数: 5、10、15、20、...
- 最初の数字が
 両方の倍数セットに現れるのは 15 です。
- したがって、15 は 3 と 5 の最小公倍数です。

```
### 倍数を取得するロジックを理解する
どの数値が特定の数値 **(例: 3)** の倍数ではないかを判断するには、剰余演算子 ``(%)`` を使用できます。

#### 倍数であるかどうか

数値が 3 で割り切れない場合 (つまり、3 で割った余りがゼロでない場合)、その数値は 3 の倍数ではありません。


`1 から n までの各整数について: 数値 % 3 が 0 に等しい場合: その数値は 3 の倍数です。`
このコードでは、「%」はモジュラス演算子で、2 つの数値の除算の余りを返します。 **数値と 3 の割り算の余りが 0** の場合、その数値は 3 の倍数であることを意味します。

たとえば、このコードを 1 から 10 までの数字に適用すると、
「3 の倍数ではない数は、1、2、4、5、7、8、10 である」ことがわかります。
これは、これらの数値を 3 で割ったときに、ゼロに等しい余りが得られないためです。

```javascript
//ejemplo Si es multiplo

let residuo = 3 %3;

console.log(residuo);

//ejemplo NO es multiplo

let residuo = 5 %3;

console.log(residuo);
```

これらの基本を確認したので、FizzBu​​zz の課題に取り組むことができます。

＃＃ チャレンジ
```javascript
// Escribe un programa que muestre por consola  los
//  números de 1 a 100 (ambos incluidos y con un salto de línea entre
//  cada impresión), sustituyendo los siguientes:
//  - Múltiplos de 3 por la palabra "fizz".
//  - Múltiplos de 5 por la palabra "buzz".
//  - Múltiplos de 3 y de 5 a la vez por la palabra "fizzbuzz".


```

#### ステップ 1: ループを初期化する

まず、1 から 100 までの数字をループするループを作成しましょう。これは、多くのプログラミング言語の「for」ループで実現できます。

```javascript
for (let i = 1; i <= 100; i++) {
    // Cuerpo del bucle
}
```

このループは本体内のコードを 100 回実行します。「i」は各反復で 1 から 100 までの値を取ります。

#### ステップ 2: 3 と 5 の倍数を確認する

ループ内で、現在の数値 (「i」) が 3、5、またはその両方の倍数であるかどうかを確認します。 3の倍数の場合は「fizz」と出力します。 5の倍数の場合は「buzz」と出力します。両方の倍数の場合は、「fizzBu​​zz」と出力します。

```javascript
if (i % 3 === 0 && i % 5 === 0) {
    console.log("fizzBuzz");
} else if (i % 3 === 0) {
    console.log("fizz");
} else if (i % 5 === 0) {
    console.log("buzz");
} else {
    console.log(i);
}
```

式 `i % 3 === 0` は、余りを残さずに `i` が 3 で割り切れるかどうかをチェックします。同じことが 5 にも当てはまります。 `i` が両方で割り切れる場合、それは 3 の公倍数であり、 5.

#### ステップ 3: ソリューションを実行してテストする

コードが完成したら、それを実行して結果を確認します。これにより、ソリューションが正しく機能し、FizzBu​​zz ルールに従って予想される一連の数字と単語が生成されるかどうかを確認できます。

```javascript
function fizzBuzz() {
    for (let i = 1; i <= 100; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
            console.log("fizzBuzz");
        } else if (i % 3 === 0) {
            console.log("fizz");
        } else if (i % 5 === 0) {
            console.log("buzz");
        } else {
            console.log(i);
        }
    }
}

fizzBuzz(); // Llamamos a la función para ejecutarla
```

このコードを実行すると、FizzBu​​zz ルールに従って、予想される一連の数字と単語が表示されるはずです。

これで、FizzBu​​zz の課題を解決するためのステップバイステップ ガイドは終わりです。この説明が明確であり、この一般的なプログラミングの問題への対処方法を理解するのに役立つことを願っています。今後のコーディングの課題も頑張ってください。