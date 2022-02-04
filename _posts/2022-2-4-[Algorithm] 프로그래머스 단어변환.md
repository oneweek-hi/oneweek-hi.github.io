---

title:  "[Algorithm] 프로그래머스: 단어변환"
excerpt: "🥳 오늘의 알고리즘 문제"

categories:
  - 프로그래머스

last_modified_at: 2022-02-04T08:02:00-3:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true
---

<br />오늘의  문제는 🚀 <a href="https://programmers.co.kr/learn/courses/30/lessons/43163" target="_blank">프로그래머스 DFS/BFS - 단어변환</a>이다. 

같은 문제를 내가 다시 풀어도 다르게 푸는게 신기해서 글을 쓴다.

조금씩 실력이 쌓이고 있는건가 라는 생각이 들어서 기록해둔다 ;)

<br /><br />

### 테스트케이스 이해하기

![image](https://user-images.githubusercontent.com/42812764/152524549-fb78093a-d5c7-42db-b298-a7bd04aee4bf.png)

begin에서 target으로 알파벳을 하나씩 바꾸어 변환할때 가장 짧은 과정을 찾는 것이다! 만약 없다면 0을 리턴!

<br /><br />

### 알고리즘 Ver.1

1. 일단 두 단어의 각 알파벳이 하나 차이 나는 경우 True를 리턴하는 함수를 만듦.
2. 빨리 끝내려고 일단 target이 word에 없으면 0을 바로 리턴하도록 함.
3. 일단 포문을 돌면서 하나 차이나는 경우를 큐에 index넣는다.
4. 만약 target과 똑같으면 return으로  끝낸다.
5. for문을 돌려서 단어 알파벳이 하나 차이나고, 이전에 방문한적이 없으면 weight 업데이트해주고 큐에 index를 넣는다.

```python
from collections import deque

def wordchecker(word, compare):
    count = 0
    for i in range(len(word)):
        if word[i] == compare[i]:
            count += 1
    if count == len(word) - 1:
        return True
    return False

def solution(begin, target, words):
    beginlen = len(begin)
    if not target in words:
        return 0

    weight = [-1] * len(words)

    q = deque()
    for i in range(len(words)):
        if wordchecker(begin, words[i]):
            weight[i] = 1
            q.append(i)

    while q:
        new = q.popleft()
        word = words[new]
        if word == target:
            return weight[new]
        for i in range(len(words)):
         	  #알파벳 하나차이 & 이전에 방문X
            if wordchecker(word, words[i]) and weight[i] == -1: 
                weight[i] = weight[new] + 1
                q.append(i)

    return 0
```

<br /><br />

### 알고리즘 Ver.2

ver.1과 알고리즘이 크게 다를건 없지만, 확실히 코드가 깔끔하다.

```python
from collections import deque

def solution(begin, target, words):
    wordlen = len(begin)
    d = [0] * len(words)
    q = deque()
    q.append((begin, 0))

    while q:
        word, value = q.popleft()
        for i in range(len(words)):
            count = 0
            for j in range(wordlen):
                if words[i][j] != word[j]:
                    count += 1
            if count == 1 and d[i] == 0: #알파벳 하나차이 & 이전에 방문X
                d[i] = value + 1
                if words[i] == target:
                    return d[i]
                q.append((words[i], d[i]))

    return 0
```

<br /><br /><br />

<br />

그리고 내일 코테 아자아자 화이자~!

🚀Reference:   <a href="https://programmers.co.kr/learn/courses/30/lessons/43163" target="_blank">프로그래머스 DFS/BFS - 단어변환</a><br />



