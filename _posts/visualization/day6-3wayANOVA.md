데이터 시각화
===========
---
title: "day 6"
date: 2020-01-25
categories: blog
---

# 이번 강의는 catplot을 이용하여 three way ANOVA를 하는 법을 배운다.
three way ANOVA(삼원분산분석)은 변수가 3개인 요소들에 대한 분산분석을 진행하는 것이다.
분산분석은 얼핏들으면 분산을 알기 위한 분석이라고 착각할 수 있으나, 사실은 관측하고자 하는 모수는 평균과 같은 것들이다.
그러나, 분산때문에 평균이 잘못측정되는 경우를 배제하기 위해서 분산을 선험적으로 검토하는 것이다.

## 코드 첨부
<pre>
<code>
import seaborn as sns
sns.set(style="whitegrid")

# Load the example exercise dataset
df = sns.load_dataset("exercise")

# Draw a pointplot to show pulse as a function of three categorical factors
g = sns.catplot(x="time", y="pulse", hue="kind", col="diet",
                capsize=.2, palette="YlGnBu_d", height=6, aspect=.75,
                kind="point", data=df)
g.despine(left=True)
</code>
</pre>

## 코드설명
sns.catplot을 이용하여 plotting하게 되는데, 해당 코드에선 time, pulse, kind, diet의 사원 분산분석을 진행하였다.
요소들에대해 x축 y축 뿐만 아니라, hue나 col로 분류하여 각각의 데이터에대해 표현 할 수 있는 것이다.

## 분산의 중요성.
day1 commit에서 다루었던 lmplot을 보면, 각각 다른 데이터 셋으로부터 동일한 회귀선이 유도되기도 하는데,
그렇다고 모두 같은 데이터라고 바라보기엔 비약이 존재한다는 것이다.

따라서, 우리는 분석을 통해 조금 더 정확한 시각을 가질 수 있다는 것이다.

## 암튼 그렇다....
분산은 중요하고, 나의 명절도 중요하지만, 오늘도 나는 1커밋을 남긴다...
