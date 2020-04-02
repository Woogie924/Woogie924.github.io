---
title: "정수 인코딩 - Integer Encoding"
category:
  - post
tag:
  - DeepLearning
toc: true
toc_label: "목차 바로가기" # toc 이름 정의
toc_sticky: true # 스크롤 내릴때 같이 내려가는 목차
header:
  teaser: https://github.com/Woogie924/Woogie924.github.io/blob/master/assets/images/TF.PNG?raw=true
---

# 정수 인코딩(Integer Encoding)

컴퓨터는 텍스트보다 숫자를 더 잘 처리할 수 있습니다. 이를 위해 자연어 처리에서는 텍스트를 숫자로 바꾸는 여러가지 기법들이 있습니다.
그리고 그러한 기법들을 본격적으로 적용시키기 위한 첫 단게로 각 단어를 고유한 정수에 맵핑(mapping)시키는 전처리 작업이 필요할 때가 있습니다.

> 보통은 단어에 대한 빈도수를 기준으로 정렬한 뒤에 인덱스를 부여합니다.

## 정수 인코딩(Integer Encoding)

## 케라스(Keras)의 텍스트 전처리

케라스(keras)는 기본적인 전처리를 위한 도구들을 제공합니다.

> 정수 인코딩을 위해, 케라스의 전처리 도구인 토크나이저를 사용해야 함.

```python
from tensorflow.keras.preprocessing.text import Tokenizer

sentences=[['barber', 'person'], ['barber', 'good', 'person'], ['barber', 'huge', 'person'], ['knew', 'secret'], ['secret', 'kept', 'huge', 'secret'], ['huge', 'secret'], ['barber', 'kept', 'word'], ['barber', 'kept', 'word'], ['barber', 'kept', 'secret'], ['keeping', 'keeping', 'huge', 'secret', 'driving', 'barber', 'crazy'], ['barber', 'went', 'huge', 'mountain']]
```

```python
tokenizer = Tokenizer()
tokenizer.fit_on_texts(sentences) # fit_on_texts()안에 코퍼스를 입력으로 하면 빈도수를 기준으로 단어 집합을 생성한다.
```

- filt_on_text
  - 입력한 텍스트로부터 단어 빈도수가 높은 순으로 낮은 정수 인덱스를 부여
  - 정수 인코딩 작업이 이루어진다고 보면 된다.

`word_index` : 각 단어에 인덱스가 어떻게 부여되어 있는 지

```python
print(tokenizer.word_index)
```

`word_counts` : 각 단어가 카운트를 수행했을 때 몇 개였는지 확인

```python
print(tokenizer.word_counts)
```

`texts_to_sequences` : 입력으로 들어온 코퍼스에 대해서, 각 단어를 이미 정해진 인덱스로 변환

```python
print(tokenizer.texts_to_sequences(sentences))
```

## ❤참고

- [위키](https://wikidocs.net/31766)
