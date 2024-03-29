# 자료구조   

<details>
<summary>❓ Array(List)의 가장 큰 특징과 그로 인해 발생하는 장점과 단점에 대해 설명해주세요.</summary>
<div markdown="1">

Array의 가장 큰 특징은 순차적으로 데이터를 저장한다는 점입니다.

데이터에 순서가 있기 때문에 0부터 시작하는 index가 존재하며, index를 사용해 특정 요소를 찾고 조작이 가능하다는 것이 Array의 장점입니다.

순차적으로 존재하는 데이터의 중간에 요소가 삽입되거나 삭제되는 경우 그 뒤의 모든 요소들을 한 칸씩 뒤로 밀거나 당겨줘야 하는 단점도 있습니다.

이러한 이유로 Array는 정보가 자주 삭제되거나 추가되는 데이터를 담기에는 적절치 않습니다.

</div>
</details>

<details>
<summary>❓ Array를 적용시키면 좋을 데이터의 예를 구체적으로 들어주세요. 구체적 예시와 함께 Array를 적용하면 좋은 이유, 그리고 Array를 사용하지 않으면 어떻게 되는지 함께 설명해주세요.</summary>
<div markdown="1">

Ex) 주식 차트가 있다.

주식 차트에 대한 데이터는 요소가 중간에 새롭게 추가되거나 삭제되는 정보가 아니며, 날짜 별로 주식 가격이 차례대로 저장되어야 하는 데이터입니다. 

즉, 순서가 굉장히 중요한 데이터이므로 Array 같이 순서를 보장해주는 자료구조를 사용하는 것이 좋습니다. 

Array를 사용하지 않고 순서가 없는 자료 구조를 사용하는 경우에는 날짜 별 주식 가격을 확인하기 어려우며 매번 전체 자료를 읽어 들이고 비교해야 하는 번거로움이 발생합니다.

</div>
</details>

<details>
<summary>❓ Stack과 Queue, Tree와 Heap의 구조에 대해 설명해주세요.</summary>
<div markdown="1">

Stack과 Queue는 선형 자료구조의 일종이며, Array와 LinkedList로 구현할 수 있습니다.

Stack은 후입선출(LIFO)방식 즉, 나중에 들어간 원소가 먼저 나오는 구조이고

Queue는 선입선출(FIFO)방식 즉, 먼저 들어간 원소가 먼저 나오는 구조를 갖습니다.

Tree는 스택과 큐와 같은 선형 구조가 아닌 비선형 자료구조이며, 계층적 관계를 표현하기에 적합합니다. 

Heap은 최댓값 또는 최솟값을 찾아내는 연산을 쉽게 하기 위해 고안된 구조로,

각 노드의 키 값이 자식의 키값보다 작지 않거나(최대힙) 그 자식의 키값보다 크지 않은 (최소힙) 완전이진트리 입니다.

</div>
</details>

<details>
<summary>❓ Stack과 Queue의 실사용 예를 들어 간단히 설명해주세요.</summary>
<div markdown="1">

**Stack** - **자바의 Stack 메모리 영역**

지역변수와 매개변수 데이터 값이 저장되는 공간이며, 메소드 호출 시 메모리에 할당되고 종료되면 메모리가 해제되며, LIFO(Last In First Out) 구조를 가집니다. 

**Queue - OS의 스케쥴러**

자원의 할당과 회수를 하는 스케쥴러 역할을 큐가 할 수 있습니다.

메모리에 적재된 다수의 프로세스 중 어떤 프로세스에게 자원을 할당할 것인가 그 순서를 결정하는 것이 자원의 효율적인 사용에 있고,

가장 단순한 형태의 스케쥴링 정책이 선입선처리(First Come First Served) 즉, 큐라고 볼 수 있습니다.

</div>
</details>

<details>
<summary>❓ Stack 클래스를 손코딩으로 구현해주세요.</summary>
<div markdown="1">

```java
public class Stack {
	private static int MAX_STACK_SIZE = 10;
	private int top;
	private int[] data = new int[MAX_STACK_SIZE];

	public Stack() {
		top = -1;
	}

	public void push(int data_) throws Exception {
		if(isFull()) {
			throw new Exception("스택이 가득 찼습니다.");
		}
		data[++top] = data_;
	}

	public int pop() throws Exception {
		if(isEmpty()) {
			throw new Exception("스택이 비었습니다.");
		}
		return data[top--];
	}

	public int peek() throws Exception {
		if(isEmpty()) {
			throw new Exception("스택이 비었습니다.");
		}
		return data[top];
	}

	public boolean isEmpty() {
		return top == -1;
	}

	public boolean isFull() {
		return top == MAX_STACK_SIZE -1;
	}

	public int size() {
		return top+1;
	}

}
```

</div>
</details>

<details>
<summary>❓ Priority Queue(우선순위 큐)에 대해 설명해주세요.</summary>
<div markdown="1">

우선순위 큐는 들어간 순서에 상관없이 우선순위가 높은 데이터를 먼저 꺼내기 위해 고안된 자료구조입니다. 
우선순위 큐 구현 방식에는 배열, 연결 리스트, 힙이 있고, 그 중 힙 방식이 worst case 라도 시간 복잡도 O(logN) 을 보장하기 때문에 일반적으로 완전 이진트리 형태의 힙을 이용해 구현합니다.

</div>
</details>

<details>
<summary>❓ Array와 ArrayList의 차이점에 대해 설명해주세요.</summary>
<div markdown="1">

Array는 크기가 고정적이고, ArrayList는 크기가 가변적입니다.

Array는 초기화 시 메모리에 할당되어 ArrayList보다 속도가 빠르고,

ArrayList는 데이터 추가 및 삭제 시 메모리를 재할당하기 때문에 속도가 Array보다 느립니다.

</div>
</details>

<details>
<summary>❓ Array와 LinkedList의 장/단점에 대해 설명해주세요.</summary>
<div markdown="1">

**Array**는 인덱스(index)로 해당 원소(element)에 접근할 수 있어 **찾고자 하는 원소의 인덱스 값을 알고 있으면 O(1)에 해당 원소로 접근**할 수 있습니다.

즉, RandomAccess가 가능해 **속도가 빠르다는 장점**이 있습니다. 

하지만, **삽입 또는 삭제의 과정에서 각 원소들을 shift 해줘야 하는 비용이 생겨 이 경우 시간 복잡도는 O(n)이 된다는 단점**이 있습니다.

이 문제점을 해결하기 위한 자료구조가 **LinkedList**입니다.

각각의 원소들은 자기 자신 다음에 어떤 원소인지만을 기억하고 있기 때문에 이 부분만 다른 값으로 바꿔주면 **삽입과 삭제를 O(1)로 해결**할 수 있습니다. 

하지만, LinkedList는 **원하는 위치에 한 번에 접근할 수 없다는 단점**이 있습니다. 원하는 위치에 삽입을 하고자 하면 **원하는 위치를 Search 과정에 있어서 첫번째 원소부터 다 확인해야** 합니다.

정리하자면,

**Array는 검색이 빠르지만, 삽입, 삭제가 느리다.**

**LinkedList는 삽입, 삭제가 빠르지만, 검색이 느리다.**

</div>
</details>

<details>
<summary>❓ 해시 테이블(Hash Table)과 시간 복잡도에 대해 설명해주세요.</summary>
<div markdown="1">

해시 테이블은 (Key, Value)로 데이터를 저장하는 자료구조 중 하나로 빠르게 데이터를 검색할 수 있는 자료구조입니다.

빠른 검색 속도를 제공하는 이유는 내부적으로 배열(버킷)을 사용하여 데이터를 저장하기 때문입니다. 

각 Key값은 해시함수에 의해 고유한 index를 가지게 되어 바로 접근할 수 있으므로 평균 O(1)의 시간 복잡도로 데이터를 조회합니다.

하지만, index 값이 충돌이 발생한 경우 Chanining에 연결된 리스트들까지 검색해야 하므로 O(N)까지 증가할 수 있습니다.

</div>
</details>

<details>
<summary>❓ BST(Binary Search Tree)와 Binary Tree에 대해 설명해주세요.</summary>
<div markdown="1">

**이진트리(Binary Tree)** 는 자식 노드가 최대 2개인 노드들로 구성된 트리이고,

**이진탐색트리(BST)** 는 이진 탐색과 연결 리스트를 결합한 자료구조입니다.

이진 탐색의 효율적인 탐색 능력을 유지하면서, 빈번한 자료 입력과 삭제가 가능하다는 장점이 있다.

**이진 탐색 트리**는 왼쪽 트리의 모든 값은 반드시 부모 노드보다 작아야 하고, 오른쪽 트리의 값은 부모 노드보다 커야 하는 특징이 있다.

이진 탐색 트리의 탐색 연산은 트리의 높이에 영향을 받아 높이가 h일 때, 시간 복잡도는 O(h)이며,

트리의 균형이 한쪽으로 치우쳐진 경우 worst case가 되고, O(n)의 시간 복잡도를 가진다.

이런 worst case를 막기 위해 나온 기법이 RBT(Red-Black Tree)이다.

</div>
</details>

<details>
<summary>❓ RBT(Red-Black Tree)에 대해 설명해주세요.</summary>
<div markdown="1">

RBT(Red-Black Tree)는 BST를 기반으로 하는 트리 형식 자료구조이며,

RBT는 BST의 삽입, 삭제 연산 과정에서 발생할 수 있는 문제점을 해결하기 위해 만들어졌습니다.

BST를 기반으로 하기 때문에 당연히 BST의 특징을 모두 갖습니다.

노드의 child가 없을 경우, child를 가리키는 포인터는 NIL 값을 저장합니다. 이러한 NIL들을 leaf node로 간주합니다.

모든 노드를 빨간색 또는 검은색으로 색칠하며, 연결된 노드들은 색이 중복되지 않습니다.

![rbt](https://github.com/whdydrhks/CS/assets/109534450/915e48f1-469b-4ff0-aee0-d4eaac2fced4)

</div>
</details>