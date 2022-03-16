# Array vs. ArrayList vs. LinkedList

1. 크기
    1. Array: 크기 고정. 선언 시점에 지정함
    2. ArrayList: 크기 가변. add() 또는 remove()로 추가 삭제 가능. 중간에 빈공간을 허용하지 않음.
    3. Linked List: 크기 가변
    
2. 접근
    1. Array: 인덱스로 바로 접근 가능 O(1)
    2. ArrayList: 내부적으로 배열을 사용. 물리공간 == 논리공간. 인덱스 사용하나 get, set으로 값에 접근함.
    3. Linked List: 순차접근을 해야함. 특정 원소를 찾기 위해 처음부터 검색하며 찾기. O(N)
    
3. 삽입과 삭제
    1. Array: 배열의 요소들이 인접해서 저장됨. 인덱스로 접근 후 삽입 삭제 O(1) + 전체 배열 요소 Shift O(N). 자리가 부족하면 메모리 공간 확장이 필요함
    2. ArrayList: Array와 같은 이유로 O(N)
    3. Linked List: 새로운 요소의 위치가 이전 요소에 저장. 위치 접근 후 삽입 삭제 O(N). 삽입 삭제시 주소값만 변경해주면 돼서 유리.
    
4. 메모리 할당
    1. Array: 선언되자마자 compile 시 메모리 할당. Stack
    2. ArrayList: 값 추가할때 메모리 재할당함.
    3. Linked List: 새로운 node가 추가/삭제 될 때 runtime에 메모리 할당. Heap

|  | Array | ArrayList | LinkedList |
| --- | --- | --- | --- |
| 저장공간 크기 | 고정 | 고정 | 가변 |
| 물리주소 == 논리주소? | O | O | X |
| 특정위치 요소 접근/수정 | O(N) | O(N) | O(N) |
| 맨 앞 요소 삽입/삭제 | O(N) | O(N) | O(1) |
| 중간에 요소 삽입/삭제 | O(N) | O(N) | O(N) |
