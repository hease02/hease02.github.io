---
layout: post
title: Mardown 문법 정리
comments: true
tags: [tag1, github]
---

# 1. 마크다운 문법
## 1.1. Headers
* 글머리: 1~6까지만 지원
# H1 -> 큰 제목으로 많이 쓰임
## H2 -> 작은 제목(부제)로 많이 쓰임
### H3
#### H4
##### H5
###### H6

## 1.2. List
### 1.2.1. 순서 목록
1. 첫번째
2. 두번째
3. 세번째

### 1.2.2. 순서없는 목록
* 사과
* 딸기
* 포도
	   
- [ ] 딸기 
- [ ] 사과
- [ ] 포도
	    
+ [ ] 사과
+ [ ] 딸기
+ [ ] 포도 

## 1.3. Code
하나의 탭 + 4 공백 들여쓰기를 만나면 변환

### 1.3.1. Code블록
1.  `<pre><code>{code}</code></pre>` 
<pre>
<code>
int main (int argc, char* argv[])
{
    return 0;
}
</code>
</pre>

2. 코드블럭코드("\'''") 
```
int main (int argc, char* argv[])
{
    return 0;
}
```


## 1.4. 강조
* **bold**
* _기울기_
* ~~점선~~



## 1.5. 개행
3칸 이상 띄어쓰기를 하면 개행
띄    어쓰기    





##### 마크다운 문법은 쓰면서 점점 추가할 예정
