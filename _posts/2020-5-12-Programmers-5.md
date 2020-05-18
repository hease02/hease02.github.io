---
layout: post
title: 알고리즘_Programmers(5)
comments: true
---



## 코딩테스트 고득점 Kit



#### 해쉬 - 전화번호 목록



### *Code*

---

```python
def solution(phone_book):
    answer = True
    book = []

    phone_book = sorted(phone_book)

    for phone in phone_book:
        tel = ""

        for p in phone:
            tel = tel + p

            if tel in book:
                answer = False
                return answer
        book.append(phone)

    return answer
```

 book: 전화번호로 비교할 접두어 리스트     

 전화번호를 앞에서 부터 하나 씩 읽어와  접두어 book에 있는지 비교한다. 있으면 바로 False를 리턴.   

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42577>



