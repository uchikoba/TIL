ES6で使えるようになった、 `let` と `const` 、 `var` と何が違うのか調べた

- `'use strict'` って書かないと使えない
- var
  - 何度でも宣言可能
  - 値の再代入：OK
- let
  - 一度宣言したら再宣言はできない
  - 値の再代入：OK
- const
  - 一度宣言したら再宣言はできない
  - 値の再代入：NG

```JavaScript
var aaa = "AAA"; // 問題ない
var aaa = "BBB"; // これも大丈夫

console.log(aaa); // #=> BBB

let bbb = "CCC"; // 大丈夫
bbb = "DDD"; // これも大丈夫

console.log(bbb); // #=> DDD

let bbb = "EEE"; // これはNG

const ccc = "FFF"; // OK

console.log(ccc); // #=> FFF

ccc = "GGG"; // NG
const ccc = "HHH"; // これもNG
```

スコープも違う  
varはif内で宣言した後、外部からも参照可能。let と constは駄目。
```JavaScript
if (true) {
  var i = 10;
}
console.log(i); // #=> 10

if (true) {
  let j = 20;
}
console.log(j); // Reference Error

if (true) {
  let k = 30;
}
console.log(k); // Reference Error

let x = 40;
const y = 50;
if (true) {
  console.log(i); // #=> 10
  console.log(x); // #=> 40
  console.log(y); // #=> 50
}
```

オブジェクトの要素に対してはletだろうがconstだろうが変更できる
```JavaScript
var a = {one: 1, two: 2};
a.one = 11; // OK
a = 1;
console.log(a);

let b = {one: 1, two: 2};
b.one = 11; // OK
b = 11; // OK
console.log(b);

const c = {one: 1, two: 2};
c.one = 11; // OK
console.log(c);

c = 1; // これはNG
```
