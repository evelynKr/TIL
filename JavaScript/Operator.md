# Operator 연산자

## 1. 연산자란?

- Operator : 무언가 연산(계산)하는 것.
- 무언가 계산을 하고 처리를 할 때 필요하다.
- 프로그래밍에서 많이 쓰이는 다양한 연산자들이 있다.

<br />

## 2. 값으로 평가될 수 있는 것들?

- 리터럴(Literal) : 코드에서 특벙한 값을 나타내는 표기법.
- 템플릿 리터럴(Template Literal) : 템플릿 문자열을 만들 수 있는 표기법
- 문(Statement) : 코드에서 최소 실행 단위

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
- `-` (음) : 숫자를 플러스를 마이너스로 변환 할때 사용.
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

- ! 부정연산자
- !! 값을 boolean 타입으로 변환함.

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

<br />

## 7. 비교 연산자

<br />

## 8. 연산자 우선순위 (암기 , 제일좋은방법)

<br />

## 9. 동등 비교 연산자
