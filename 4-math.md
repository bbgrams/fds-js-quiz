### 문제 1

양수를 입력받아 이 수를 반지름으로 하는 원의 넓이를 반환하는 함수를 작성하세요.
넓이 = 파이 * 반지름제곱
넓이 = ㅠ * 반지름^2

```javascript
function circle(input){
  area = (input ** 2) * Math.PI;
  return area;
}

circle(5);  
```

### 문제 2

두 정수 `min`, `max` 를 입력받아, `min` 이상 `max` 미만인 임의의 정수를 반환하는 함수를 작성하세요.

```javascript
function random(min, max){
  randomNum = Math.floor(Math.random() * (max - min)) + min;
  return randomNum;
}

random(1, 7) 
```

### 문제 3

정수를 입력받아, 5 단위로 올림한 수를 반환하는 함수를 작성하세요.

예:
```
ceilBy5(32); -> 35
ceilBy5(37); -> 40
```
```javascript
function ceilBy5(input){
  return Math.ceil(input / 5) * 5
}
ceilBy5(32);
```


### 문제 4

배열을 입력받아, 요소들의 순서를 뒤섞은 새 배열을 반환하는 함수를 작성하세요.
```javascript
function shuffle(arr) {
  for (let i = arr.length - 1; i >= 0; i--) {
    let x = Math.floor(Math.random() * (i + 1));
    let tmp = arr[i];
    arr[i] = arr[x];
    arr[x] = tmp;
  }
  return arr;
}

shuffle([1, 2, 3, 4, 5]);
```

### 문제 5

임의의 HTML 색상 코드를 반환하는 함수를 작성하세요.
```javascript
function randomColor(){
  return "#" + Math.random().toString(16).slice(2, 8);
}
```

### 문제 6

양수를 입력받아, 그 수만큼의 길이를 갖는 임의의 문자열을 반환하는 함수를 작성하세요.

```javascript
// 문자의 유니코드 변환 : a(97)~z(122)

function returnStr(input){
  let str = '';
  for ( let i = 0; i < input; i++){
    let randomNum = Math.floor(Math.random() * 26 + 97 );
    str = str + String.fromCharCode(randomNum);
  }
  return str;
}
returnStr(100)
```

### 문제 7 

수 타입의 값으로만 이루어진 배열을 입력받아, 그 값들의 표준편차를 구하는 함수를 작성하세요.

```javascript
function stdDev(arr){
  // arr의 평균 구하기
  const sum = arr.reduce((acc, item) => acc + item, 0)
  const mean = sum / arr.length
  console.log(`mean:${mean}`)
  // 각 요소에 대한 편차 구하기 ( 편차 = 값 - 평균 )
  const ps = arr.map(item => item - mean)
  console.log(`ps:${ps}`)
  // 각 요소에 대해 제곱하기
  const powers = ps.map(item => item ** 2 )
  console.log(`powers:${powers}`)
  // 위 제곱한 배열의 평균 구하기
  const vv = powers.reduce((acc, item) => acc + item, 0) / powers.length
  console.log(`vv:${vv}`)
  // 루트 씌우기
  return Math.sqrt(vv) // 스퀘어루트 제곱근


}
stdDev([1,2,3,4,5])
```
