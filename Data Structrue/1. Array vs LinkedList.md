## Array vs Linked List

| 비교        | array                                                                              | linked list                                                                         |
| ----------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| 검색        | `random access` 지원<br/>index를 통해 직접적으로 접근 가능, O(1)                   | `Sequential Access` 지원<br/>처음부터 node를 순회, O(n)                             |
| 저장        | 논리적 저장순서와 물리적 저장순서가 일치함                                         | 모두 흩어져서 저장됨<br/>`[head, [tail]]`에서 tail에 연결된 node 정보 저장          |
| 삽입, 삭제  | 데이터를 중간에 삽입 or 맨 앞에 삽입하는 경우 : 이후 데이터를 shift 해야함 -> O(n) | 맨 앞 or 맨 뒤에 삽입 -> O(1)<br/>중간에 삽입 : 삽입할 위치를 검색하고 삽입 -> O(n) |
| 메모리 할당 | **Stack**에 할당함<br/>compile time에 할당됨 : Static Memory Allocation            | **Heap**에 할당<br/>runtime에 할당됨 : Dynamic Memory Allocation                    |
| 크기        | 반드시 array 선언 시점에 지정되야 함, 불변                                         | runtime 시점에서 사이즈가 커질 수 있음, 가변                                        |
