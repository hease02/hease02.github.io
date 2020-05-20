---
layout: post
title: 알고리즘_Programmers (2)
comments: true
tag: [Algorithm, Programmers, python, Hash]
---



## 코딩테스트 고득점 Kit

### Hash - 위장


*문제 설명*

스파이들은 매일 다른 옷을 조합하여 입어 자신을 위장합니다.

예를 들어 스파이가 가진 옷이 아래와 같고 오늘 스파이가 동그란 안경, 긴 코트, 파란색 티셔츠를 입었다면 다음날은 청바지를 추가로 입거나 동그란 안경 대신 검정 선글라스를 착용하거나 해야 합니다.

| 종류 | 이름                       |
| ---- | -------------------------- |
| 얼굴 | 동그란 안경, 검정 선글라스 |
| 상의 | 파란색 티셔츠              |
| 하의 | 청바지                     |
| 겉옷 | 긴 코트                    |

스파이가 가진 의상들이 담긴 2차원 배열 clothes가 주어질 때 서로 다른 옷의 조합의 수를 return 하도록 solution 함수를 작성해주세요.


*제한사항*

- lothes의 각 행은 [의상의 이름, 의상의 종류]로 이루어져 있습니다.
- 스파이가 가진 의상의 수는 1개 이상 30개 이하입니다.
- 같은 이름을 가진 의상은 존재하지 않습니다.
- clothes의 모든 원소는 문자열로 이루어져 있습니다.
- 모든 문자열의 길이는 1 이상 20 이하인 자연수이고 알파벳 소문자 또는 '_' 로만 이루어져 있습니다.
- 스파이는 하루에 최소 한 개의 의상은 입습니다.

---

#### *Code*

```python
def solution(clothes):
    cloth_dict = {}
    for name, kind in clothes:
        if not kind in cloth_dict.keys():
            cloth_dict[kind] = [name]
        else:
            cloth_dict[kind].append(name)

    answer = 1

    for kind in cloth_dict.keys():
        num = len(cloth_dict[kind])

        answer = answer * (num+1)

    return answer-1
```

 의상의 종류-key 값, 의상의 이름-value로 딕셔너리를 만들어 Hash를 구현하였다.     
 조합을 이용하여 경우의 수를 계산한다. 각 종류의 옷을 안 입을 수도 있기 때문에 num+1하여 각각의 종류를 곱한다.그리고 모든 종류의 옷을 압 입는 경우는 제외해야 하기 때문에 -1를 뺀다. 

---
###### 문제 링크
<https://programmers.co.kr/learn/courses/30/lessons/42578>
