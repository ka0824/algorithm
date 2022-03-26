## 멱집합 (모든 부분 집합) 구하기

- dfs를 이용해 어떤 항만 포함할 지 체크한 배열을 구함.
- depth(index), checkList(포함 여뷰를 담은 배열), 부분 집합을 담을 배열 3가지 변수가 필요

<br />

```
function getPowerSet (arr) {
  const result = [];         // 완성된 부분 집합들을 담을 배열
  const checkList = new Array(arr.length).fill(false);    // 포함 여부를 확인하는 배열
  
  const dfs = (depth) => {
    if (depth === checkList.length) {              // 모든 항을 탐색 마쳤을 때
      result.push(arr.filter((el, idx) => checkList[idx]));   // 포함된 것만 result 배열에 추가하기
      
    } else {
      checkList[depth] = true;
      dfs(depth + 1);
      
      checkList[depth] = false;
      dfs(depth + 1);
    }
  }
  
  dfs(0);
  return result;
}
```
