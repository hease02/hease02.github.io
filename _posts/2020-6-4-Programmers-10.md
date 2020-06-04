---
layout: post
title: 알고리즘_Programmers (10)
comments: true
tag: [Algorithm, Programmers, python, heap]
---



## 코딩테스트 고득점 Kit



#### 힙  - 라면공장           

### *Code*

---

```python
import heapq

def solution(stock, dates, supplies, k):
    answer = 0
    num = 0
    priorityQ = []

    while stock < k :
        for i in range(num, len(dates)):
            if stock < dates[i]:
                break
            heapq.heappush(priorityQ, supplies[i] * (-1))
            num = i + 1

        stock = stock + (heapq.heappop(priorityQ) * (-1))
        answer = answer + 1

    return answer
```

 heapq 모듈을 이용해서 우선순위큐로 풀었다. heapq은 최소힙만 가능해서 최대힙처럼 사용하기 위해 큐에 넣을 때 -1을 곱해준다.

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42629>