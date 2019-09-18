ES6で使えるようになった、 `let` と `const` 、 `var` と何が違うのか調べた

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
