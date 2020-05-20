---
layout: post
title: 알고리즘_Programmers (7)
comments: true
tag: [Algorithm, Programmers, python, 완전 탐색]
---



## 코딩테스트 고득점 Kit



#### 완전 탐색 - 모의고사



### *Code*

---

```python
def solution(answers):
    math1 = [1, 2, 3, 4, 5] #5
    math2 = [2, 1, 2, 3, 2, 4, 2, 5] #8
    math3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5] #10

    answer = []
    ans1 = 0; ans2 = 0; ans3 = 0
    size = len(answers)

    for ans in range(0, size):
        if math1[ans % 5] == answers[ans]:
            ans1 = ans1 + 1
        if math2[ans % 8] == answers[ans]:
            ans2 = ans2 + 1
        if math3[ans % 10] == answers[ans]:
            ans3 = ans3 + 1

    maxValue = max(ans1, max(ans2, ans3))

    if maxValue == ans1:
        answer.append(1)
    if maxValue == ans2:
        answer.append(2)
    if maxValue == ans3:
        answer.append(3)

    return answer
```

 전부 다 비교하면 끝! 

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42840>