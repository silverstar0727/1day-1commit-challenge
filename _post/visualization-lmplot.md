데이터 시각화
===========
---
title: "day 1"
date: 2020-01-20
categories: blog
---

## 깃허브는 너무 어렵따.
유튜버 '생활코딩'님의 강의를 수강하였다. 
수강하기는 했는데, 유튜브로 배우는 것 보다 깃허브에 올리는게 너무 어렵다...ㅠㅠㅠ

우선 seaborn을 이용했는데, seaborn은 matplotlib의 약간 상위호환? 이런 느낌이다.
더 쉽게 다양한 시각화를 표현할 수 있는 것이 seaborn의 장점이다.

해당 강의는 seaborn의 공식 홈페이지에 있는 코드를 그대로 복사 붙여넣기해서 응용을 한다.

사실 개인적인 생각이지만, 나는 개발을 약간 문제해결의 도구?로 인식하기 때문에
아주아주 마음에 드는 강의 진행이 아닐 수 없다!!!

모두 외우는 것도 좋지만... 필요할 때 찾아쓰는 것도 능력이 아닐까 생각한다.


> 무튼, 이번 강의는 seaborn의 lmplot을 이용하여 선형 회귀선을 표현하는 것이 목표이다.

해당 코드는 다음과 같다(사실 코드를 이렇게 집어넣는게 아닌 것 같다.. 다음에 제대로 배워야지 ㅠㅠㅠ)


## 코드 설명
seaborn을 sns로 import해준다
>import seaborn as sns

sns의 기본 스타일은 blackgrid로 설정이 되어 있는데 이를 ticks로 바꿔주었다
>sns.set(style="ticks")

anscombe라는 데이터셋이 기본적으로 내장되어 있는데 이를 불러왔다.
>df = sns.load_dataset("anscombe")

4종류의 데이터를 이용하여 선형회귀선을 그려준다. 여기서 어떤 메소드가 쓰일지에 대한 팁은 (shift+tab)을 눌러 확인할 수 있다.
각각의 원하는 메소드에 대한 value를 입력해주고 lmplot을 이용하여 선형 회귀선을 그린다~!!
> sns.lmplot(x="x", y="y", col="dataset", hue="dataset", data=df,
>           col_wrap=2, ci=None, palette="muted", height=4,
>           scatter_kws={"s": 50, "alpha": 1})
----------------------------------------------

### 잘한건가...
코드에 대해서 (-)처리후 설명(주석)을 달았는데 제대로 한 지 정말 모르겠다...
맞겠지뭐 ㅠㅠ


### 강의 내용 고찰 
    사실 이번 강의의 핵심은 lmplot을 그린다기보단, 각각의 다른 데이터에 대해서 동일한 선형회귀선이 그려진다는 것이 아닐까...
    통계학을 배워본 사람을 알겠지만, ANOVA를 이용하여 선형회귀에대한 적합도 검정을 시행할 수도 있다.
    선형회귀는 최소제곱법으로 이루어지는데 이에대한 한계인 것.... 
    

### 소감..ㅠㅠ
제대로 된 첫 커밋이 될 것 같은데, 이렇게 하는게 맞는건지도 잘 모르겠구... 기숙사 방빼느라 너무 혼란스러운 하루였다ㅠㅠ
내일은 깃허브에 대해서 공부를 먼저 해야할 것 같다 휴우