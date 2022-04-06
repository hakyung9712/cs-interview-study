## Stack

- 데이터가 입력되면 입력되는 순서대로 쌓고, 나중에 들어온 것부터 먼저 사용하는 자료구조
  - LIFO(Last in First Out)의 구조.
- 활용
  - 프로그램을 수행할때 사용
    - main 프로그램 위에 실행되는 함수가 쌓여서 호출됨
- 시간복잡도 : O(n)
- 공간복잡도 : O(n)

```java
/*
 * @ TITLE Stack (배열로 구현한 스택)
 */
interface Stack{
    boolean isEmpty();
    boolean isFull();
    void push(char item);
    char pop();
    char peek();
    void clear();
}

public class ArrayStack implements Stack {

    private int top;
    private int stackSize;
    private char stackArr[];

    // 스택을 생성하는 생성자
    public ArrayStack(int stackSize) {
        top = -1;    // 스택 포인터 초기화
        this.stackSize = stackSize;    // 스택 사이즈 설정
        stackArr = new char[this.stackSize];    // 스택 배열 생성
    }

    // 스택이 비어있는 상태인지 확인
    public boolean isEmpty() {
        // 스택 포인터가 -1인 경우 데이터가 없는 상태이므로 true 아닌 경우 false를 return
        return (top == -1);
    }

    // 스택이 가득찬 상태인지 확인
    public boolean isFull() {
        // 스택 포인터가 스택의 마지막 인덱스와 동일한 경우 true 아닌 경우 false를 return
        return (top == this.stackSize-1);
    }

    // 스택에 데이터를 추가
    public void push(char item) {
        if(isFull()) {
            System.out.println("Stack is full!");
        } else {
            stackArr[++top] = item;    // 다음 스택 포인터가 가리키는 인덱스에 데이터 추가
            System.out.println("Inserted Item : " + item);
        }
    }

    // 스택의 최상위(마지막) 데이터 추출 후 삭제
    public char pop() {
        if(isEmpty()) {
            System.out.println("Deleting fail! Stack is empty!");
            return 0;
        } else {
            System.out.println("Deleted Item : " + stackArr[top]);
            return stackArr[top--];
        }
    }

    // 스택의 최상위(마지막) 데이터 추출
    public char peek() {
        if(isEmpty()) {
            System.out.println("Peeking fail! Stack is empty!");
            return 0;
        } else {
            System.out.println("Peeked Item : " + stackArr[top]);
            return stackArr[top];
        }
    }

    // 스택 초기화
    public void clear() {
        if(isEmpty()) {
            System.out.println("Stack is already empty!");
        } else {
            top = -1;    // 스택 포인터 초기화
            stackArr = new char[this.stackSize];    // 새로운 스택 배열 생성
            System.out.println("Stack is clear!");
        }
    }

    // 스택에 저장된 모든 데이터를 출력
    public void printStack() {
        if(isEmpty()) {
            System.out.println("Stack is empty!");
        } else {
            System.out.print("Stack elements : ");
            for(int i=0; i<=top; i++) {
                System.out.print(stackArr[i] + " ");
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        int stackSize = 5;
        ArrayStack arrStack = new ArrayStack(stackSize);

        arrStack.push('A');
        arrStack.printStack();

        arrStack.push('B');
        arrStack.printStack();

        arrStack.push('C');
        arrStack.printStack();

        arrStack.pop();
        arrStack.printStack();

        arrStack.pop();
        arrStack.printStack();

        arrStack.peek();
        arrStack.printStack();

        arrStack.clear();
        arrStack.printStack();
    }

}
```

출처: https://freestrokes.tistory.com/82 [FREESTROKES DEVLOG]

## Queue

- 데이터가 입력되면 입력되는 순서대로 쌓고, 먼저 들어온 것부터 먼저 사용하는 자료구조
  - FIFO(First in First out)의 구조
- 활용
  - 운영체제 프로세스 관리
    - 여러 개의 프로세스가 실행될 때, 새로운 프로세스가 수행되어야 하면 : 기존에 실행되던 프로세스 중에서 가장 메모리에 올라온지 오래된 프로세스 아웃 -> 새로운 프로세스를 올린다
- 시간복잡도 : O(n)
- 공간복잡도 : O(n)

```java
public class Queue {
	int front;
	int rear;
	int capacity;
	Object[] queue;
	Queue(int capacity){
		this.front = -1;
		this.rear = -1;
		this.capacity = capacity;
		queue = new Object[this.capacity];
	}

	public boolean isFull() {
		return (this.rear == this.capacity-1);
	}

	public boolean isEmpty() {
		if(front == rear) {
			front = -1;
			rear = -1;
		}
		return (this.front == this.rear);
	}

	public void enqueue(Object element) {
		if(isFull()) {
			System.out.println("Queue is Full!");
			return;
		}

		rear = (rear+1) % this.capacity;
		queue[rear] = element;
	}

	public Object dequeue() {
		if(isEmpty()) {
			System.out.println("Queue is empty");
			return null;
		}

		front = (front+1) % this.capacity;
		return queue[front];
	}

	public Object peek() {
		if(isEmpty()) {
			System.out.println("Queue is empty");
			return null;
		}

		return queue[front+1];
	}

	public int size() {
		return Math.abs( (rear+1) - (front+1) );
	}

	public void clear() {
		if(isEmpty()) {
			System.out.println("Queue is already empty!");
		}
		else {
			front = -1;
			rear = -1;
			queue = new Object[this.capacity];
			System.out.println("Queue has cleared!");
		}
	}
}
```

출처: https://dev-whoan.xyz/24
