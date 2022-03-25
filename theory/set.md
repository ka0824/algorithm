## Set

> ### 사용 이유
- 중복된 값을 가지지 않는 자료 구조
- 기존에는 object의 프로퍼티를 이용해 중복 값을 관리 했다면 Set을 이용하면 더 간편하게 관리가 가능.
- 단, 참조형 타입은 같은 형태더라도 주소 값이 다르기에 원하는 대로 작동하지 않을 수 있음에 유의!

<br />

> ### 사용법

  - Set 생성하기
  
  ```
  const set1 = new Set();
  
  or
  
  const set2 = new Set([1, 2, 3]);
  ```
  
  <br />
  
  - Set 값 추가하기

  ```
  const set = new Set();
  
  set.add(1);
  set.add(1);     <== 이미 1이라는 값이 있으므로 추가되지 않음.
  
  cf)
  const obj1 = {name: 'james'};
  const obj2 = {name: 'james'};
  
  set.add(obj1);
  set.add(obj2);   <= 형태는 같더라도 주소 값이 다르므로 {name: 'james} 형태의 값이 2개 존재.
  ```
  
  <br />
  
  - 특정 값이 있나 조회하기

  ```
  const set = new Set();
  
  set.add(1);
  
  set.has(1);   // true;
  set.has(2);   // false;
  ```
  
  <br />
  
  - 길이 조회하기

  ```
  const set = new Set([1, 2, 3]);
  
  set.size();    // 3
  ```
  
  <br />
  
  - 배열로 변환하기

  ```
  const set = new Set([1, 2, 3]);
  
  const arr = [...set];     
  console.log(arr)       //   [1, 2, 3];
  ```
