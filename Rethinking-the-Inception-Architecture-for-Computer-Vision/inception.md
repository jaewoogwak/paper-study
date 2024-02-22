# Rethinking the Inception Architecture for Computer Vision

컴퓨터 비전에 있어서 Inception architecture을 다시 생각해보기?

Inception architecture가 뭔지 알기 위해선 이게 나온 배경을 알아야함.

deep neural network의 성능을 향상시키는 가장 간단한 방법은 모델의 크기를 늘리는 것

근데 여기엔 두 가지 문제가 있음 

1. Overfitting 되기 쉬움
2. Computational resource 증가

기존에는 Fully connection architecture를 사용함. 

여기서 Sparsely connected architecture로 바꿔보자.

Sparsely connected architecture는 fully connected처럼 다 연결된 것이 아니라 연결된 노드끼리 구멍이 뿅뿅 뚫려있는 것을 생각하면됨.

이전 노드의 output의 연관관계가 높으면 둘은 연결시켜주고 그렇지 않으면 연결x

그러면 cluster가 생기고 sparsely connection architecture 구조

근데 이것도 문제가 있음. 오늘날 컴퓨팅 인프라는 균일하지 않은 sparse 데이터 구조에 대한 수치 계산이 매우 비효율적 -> 이건 왜그런지 모르겠음

그래서 중간 단계를 고민하게 됨. Fully connection architecture와 Sparsely connected architecture의 중간단게 -> Inception module