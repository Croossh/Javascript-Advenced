# JavaScript Advenced
### π λ°°μ΄ λ΄μ©μ κΈ°λ‘νλ repository μλλ€. π

## πββοΈContents
* [1. Truthyμ Falsy](#1-truthyμ-falsy)
* [2. μΌν­μ°μ°μ](#2-μΌν­μ°μ°μ)
* [3. μ€μ½ν](#3-μ€μ½ν)

## 1. Truthyμ Falsy
### β μ°Έ κ°μ κ°, κ±°μ§ κ°μ κ°
+ JSλ μ‘°κ±΄μμ boolean κ°μ λ£μ§ μμλ μ°Έμ΄λ κ±°μ§μΌλ‘ μΈμνλ μμ±μ΄ μλ€!
```javascript
let a ="";

if(a){
  console.log("true");
  }else{
    console.log("false");
    }
// κ²°κ³Όλ false

let b = "string";

if(b){
  console.log("true");
  }else{
    console.log("false");
    }
// κ²°κ³Όλ ture
```
+ JS μ κΈ°μ€μ μ΄ν΄λ³΄μ
#### >> Truthy
```javascript
let a = []; // true
let a = {}; // true
let a = μ«μ; // true
let a = "λ¬Έμμ΄"; // true
```
#### >> Falsy
```javascript
let a = undefined; // false
let a = null; // false
let a = 0; // false
let a = -0; // false
let a = Nan; // false
let a = ""; // false
```
+ νμ© μμ
```javascript
const getName = (person) => {
  return person.name;
  }
  
let person = {
  name: "Croossh",
  age: 29
  }

const callName = getName(person);

console.log(callName); // Croossh
```
+ μμ κ°μ μν©μμ μλμ κ°μ΄ μμ©ν΄λ³Όμ μλ€
```javascript
const getName = (person) => {
  if(person === undefined){
    return "κ°μ²΄κ° μλλλ€";
    }else{
      return person.name;
    }
}
let person; //λ§μ½ person λ³μμ μλ¬΄κ²λ ν λΉνμ§ μμλ€λ©΄?
const callName = getName(person);
 
console.log(callName); // κ°μ²΄κ° μλλλ€

// BUT!
let person = null // if μ‘°κ±΄λ¬Έμ undefined λ§ κ±ΈμμΌλ nullμ μλ¬κ° λ¨

// μ΄λ κ² μμ±ν΄λ³Όμ μκ² λ€
const getName = (person) => {
  if(person === undefined){
    return "κ°μ²΄κ° μλλλ€";
    }else{
      return person.name;
    }
}
```

## 2. μΌν­μ°μ°μ
### β μ‘°κ±΄λ¬Έμ νκ²©μ μΌλ‘ μ€μΌ μ μλ λ°©λ²!
+ κΈ°λ³Έν: μ‘°κ±΄μ, ?, μ°ΈμΌλ μνν  μ, :, κ±°μ§μΌλ μνν  μ;
```javascript
if(a >= 0){
  console.log("μμ");
  }else{
    console.log("μμ");
    }

// μμ μμ μΌν­μ°μ°μλ₯Ό ν΅ν΄ μ½κ² μμ±ν μ μλ€!
a >=0 ? console.log("μμ") : console.log("μμ");

// ex)
let a = [];

a.length === 0 ? console.log("λΉ λ°°μ΄") : console.log("μμ§λ‘±"); // λΉ λ°°μ΄
```

## 3. μ€μ½ν
### β λ³μμ μ ν¨ λ²μ (λΈλ‘ λ²μ)
+ μ€μ½ν: λ³μ μ κ·Ό κ·μΉμ λ°λ₯Έ μ ν¨ λ²μλ₯Ό λ»νλ€
+ λΈλ‘ μμͺ½/λ°κΉ₯μͺ½ λ³μ μ μΈμ λ°λΌ μμͺ½μ€μ½ν/λ°κΉ₯μ€μ½νλ‘ κ΅¬λΆλλ€.
```javascript
let city = "Seoul";

function hometown() {
  let city = "Busan"
  console.log(city);
}

hometown(); // "Busan"
// hometown ν¨μ μ(μμͺ½μ€μ½ν)μ μλ λ³μλ₯Ό μ΄μ©ν¨
console.log(city); // "Seoul" 
// hometown ν¨μ(μμͺ½μ€μ½ν)κ° μ€νλμ§ μμμΌλ λ°κΉ₯μ€μ½νμ μ μΈλ city λ³μλ₯Ό μ΄μ©ν¨
```

+ λ°κΉ₯ μ€μ½νμμ μ μΈν λ³μλ μμͺ½μ€μ½νμμ μ¬μ©μ΄ κ°λ₯νμ§λ§, λ°λλ λΆκ°λ₯!
```javascript
let greeting = "Hello";

function saySomething() {
  let name = "Chris";
  return greeting + ' ' + name
}

console.log(saySomething()) // 'Hello Chris'
// λ°©ν₯: μμͺ½μ€μ½ν >> λ°κΉ₯μ€μ½ν (OK~!)
console.log(name) // ReferenceError
// λ°©ν₯: λ°κΉ₯μ€μ½ν >> μμͺ½μ€μ½ν (NOPE!)
```


[πΌμ΅μλ¨μΌλ‘ κ°κΈ°πΌ](#javascript-advenced)
