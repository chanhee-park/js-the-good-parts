# JavaScript The Good Parts 
더글라스 크락포드의 자바스크립트 핵심 가이드


- - -
# 1. 자바스크립트의 좋은 점들
자바스크립트는 좋은 점과 나쁜 점을 갖고있다. **자바스크립트의 좋은 점을 취하고 나쁜 점을 피하면** 좋은 프로그래머가 될 수 있다.

**자바스크립트의 좋은 점** :
- 함수
- 느슨한 타입 체크
- 동적 객체
- 표현적인 객체 리터럴 등

**자바스크립트의 나쁜 점** :
- 프로그래밍 모델이 전역변수에 기초하고 있음
- 유효 범위 등


- - -
# 2. 자바스크립트의 좋은 문법들
자바스크립트의 좋은 점에 해당하는 문법을 살펴보자.

1. **공백(Whitespace)**

공백은 문자를 구분하는 형태 또는 주석의 형태를 취한다.

자바스크립트에서는 // 로 시작하는 한 줄 주석과 /*  \*/ 형태의 블록주석을 사용할 수 있다. /* 와 \*/ 는 정규 표현식 리터럴에서 등장 할 수 있기 때문에 안전하지 않다. 특별한 이유가 없다면 // 를 사용하는 것을 권장한다. 

```js
// GOOD
// var rma a /a*/.match(5)

/*
  BAD
  var rma a /a*/.match(5)
*/
```


2. **이름(Names)**

자바스크립트에서 이름은 하나의 문자나 그 뒤를 이어서 하나 이상의 문자, 숫자, _ 가 붙은 문자열로 문장, 변수 매개변수, 속성명 연산자, 라벨에 사용한다.

예약어는 이름으로 사용될 수 없다.


3. **숫자(Numbers)**

자바스크립트는 숫자형이 하나만 있다. 64비트 부동 소수점 형식(자바의 double)이다. 

NaN은 수치 연산을 해서 정상적인 값을 얻지 못할 때의 값이다. NaN은 구 자신을 포함해서 어떤 값하고도 같지 않다. 
```js
NaN === NaN; // false
```


4. **문자열(Strings)**

문자열은 작은 따옴표나 큰 따옴표로 묶어서 나타내며, 따옴표 안에는 문자를 0개 이상 포함한다. 

자바스크립트에서 문자열은 몇가지 특성을 갖는다. 
- 문자열은 변하지 않는다(immutable).
- 길이(length) 속성을 갖는다.
- 덧샘 연산이 가능하다. 
- 메소드를 갖는다. (ex. toUpperCase())
```js
'hello, js'.length; // 9

'c' + 'a' + 't' === 'cat'; // true

'cat'.toUpperCase(); // 'CAT'
```


5. **문장(Statements)**

하나의 컴파일 단위에는 실행을 위한 문장들이 포함되어 있다. 문장들은 대게 위에서 아래 순서로 실행된다. 실행순서는 조건문(if, swtich), 반복문(for, while, do), 벗어나는 문장(break, return, throw) 이나 함수 호출로 변경할 수 있다.

블록은 중괄호로 쌓인 문장들의 집합이다. 다른 언어들과 달리 **자바스크립트에서는 블록이 새로운 유효범위(scope)를 생성하지 않는다**. 따라서 변수는 블록 안에서가 아니라 함수의 첫 부분에서 정의해야한다. 
```js
function scopeExam1(){  
    let scope = 'hello.';
    console.log("scope1 : " + scope);
    scope = 'wtf?'
}

function scopeExam2(){  
    console.log("scope2 : " + scope);
}

scopeExam1(); // scope1 : hello.
scopeExam2(); // scope2 : wtf?
```

6. **표현식(Expressions)**

표현식에는 리터럴 값, 변수, 내장값들, new 키워드에 의한 호출 표현식, 이항 연산자의 표현식, ? 삼항연산자의 표현식, 호출 등이 있다. 중요한 내용들은 뒷장에 후술된다.
 

7. **리터럴(Literals)**

객체 리터럴은 새로운 객체를 생성할 때 편리한 표기법이다. 
3장, 4장, 6장, 7장에서 각각 객체, 함수, 배열, 정규표현식의 리터럴을 자세하게 살펴보자.


8. **함수(Functions)**

함수는 이름, 매개변수, 몸체로 이뤄져 있다. 함수의 자세한 내뇽은 4장에서 살펴보자.
