# useEffect Hook 이란?

### 컴포넌트가 렌더링 될 때 특정 작업(side effect)을 실행할 수 있도록 하는 Hook

```plaintext
1. 컴포넌트가 mount 됐을 때
2. 컴포넌트가 unmount 됐을 때
3. 컴포넌트가 update 됐을 때
```

#### 📢 페이지가 처음 렌더링 되고 난 후 useEffect는 무조건 한 번 실행된다.

#### 📢 useEffect에 배열로 지정한 useState가 변경되면 실행되게 된다.

<br>

#### 즉 useEffect는 렌더링, 변수의 값, 오브젝트가 달라지게 되면 그것을 인지하고 업데이트 해주는 함수이다.

#### useEffect는 콜백 함수를 부르게 되며, 렌더링, 값 오브젝트의 변경에 따라 함수나 여러개의 함수들을 동작시킬 수 있다.

<br>

# useEffect의 사용법

#### 기본형태 : useEffect(function, deps)

- function : 수행하고자 하는 작업
- deps : 배열 형태이며, 배열 안에는 검사하고자 하는 특정 값 또는 빈 배열을 집어넣는다.

```JavaScript
import React, { useEffect } from 'react';

useEffect(() => {
    console.log('마운트 될 때만 실행된다.')
},[]);
```

<br>

# 👍 useEffect() 정리

#### useEffect는 어떤 값의 변화가 감지되면, 실행되어 특정 함수나 작업을 실행하는 함수이다.

#### useEffect는 콜백 함수를 가지며, Dependency는 있을 수도 없을 수도 있다.

#### useEffect는 무조건 렌더링 후 한 번 실행된다.

<br>

#### 1. Depency가 없는 방법

```JavaScript
useEffect(() =>{})
```

#### 2. 대괄호를 이용하는 방법

```JavaScript
useEffect(() => {}, [])
```

#### 3. 대괄호 안에 특정 변수(들)을 지정하는 방법

```JavaScript
useEffect(() => {}, [특정 변수 or 오브젝트])
```

<br>

# 👏 useState() 정리

```JavaScript
const [state, setState] = useState([]);
```

#### 1. state 값 변경은 자동적으로 생성되는 setState() 함수를 사용해야만 가능하다.

#### 2. stste 값을 변경할 때 setState() 함수 내에 들어갈 수 있는 데이터는 useState(데이터)의 데이터와 자료형을 맞춰서 (array, object 등)변경해야 한다.

#### 3. state 데이터를 직접 변경할 수 없어, deep copy : [...] 를 사용해서 데이터 값을 변경한다.

<br>

### ❗copy를 할 때 [...]을 사용하지 않으면 그냥 "값 공유"를 하는 것이다.
