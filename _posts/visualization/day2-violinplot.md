데이터 시각화
=======
---
title: "day 2"
date: 2020-01-21
categories: blog
---

## 깃허브를 많이 배웠다...
곧 올리겠지만! 깃허브를 인터넷을 통해 많이 배워왔다.
전에 올렸던 자료들도 꽤나 수정을 거쳤는데, 사실 잘 고쳤는지는 아직도 모르겠다.. ㅎㅎ

## seaborn의 violin
이번에도 역시나 seaborn을 사용하였고, 
seaborn의 violinplot을 사용하여 바이올린 모양의 graph를 plotting할 수 있다.


## 코드 첨부
>>코드 첨부를 배워왔다 이말이지!!
<pre>
<code>
{
import seaborn as sns
sns.set(style="whitegrid", palette="pastel", color_codes=True)

# Load the example tips dataset
tips = sns.load_dataset("tips")

# Draw a nested violinplot and split the violins for easier comparison
sns.violinplot(x="day", y="total_bill", hue="smoker",
               split=True, inner="quart",
               palette={"Yes": "y", "No": "b"},
               data=tips)
sns.despine(left=True)
}
</code>
</pre>

## 코드 설명
코드 설명을 조금 해보자면, tips에 데이터셋을 저장하는 것까지는 지난번과 크게 다르지 않다.
sns.violinplot에서 이를 이용하여 본격적으로 violinplot을 plotting하였는데,
violinplot내부의 메소드들을 통해 내가 원하는 그래프의 세부사항들을 지정할 수 있다.
마지막의 sns.despine은 축을 진하게 표시하는 코드이고, 뭐... 조금 새로울 순 있으나 중요한 코드는 아니다.

## 역시나.. 도움이 되는건 코딩지식보단 통계지식..
violinplot은 boxplot의 상위버젼이라고 말할 수 있을 것 같다.
boxplot은 그 quartile내부의 분포를 확인할 수 없으나, violinplot은 확인할 수 있다는 것이 바로 violinplot의 핵심!!

처음알게된 사실이다.. ㅎㅎㅎ
앞으로 애용하지 않을까!!!

## 곧 설날인데.. 더 열심히 해둬야지!
설날에도 1일 1커밋 하쟈 
