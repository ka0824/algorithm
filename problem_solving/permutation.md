## 배열 arr에서 중복 허용하지 않고 n번 뽑는 경우의 수 구하기

```

function solution(arr, n){
                let answer = [];

                let check = Array.from({length: arr.length}, () => false);    // 해당 인덱스를 뽑았나, 안 뽑았나 확인 용도의 배열
                let tmp = Array.from({length: n}, () => 0);                   // 하나 하나의 경우의 수를 담을 배열

                function dfs (number) {                        // 뽑은 횟수 -1 ex) dfs(0)은 첫번째로 뽑을 때를 의미함
                    if (number === n ) {
                        array.push(tmp.slice());               // 한 번 뽑은 순서를 담은 배열
                    } else {
                        for (let i = 0; i < arr.length; i++) {
                            if (check[i] === false) {          // 해당 인덱스를 안 뽑았을 경우에만 진행
                                check[i] = true;
                                tmp[m] = arr[i];               // 각 횟수에서 뽑은 값 tmp에 저장
                                dfs(m + 1);                    // 다음 횟수 뽑기 진행
                                check[i] = false;              // 탐색 완료한 인덱스 다시 false 상태로 초기화
                            }
                        }
                    }
                }

                dfs(0);

                return answer;
            }


```
