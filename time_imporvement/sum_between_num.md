## 두 수 사이의 합 반복문 사용하지 않고 구하기

> ### 문제 보러가기

### [프로그래머스 링크](https://programmers.co.kr/learn/courses/30/lessons/68644)

<br />

> ### 생각해보기

- 반복문을 식을 통해 함축적으로 표현할 수 없을까?
- 반복문을 수식을 통해 표현할 수 있는지 고려하기.

<br />

> ### 개선전 코드

- 값을 더하는 과정 하나하나를 반복문으로 순차적 실행.

```

function solution(a, b) {
    let answer = 0;
    
    let bigNum = Math.max(a, b);
    let smallNum = Math.min(a, b);
    
    for (let i = smallNum; i <= bigNum; i++) {
        answer += i;
    }
    
    return answer;
}

```

<br />

> ### 개선한 코드

- 수식을 통해 반복문을 사용하지 않음.
- 홀수, 짝수가 헷갈릴 때는 간단한 예시를 직접 계산해보기.
    
    - 전체 갯수가 짝수 일 때, 1, 2, 3, 4
      - (맨 처음 + 맨 끝) * (전체 갯수 / 2) 

    - 전체 갯수가 홀수 일 때, 1, 2, 3, 4, 5
      - (맨 처음 + 맨 끝) * (전체 갯수 / 2)    <= (전체 갯수 / 2) 값이 .5 형태이므로 자동적으로 평균의 중간값(짝이 없는 수)를 더하게 됨.

```
function solution(a, b) {
    let answer = 0;
    
    return (a + b) * ((Math.abs(a - b) + 1) / 2);
}

```
