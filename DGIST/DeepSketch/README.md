# DeepSketch: A New Machine Learning-Based Reference Search Technique for Post-Deduplication Delta Compression

-   [Link](https://www.usenix.org/conference/fast22/presentation/park)
-   [Code](https://github.com/dgist-datalab/deepsketch-fast2022)

1. 저자가 뭘 해내고 싶어했는가?

-   스토리지 시스템에서 데이터 감소를 통한 스토리지 저장 경제성 및 효율성 증대
-   좋은 참조 블록을 찾아 데이터 감소율을 높이는 것

2. 이 연구의 접근에서 중요한 요소는 무엇인가?

-   데이터 블록을 클러스터링하여 (DK-Clustering) 생성된 클러스터를 타켓 클래스로 하여 Neural Network로 데이터 블록의 스케치를 생성해냄.
-   Neural Network로 유사한 블록에 대해 유사한 스케치를 생성하여 데이터 감소를 잘할 수 있는 좋은 참조 블록을 찾아내는 것

3. 당신(논문독자)은 스스로 이 논문을 이용할 수 있는가?

-   스토리지 시스템에서 데이터 블록 감소를 통한 저장 공간 최적화에 사용

4. 당신이 참고하고 싶은 다른 레퍼런스에는 어떤 것이 있는가?

-   Unsupervised Learning 방식을 적용하여 기존 DK Clustering + NN 부분을 NN 하나로만 대체할 수 있게 하고 싶음.
-   DeepSketch에 적용할 수 있는 Unsupervised Learning을 찾아보는 것
