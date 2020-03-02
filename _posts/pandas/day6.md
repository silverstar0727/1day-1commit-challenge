## Pandas day6

## pandas profiling

### markdown으로 올리는 이유..
기존엔 계속 colab의 python파일로 올리다가 markdown언어로 올리는 이유는, profile파일이 보이지가 않는다...

원래 profile_report()를 적용했을 때, 관련된 profiling이 진행되어야하는데 보이지가 않아서 하루가 지난 지금 다시올린당 ㅠㅠㅠ...

## 코드첨부
<pre>
<code>
!pip install-U pandas_profiling
import seaborn as sns
import pandas_profiling as pp

mpg = sns.load_dataset('mpg')

mpg.profile_report()
</code>
</pre>

## 위 코드를 실행시키면된다

## 코드 설명
!pip install -U pandas_profiling은 profiling을 import하기 위한 install과정이라고 볼 수 있다.
여기서 dataset은 seaborn의 내장된 mpg기본 데이터 셋을 활용하였다.

mpg.profile_report()
이런식으로 하면된다.!!!

### 갑자기 보이지가 않아서 마음이 아프다,.. ㅠㅠ
