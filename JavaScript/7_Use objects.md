# Use objects 유용한 객체들

## 1. 빌트인 객체란?

### 내장 객체 (built-in objects)

자바스크립트 런 타임에서 동작할 수 있다.
`런 타임 환경`은 **브라우저**가 될수도 있고, **노드js**가 될수도 있다.
자바스크립트안에는 정말 **유용한 객체들이 존재**한다.
이걸 이용해서 조금 더 쉽게 코딩을 할 수 있다.  
**자바스크립트만으로는 브라우저의 화면을 보여주거나 네트워크 전송을 하거나 컴퓨터에 있는 파일을 읽을 수 없다.**
이런 일들을 하기 위해서는 이제 **런 타임환경에서 제공해주는 호스트 객체를 사용**해야 한다.

### 호스트 객체란?

- `브라우저 런타임 환경`이라면, 브라우저 호스트가 제공해주는 다양한 객체들, 다양한 웹 APIs들을 가리키고 있다.
- `노드 환경`이라면, 노드에서 제공해주는 노드 APIs가 있다.

그리고 코딩을 할 때, 이것뿐만이 아니라 우리 어플리케이션에서 필요한 우리가 정의한 객체들, 우리가 정의한 함수들 이런 사용자 정의 객체들도 있다.
자바스크립트에서 제공해주는 유용한 객체들은 어떤 것들이 있는지, 데이터 타입에 연관된 유용한 것들을 살펴볼것이다.

<br />

## 2. 래퍼 객체

### 래퍼 객체(wrapper object)

- 원시값을 필요에 따라서 관련된 빌트인 객체로 변환한다.
- 필요하지 않는다면 다시 원시값으로 되돌려 준다.
- **자바스크립트에서는 필요에 따라서 원시타입을 한단계 감싸는 레핑하는 레퍼 오브젝트가 있다.**
- 어떤 원시타입이냐에 따라서 그에 맞는 숫자라면 Number, 문자열이라면 String 이라는 걸로 변환이 된다.
- `.`을 찍어서 우리가 필요한 함수를 호출할 수 있다.
- `.`을 찍는(함수를 호출하는) 순간 number 원시타입이 아니라 number 원시타입을 감싸고 있는 Number 객체로 감싸진다.

```js
const number = 123; // number 원시 타입
console.log(number.toString()); // number 원시타입을 감싸고 있는 Number 객체로 감싸짐
console.log(number); // number 원시 타입

const text = 'text'; // string 문자열 원시타입
console.log(text);
text.length; // String 객체
text.trim(); // String 객체
```

#### 그럼 왜 이렇게 유용한 객체를 바로 쓰지 않나요?

- 바로 `객체`는 값뿐만 아니라 함수들, 다양한 정보들을 가지고 있기 때문에 **원시타입보다 훨씬 더 무겁고 메모리를 많이 차지**한다. 그래서 값을 만들때마다 객체를 생성하면 어플리케이션이 뚱뚱해진다.
- 그래서 <u>가능하면 원시타입을 쓰다가 정말 필요할때만 객체로 변환하고 다시 원시타입으로 변환해서 객체는 많이 사용하지 않도록 만들어져 왔다.</u>

<br />

## 3. 글로벌 객체

### 글로벌 객체 (global object)

자바스크립트 전역에서 사용할 수 있는 (어떤 오브젝트를 통하지 않고 바로 호출 할 수 있는) 접근할 수 있는 속성과 함수들이다.

- 전역적으로 `globalThis`라는 걸 쓸 수 있다.
- 노드에서 사용하는 글로벌 객체가 출력된다.
- 그래서 글로벌적으로 `clearInterval`이나 `clearTimeout`이나 `setTimeout`도 사용할 수 있다.

- 브라우저에서도 동일하게 사용할 수 있는데 개발툴에서 열어 `globalThis` or `this`를 출력하면 바로 `Window`가 나온다.
- 브라우저 같은 경우는 윈도우가 전역 객체이다.
- 윈도우 안에 `setTimeout`이라던지 브라우저에서 사용한 `APIs`들이 있다.

- 노드에서 `this`는 약간 다른 개념으로, 현재 모듈에 있는 정보를 출력한다.

```js
console.log(globalThis); // 전역 객체를 가리킨다.
console.log(this); // 전역 객체를 가리킨다. -> 노드에서 this는 모듈을 가리키긴 하지만 대체로 전역을 가르킨다.
console.log(Infinity);
console.log(NaN);
console.log(undefined);
```

### 전역적으로 사용할 수 있는 정말 유용한 함수들

- `eval` : 자바스크립트를 한줄 한줄 표현하는 함수이다. 문자열 형태로 코드를 작성하면 값으로 평가해서 출력한다. 문자열이지만 자바스크립트 코드로 평가해서 출력된다.

```js
eval('const num = 2; console.log(num)'); // 2가 출력됨
```

- `isFinite` : 숫자가 유한한지 아닌지 확인하는 함수이다.

```js
console.log(isFinite(1)); // true
console.log(isFinite(Infinity)); // false
```

- `parseFloat` : 문자열 안에 소수점자리 숫자를 숫자로 변환한다.
- `parseInt` : 문자열 안에 소수점자리 숫자를 정수로 변환해준다.

```js
console.log(parseFloat('12.43')); // 12.43
console.log(parseInt('12.43')); // 12
console.log(parseInt('11')); // 11
```

#### URL (URI 하위 개념)

> `URI (Uniform Resource Identifier)` : 어떤 리소스를 나타낼 수 있는 단 하나의 고유한 주소나 아이디 같은 걸 가리킨다. <br /> `URL` : 웹사이트를 나타낼 수 있는 유일한 주소이다.
> URL은 아스키 문자로만 구성되어야 한다.
> 그래서 주소에 한글이나 특수문자를 쓴다면 이스케이프 처리를 해줘야한다.

- 프론트엔드와 백엔드가 서로 통신을 할때 유용하게 쓰인다.
- `encodeURI` : 한글이나 특수문자가 있는 주소를 이스케이프 처리를 해주는 함수이다. 한글, 특수문자를 정해진 다른 문자로 변환해준다.
- `decodeURI` : 이스케이프 처리된 걸 다시 한글이나 원상태로 되돌릴때 사용하는 함수이다.
- `encodeURIComponent` : 전체 URL이 아니라 **부분적인 URL를 이스케이프 처리**해주는 함수이다.

```js
const URL = 'https://글로벌컴퍼니.com';
const encodeed = encodeURI(URL);
console.log(encodeed);

const decoded = decodeURI(encodeed);
console.log(decoded);

const part = '글로벌컴퍼니.com';
console.log(encodeURIComponent(part));
```

<br />

## 4. 불리언 함수들

### 불리언 함수 (boolean object)

- boolean도 boolean에 해당하는 래퍼 객체가 있다.
- boolean 원시타입도 해당하는 객체 타입이 있지만 객체 안에 유용한 함수는 없다.
- `valueOf` : boolean의 value를 출력할 수 있게 도와준다.

```js
// 레퍼 객체로 new Boolean(true) 만들어준다.
const isTrue = new Boolean(true);

// 객체를 사용하면 메모리를 더 소비할 수 있기때문에 굳이 객체를 사용하지않는다.
const isTrue = true;
console.log(isTrue.valueOf()); // true

/**
 * Falshy : 거짓이 되는 값들
 * 0
 * -0
 * null
 * NaN
 * undefined
 * ''
 */

/**
 * Truthy : 참인 값들
 * 1
 * '0'
 * 'false'
 * []
 * {}
 */
```

<br />

## 4. 숫자 함수들

### 숫자 함수 (number object)

- `Number()` : 생성자를 통해서 오브젝트 인스턴트를 만들 수 있다.

- Static properties (클래스만으로 접근이 가능한 속성들)

  - `Number.EPSILON` : 두 숫자(0과 1) 사이의 나타낼 수 있는 가장 작은 숫자.
  - `Number.MAX_SAFE_INTEGER` : 정수에서 사용할 수 있는 최고의 값. (최대 정수: 2^53 - 1)
  - `Number.MIN_SAFE_INTEGER` : 정수에서 사용할 수 있는 최소의 값. (최소 정수: -(2^53 - 1))
  - `Number.MAX_VALUE` : 가장 큰 양수.
  - `Number.MIN_VALUE` : 가장 작은 양수. (즉, 0보다 크지만 0에 가장 가까운 양수)
  - `Number.NaN` : "Not a Number"(숫자가 아님)을 나타내는 특별한 값.
  - `Number.NEGATIVE_INFINITY` : 음의 무한대를 나타내는 특수한 값.
  - `Number.POSITIVE_INFINITY` : 양의 무한대를 나타내는 특수한 값.
  - `Number.prototype` : Number 객체에 속성을 추가.

- 정적 메소드(클래스에서 접근이 가능한 클래스 함수)

  - `Number.isNaN()` : 주어진 값이 NaN인지 확인.
  - `Number.isFinite()` : 주어진 값이 유한수 인지 확인.
  - `Number.isInteger()` : 주어진 값이 정수인지 확인.
  - `Number.isSafeInteger()` : 주어진 값이 안전한 정수(-(2^53 - 1)과 2^53 - 1 사이의 정수)인지 확인.
  - `Number.parseFloat(string)` : 전역 객체 `parseFloat()`와 동일한 값.
  - `Number.parseInt(string, [radix])` : 전역 객체 `parseInt()`와 동일한 값.

- 인스턴스 메소드 (Number라는 객체를 만들어서 접근 가능한 함수)
  - `Number.prototype.toExponential(fractionDigits)` : 지수 표기법으로 표기된 숫자를 표현하는 문자열을 반환.
  - `Number.prototype.toFixed(digits)` : 고정 소수점 표기법으로 숫자를 표현하는 문자열을 반환.
  - `Number.prototype.toLocaleString([locales [, options]])` : 이 숫자를 해당 언어 방식으로 표현된 문자열을 반환.
  - `Number.prototype.toPrecision(precision)` : 고정 소수점 또는 지수 표기법으로 지정된 정밀도로 숫자를 표현하는 문자열을 반환.
  - `Number.prototype.toString([radix])` : 지정한 기수("base")에서 지정한 개체를 표현하는 문자열을 반환.
  - `Number.prototype.valueOf()` : 명시된 객체의 원시 값을 반환.

```js
const num1 = 123;
const num2 = new Number(123);
console.log(typeof num1); // 원시타입 123, number
console.log(typeof num2); // 객체타입 [Number: 123], object

console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
console.log(Number.MIN_VALUE); // 5e-324
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
console.log(Number.MIN_SAFE_INTEGER); // -9007199254740991
console.log(Number.NaN); // NaN
console.log(Number.NEGATIVE_INFINITY); // -Infinity
console.log(Number.POSITIVE_INFINITY); // Infinity

// 위 예시들은 언제 사용하느냐?
// num1이 숫자인지 아닌지 확인하고 싶다면 비교할때 사용.
if (num1 === Number.NaN) {
}
if (Number.isNaN()) {
}
```

### 지수 표기법

- 매우 크거나 작은 숫자를 표기할때 사용
- 10의 n승으로 표기

```js
const num3 = 102;
console.log(num3.toExponential()); // 1.02e+2
// 102라는 큰 숫자를 toExponential()함수를 사용해 지수로 만든다.
```

### 반올림하여 문자열로 변환

```js
const num4 = 1234.12;
console.log(num4.toFixed()); // 1234
console.log(num4.toString()); // 1234.12
console.log(num4.toLocaleString('ar-EG'));
```

### 원하는 자릿수까지 유효하도록 반올림

```js
console.log(num4.toPrecision(5)); // 1234.1
console.log(num4.toPrecision(4)); // 1234
console.log(num4.toPrecision(2)); // 1.2e+3  -> 전체 자릿수 표기가 안될떄는 지수표기법으로 변환

// 0과 1사이에서 나타낼 수 있는 가장 작은 숫자
if (Number.EPSILON > 0 && Number.EPSILON < 1) {
  console.log(Number.EPSILON); // 2.220446049250313e-16
}

const num = 0.1 + 0.2 - 0.2;
console.log(num); // 0.10000000000000003
```
