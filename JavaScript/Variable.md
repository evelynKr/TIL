# Variable 변수

## 1. 컴퓨터의 구성요소 (메모리)

### 컴퓨터의 구성요소

컴퓨터에는 Hard Drive, CPU, Memory가 있다.

우리가 문서 파일을 선택할 때,
어떤 것을 선택하고 열고 계산하는 것을 CPU가 처리를 해서 하드디스크에 있는 문서 파일의 데이터를 메모리 상으로 가져오고, 이 파일을 열고 처리할 수 있는 어플리케이션을 우리 화면 모니터에 열게 된다.

그리고 사용자가 수정하는 내용들을 메모리 상의 주기적으로 업데이트 하면서 여러가지 일들의 작업을 처리하고, 작업한 내용을 저장하고 어플리케이션을 종료하면 메모리 상의 데이터를 하드 디스크에 다시 저장하는 일들을 거치게 된다.

### 메모리

메모리에는 어플리케이션을 구동하기 위한 (개발자가 작성한) 코드가 있는 `Code`, 어플리케이션에서 전반적으로 필요한 변수, 데이터들을 보관하는 `Data`, 어플리케이션을 실행하는 함수를 호출하는 순서(실행순서)를 보관하는 `Stack`, 어플리케이션에서 복잡한 여러가지 데이터를 함께 묶어놓은 데이터타입(=객체)들을 특별한 곳에 할당하는 `Heap`이 있다.

<br />

## 2. 변수 선언과 할당

### 변수란?

- variables : 값을 저장하는 공간.
- 자료를 저장할 수 있는 `이름이 주어진 기억장소`.
- 임의로 무언가를 저장할 수 있는 저장 장소이다.
- 이름을 붙일 수 있다.
- 계속 변할 수 있어 값을 재할당 할 수 있다.
- 변수는 메모리 주소를 가리키고 있다.

### 변수 선언과 값의 할당

```javascript
let a = 0; // 변수 선언과 값의 할당
a = 1; // 값의 재할당
```

<br />

## 3. 변수 이름짓기

### Naming Variables

- 저장된 값을 **잘 나타낼 수 있는 `의미 있는` 이름**.
- 구체적일 수록 좋다.

### 변수 규칙

- 라틴문자(0-9, a-z, A-Z), \_
- 대소문자 구별
- camelCase 추천
- 한국어, 예약어, 특수문자외( \_ , $ 두가지 예외), 이모지 ❌
- 여러개의 변수명을 1,2,3 숫자로 구분 ❌
- 최대한 의미있게, 구체적인 이름으로 작성 !

```Javascript
let apple;
let redApple;

let number = 20; // 나쁜 예제
let myAge = 20;  // 좋은 예제

// 나쁜 예제
let audio1;
let audio2;

// 좋은 예제
let backgroundAudio;
let windAudio;
```

<br />

> 꿀팁 ! 🍯<br />
> 중복되는 전체분류를 먼저 적고 구체적인 걸 뒤로 빼서 적으면 <br />
> 나중에 코드 작성 시, 찾고싶은 분류를 치면 관련된 것들이 한번에 나온다.

```javascript
let audioBackground;
let audioWind;
```

<br />

## 4. 데이터 타입

데이터 타입에는 원시 타입(단일 데이터)과 객체 타입(복합 데이터)이 있다.

### 원시 타입(Primitive)

### 1. number 타입

- 자바스크립트의 숫자 데이터 타입은 변수에 숫자를 아무거나 할당 할 수 있다.

- 유의 할 점 ! <br />
  특정한 숫자를 0으로 나눌 때 인피니트가 나올 수 있다. 인피니트가 화면에 나오면 안 좋기때문에 이런 것들을 적절히 처리 해줘야 한다.

- infinity 란? <br />
  점점 작은 숫자를 나눌 수록 숫자가 기하급수적으로 늘어나니까 무한정으로 늘어날 수 있다.

- bigInt 란? <br />
  원시 값이 안정적으로 나타낼 수 있는 최대치인 2^53 - 1보다 큰 정수를 표현할 수 있는 내장 객체이다. 숫자 뒤에 `n`을 붙여 다루고 처리할 수 있다.

```javascript
let integer = 123; // 정수
let negative = -123; // 음수
let double = 1.23; // 실수

let binary = 0b1111011; // 2진수
let octal = 0o173; // 8진수
let hex = 0x7b; // 16진수

console.log(0 / 123); // 0
console.log(123 / 0); // Infinity
console.log(123 / -0); // -Infinity
console.log(123 / 'text'); // NaN

// 정말 큰 숫자를 가지고 나누거나 곱하거나 연산을 하거나 그럴 일이 아니라면, 이 타입을 쓸 일은 없다.
let bigInt = 9007199254740991n;
```

<br />

### 2. string 타입

- 문자열 타입이다.
- 문자를 "" 이나 ''으로 감싸 준다.
- 템플릿 리터럴(Template Literal) ``

```javascript
let string = '안녕하세요';
string = `안녕!`;

//특수 문자 출력하는 법
string = "'안녕!'";
string = '안녕!\n엘리야!\t\t내 이름은\\\u09AC';

let id = '엘리';
let greetings = "'안녕!, " + id + "🖐\n즐거운 하루 보내요!'";

//템플릿 리터럴 (Template Literal) ``
greetings = `'안녕!, ${id} 👋
즐거운 하로 보내요!'`;
```

<br />

### 3. boolean 타입

- 참, 거짓 타입이다.

```javascript
let 참 = true;
let 거짓 = false;

// 활용 예 :
let isFree = true;
let isActivated = false;
let isEnrolled = true;
console.log(isActivated);

// Falshy 거짓인 값
console.log(!!0);
console.log(!!-0);
console.log(!!'');
console.log(!!null);
console.log(!!undefined);
console.log(!!NaN);

// Truthy 참인 값
console.log(!!1);
console.log(!!-1);
console.log(!!'text');
console.log(!!{});
console.log(!!Infinity);
```

<br />

### 4. null과 undefined 타입

- null <br /> 값이 없다. 비어 있다.
- undefined <br /> 미정. 값이 정해진 게 없다.
- | 타입      | 값 <br /> |
  | --------- | --------- |
  | value     | 👩🏻 <br /> |
  | null      | 👨🏻‍🦲<br />  |
  | undefined |

```javascript
//null, undefined
let variable;
variable = null;

let activeItem; //아직 활성화된 아이템이 있는지 없는지 모르는 상태 !
activeItem = null; //활성화된 아이템이 없는 상태 !

console.log(typeof null); // -> object: 값이 null
console.log(typeof undefined); // -> undefined: 값이 X
```

<br />

### 객체 타입(Object)

- {key : value}
- 객체 object (=복합데이터) <br />
  : 연관된 상태와 행동의 여러타입의 데이터를 묶어 놓은 것을 객체라고 한다.
- 객체 타입 경우, 오브젝트가 키와 밸류 형태로 여러 개가 묶일 수 있기 때문에 사이즈가 정해져 있지 않다. 즉, 메모리 셀 안에 한번에 들어갈 수 없기 때문에, "Heap" 이라는 스페셜한 메모리 공간에 메모리가 할당 되어진다.
- Heap 안에는 데이터 사이즈가 정해져 있지 않는 동적으로 사이즈가 줄었다 늘었다 할 수 있는 것등이 보관되어지는 장소이다.
- 객체는 뚱뚱해서 하나의 메모리 안에 다 들어가지 못한다.

```javascript
let name = 'apple';
let color = 'red';
let display = '🍎';

let apple = {
  name: 'apple',
  color: 'red',
  display: '🍎',
};

console.log(apple);
console.log(apple.name);
console.log(apple.color);
console.log(apple.display);

let orange = {
  name: 'orange',
  color: 'orange',
  display: '🍊',
};

console.log(orange);
```

<br />

## 5. 값과 참조의 차이 (정말 중요 🌟)

### 메모리 상에서 다른점 (= 어떻게 복사되어 전달되는지 다름)

- 원시 타입은 메모리 셀안에 값이 바로 들어가 있다. 변수가 그 메모리 자체를 가리키고 있다.
- 객체 타입은 실제로 객체가 들어있는 메모리 주소를 보관하고 있다.
- 원시는 값 자체가 메모리 셀안에 들어가 있는 반면에 객체는 참조값(메모리 주소)가 변수에 들어있다.

### `Copy by Value`

- 원시 타입은 `값` 자체가 복사되어서 할당되어진다.

### `Copy by Reference`

- 객체는 메모리 셀 안에 `메모리 주소 레퍼런스`가 들어있기 때문에 이 레퍼런스 자체가 복사되어 재할당된다.
- 동일한 오브젝트를 가리키고 있기 때문에 한 곳에서만 수정을 해도 둘다 업데이트된다.

> 주의할 점 !

- 다른 변수에 재할당 하는 경우나 함수에서 매개변수로 전달할 때 등 메모나 주소만 복사해서 전달하게 되면, **한 곳에서 수정하면 오브젝트 자체의 값도 변경이 되니까 이것을 유념해서 코딩해야한다.**

```javascript
// 원시타입은 값이 복사되어 전달됨
let a = 1;
let b = a; // 1
b = 2;
console.log(a);
console.log(b);

// 객체타입은 참조값(메모리주소, 레퍼런스)가 복사되어 전달됨
let apple = { // 0x1234
  name: '사과';
};
let orange = apple; // 0x1234
orange.name = '오렌지';
console.log(apple);
console.log(orange);
```

<br />

## 6. 상수 변수

- const 키워드는 `한번 할당하고 그 뒤로도 재할당이 불필요한 경우`에는 let보다 `const를 사용`하는게 좋다.
- 프로그래밍을 할때 웬만하면 const를 더선호해서 작성하는게 좋다.
- const는 `변수가 가리킨 메모리 셀에 재할당이 불가능`하다. const 변수에 다른 메모리 주소를 담을 수 없다.
- `가리키고 있는 오브젝트의 변경은 가능`하다.

| 변수  | 재할당(Reassignable) | 변경(Mutable) |
| ----- | :------------------: | :-----------: |
| let   |         Yes          |      Yes      |
| const |          No          |      Yes      |

```javascript
// let 재할당이 가능
let a = 1;
a = 2;

// const 재할딩이 불가능
// 1. 상수
// 2. 상수변수 또는 변수
const text = 'hello';
// text = 'hi';  이렇게 하면 안됨!

// 1. 상수
const MAX_FRUITS = 5; // 상수를 사용할 땐 항상 대문자로 ! 단어와단어 사이에는 언더스코어로 분리.

// 2. 재할당 불가능한 상수변수 또는 상수
const apple = {
  name: 'apple',
  color: 'red',
  display: '🍎',
};

// apple = {};
console.log(apple);
apple.name = 'orange';
apple.display = '🍏';
console.log(apple);
```

<br />

## 7. 타입 확인 법

### (1) 컴파일러(Compiler)

```
(JAVA)
 코드  ---->  컴파일러  ---->  실행파일  ---->
          ↓
       정적타입(Static Type)
       : 실행 하기 전 모든 코드를 컴파일링 함!
```

- 보통 컴파일 언어에서는 타입을 명시해주고 변수 이름을 명시한 다음 값을 할당해준다.
- 타입 재할당이 불가능하다.
- 자바같은 경우, strongly type 이다.

```
(JAVASCRIPT)
 자바스크립트 엔진 ---->
    ↓
  동적타입(Dynamic Type)
  : 인터프리터, 런 타임시 코드를 한줄식 번역해서 실행
```

- 자바스크립트는 동적으로 실행할때 할당된 값에 따라서 타입이 변경된다.
- 자바스크립트 경우, `weakly type` 이다.

### (2) Typeof

- 데이터 타입을 확인할 수 있는 연산자 타입이다.

### (3) 자바스크립트 타입 특징

- 1. `동적`이라는 것
- 2. 하나의 변수가 `어떤 값을 할당하느냐에 따라서 타입이 변경`된다.
- 타입이 있다. **다만 동적으로 결정이 되고, 할당된 값에 따라서 타입이 결정된다.**

```javascript
// typeof : 데이터 타입을 확인
// 값을 타입 문자열로 반환
let variable;
console.log(typeof variable);

variable = '';
console.log(typeof variable);

variable = 123; //  ← 할당된 값에 따라 타입이 결정됨!
console.log(typeof variable);

variable = {};
console.log(typeof variable);

variable = function () {};
console.log(typeof variable);

variable = Symbol();
console.log(typeof variable);

console.log(typeof 123);
console.log(typeof '123');
```
