- 종류
  - c++ : vector
  - java : ArrayList
- dynamic array
  - 요소의 개수에 따라서 자동으로 크기를 늘였다 줄이는 **배열**
  - 장점
    - 인덱스를 이용해서 접근, 검색하면 속도가 매우 빠름 : O(1)
      - `맨 앞에 위치한 요소의 주소값` + `offset`
  - 단점
    - 새로운 값을 삽입하거나 삭제할 땐 임시적으로 배열을 새로 생성하므로 속도가 느림 : O(n)
- Linked List
  - `[head, [tail]]` 의 구조를 가지고 있는 형태의 자료구조
    - head : 데이터
    - tail : 연결된 다른 linked list
  - 장점
    - 삽입과 삭제를 위해 데이터 복제 없이 단순히 삽입하거나 삭제하고 남은 요소들을 연결하면 되어서 삽입과 삭제가 빠르다 : O(1)
      - 그러나 삽입, 삭제를 하기 위해 그 요소를 찾기 위해 O(n)이 필요해서 맨 앞, 맨 뒤에 삽입하거나 삭제하는 경우만 O(1)임
    - 영구적인 자료형태이다. 따라서 서로 다른 두 linked list가 `tail` 을 공유할 수 있게 하고, 이는 linked list가 **copy-on-write** 자료구를 띄게 한다
      - copy-on-write
        분명 처리되고 있는 프로세스들 중에는 같은 Resource를 공유하는 경우가 종종 있다. 물론 각각이 Resource 영역을 두고 처리하는 것이 가장 이상적이겠지만, Resource 영역이라는 것이 한정되어 있기 때문에 상황에 따라서는 공유가 되어야 한다. 하지만 문제는 공유하는 주체인 프로세스 중 하나가 이 Resource에 대해서 임의의 수정을 요구하는데서 발생한다. 물론 그 주체 프로세스는 자신의 필요에 따라 수정하는 것이기 때문에 동작에 별 영향을 받지 않는다. 하지만 이걸 같이 공유하는 다른 프로세스의 입장에서 보면 수정되기 이전의 Resource가 어쩌면 동작에 있어서 중요한 역할을 차지 할 수도 있는 것이다. 결국 주체 프로세스가 Resource를 수정하고 난 이후에는 상황에 따라서 다른 프로세스의 동작에 영향을 줄 수 있다는 것이다.
        Copy On Write는 이런 상황을 막기 위해 적용되는 방법이다. 평소에는 Resource를 공유하다가도 위의 상황처럼 Resource를 수정할 경우가 발생하면 이전 Resource의 복사본을 쓰게끔 하는 것이다. 그 후에 각각의 프로세서의 포인터를 변경만 시켜주면 이전과 같이 원활하게 동작하도록 보장하는 방안이다.
  - 단점
    - 데이터를 검색하기 위해 노드를 순회해야 한다 : O(n)
    - 배열과 달리 linked list의 데이터는 순서대로 위치하지 않고 여기저기 흩어져 있다
