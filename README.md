# JavaScript Advenced
### 😍 배운 내용을 기록하는 repository 입니다. 😍

## 🙋‍♂️Contents
* [1. Truthy와 Falsy](#1-truthy와-falsy)
* [2. 삼항연산자](#2-삼항연산자)
* [3. 스코프](#3-스코프)

## 1. Truthy와 Falsy
### ✔ 참 같은 값, 거짓 같은 값
+ JS는 조건식에 boolean 값을 넣지 않아도 참이나 거짓으로 인식하는 속성이 있다!
```javascript
let a ="";

if(a){
  console.log("true");
  }else{
    console.log("false");
    }
// 결과는 false

let b = "string";

if(b){
  console.log("true");
  }else{
    console.log("false");
    }
// 결과는 ture
```
+ JS 의 기준을 살펴보자
#### >> Truthy
```javascript
let a = []; // true
let a = {}; // true
let a = 숫자; // true
let a = "문자열"; // true
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
+ 활용 예시
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
+ 위와 같은 상황에서 아래와 같이 응용해볼수 있다
```javascript
const getName = (person) => {
  if(person === undefined){
    return "객체가 아닙니다";
    }else{
      return person.name;
    }
}
let person; //만약 person 변수에 아무것도 할당하지 않았다면?
const callName = getName(person);
 
console.log(callName); // 객체가 아닙니다

// BUT!
let person = null // if 조건문에 undefined 만 걸었으니 null은 에러가 남

// 이렇게 작성해볼수 있겠다
const getName = (person) => {
  if(person === undefined){
    return "객체가 아닙니다";
    }else{
      return person.name;
    }
}
```

## 2. 삼항연산자
### ✔ 조건문을 파격적으로 줄일 수 있는 방법!
+ 기본틀: 조건식, ?, 참일때 수행할 식, :, 거짓일때 수행할 식;
```javascript
if(a >= 0){
  console.log("양수");
  }else{
    console.log("음수");
    }

// 위의 식을 삼항연산자를 통해 쉽게 작성할수 있다!
a >=0 ? console.log("양수") : console.log("음수");

// ex)
let a = [];

a.length === 0 ? console.log("빈 배열") : console.log("있지롱"); // 빈 배열
```

## 3. 스코프
### ✔ 변수의 유효 범위 (블록 범위)
+ 스코프: 변수 접근 규칙에 따른 유효 범위를 뜻한다
+ 블록 안쪽/바깥쪽 변수 선언에 따라 안쪽스코프/바깥스코프로 구분된다.
```javascript
let city = "Seoul";

function hometown() {
  let city = "Busan"
  console.log(city);
}

hometown(); // "Busan"
// hometown 함수 안(안쪽스코프)에 있는 변수를 이용함
console.log(city); // "Seoul" 
// hometown 함수(안쪽스코프)가 실행되지 않았으니 바깥스코프에 선언된 city 변수를 이용함
```

+ 바깥 스코프에서 선언한 변수는 안쪽스코프에서 사용이 가능하지만, 반대는 불가능!
```javascript
let greeting = "Hello";

function saySomething() {
  let name = "Chris";
  return greeting + ' ' + name
}

console.log(saySomething()) // 'Hello Chris'
// 방향: 안쪽스코프 >> 바깥스코프 (OK~!)
console.log(name) // ReferenceError
// 방향: 바깥스코프 >> 안쪽스코프 (NOPE!)
```


[🔼최상단으로 가기🔼](#javascript-advenced)
