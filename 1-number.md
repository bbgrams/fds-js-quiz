### 문제 1

두 수를 입력받아 큰 수를 반환하는 함수를 작성하세요.
```js
function larger(x, y){
  const a = x
  const b = y
  let c;

  // a가 크면 a를 c에 넣고 아니면 b를 c에 넣는다.
  if (a > b){
    c = a
  } else {
    c = b
  }
  return c;  
}
```
```js
function larger(x, y){
  let c;

  // a가 크면 a를 c에 넣고 아니면 b를 c에 넣는다.
  if (x > y){
    c = x
  } else {
    c = y
  }
  return c;  
}
```
```js
function larger(x, y){

  // x가 크면 x를 반환하고 y가 크면 y를 반환한다.
  if (x > y){
    return x
  } else {
    return y
  }
}
```
```js
function larger(x, y){

  // x가 크면 x를 반환하고 y가 크면 y를 반환한다. => if else 연산자 사용
  return x > y ? x : y;
}
```


### 문제 2

세 수를 입력받아 그 곱이 양수이면 `true`, 0 혹은 음수이면 `false`, 둘 다 아니면 에러를 발생시키는 함수를 작성하세요.

에러를 발생시키는 코드는 다음과 같습니다.

```js
throw new Error('입력값이 잘못되었습니다.');
```

```js
function isPositive(x, y, z){
  if (x * y *z > 0){
    return true;
  } else if (x * y * z <= 0 ){
    return false;
  } else {
    throw new Error('입력값이 잘못되었습니다.');
  }
}

console.log(isPositive(1, -3, 9))
console.log(isPositive(1, 1, 9))
console.log(isPositive(1, 0, 9))
console.log(isPositive(1, 'w', 9))
```


### 문제 3

세 수 `min`, `max`, `input`을 입력받아, 다음과 같이 동작하는 함수를 작성하세요.
- `min`보다 `input`이 작으면, `min`을 반환합니다.
- `max`보다 `input`이 크면, `max`를 반환합니다.
- 아니면 `input`을 반환합니다.

예:
```
limit(3, 7, 5); -> 5
limit(3, 7, 11); -> 7
limit(3, 7, 0); -> 3
```

```js
function limit(min, max, input){

  if (min > input){
    return min;
  } else if(max < input){
    return max;
  } else{
    return input;
  }
}

console.log(limit(3, 7, 5));
console.log(limit(3, 7, 11));
console.log(limit(3, 7, 0));
```



### 문제 4

어떤 정수가 짝수인지 홀수인지 출력하는 함수를 작성하세요. 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.
```js
function evenOrOdd(x){
  //만약 x가 짝수면 'x: 짝수' 라고 출력
  if (x % 2 === 0){
    console.log('x : 짝수');
  }else{
    console.log('x : 홀수')
  }
  //아니면 'x : 홀수' 라고 출력
}

evenOrOdd(1)
evenOrOdd(2)
evenOrOdd(10)
evenOrOdd(15)
```

### 문제 5

100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 프로그램을 작성하세요.
- [repl.it](https://repl.it/@bbgrams/1-number-Q5)
```js
// 함수 없이 할 때
for(let i = 0; i < 100; i++){
  const num = i + 1
  if((num % 3 === 0) && (num % 5 === 0)){
    console.log(`${num} : 공배수`)
  }else{
    console.log(`${num} : 아님`)
  }
}

// 함수에 넣어서 사용할 때

```


### 문제 6

자연수를 입력받아, 그 수의 모든 약수를 출력하는 함수를 작성하세요.
```js
1단계 - 제대로 12번만 출력되는지 확인
//반복되는 횟수가 입력되는 값에 따라 달라진다!! >> x의 값!
function print(x){
  for( let i = 0; i < x; i++){
    console.log('ha')
  }
}


print(12)
```
```js
function print(x){
  for( let i = 0; i < x; i++){
    const num = i + 1;
    if ( x % num === 0 ){
      console.log(`${num} : 약수`)
    }
  }
}
/// else를 지우면 : 나누어 떨어지지 않을 시에는 아무것도 하지 않는다
```

### 문제 7 @과제@

2 이상의 자연수를 입력받아, 그 수가 소수인지 아닌지를 판별하는 함수를 작성하세요.
판별하는 함수 : true, false로 나오게 
```js
// 내 풀이
function primeNumber(num){
  // num이 2 미만이거나, 정수가 아닐때 false
  if (num < 2 || !(Number.isInteger(num)) ) throw new Error('2 이상의 정수를 입력해주세요 ')
  // 2부터 받은 숫자까지 나누어서 떨어지면 소수가 아님 출력
  // 나누어 떨어지지 않으면 소수임 출력
  for( let i = 2; i <= num; i++){
    if ( num === i){
      console.log(`${num} : 소수`)
      break;
    } else if ( num % i === 0 ){
      console.log(`${num} : 소수가 아닙니다`)
      break;
    }
  }
}

primeNumber(15)
primeNumber(7)


// 샘 풀이
function isPrime(x){
  // 소수 : 1과 자기자신밖에 약수가 없는 수
  // -> 1과 자기자신이 아닌 약수가 하나ㅏㄹ도 있으면 소수가 아니다.
  for( let i = 2; i < x; i++){
    if( x % i === 0){
      return false
    }
  } 
  return true
}
```


### 문제 8

1부터 100까지의 수를 차례대로 출력하되, 자릿수에 3, 6, 9중 하나라도 포함되어 있으면 '짝!'을 대신 출력하는 프로그램을 작성하세요.
```js
for( let i = 0; i < 100; i++){
  const num = i + 1
  if((num.toString().includes('3')) || (num.toString().includes('6')) || (num.toString().includes('9')) ){
    console.log('짝!')
  }else{
    console.log(num)
  }
}
```
```js
// .toString을 하나로 묶음
for(i=1; i<=100; i++){
  const num = i.toString()
  if(num.includes(‘3’) || num.includes(‘6’) || num.includes(‘9’)){
    console.log(‘짝!’);
  } else {
  console.log(i);
  }
}
```

### 문제 9 

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

```js
// 내 풀이
function star(num){
  //console.log( '*'.repeat(num) ) // num의 갯수만큼 * 출력
  for ( let i = 0; i < num; i++){
    console.log( '* '.repeat(i+1) )
  }
}

star(5);

// 샘 풀이 1.
function print(height){
  for (let i = 0; i < height; i++){
    // 한 줄 출력
    let stars = ''
    for ( let j = 0; j < i + 1 ; j++){
    // 별 표 하나를 출력
      stars += '* '
    }
  console.log(stars)
  }
}
print(5)

// 샘 풀이 2.
function print(height){
  for (let i = 0; i < height; i++){
    // 한 줄 출력
    const stars= '* '.repeat(i+1)
    console.log(stars)
  }
}
print(5)
```

### 문제 10 @과제@

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

```js
// 내 풀이
function starRhombus(star){
  // num - i만큼 별별?
  for ( let i = 1; i <= star; i++){
    let space = star - i
    console.log( ' '.repeat(space) + '* '.repeat(i) )
  }
  for ( let i = (star-1); i > 0; i--){
    let space = star - i
    console.log( ' '.repeat(space) + '* '.repeat(i) )
  }
}


starRhombus(5)

// 샘 풀이 1. (잘못따라썼는지 뭔가 오류가 난다)
function print(height) {
  for (let i = 0; i > height; i++) {
    const n = i + 1;
    const line = ' '.repeat(height - n) + '* '.repeat(n)
    console.log(line)
  }
  for (let i = height; i >= 0; i--) {
    const n = i + 1;
    const line = ' '.repeat(height - n) + '* '.repeat(n)
    console.log(line)
  }
}


// 샘 풀이 1번의 축약형
function printLine(height, i){
  const n = i + 1;
  const line = ' '.repeat(height - n) + '* '.repeat(n)
  console.log(line)
}

function print(height){
  for ( let i = 0; i < height; i++){
    printLine(height, i)
  }
  for ( let i = height - 2; i>= 0; i--){
    printLine(height, i)
  }
}

print(5)
```

### 문제 11

두 수를 입력받아서, 두 수의 최대공약수를 반환하는 함수를 작성하세요. ([유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)을 참고하세요.)

### 문제 12

세 수를 입력받아 큰 것부터 차례대로 출력하는 함수를 작성하세요.

### 문제 13

자연수 `n`을 입력받아, `n`번째 피보나치 수를 반환하는 함수를 작성하세요.
