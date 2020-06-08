---
layout: post
title: 알고리즘_Programmers (11)
comments: true
tag: [Algorithm, Programmers, python, 정렬]
---



## 코딩테스트 고득점 Kit



#### 정렬 - H-Index       



#### 

### *Code*

---

```python
def solution(citations):
    answer = 0
    sort_list = sorted(citations, reverse=True)
    index = 0

    while index <= len(sort_list):
        cnt = 0

        for n in range(0, len(sort_list)):
            if index <= sort_list[n]:
                cnt = cnt + 1

        if (cnt >= index) and (len(sort_list) - cnt <= index):
            answer = max(answer, index)

        index = index + 1

    return answer
```

   배열의 개수가 1000이기 때문에 전부 탐색을 해도 시간이 널널하다. 그래서 역으로 정렬 후 index보다 큰 개수들을 하나씩 탐색했다.

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42747>

