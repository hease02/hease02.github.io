---
layout: post
title: 알고리즘_Programmers (8)
comments: true
tag: [Algorithm, Programmers, python, heap]
---



## 코딩테스트 고득점 Kit

#### 힙  - 더 맵게        

### *Code*

---

```python
import heapq

def scale(scov1, scov2):
    scov = scov1 + (scov2 * 2)
    return scov

def solution(scoville, K):
    answer = 0

    heapq.heapify(scoville)

    while scoville[0] < K:
        if len(scoville) == 1:
            return -1

        min1 = heapq.heappop(scoville)
        min2 = heapq.heappop(scoville)

        scov_scale = scale(min1, min2)
        answer += 1

        heapq.heappush(scoville, scov_scale)

    return answer
```

 heaps 모듈을 이용해서 풀면된다.

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42626>