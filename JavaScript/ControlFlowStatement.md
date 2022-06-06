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
- 조건식이 true이면 표현식1, false이면 표현식2가 실행된다.

```javascript
// if문
let fruit = 'apple';
if (fruit === 'apple') {
  console.log('🍎');
} else {
  console.log('😍');
}

// 삼항 조건식
// if와 else를 쓸 수 있는 조건이라면 간편하게 ternary operator를 쓸 수 있다.
fruit === 'apple' ? console.log('🍎') : console.log('😍');

// 무언가를 실행하는 경우에도 쓸 수 있지만, 변수에 바로 할당 해줄 수도 있다.
let emoji = fruit === 'apple' ? '🍎' : '😍';
console.log(emoji);
```

<br />

## 04. 제어문 연습퀴즈

### 퀴즈!

- num의 숫자가 짝수이면 👍, 홀수라면 👎을 출력하도록 해라!

- 내가 푼 방식

```javascript
let num = 2;
// if
if ((num %= 3)) {
  console.log('👍');
} else {
  console.log('👎');
}

// ternary
num %= 3 ? console.log('👍') : console.log('👎');
```

- 정답

```javascript
let num = 2;
// if
if (num % 2 === 0) {
  console.log('👍');
} else {
  console.log('👎');
}

// ternary
let emoji = num % 2 === 0 ? '👍' : '👎';
console.log(emoji);
```

<br />

## 05. 스위치

### switch 조건문 (Switch Conditional Statement)

- 정해진 범위 안의 값에 대해 특정한 일을 해야 하는 경우

```javascript
let day = 10; // 0:월요일, 1: 화요일... 6: 일요일

switch (day) {
  case 0:
    dayName = '월요일';
    break;
  case 1:
    dayName = '화요일';
    break;
  case 2:
    dayName = '수요일';
    break;
  case 3:
    dayName = '목요일';
    break;
  case 4:
    dayName = '금요일';
    break;
  case 5:
    dayName = '토요일';
    break;
  case 6:
    dayName = '일요일';
    break;
  default:
    console.log('해당하는 요일이 없음!');
}
console.log(dayName);

let condition = 'bad'; // okay, good  -> 좋음!, bad -> 나쁨!
let text;
switch (condition) {
  case 'okay':
  case 'good':
    text = '좋음!';
    break;
  case 'bad':
    text = '나쁨!';
    break;
}
console.log(text);
```

<br />

## 06. 반복문 for

### for 반복문 (For Loop Statement)

- for(변수선언문; 조건식; 증감식) { }
- 실행순서:
  1. 변수선언문
  2. 조건식의 값이 참이면 { } 코드블럭을 수행
  3. 증감식을 수행
  4. 조건식이 거짓이 될때까지 2번과 3번을 반복함

```javascript
for (let i = 0; i < 5; i++) {
  // 변수선언문: for문을 얼마만큼 반복할 것인지 얼마나 기억하기위한 변수이다.
  // i을 0으로 초기화
  // 반복할 조건을 적어줌
  // 얼마나 증가할건지 적어줌
  console.log(i); // i가 0부터 5보다 커질때까지 출력
}

// 중첩 for문을 작성할 수 있다.
for (let i = 0; i < 5; i++) {
  for (let j = 0; j < 5; j++) {
    console.log(i, j);
  }
}

// 무한루프 💩
// for (;;) {
// }

// 반복문 제어: continue, break;
for (let i = 0; i < 20; i++) {
  if (i === 10) {
    continue;
    console.log('i가 드디어 10이 되었다!');
    break;
  }
  console.log(i);
}
```

<br />

## 07. 반복문 while

<br />

## 08. 제어문에서 자주 쓰이는 연산자
