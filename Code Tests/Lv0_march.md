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

<br>

<div align="center">
<h2>💫 배열 뒤집기</h2>
</div>

<div align="center">
📆 2023.03.24
</div>
<br>

```plaintext
정수가 들어 있는 배열 num_list가 매개변수로 주어집니다. num_list의 원소의 순서를 거꾸로 뒤집은 배열을 return하도록 solution 함수를 완성해주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(num_list) {
    return num_list.reverse();
}
```

<br>

### 🐣 풀이

1. reverse() 함수를 사용해 배열을 뒤집는다.
2. 뒤집은 배열을 반환한다.

<br>

### ❗ reverse() 함수를 사용하지 않고 해보기

```JavaScript
function solution(num_list) {
let answer = [];
let a = num_list.length;
for (let i = 1; i <= a; i++) {
    answer.push(num_list[a - i])
    }
    return answer;
}
```

<br>

<div align="center">
<h2>🔺 삼각형의 완성조건 (1)</h2>
</div>

```plaintext
선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.
* 가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.
삼각형의 세 변의 길이가 담긴 배열 sides이 매개변수로 주어집니다. 세 번으로 삼각형을 만들 수 있다면 1, 만들 수 없다면 2를 return 하도록 solution 함수를 완성해주세요.
```

<br>

## 📌 My Answer

```JavaScript
function solution(sides) {
    const array = sides.sort((a, b) => a - b);
    if (array[0] + array[1] <= array[2]>) {
        return 2;
    } else {
        return 1;
    }
}
```

<br>

### 🐣 풀이

1. sort 함수와 파라미터를 통해 배열을 오름차순으로 정렬 해준다.
2. if 문을 작성하여 0번째 값과 1번째 값을 더했을 떄 2번째 값보다 크거나 작을 경우의 조건을 걸어준다.
3. if 문에 작성한 조건에 맞을 때 2를 return 하게 하고 조건에 일치하지 않을 때 1을 return 한다.

<br>

### ❗if 문을 사용하지 않고 삼항조건연산자를 사용하는 법

```JavaScript
function solution(sides) {
    sides = sides.sort((a, b) => a - b);
    return sides[0] + sides[1] > sides[2] ? 1 : 2
}
```

<br>

<div align="center">
<h2>🍕 피자 나눠 먹기 (3)</h2>
</div>

```plaintext
머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다. 피자 조각 수 slice와 피자를 먹는 사람의 수 n이 매개변수로 주어질 때, n명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return하도록 solution 함수를 완성해보세요.
```

<br>

입출력 예

| slice |  n  | result |
| :---: | :-: | :----: |
|   7   | 10  |   2    |
|   4   | 12  |   3    |

<br>

## 📌 My Answer

```JavaScript
function solution(slice, n) {
    const answer = (n % slice == 0) ? n / slice : n / slice + 1;
    return Math.floor(answer);
}
```

<br>

### 🐣 풀이

1. 삼항조건연산문을 사용해 사람수 % 나눈조각이 0과 같을 때는 사람수 / 조각, 아닐 땐 사람수 / 조각에 + 1
2. Math.floor()함수를 사용해 소숫점을 버려준 값을 리턴한다.

<br>

### ❗ Math.ceil() 함수를 사용

```JavaScript
function solution(slice, n) {
    return Math.ceil(n / slice);
}
```

❗ Math.ceil() 함수란?
<br>

- 소수점 이하를 올림해주는 함수

  <br>

<div align="center">
<h2>🙃 중앙값 구하기</h2>
</div>

```plaintext
중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미한다. 예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다. 정수 배열 array가 매개변수로 주어질 때, 중앙값을 return하도록 solution 함수를 완성해보세요.
```

<br>

입출력 예

| array             | result |
| :---------------- | :----: |
| [1, 2, 7, 10, 11] |   7    |
| [9, -1, 0]        |   0    |

<br>

## 📌 My Answer

```JavaScript
function solution(array) {
    array.sort((a, b) => a - b);
    const answer = parseInt(array.length / 2);
    return array[answer];
}
```

<br>

### 🐣 풀이

1. 크기를 순서대로 정렬하기 위해 sort 함수를 사용한다.
2. array 길이의 값을 2(반)으로 나눠주고 parseInt를 사용해 정수로 바꾼 값을 변수에 선언한다.
3. array[변수로 선언한 값]을 return 해준다.

<br>

### ❗ 짧게 줄여보자.

```JavaScript
function solution(array) {
    return array.sort((a, b) => a - b)[Math.floor(array.length / 2)];
}
```
