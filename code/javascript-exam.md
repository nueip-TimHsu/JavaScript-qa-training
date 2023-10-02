# JavaScript 測驗

## 概述

這是一個基於JavaScript的測驗，旨在評估 QA Team 在 JavaScript 的基礎知識和編程能力。

## 題目

### 1. 基礎知識

1. **變數與資料類型**：請解釋`let`、`const`和`var`的區別。

```JavaScript
var宣告的變數在運行時就會被"提升"用下例來解釋
console.log(a);
var a = 0；
這時會回應undefined，因為在執行時a已經被提升上去了，然後還沒運行到a=0所以是console.log時 a沒有值

let的話只會在它所在的區域內有效
像是function a()
{
let a = 0;
  }
這時a只在{}內有效

const宣告的變數不可以被修改
const宣告的array、object一樣不能修改裡面的值，但可以加值進去
```

1. **函數**：如何定義一個函數？箭頭函數和傳統函數有何不同？

```JavaScript
1、
傳統函數
function 函數名稱()
{
函式內容
}


箭頭函數
const 函式名稱 或 (參數) =>
{
函式內容
}
2、
箭頭函數寫起來比較簡潔


```

3. **陣列方法**：請解釋`map`、`filter`和`reduce`的用途。

```
filter:
將陣列依下的條件篩選，再將符合條件的資料回傳新的陣列
map
對陣列裡所有資料執行函式，然後將回傳的值組成新的陣列
reduce
將陣列所有資料左至右進行累積計算
最後會得到一個單一值



```

### 2. 編程練習

1. **FizzBuzz**：
  2_1.html

2. **陣列操作**：
  給定一個數字陣列，例如`[1, 2, 3, 4, 5]`，請寫一個函數返回一個新陣列，其中每個元素都乘以2。

  ```

  2_2.html
  
  
  ```

3. **使用 axios 取得 API 資料**：
  請使用 `axios` 函式庫，從以下的 API 端點取得資料：
  > https://jsonplaceholder.typicode.com/posts

  當資料成功取得後，請將該文章的標題（title）以及內文（body）渲染至畫面上。

  ```
   2_3.html 
  ```

### 3. 進階問題

1. **`this` 關鍵字**：
  - 請解釋 JavaScript 中的 `this` 關鍵字。
  - 在哪些情境下，`this` 的值會改變？
  - `this` 在箭頭函數和傳統函數中有什麼不同？
  - 請給出一個例子展示箭頭函數和傳統函數中 `this` 的差異。
```


1.一個可以取得物件本身屬性或資料的方法

2.使用this時要看是甚麼呼叫了this，用下例舉例
const i ={
  name : Tim ,
  sex : boy
}

function a(){
  console.log(this.name)
}

i.a()  //會得到Tim，i去呼叫了a function，所以this是指向i

如果this沒有被物件呼叫那this會取得window或是undefined，用上面的例子
改成直接呼叫a function沒有透過i ，這時this會指window



3
傳統函數this看調用的對象而動態決定指向哪裡
箭頭函數this依定義它的上文靜態決定指向哪裡


4.
const afunction = () => {
  const name = "Tim";

  const bfunction = () => {
    console.log(`Hello, ${this.name}!`); 
  };

  bfunction();
};

afunction();

//箭頭函數這個粒子，this會指向bfunction上一層的afunction，所以會取到afunction中name的值 Tim 得到  Hello,Tim 的結果

function afunction() {
  const name = "Tim";

  function bfunction() {
    console.log(`Hello, ${this.name}!`); 
  }

  bfunction();
}

afunction(); 

  //這時this不會取到afunction中name的值，因為傳統函數中的this看誰調用了這個函數而不是往上一層指定，這時this會指到window，得到Hello,undefined!
  
  
  
  
  
  
  
    
  ```