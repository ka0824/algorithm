## 단순 queue 활용 문제 시간 단축하기

> ### 결론

- 반복문을 실행할 때, 일부 과정을 생략할 수 있는 지 고려해보자.
- queue, stack을 사용할 때, 특정 상황만 고려할 수 있는지 생각.
- count를 어디서 늘려야 할지 생각. (맨 처음에 카운트를 늘릴건지, 전체 과정이 끝나고 나서 카운트를 늘릴건지 고려)

> ### 기존 작성 코드

- queue 배열을 생성하여, 다리를 지나는 과정 자체를 고려함.
- 그결과, 전체 시간의 값만큼 반복문이 실행됨.

```

function solution(bridge_length, weight, truck_weights) {
    let answer = 0;
    const queue = new Array(bridge_length).fill(0);
    let weightSum = 0;
    
    do {
        const currentTruck = truck_weights.shift();
        
        weightSum -= queue.shift();
        answer++;
        
        if (weightSum + currentTruck <= weight) {
            weightSum += currentTruck; 
            queue.push(currentTruck);
        } else {
            queue.push(0);
            truck_weights.unshift(currentTruck);
        }
    } while (weightSum > 0);
    
    return answer;
}

```

> ### 개선한 코드

- queue 배열에 각 트럭이 지나가는 과정만 담음.
- 더이상 다리 위에 트럭이 추가될 수 없을 경우, 시간을 이동시킴.

```

function solution(bridge_length, weight, truck_weights) {
    let answer = 0;
    const queue = [];     // [트럭의 무게, 트럭이 다리를 지나는 시간(현재 시간 + 다리의 길이)]의 형태로 값 추가.
    let weightSum = 0;
    
    do {
        debugger;    
        const currentTruck = truck_weights.shift();
        
        if (queue[0] && queue[0][1] === answer) {
            weightSum -= queue.shift()[0];
        }
        
        if (weightSum + currentTruck <= weight) {
            queue.push([currentTruck, answer + bridge_length]);
            weightSum += currentTruck;
        } else {
            if (queue[0]) {
                truck_weights.unshift(currentTruck);      
                answer = queue[0][1] - 1;                 // 다리 위에 더이상 트럭을 추가할 수 없을 시 가장 앞의 트럭이 다리에서 내려가는 시간으로 이동함.
            } 
        }
        answer++;
        
    } while (weightSum > 0);
    
    return answer;
}

```

> ### 유의 사항
- 좀더 가시성을 좋게 하기 위해 객체로 만들었더니 시간이 오히려 늘어남.
