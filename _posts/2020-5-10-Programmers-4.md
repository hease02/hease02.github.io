---
layout: post
title: 알고리즘_Programmers (4)
comments: true
tag: [Algorithm, Programmers, python, 스택, 큐]
---



## 코딩테스트 고득점 Kit



#### 스택/큐 - 탑



*문제 설명*

수평 직선에 탑 N대를 세웠습니다. 모든 탑의 꼭대기에는 신호를 송/수신하는 장치를 설치했습니다. 발사한 신호는 신호를 보낸 탑보다 높은 탑에서만 수신합니다. 또한, 한 번 수신된 신호는 다른 탑으로 송신되지 않습니다.

예를 들어 높이가 6, 9, 5, 7, 4인 다섯 탑이 왼쪽으로 동시에 레이저 신호를 발사합니다. 그러면, 탑은 다음과 같이 신호를 주고받습니다. 높이가 4인 다섯 번째 탑에서 발사한 신호는 높이가 7인 네 번째 탑이 수신하고, 높이가 7인 네 번째 탑의 신호는 높이가 9인 두 번째 탑이, 높이가 5인 세 번째 탑의 신호도 높이가 9인 두 번째 탑이 수신합니다. 높이가 9인 두 번째 탑과 높이가 6인 첫 번째 탑이 보낸 레이저 신호는 어떤 탑에서도 수신할 수 없습니다.

| 송신 탑(높이) | 수신 탑(높이) |
| ------------- | ------------- |
| 5(4)          | 4(7)          |
| 4(7)          | 2(9)          |
| 3(5)          | 2(9)          |
| 2(9)          | -             |
| 1(6)          | -             |

맨 왼쪽부터 순서대로 탑의 높이를 담은 배열 heights가 매개변수로 주어질 때 각 탑이 쏜 신호를 어느 탑에서 받았는지 기록한 배열을 return 하도록 solution 함수를 작성해주세요.



*제한 사항*

- heights는 길이 2 이상 100 이하인 정수 배열입니다.
- 모든 탑의 높이는 1 이상 100 이하입니다.
- 신호를 수신하는 탑이 없으면 0으로 표시합니다.



### *Code*

---

```python
def solution(heights):
    heights = list(reversed(heights))
    answer = [0 for i in range(len(heights))]

    index = 0

    for i in range(0, len(heights)):
        cur = heights[0]
        del heights[0]
        temp = []

        for j in range(0, len(heights)):
            if heights[0] > cur:
                answer[index] = len(heights)
                break
            else:
                temp.append(heights[0])
                del heights[0]

        index = index+1

        if len(temp) > 0:
            heights = temp + heights

    answer = list(reversed(answer))
    return answer
```

 뒤에서 부터 값을 하나씩 빼가며 앞의 값들을 비교하면 된다. 보기 편하기 위해 reverse를 시켰는데 굳이 할 필요는 없다. 

---

###### 문제 링크

<https://programmers.co.kr/learn/courses/30/lessons/42588>

