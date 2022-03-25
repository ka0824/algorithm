## 시간 복잡도

> ### 의미와 의의
- 입력된 N의 크기(길이)에 따라 실행되는 횟수.
- 데이터 크기(길이)에 따라 어떠한 방식으로 해결해야 실행 시간이 길어지지 않을 지 판단 해야함.
- 실행 시간 즉, 성능을 판단하는 척도.

<br />

> ### 종류
- Big-Ω / 빅 오메가 : 최소로 걸리는 시간
- Big-θ / 빅 세타 : 평균으로 걸리는 시간
- Big-O / 빅 오 : 최대로 걸리는 시간
  - 언제나 예외의 경우를 고려해야 하므로 보통 빅 오를 기준으로 생각.

<br />

> ### 빅 오 표기법


- O(1)   
N의 크기와 관계없이 단 한번만 실행.   
```
function solution(arr) {
  return arr[0];
}
```
<br />

- O(logn)      
특정 과정을 통해 시행될 때 마다 시행 횟수가 줄어듬.  
ex) 이분 정렬   

```
function solution(arr, target) {
  let start = 0;
  let end = arr.length - 1;
  
  while (start <= end) {
    const mid = parseInt(start + end);
    
    if (mid > target) {
      end = mid;
    } else if (mid < target) {
      start = mid;
    } else {
      return mid;
  }
  return start
}

```

<br />

- O(n)      
데이터 N의 크기만큼 실행.     
ex) 반복문      

```
function solution (arr) {
  let cnt = 0;
  
  for (let i = 0; i < arr.length; i++) {
    cnt++;
  }
  
  return cnt;
}
```

<br />

- O(nlogn)          
ex) 반복문과 O(logn)의 결합               

```

function soultion(arr) {
  let cnt = 0;
  
  for (let i = 0; i < arr.length; i++) {
    for (let j = arr.length - 1; j > 0; j = j / 2) {
      cnt++;
    }
  }
  return cnt;
}

```

<br />

- O(n^2)       
ex) 이중 반복문       
```
function solution(arr) {
  let cnt = 0;
  
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      cnt++;
    }
  }
  return cnt;
}

```
