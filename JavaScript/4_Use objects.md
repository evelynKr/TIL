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
console.log(this); // 전역 객체를 가리킨다. -> 노드에서 this는 모듈을 가리키긴 하지만 대체로 전역을 가르틴다.
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

> URI (Uniform Resource Identifier) : 어떤 리소스를 나타낼 수 있는 단 하나의 고유한 주소나 아이디 같은 걸 가리킨다.
> URL : 웹사이트를 나타낼 수 있는 유일한 주소이다.
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
