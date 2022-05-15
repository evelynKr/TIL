# Operator 연산자

## 1. 연산자란?

- Operator : 무언가 연산(계산)하는 것.
- 무언가 계산을 하고 처리를 할 때 필요하다.
- 프로그래밍에서 많이 쓰이는 다양한 연산자들이 있다.

<br />

## 2. 값으로 평가될 수 있는 것들?

- 리터럴(Literal) : 코드에서 특벙한 값을 나타내는 표기법.
- 템플릿 리터럴(Template Literal) : 템플릿 문자열을 만들 수 있는 표기법.
- 문(Statement) : 코드에서 최소 실행 단위.

### `표현식(Expressions)` : **값으로 평가 될 수 있는 문**.

```javascript
1; // 숫자 리터럴 표현식
1 + 1; // 연산자 표현식
call(); // 함수 호출 표현식

let b; // 선언문
b = 2; // 할당문, 할당 표현식인 문
```

> Point <br /> > `코드가 실행되면 어떤 일이 발생하는가?`<br /> > `코드가 실행되면 어떤 값이 생성되는가?`<br />
> 이 두가지를 유념하면서 코드를 작성하고 다른 사람의 코드를 바라볼 때도 이 부분을 잡고 코드를 읽으면 큰 도움이 된다.<br />
> 그리고 결국 생성된 값이 변수에 할당이 된다면 `이 변수에는 어떤 값이 들어 있는가?`를 포인트로 잡고 코딩하면 좋을 것 같다.

```javascript
let b; // 선언문
b = 2; // 표현식, 할당문

let a1 = let b; // 선언문을 할당하면 에러가 발생
let a2 = (b = 2);

console.log(a2);
```

- 선언문 자체는 값을 생성하지 않기 때문에 변수에 할당할 수 없다.
- 2가 a2에 할당이 된다. 평가되어서 값을 생성할 수 있으므로 b에 2을 할당하는 것은 표현식이기도 하면서 또 하나의 할당문이라고도 부를 수 있다.

<br />

## 3. 산술 연산자

### 산술 연산자 (Arithmatic operators)

- `+` 더하기
- `-` 빼기
- `*` 곱하기
- `/` 나누기
- `%` 나머지
- `**` 지수(거듭제곱)

```javascript
console.log(5 + 2);
console.log(5 - 2);
console.log(5 * 2);
console.log(5 / 2);
console.log(5 % 2);
console.log(5 ** 2); //es7
console.log(Math.pow(5, 2));

// + 연산자 주의점!
let text = '두개의' + '문자들';
console.log(text);
text = '1' + 1; // 숫자 + 문자열 = 문자열
console.log(text);
```

- 플러스 연산자를 쓸 때 주의점: 문자를 연결할 때도 쓰는데, 숫자와 문자열을 실수로 더하는 경우가 생긴다. 그때 문자열로 변환된다. 그래서 코딩을 할 때, 내가 숫자를 더하는건지 문자를 더하는건지 유념해서 써야한다.

<br />

## 4. 단항 연산자

### 단항 연산자(Unary Operators)

- `+` (양) : 음을 양으로 변환할 때 사용.
- `-` (음) : 숫자를 플러스를 마이너스로 변환할 때 사용.
- `!` (부정) : 서로 부정할 때 사용.

```javascript
let a = 5;
a = -a; // -1 *  5
console.log(a);
console.log(-a);

a = -a;
console.log(a);

a = +a;
console.log(a);

a = -a; // -5
a = +a; // +(-5)
console.log(a);

let boolean = true;
console.log(boolean); //true
console.log(!boolean); // false
console.log(!!boolean); // true
```

- `+` : 숫자가 아닌 타입들을 숫자로 변환하면 어떤 값이 나오는지 확인할 수 있음.

```javascript
console.log(+false); // 0
console.log(+null); // 0
console.log(+''); // 0
console.log(+true); // 0
console.log(+'text'); // NaN
console.log(+undefined); // NaN
```

- `!` 부정연산자
- `!!` 값을 boolean 타입으로 변환함.

```javascript
console.log(!1); // false
console.log(!!1); // true
```

<br />

## 5. 할당 연산자

### 할당 연산자 (Assignment oprators)

- 변수에 값을 할당하는 것.
- 하나의 `equal` 사인을 쓰면 할당을 할 수 있다.

```javascript
let a = 1;
a = a + 2;
console.log(a); // 3

a += 2; // a = a + 2; 축약버전
console.log(a); // 5

a -= 2; // a = a - 2; 축약버전
console.log(a); // 3

a *= 2; // a = a * 2; 축약버전
console.log(a); // 6

a /= 2;
a %= 2;
a **= 2;
```

<br />

## 6. 증감 연산자

### 증가 & 감소 연산자(Increment & Decrement Operators)

- 증가 연산자 : 변수 자기 자신에 값을 1 더해서 다시 할당
- 증가 연산자 : 변수 자기 자신에 값을 1 감소해서 다시 할당

```javascript
let a = 0;
console.log(a);

a++; // a = a + 1;
console.log(a);
a--; // a = a - 1;
console.log(a);
```

> 주의 !

- a++ : `필요한 연산`을 하고, 그 뒤에 `값을 증가`시킴.
- ++a : `값을 먼저 증가`하고, `필요한 연산`을 함.

```javascript
console.clear();

a = 0;
let b = a++; // a의 값을 b에 할당(할당연산 먼저)하고, 그 뒤에 a의 값을 증가시킴.
console.log(b); // 0
console.log(a); // 1

console.clear();

a = 0;
let c = ++a; // a의 값을 먼저 증가하고, 그 뒤에 a의 값을 c에 할당 함.
console.log(c); // 1
console.log(a); // 1

console.log(a++); // a의 값을 먼저 출력하고, 그 뒤에 a의 값을 증가
console.log(a);
```

<br />

## 7. 비교 연산자

### 대소 관계 비교 연산자 (Relational oprators)

- `>` 크다
- `<` 작다
- `>=` 크거나 같다
- `<=` 작거나 같다

- 크고 작은 걸 비교해주는 연산자.
- 특정한 값과 값을 비교할 떄 사용.

```javascript
console.log(2 > 3); // false
console.log(2 < 3); // true
console.log(3 > 2); // true
console.log(3 < 2); // false

console.log(3 <= 3); // true
console.log(3 <= 3); // true
console.log(3 >= 3); // true
console.log(3 >= 3); // true
```

<br />

## 8. 연산자 우선순위 (암기 , 제일좋은방법)

### 연산자 우선순위 (Priority)

- 연산자에도 우선순위가 있다.
- 우선 순위를 조정하고 싶을 때는 괄호()를 써준다.

```javascript
let a = 2;
let b = 3;

let result2 = a + b * 4;
console.log(result2); // 14

result = a++ + b * 4;
console.log(result); // 14

let result = (a + b) * 4;
console.log(result); // 20
```

[MDN연산자우선순위](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

<br />

## 9. 동등 비교 연산자

### 동등 비교 관계 연산자 (Equality operators)

- `==` 값이 같음
- `!=` 값이 다름
- `===` 값과 타입이 둘다 같음
- `!==` 값과 타입이 다름

```javascript
console.log(2 == 2); // true
console.log(2 != 2); // false
console.log(2 != 3); // true
console.log(2 == 3); // false

console.log(2 == '2'); // true
// 타입은 비록 다르지만, 숫자와 문자를 비교할 때 문자열 안에 있는 숫자 2가 자동으로 변환이 되면서 비교가 된다. 그래서 true가 나온다.

console.log(2 === '2'); // false
// 가지고 있는 값 자체는 동일할지 몰라도 타입이 다르다. 숫자와 문자이기 때문에 false로 나온다.

console.log(true == 1); // 타입은 다르지만, 1를 boolean으로 변환하면 true이다.
console.log(true === 1); // 타입이 다르다. 불리언과 숫자 타입으로 false이다.
```

- `==` : 값만 비교하고 싶을 때, 연산자 2개만 쓴다.
- `===` : 값과 타입까지 엄격하게 비교하고 싶을 때는 연산자를 3개 쓰면된다.

```javascript
console.clear();

const obj1 = {
  name: 'js',
};
const obj2 = {
  name: 'js',
};

console.log(obj1 == obj2); // false
// 안에 들어 있는 key와 value가 같지만, 엄연히 새로운 오브젝트를 만들었기 때문에 메모리 공간에 서로 다른 개별적인 오브젝트로 할당되어져 있다. 서로 다른 메모리 주소를 가지고 있으므로 false가 나온다.
console.log(obj1 === obj2); // false
// 타입도 값 자체가 다르고 서로 다른 메모리 주소를 가르키고 있기 때문에 false가 나온다.

console.log(obj1.name == obj2.name); // true
// 문자열 js 같고 동일한 값을 가지고 있으므로 true가 나온다.
console.log(obj1.name === obj2.name); // true
// 값도 똑같고 타입도 똑같으므로 true가 나온다.

let obj3 = obj2;
console.log(obj3 == obj2); // true
console.log(obj3 === obj2); // true
// obj3와 obj2는 동일한 메모리 주소를 가지고 있기 때문에 값도 타입도 똑같다.
```
