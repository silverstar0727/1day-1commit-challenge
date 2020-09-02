# Ezzat 논문(2016)

* between-class imbalance : 상호작용하지 않는 drug-target 쌍 > 상호작용하는 drug-target 쌍

* within-class imbalance : predict performance를 저하시키지만 이전에 언급된 적 없는 방법, rare cases가 data내에 존재할 때 발생하는 imbalance 

* 이 연구에선 between-class imbalance, within-class imbalance를 다루는 simple method제안 

1. method class로부터 버려진 정보의 양을 크게 줄이면서 minority와 majority class사이의 높은 불균형 비율을 위한 해결책 제시
2. minority class내에 다른 concepts들 사이의 ratio를 balance하여 data내에 일반적인 within-class imbalance 를 다룸.

* 첫 번째로 각 그룹이 하나의 특정한 concept과 일치하는 homogenous group을 탐색하기 위한 clustering을 수행,
* 두번째로 부정확하게 classfied되는 것이 비교적으로 쉬운 작은 그룹 안의 상호작용을 탐색하는 clustering을 수행

>인위적으로 제시한 classification model이 classification 오류를 최소화하기위해 이 small concept들에 집중할 수 있도록 oversampling 과정을 통해 small group 향상

## DATA

* Drug-Target interaction data
  * DrugBank에서 추출

total 12674개의 drug-target interaction존재 (5877개의 drug와 3348개의 protein interaction partner사이)
전체 drug와 target의 list와 interaction data는 Additional files 1,2,3,에서 확인 가능

* Data representation 
 * drug와 target 데이터 각각 feature를 만듦
 * drug의 descriptor는 RCPI pacage를 사용하여 계산됨
 * target feature는 PROFEAT[26] 웹 서버의 도움& target feature들의 genomic sequence로부터 계산됨.
 * drug와 target의 feature만든 후 모든 drug나 target에 고정값을 가진 feature들이 있다.
>이들은 제거됨(drug-target interaction의 예측에 기여하지 못하기 때문) &몇몇 drug와 target에 값이 빠진 feature들도 존재 ->모든 drug와 target feature의 평균값으로 대체
>193개의 drug와 1290의 target feature들만 남음

## Method

* Our purposed algorithm
 * base learner를 위해 decision tree를 사용 ->이는 unstable learners로 알려짐
 * unstable learners : 이들의 예측 결과가 training set을 수정하면서 쉽게 동요되고, 예측 performance를 증진시키기위해 그들의 base learner에게 diversity를 사용하게 하는 앙상블 기법과 잘 어울리게 하는 것을 의미
 * 일반적으로 앙상블 학습 기법은 이것을 구성하는 base learner들이 uncorrelated되어 있을때만 예측 performanece가 증가한다고 알려져있음
 * base learner에게 diversity를 소개하는 방법은 각 base learner에게 다른 training set을 제공하는 것. diversity를 추가하는 다른 방법은 feature subspacing : 
각 base learner에게 feature의 다른 subset을 사용하는 instance를 나타냄
 * 더 정확하게, 각 base learner에게 instance를 나타내기 위해 랜덤하게 2/3의 feature를 선택 

* Within-class imbalance : positive set의 상호작용의 특정한 type의 존재를 나타냄
 * positive class : 상호작용하는 drug-target쌍으로 구성
 *negative class : 상호작용하지 않는 drug-target쌍으로 구성
 *상호작용의 특정한 type : 다른 상호작용 type에 비해 data에서 충분히 표현 되지 않음
> 이를 다루기 위해 K-means clustering method를 사용
> data를 각 cluster가 하나의 특정한 concept에 일치하는 K(parameter) homogeneous cluster로 cluster하기 위함

* Algorithm 2: oversampling procedure의 pseudo코드
 * 이 방법에서 positive으로부터의 small-concept data의 중요성을 높임
> predict performance의 noise의 잠재적 영향이 최소화 됨.

* Between-class imbalance
 * majority class를 향한 예측 결과에 bias를 나타냄. 이는 minority example이 majority class내로 분류되는 오류를 만듦 
 * 피라미터 T사용(훈련에서 majority class의 범위를 넓히기 위해)
 * T : 앙상블 method에서 base learner의 수를 나타내고, negative set N으로부터 우리가 원하는 만큼의 instance를 그릴 수 있는지 그 횟수를 결정
> T가 증가함에 따라, majority class로부터의 유용한 정보는 최종 classification model을 구축하기 위해 사용.

## Results and discussion
* 4가지 방법으로 비교(2개의 최신기술, 2개의 baseline방법)
* 실험적 setting을 정교하게 만듦 -> CV실험과 비교 결과의 세부사항 제공
>새로운 drug design과 drug repositioning task에 결정적인 새로운 drug와 새로운 target의 상호작용 예측에 중점을 둠.

* Experimental settings
 * 2개의 최신기술과 2개의 baseline방법을 실험에 의거해 비교
  * 2개의 최신기술 : RF,SVM : drug-target상호작용을 예측하기위한 최근 작업에 사용됨.
  1. 이 두 방법에 대한 parameter들은 [27]에서 제공된 최적 값을 default하기 위해 설정됨.
  2. 2개의 baseline 방법 : decision tree, Nearest Neighbor 
   2.1. Decision tree : 합리적인 좋은 결과를 생산하는 것으로 발견된 파라미터 값들을 default
   2.2. Nearest Neighbor : 유사성을 계산하면서 예측 점수 제공

* Cross Validation experiments
 * 5-fold CV방법을 수행, 각 방법마다 AUC계산
   * 각 방법을 비교하고 5AUC값이 계산되면 모든 AUC 점수에 평균값을 최종 값으로 지정
 * Table 2 에서 Random Forest와 연구방법 결과값이 비슷
   * feature subspacing을 가진 decision tree앙상블 기법이기 때문
 * 차이점
  * 연구방법은 다른 base learner를 위해 다중의 non-overlapping negative set에 영향력이 있음
  * Within-class imbalance를 다루기 위해 의도한 방법대로 positive set을 oversampling함
> data내의 class imbalance를 다루는 것이 predict performance를 증진시키기 위해 중요함
  * Predicting interaction for new drugs and targets
   1. new drug, new target : drug나 target에 상호작용 정보가 없는 것
   2. 정확하게 상호작용을 예측하는 것을 시험하기 위해, new drug와 target의 case를 dataset밖으로 내보내고 나머지 data로 학습한 후 내보낸 이 새로운 drug와 target의 예측을 얻는 방법으로 시뮬레이션 함.
