---
title: "토큰화 - Tokenization"
category:
  - post
tag:
  - DeepLearning
toc: true
toc_label: "목차 바로가기" # toc 이름 정의
toc_sticky: true # 스크롤 내릴때 같이 내려가는 목차
header:
  teaser: https://github.com/Woogie924/Woogie924.github.io/blob/master/assets/images/myLogo.png?raw=true
---

# 토큰화 (Tokenization)

- 토큰화가 필요한 경우

  - 자연어 처리에서 크롤링 등으로 얻어낸 코퍼스 데이터가 필요에 맞게 전처리되지 않은 상태
  - 해당 데이터를 사용하고자 하는 용도에 맞게 토큰화(tokenization)

- 토큰화란?
  - 주어진 코퍼스(corpus)에서 토큰(token)이라고 불리는 단위로 나누는 작업
  - 토큰의 단위는, 보통 의미있는 단위로 토큰을 정의
  - NLTK 패키지, koNLPY 패키지를 샘플로 쓸 예정

## NLTK와 KoNLPy를 이용한 영어, 한국어 토큰화

### 영어 토큰화

#### 1) 토큰화하기

```python
from nltk.tokenize import word_tokenize
text="I am actively looking for Ph.D. students. and you are a Ph.D. student."
print(word_tokenize(text))
```

#### 2) 품사 태깅

```python
from nltk.tag import pos_tag
x=word_tokenize(text)
pos_tag(x)
```

### 한국어 토큰화

#### 1) 토큰화하기

```python
from konlpy.tag import Okt
okt=Okt()

print(okt.morphs("열심히 코딩한 당신, 연휴에는 여행을 가봐요"))
```

#### 2) 품사 태깅

```python
from konlpy.tag import Okt
okt=Okt()
print(okt.pos("열심히 코딩한 당신, 연휴에는 여행을 가봐요"))
```

- `morphs` : 형태소 추출
- `pos` : 품사 태깅(Part-of-speech tagging)
- `nouns` : 명사 추출
