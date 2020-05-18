---
layout: post
title: 알고리즘_Programmers (1)
comments: true
tag: [알고리즘, 프로그래머스, 파이썬3, Hash]
---

## 코딩테스트 고득점 Kit

#### Hash - 완주하지 못한 선수
   
*문제 설명*    
수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.
마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.   

*제한사항*
* 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.
* completion의 길이는 participant의 길이보다 1 작습니다.
* 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.
* 참가자 중에는 동명이인이 있을 수 있습니다.

   
   
#### *Code*

```
def solution(participant, completion):
    part = {}
    answer = ''
    for name in participant:
        if name in part:
            part[name] = part[name] + 1
        else :
            part[name] = 1
    
    for com in completion:
        part[com] = part[com] - 1
    
    for key, val in part.items():
        if part[key] > 0:
            answer = key
        
    return answer
```

#### 딕셔너리를 사용해서 간단하게 해결 완료.
---
###### 문제 링크
<https://programmers.co.kr/learn/courses/30/lessons/42576>
