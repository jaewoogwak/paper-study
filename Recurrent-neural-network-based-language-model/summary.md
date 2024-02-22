# Abstract

>> A new recurrent neural network based language model (RNN LM) with applications to speech recognition is presented.

- 음성 인식에 적용할 수 있는 RNN LM을 소개함.
- RNN LM은 RNN based language model임

>> Results indicate that it is possible to obtain around 50% reduction of perplexity by using mixture of several RNN LMs, compared to a state of the art backoff language model. 

- RNN LMs의 혼합을 사용하여 perplexity 50% 감소시킬 수 있었음.
- perplexity는 당황스러움이란 뜻
    - NLP에서 언어 모델의 평가 지표로, 낮을수록 좋은 것



>> We provide ample empirical evidence to suggest that connectionist language models are superior to standard n-gram techniques, except their high computational (training) complexity

- 언어 모델이 표준 n-gram 기법보다 더 우수함. (대신 계산 복잡도는 더 높음)
- n-gram model은 딥러닝 이전에 언어 모델에 주로 사용된 모델임
- 연속된 N개의 단어 덩어리
- ex. 4gram model은 예측할 단어 이전 3개 단어를 보고 현재 단어를 예측함.
- n이 커지면 계산 복잡도가 커짐








# Introduction

>> Sequential data prediction is considered by many as a key problem in machine learning and artificial intelligence (see for example [1]).

- 이 연구를 왜 할까?
- ML과 AI에서 Sequential data prediction이 중요하기 때문.
- 우리가 말하고 입력하는 등의 행위로 구성되는 글(text)이 Sequential data에 해당함

>> The goal of statistical language modeling is to predict the next word in textual data given context;

- 언어 모델링의 목표는 주어진 context에서 다음 단어를 예측하는 것
- 위의 문단과 비슷한 말


>> In fact, most of the proposed advanced language modeling techniques provide only tiny improvements over simple baselines, and are rarely used in practice.

- 대부분의 고급 언어 모델링 기술이 제안된 가이드라인에 대해 약간의 개선만 있었고, 실제로 사용되는 일은 거의 없었음.


"결국 지금까지의 언어 모델링 기술이 효과적이지 못했다"를 말하고 싶음


>> However, it does not seem that simple recurrent neural networks can capture truly long context information, as cache models still provide complementary information even to dynamic models trained with BPTT

- 그러나 캐시 모델은 보완적인 정보를 제공하기 때문에 단순한 RNN으로는 정말 긴 context 정보를 캡쳐할순 없다.


# Model description

>>  Using artificial neural networks in statistical language modeling has been already proposed by Bengio [3], who used feedforward neural networks with fixedlength context. This approach was exceptionally successful and further investigation by Goodman [2] shows that this single model performs better than mixture of several other models based on other techniques, including class-based model. 


- 통계적 언어 모델링에서 인공 신경망을 사용하는 것은 고정된 길이의 context에 대해 feedforward 인공 신경망을 사용한 Bengio에 의해 드러났음.
- 이러한 접근은 성공적이었고, 이후 진행된 연구에 대해서 단일 모델이 다른 기술을 기반으로한 모델들(class-based model을 포함한)의 혼합보다 더 나음을 보임.

>> Later, Schwenk [4] has shown that neural network based models provide significant improvements in speech recognition for several tasks against good baseline systems.

- 신경망 기반 모델이 음성 인식 task에서 상당한 개선을 보임.


>> Usually this means that neural networks see only five to ten preceding words when predicting the next one. 

- 신경망은 다음에 올 단어를 예측할 때 앞선 5~10개의 단어만 봄. 
- 여기서 `this means`는 Bengio가 고정된 길이의 context에 대해 feedforward NN를 사용한걸 말함


>> In our work, we have used an architecture that is usually called a simple recurrent neural network or Elman network [7].

- 이 연구에서 단순 RNN이나 Elman network라 불리는 아키텍쳐를 사용함
- RNN은 다음 구조로 이루어짐
    - input layer x
    - hidden layer s
    - output layer y


- 초기에 s(0), 즉 hidden layer의 첫번째 값이 0.1과 같은 작은 값으로 초기화되지만, 초기값은 그리 중요하지 않음.