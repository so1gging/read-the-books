# Chapter 03 유니언과 리터럴
`유니언 (Union)`

> 값에 허용된 타입을 두개 이상의 가능한 타입으로 확장하는 것

`내로잉 (Narrowing)`
> 값에 허용된 타입이 하나 이상의 가능한 타입이 되지 않도록 좁히는 것

## 유니언 타입
```typescript
let mathmatician: string | number
```

값이 유니언 타입일 때, 유니언으로 선언한 모든 가능한 타입에 존제하는 멤버 속성에만 접근할 수 있다.
즉, 유니언으로 선언된 타입 둘다 가지고 있는 속성 만 접근이 가능하다.

유니언 타입으로 정의된 여러 타입 중, 하나의 타입으로 된 값의 속성을 사용하려면 내로잉을 해야 한다.

## 내로잉
더 구체적인 타입임을 코드에서 유추하는 것.
내로잉을 하기 위한 논리적 검사를 타입가드 (Type guard) 라 한다.

### 값 할당을 통한 내로잉
```typescript
let admiral: number | string
admiral = 'Grace Hopper' // String 으로 좁혀짐
admiral.toUpperCase() // OK
```
변수에 유니언 타입 애너테이션이 명시되고 초깃값이 주어질 때 값 할당 내로잉이 적용된다.

### 조건검사를 통한 내로잉
```typescript
let scientist = Math.ramdom() > 0.5 ? "Rosalind Frankin" : 51

if (scientist === "Rosalind Frankin") {
  // scientist 은 string
}

// scientist 은 number | string
```

### typeof
```typescript
typeof num === 'number'
```

## 리터럴 타입
* 구체적인 버전의 원시타입
* `특정 원싯값`이다.
* 원시타입 string 은 존재할 수 있는 모든 가능한 문자열의 집합
* 하지만 리터럴 타입은 그 특정 원싯값을 나타낸다.

## 타입별칭
* 타입 별칭은 타입 애너테이션 처럼 자바스크립트로 컴파일 되지 않는다.
* 타입시스템에만 존재하므로 런타임 코드에서는 참조할 수 없다



