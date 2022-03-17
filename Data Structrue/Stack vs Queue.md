# Stack vs Queue
Data Structure - 3번째 스터디 : Stack과 Queue

## Stack이란?
![stack](../images/stack.jpg)
* **후입 선출 FILO / LIFO의 자료구조**
* **FILO: First In Last Out - 먼저 들어간 것이 나중에 나옴**
* **LIFO: Last In First Out - 나중에 들어간 것이 먼저 나옴**
* 시간/공간복잡도: O(n) / O(n)
* push(삽입): 스택에 삽입하는 연산
* pop(삭제): 가장 위(top)에 있는 자료를 꺼내며 삭제하는 연산
* peak(읽기): 가장 위(top)에 있는 데이터를 읽기 (삭제X)
* 활용 예시
	* 안드로이드의 액티비티 관리
	* 웹 브라우저의 방문기록 (뒤로가기)
	* 역순 문자열 만들기
	* 실행 취소(undo)
	* 연산자 후위 표기법

## Queue란?
![queue](../images/queue.jpg)
* **선입 선출 FIFO / LILO의 자료구조**
* **FIFO: First In First Out - 먼저 들어간 것이 먼저 나옴**
* **LILO: Last In Last Out - 나중에 들어간 것이 나중에 나옴**
* 시간/공간 복잡도: O(n)/O(n)
* Enqueue: 큐 맨 뒤에 추가
* Dequeue: 큐 맨 앞쪽(Front)의 요소를 삭제
* Peek: 큐 맨앞쪽(Front)의 데이터를 읽음 (삭제X)
* Front: 큐 맨 앞의 위치(인덱스)
* Rear: 큐 맨 뒤의 위치(인덱스)
* 활용 예시
	* 버퍼(buffer)
	* 안드로이드 루퍼의 메시지 큐
	* 우선순위가 같은 작업 예약 (프린터의 인쇄 대기열)
	* 놀이공원 입장 / 티켓팅 서비스
	* 은행 업무
	* 콜센터 고객 대기시간
	* 캐시(cache) 구현
	* BFS (Breadth First Serach) 탐색

## Stack 구현 (Python)

## Queue 구현 (Python)


## 다양한 Queue/Stack의 변형과 활용
#### 순환 큐
* 일반적인 큐는 빈공간을 메꾸기 위해서 원소들을 계속 앞쪽으로 이동시켜줘야 함
* 큐의 **양 끝을 연결시켜서, 원소가 이동할 필요 없이 전체 공간을 사용하도록 한 것 **
#### 우선순위 큐
* 일반적인 큐는 부가적인 조건 없이 먼저 들어온 데이터가 먼저 나가는 구조
* 우선순위 큐는 **들어간 순서에 상관없이 우선순위가 높은 데이터가 먼저 나옴**
* 우선순위 큐는 힙(Heap)이라는 Complete Binary Tree 자료구조를 가지고 구현할 수 있음
#### 스택을 사용한 수식 풀이
* 수식은 연산자(operator)와 피연산자(operand)로 구성
* 연산자의 종류: 산술, 논리, 대입 등
* 피연산자의 종류: 변수 또는 상수
* 연산자의 위치에 따른 수식 표기법
	* 중위 표기법(infix): 연산자가 피연산자 사이에 옴 → 연산자 별로 우선순위가 있으며 괄호를 사용하여 우선순위를 바꿀 수도 있음 → 사람이 이해하기는 쉬우나, 프로그래밍이 어려움
	* **후위 표기법(postfix)**: 연산자가 피연산자 맨 뒤에 옴 → 연산자의 우선순위가 없고 괄호를 사용하지 않음 → 프로그래밍이 쉬움
	* 전위 표기법(prefix): 연산자가 피연산자 앞에 옴

## 참고 문헌
* https://seill.tistory.com/576
* https://monsieursongsong.tistory.com/5
* 유석종, 『자료구조 개념 및 구현』, 휴먼싸이언스(2018)
