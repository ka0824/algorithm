## if 중첩문에서 반드시 실행 해야 하는 코드가 있을 경우

> ### 문제 보러 가기
### [프로그래머스 링크](https://programmers.co.kr/learn/courses/30/lessons/42587)

<br />

> ### 결론

- 반드시 실행해야 하는 마지막 코드가 있다면 해당 코드를 고려해서 상단의 코드를 작성해보도록 할 것.
- 다른 코드 간의 유기성을 생각해보도록 할 것.

<br />

> ### 문제 코드


```
function solution(priorities, location) {
    let answer = 0;
    
    while (location >= 0) {
        const currentPrint = priorities.shift();
        
        if (currentPrint < Math.max(...priorities)) {
            priorities.push(currentPrint);
            
            if (location === 0) {
                location = priorities.length - 1;    << location 변수가 index를 의미하므로 1을 무조건 여기서 빼줘야 한다고 생각했음.
            }
        } else {
            answer++;
        }
        
        location--;
    }
    
    return answer;

```

> ### 수정 코드

```
function solution(priorities, location) {
    let answer = 0;
    
    while (location >= 0) {
        const currentPrint = priorities.shift();
        
        if (currentPrint < Math.max(...priorities)) {
            priorities.push(currentPrint);
            
            if (location === 0) {
                location = priorities.length;    << 하단 코드에서 어차피 1을 빼므로 -1 과정을 생략
            }
        } else {
            answer++;
        }
        
        location--;
    }
    
    return answer;
```
