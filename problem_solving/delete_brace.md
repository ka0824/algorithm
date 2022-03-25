## 괄호 제거하기

스택을 이용하여 괄호를 한쌍씩 제거한다.

```

- 주어진 문자열이 올바른 괄호로 이루어진 형태인지 판단하기.
- str은 괄호로만 이루어진 문자열 ex) '(()))('

function solution (str) {
 
  let answer = true;
  const stack = [];
  
  for (let brace of str) {
    if (brace === '(') stack.push(brace);    // 여는 괄호면 stack에 push
    else {
      if (stack.length === 0) return false;   // 만약 닫는 괄호인데 stack 안에 여는 괄호가 없다면 바로 false 리턴
      stack.pop();                            // stack안에 여는 괄호가 있다면 괄호 한쌍 제거.
    }
  }
 
  if (stack.length > 0) return false;        // 반복문이 전부 돌았는데도 stack 안에 여는 괄호가 있다면 false 리턴
  return answer;                             // 여기까지 도달했다면 true 리턴
 
}

```
