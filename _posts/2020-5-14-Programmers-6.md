---
layout: post
title: 알고리즘_Programmers (6)
comments: true
tag: [Algorithm, Programmers, python, 스택, 큐]
---



## 코딩테스트 고득점 Kit



#### 스택/큐 - 다리를 지나는 트럭



### *Code*

---

```python
import queue

def solution(bridge_length, weight, truck_weights):
    q = queue.Queue()

    for i in range(0, bridge_length):
        q.put(0)

    q.get() ; q.put(truck_weights[0])
    time = 1 ; q_weight = truck_weights[0] ;
    del truck_weights[0]
    value = len(truck_weights)+1

    while (len(truck_weights) > 0):
        out_truck = q.get()

        if out_truck is not 0:
            value = value-1
            q_weight = q_weight - out_truck

        time = time + 1

        if q.qsize() > bridge_length:
            continue

        if q_weight + truck_weights[0] <= weight:
            q.put(truck_weights[0])
            q_weight = q_weight + truck_weights[0]
            del truck_weights[0]

        else:
            q.put(0)

    while q.qsize() > 0 and value is not 0:
        t = q.get_nowait()
        time = time + 1

        if t is not 0:
            value=value-1

    return time
```

 코드가 왜 이렇게 긴지 의문..

 q_weight: q에 있는 트럭의 무게 총 합.   

 q: 트럭이 이동하는 도로.   

 q_weight가 도로가 견디는 무게보다 작거나 같거나 아니면 도로의 길이보다 적은 트럭이 있다면 q에 트럭을 넣는다. 조건에서 벗어나면 0을 넣어서 도로의 길이를 유지한다.     

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42583>
