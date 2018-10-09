### 문제 1

두 문자열을 입력받아, 대소문자를 구분하지 않고(case insensitive) 두 문자열이 동일한지를 반환하는 함수를 작성하세요.

예:
```
insensitiveEqual('hello', 'hello'); -> true
insensitiveEqual('hello', 'Hello'); -> true
insensitiveEqual('hello', 'world'); -> false
```
```js
function insensitiveEqual(str1, str2){
  if( str1.toLowerCase() === str2.toLowerCase() ){
    return true
  }else{
    return false
  }
}

insensitiveEqual('hello', 'hello')
```
```js
// if 괄호 문의 표현식 줄이기.
function insensitiveEqual(str1, str2){
  return str1.toLowerCase() === str2.toLowerCase()
}

insensitiveEqual('hello', 'hello')
```

### 문제 2

문자열 `s`와 자연수 `n`을 입력받아, 만약 `s`의 길이가 `n`보다 작으면 `s`의 왼쪽에 공백을 추가해서 길이가 `n`이 되게 만든 후 반환하고, 아니면 `s`를 그대로 반환하는 함수를 작성해보세요.

예:
```
leftPad('hello', 8); -> '   hello'
leftPad('hello', 3); -> 'hello'
```
```js
function leftPad(s, n){
// s의 length가 n보다 작으면 padStart(n) 또는 ' 'repeat(3)   + 'hello'
  if (s.length < n){
    const spaceNum = n - s.length // n과 s의 길이의 차이 만큼 공백 추가
    return ' '.repeat(spaceNum) + s
  }else{
    return s
  }
}

leftPad('hello', 12)
```

### 문제 3

문자열을 입력받아, 문자열 안에 들어있는 모든 모음(a, e, i, o, u)의 갯수를 반환하는 함수를 작성하세요.
```js
// 'apple'[0] 하면 'a' 반환

// 한글자씩 보면서 모음인지 아닌지 확인
// 모음이면 0을 기억하고 있던 저장소에 1을 저장.
// (손가락으로 하나씩 접으면서 세는것처럼)
// 1씩 저장 해놓은것들을 반환

// 입력된 str의 길이만큼 반복한다.
// 모음이 없으면 그냥 넘어가므로 else부분은 삭제


function count(str){
  let num = 0 // 저장소
  for ( let i = 0; i < str.length; i++){
    //console.log(str[i])   // 중간중간console.log를 넣어서 제대로 출력되는지 확인한다.
    if ( str[i] === 'a' || str[i] === 'e' || str[i] === 'i' || str[i] === 'o' || str[i] === 'u' ){ // 배열의 한글자가 모음이면
      num += 1  // num에 1을 더해준다
    }
  }
  return num 
}

count('hello')
```

### 문제 4

문자열을 입력받아, 해당 문자열에 포함된 문자의 종류와 갯수를 나타내는 객체를 반환하는 함수를 작성하세요.

예:
```
countChar('tomato'); -> {t: 2, o: 2, m: 1, a: 1}
```
```js
function countChar(input){
  const obj = {} // 내가 봤던것들을 적을 빈 객체
  for ( let i = 0; i < input.length; i++){
    const char = input[i]
    // 글자를 본 적이 없다면 "글자" : 1 을 적어준다.
    if( !(char in obj) ){ //글자를 본적이없다면
      obj[char] = 1
    }else{
      // 글자를 본 적이 있다면 횟수를 1 증가시켜준다.
      obj[char]++
    }
  }
  return obj
}


countChar('tomato')
```

### 문제 5

문자열을 입력받아 그 문자열이 회문(palindrome)인지 판별하는 함수를 작성하세요. (회문이란, '토마토', 'never odd or even'과 같이 뒤에서부터 읽어도 똑같이 읽히는 문자열을 말합니다.)

```js
const isPalindrome = (input) => {
  for ( let i = 0; i < input.length; i++){
    const left= i;
    const right = input.length - 1 - i
    if(input[left] !== input[right]){
      return false
    }
  }
  return true
}

isPalindrome('토마토마토')
```

### 문제 6

문자열을 입력받아, 그 문자열의 모든 '부분 문자열'로 이루어진 배열을 반환하는 함수를 작성하세요.

예:
```
subString('햄버거');
// 결과: ['햄', '햄버', '햄버거', '버', '버거', '거']
```

### 문제 7

문자열을 입력받아, 해당 문자열에서 중복된 문자가 제거된 새로운 문자열을 반환하는 함수를 작성하세요.

예:
```
removeDuplicates('tomato'); -> 'toma'
removeDuplicates('bartender'); -> 'bartend'
```

### 문제 8

이메일 주소를 입력받아, 아이디 부분을 별표(`*`)로 가린 새 문자열을 반환하는 함수를 작성하세요.

- 루프로 먼저 풀어보세요.
- `split` 메소드를 이용해서 풀어보세요.

### 문제 9

문자열을 입력받아, 대문자는 소문자로, 소문자는 대문자로 바꾼 결과를 반환하는 함수를 작성하세요.

### 문제 10

문자열을 입력받아, 각 단어의 첫 글자를 대문자로 바꾼 결과를 반환하는 함수를 작성하세요. (문자열에 개행이 없다고 가정합니다.)

### 문제 11 (과제@) 

문자열을 입력받아, 문자열 안에 들어있는 단어 중 가장 긴 단어를 반환하는 함수를 작성하세요. (문자열에 개행이 없다고 가정합니다.)
```js
function longestWordArr(input){
  const splitted = input.split(' ');
  splitted.sort((x,y) => y.length - x.length )
  return splitted[0]
}
longestWordArr('ediya starbucks hello javascript')
```

### 문제 12 (과제@)

문자열 `s`과 자연수 `n`을 입력받아, `s`의 첫 `n`개의 문자만으로 이루어진 새 문자열을 반환하는 함수를 작성하세요.
```js
function returnNewStr(s, n){
  return s.slice(0, n)
}
returnNewStr('samsung', 5)

// 루프 사용
function firstLetters(s, n){
  if(s.length < n){ // 문자열의 길이가 n보다 짧은 경우 바로 반환.
    return s
  }
  let memory = '';
  for( let i = 0; i < s.length; i++){
    memory += s[i]; 
    if( memory.length === n){ // 내가 지금까지 본 문자열의 길이가 n과 같으면
    return memory
    }
  }
}
firstLetters('hello', 3) // -> 'hel'
```


### 문제 13 (과제@)

Camel case의 문자열을 입력받아, snake case로 바꾼 새 문자열을 반환하는 함수를 작성하세요.
```js
function changeSnakeCase(input){
  let memory = '';
  for(let i = 0; i < input.length; i++){
    const camelCase = input[i]
    //input[i]의 대문자화가 대문자랑 같다면 '_' + input[i].toLowerCase 
    if( camelCase.toUpperCase() === camelCase){
      memory = memory + '_' + camelCase.toLowerCase()
    }else{
      memory += camelCase
    }
  }
  return memory
}
changeSnakeCase('asSoonAsPossible')
```

### 문제 14

Snake case의 문자열을 입력받아, camel case로 바꾼 새 문자열을 반환하는 함수를 작성하세요.
```js
function changeCamelCase(input){
  let memory = '';
  // 하나씩 보다가 _가 나오면, _ 다음문자를 대문자로 변경
  for ( let i = 0; i < input.length; i++){
    if( input[i] === '_'){
      memory += input[i+1].toUpperCase()
      i += 1
    }else{
      memory += input[i]
    }
  }
  return memory
}
changeCamelCase('as_soon_as_possible')
```


### 문제 15 (과제@)

`String.prototype.split`과 똑같이 동작하는 함수를 작성하세요.

예:
```
split('Hello World'); -> ['Hello World']
split('Hello World', ' '); -> ['Hello', 'World']
split('let,const,var', ',') -> ['let', 'const', 'var']
```
```js
function split(str, sec){
  let arr = [];
  let start = 0;
// sec와 같은 문자를 찾아서 분리한다.
  for ( let i = 0; i < str.length; i++){
    // 만약 str[i]= sec 이라면 슬라이스.
    if ( str[i] === sec ){
      arr.push(str.slice(start, i))
      start = i + 1;
    }else if( i === str.length - 1){
      arr.push(str.slice(start, i + 1))
    } else continue
  }
  return arr
}
split('As soon as possible', ' ')
```

### 문제 16

2진수를 표현하는 문자열을 입력받아, 그 문자열이 나타내는 수 타입의 값을 반환하는 함수를 작성하세요. (`parseInt`를 사용하지 말고 작성해보세요.)

예:
```
convertBinary('1101'); -> 13
```

### 문제 17

숫자로만 이루어진 문자열을 입력받아, 연속된 두 짝수 사이에 하이픈(-)을 끼워넣은 문자열을 반환하는 함수를 작성하세요.

예:
```
insertHyphen('437027423'); -> '4370-274-23'
```
