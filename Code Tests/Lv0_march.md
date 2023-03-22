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

## ❗ 다른 분 풀이

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

## ❗코드를 한줄로 줄여보자

```JavaScript
const solution = (numbers) => (numbers[0] + numbers[numbers.length - 1]) / 2;
```
