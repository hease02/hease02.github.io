---
layout: post
title: 알고리즘_Programmers (9)
comments: true
tag: [Algorithm, Programmers, python]

---



## 코딩테스트 고득점 Kit



#### 스택/큐  - 기능개발           

### *Code*

---

```python
def solution(progresses, speeds):
    answer = []

    q = []
    for p, s in zip(progresses, speeds):
        count = int((100 - p) / s)

        if (100 - p) % s > 0:
            count = count + 1

        q.append(count)

    top = q.pop(0)
    cnt = 1

    while len(q) > 0:
        if q[0] <= top:
            cnt = cnt + 1
            del q[0]
        else:
            top = q[0]
            answer.append(cnt)
            cnt = 0

    answer.append(cnt)
    return answer
```

 큐 모듈을 안 쓰고 리스트를 큐처럼 사용해서 풀었다. 

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42586>