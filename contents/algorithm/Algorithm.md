# 알고리즘   

<details>
<summary>❓ 동적 계획법(DP, Dynamic Programming)에 대해 설명해주세요.</summary>
<div markdown="1">

주어진 문제를 풀기 위해, 문제를 여러 개의 하위 문제로 나누어 푸는 방법을 말합니다.

동적 계획법에서는 어떤 부분 문제가 다른 문제들을 해결하는데 사용될 수 있어, 답을 여러 번 계산하는 대신 한 번만 계산하고

그 결과를 재활용하는 메모이제이션(Memoization) 기법으로 속도를 향상 시킬 수 있습니다.

* 메모이제이션: 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 재사용함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를 빠르게 하는 기술

</div>
</details>

<details>
<summary>❓ 동적 계획법(DP, Dynamic Programming)이 갖는 2가지 조건은 무엇인가요?</summary>
<div markdown="1">

1. **중복되는 부분(작은) 문제**
    
    중복되는 부분 문제는 나눠진 부분 문제가 중복되는 경우로, 메모이제이션 기법을 사용해 중복 계산을 없앱니다.
    
2. **최적 부분 구조**
    
    최적 부분 구조를 가진다는 것은 전체 문제의 최적해가 부분 문제의 최적해들로써 구성된다는 것입니다.

</div>
</details>

<details>
<summary>❓ 버블 정렬(Bubble Sort)에 대해 설명해주세요.</summary>
<div markdown="1">

버블 벙렬은 서로 인접한 두 원소를 비교하여 정렬하는 알고리즘입니다.

0번 인덱스부터 n-1번 인덱스까지 n번까지의 모든 인덱스를 비교하며 정렬합니다.

시간 복잡도는 O(n^2)입니다.
![bubble](https://github.com/whdydrhks/CS/assets/109534450/c3d10eeb-f08c-4363-b565-2da91e1433dd)

</div>
</details>

<details>
<summary>❓ 선택 정렬(Selection Sort)에 대해 설명해주세요.</summary>
<div markdown="1">

선택 정렬은 첫 번째 값을 두 번째부터 마지막 값까지 차례대로 비교하여 최솟값을 찾아 첫 번째에 놓고,

두 번째 값을 세 번째부터 마지막 값까지 비교하여 최솟값을 찾아 두 번째 위치에 놓는 과정을 반복하며 정렬하는 알고리즘입니다.

시간 복잡도는 O(n^2)입니다.
![selection](https://github.com/whdydrhks/CS/assets/109534450/977e60e6-154f-438e-b696-b2c381076299)


</div>
</details>