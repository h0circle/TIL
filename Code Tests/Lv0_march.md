<div align="center">
<h1>Programmers Lv.0</h1>
</div>
<div align="center">
 <h2>🎲 짝수의 합</h2>
</div>

```plaintext
정수 n이 주어질 때, n 이하의 짝수들을 모두 더한 값을 return하도록 solution 함수를 작성해주세요.
```

## 📌 My Answer

```JavaScript
function solution(n) {
    let result = 0;
    for (let i = 0; i <= n; i++) {
        if (i % 2 === 0)
            result += i;
    }
    return result;
}
```

<br>

### 🐣 풀이

1. for 문을 이용해 n보다 작은 숫자들을 반복해준다.
2. if 문을 사용하여 짝수가 나올 수 있는 조건(i를 2로 나눴을 때 0이 나오는 조건)을 걸어준다.
3. 조건에 맞는 숫자들을 result에 더해나간다.

<br>

### ❗ 다른 분 풀이

```JavaScript
function solution(n) {
    var half = Math.floor(n/2);
    return half*(half+1);
}
```

n이 만약 6이라면 half는 3이 되고 3 \* 4 = 12가 반환된다.

<br>
<div align="center">
<h2>⚖ 배열의 평균값</h2>
</div>

```plaintext
정수 배열 "numbers"가 매개변수로 주어집니다. "numbers"의 원소의 평균값을 return 하도록 solution 함수를 완성해 주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(numbers) {
    let answer = 0;
    for (let i = 0; i < numbers.length; i++) {
        answer += numbers[i];
    }
    return answer / numbers.length;
}
```

<br>

### 🐣 풀이

1. numbers의 길이만큼 for 문을 돌려준다.
2. numbers[i]들을 answer에 하나씩 더해준다.
3. 평균값을 내기 위해 answer를 numbers 배열의 길이만큼 나눠준다.

<br>

### ❗코드를 한줄로 줄여보자

```JavaScript
const solution = (numbers) => (numbers[0] + numbers[numbers.length - 1]) / 2;
```

<br>

<div align="center">
<h2>⚔ 점의 위치 구하기</h2>
</div>

```plaintext
사분면은 한 평면을 x축과 y축을 기준으로 나눈 네 부분입니다. 사분면은 아래와 같이 1부터 4까지 번호를 매깁니다.
1. x좌표와 y좌표가 모두 양수이면 제1사분면에 속합니다.
2. x좌표가 음수, y좌표가 양수이면 제 2사분면에 속합니다.
3. x좌표와 y좌표가 모두 음수이면 제 3사분면에 속합니다.
4. 좌표가 양수, y좌표가 음수이면 제 4사분면에 속합니다.
x좌표(x,y)를 차례대로 담은 정수 배열 dot이 매개변수로 주어집니다. 좌표 dot이 사분면 중 어디에 속하는지 1,2,3,4 중 하나를 return 하도록 solution 함수를 완성해주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(dot) {
    if (dot[0] > 0 && dot[1] > 0) {
        return 1;
    } else if (dot[0] < 0 && dot[1] > 0) {
        return 2;
    } else if (dot[0] < 0 && dot[1] < 0) {
        return 3;
    } else {
        return 4;
    }
}
```

<br>

### 🐣 풀이

1. if문에 조건들을 하나씩 걸어서 조건마다 return을 다르게 작성.

<br>

### ❗ 구조분해 할당을 통해 코드를 더 간단하게 줄일 수 있다.

```JavaScript
    function solution(dot) {
        const [num1, num2] = dot;
        const check = num + num2 > 0;
        return num > 0 ? (check ? 1 : 4) : (check ? 3 : 2);
    }
```

<br>

❗ 조금 더 간결하게

```JavaScript
function solution(dot) {
    return dot[0] > 0 ? dot[1] > 0 ? 1 : 4 : dot[1] > 0 ? 2 : 3;
}
```

<br>

<div align="center">
<h2>📏 배열 원소의 길이</h2>
</div>

```plaintext
문자열 배열 strlist 가 매개변수로 주어집니다. strlist 각 원소의 길이를 담은 배열을 return 하도록 solution 함수를 완성해주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(strlist) {
    let answer = [];
    for (let i = 0; i < strlist.length; i++) {
        answer.push(strlist[i].length);
    }
    return answer;
}
```

<br>

### 🐣 풀이

1. 빈 배열(answer)을 만들어준다.
2. for 문을 돌리고 strlist 배열의 값의 length를 빈 배열에 넣어준다.
3. answer을 return 한다.

<br>

### ❗ map함수를 활용하자. 화살표 함수는 덤.

```JavaScript
const solution = strlist = strlist.map(x => x.length);
```

❗ 난 자꾸 맵 함수를 까먹는다... 맵 함수를 까먹지 말자 !!!!!!!!!!!!

<br>

<div align="center">
<h2>🥟 최댓값 만들기(1)</h2>
</div>

```plaintext
정수 배열 numbers 가 매개변수로 주어집니다. numbers 의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return 하도록 solution 함수를 완성해주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(numbers) {
    const num1 = numbers.sort((a, b) => a - b).pop();
    const num2 = numbers.pop();
    return numb1 * num2;
}
```

<br>

### 🐣 풀이

1. numbers를 sort() 함수와 파라미터를 사용하여 숫자 크기 별로 재정렬 해준 다음, pop()을 사용해 마지막 요소를 반환 => 변수로 선언.
2. 제일 큰 숫자를 pop()을 통해 반환하여 변수에 선언하였으니 다음 크기의 숫자를 pop()을 통해 변수 선언을 해준다.
3. 두 변수끼리 곱해준다.

<br>

### ❗pop()을 사용하지 않았어도 ........

```JavaScript
function solution(numbers) {
    numbers.sort((a, b) => b - a);
    return number[0] * number[1];
}
```
