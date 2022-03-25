## Map

> ### 사용 이유
- 순서가 있는 객체, 프로퍼티를 가지는 배열 형태.
- 프로퍼티의 key를 문자열 외에도 함수, 객체 같은 다양한 타입 모두 사용 가능.
- 따라서, 어떤 타입을 사용한 변수든 key로 사용 가능. (일반 객체는 문자열만 key로 받음.)
- 순서가 있기에 반복문을 실행할 때 편리.
- 조회(get), 추가(set) 메서드가 분리되어 의도치 않은 덮어쓰기 방지.

<br />

> ### 사용법

- Map 생성하기

```
const map = new Map();
```

<br />

- Map 값 추가하기

```
let obj1 = {name: '철수'};

map.set(obj1, 'korean') // 변수 자체를 key로 사용 가능. 만약 일반 객체였다면 'obj1'이라는 문자열을 키로 생성.
```

<br />

- Map 값 조회하기

```
let obj1 = {name: '철수'};

map.set(obj1, 'korean')

map.get(obj1)       // 'korean'
```

<br />

- Map 길이 조회하기

```
map.size();
```

<br />

- Map 키 있나 확인하기

```
map.has('hi')   // boolean 값 반환
```

<br />

- Map 삭제하기

```
map.delete('hi')    // 실제로 값이 삭제 되었는지 여부를 boolean 타입으로 반환
```

<br />

- Map 반복문 사용하기

```
for (let [key, value] of map) {
  ...
}
```
