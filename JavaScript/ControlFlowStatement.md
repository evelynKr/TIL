# Control flow statement 제어문

## 1. 제어문이 왜 중요하지?

### 제어문 (Control flow statement)

프로그램, 어플리케이션은 코드 상에서 한줄씩 작성한대로 순자차적으로 코드가 작성된다.
이 실행의 순서를 제어할 수 있는것이 바로 제어문이다.
코드의 흐름을 개발자가 제어할 수 있는 것을 말한다.

제어문에는 조건문(Conditional statement)이라는 것이 있는데,
`if`나 `switch`같은 것들인데 특정한 조건일 때만 우리가 원하는 코드로 실행되도록 만들수 있다.
또는 `for while`이나 `do-while` 같은 반복문(Loop statement)을 이용해서 반복적으로 동일한 코드를 수행할 수도 있다.

<br />

## 2. 조건문

### If 조건문 (Conditional Statement)

- if(조건) { }
- if(조건) { } else {}
- if(조건1) { } else if(조건2) {} else {}

```javascript
let fruit = 'apple';

if (fruit === 'apple') {
  console.log('🍎');
} else if (fruit === 'orange') {
  console.log('🍊');
} else {
  console.log('😍');
}

if (2 < 1) {
  // false = 0, ' ', null. undefined
  console.log('출력되면 안됨!');
}
```

- if안에는 true나 false로 평가될 수 있는 표현식이 들어간다. <br />
  위의 조건이 맞을 시에만 코드 블록이 실행된다고 했을때, 표현식에는 false가 되어야 한다.

<br />

## 03. 삼항 연산자

### 삼항 조건 연산자 (Ternary Operator)

- 조건식 ? 표현식1 : 표현식2
- 조건식 ? 참인경우 : 거짓인경우

<br />

## 04. 제어문 연습퀴즈

<br />

## 05. 스위치(언제 if를 쓰고 언제 switch를 쓰나?)

<br />

## 06. 반복문 for

<br />

## 07. 반복문 while

<br />

## 08. 제어문에서 자주 쓰이는 연산자