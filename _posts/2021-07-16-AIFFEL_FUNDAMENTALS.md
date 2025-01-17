---
layout: single
title: "Python_기초1"
comments: true
categories: Python
---
Fundamentals Stage 시간의 노드 내용과 Python master 시간의 코딩도장을 복습해보려고 한다..! 시작한 지 벌써 1주일이 지났다. 2주차부터는 내용이 점점 더 어려워져서 주어진 시간에 다 못끝낸다. Python을 빨리 마스터하고 싶다.
지금까지 Aiffel에서 공부한 Python 내용들을 부족하지만 정리하려고 한다.

# 1.Everything is Object
파이썬에서는 모든 것이 객체(Object)이다. 쉽게 예를 들면 정수객체 10을 변수 a에 매칭 시키면 변수 a는 입력했을 때 정수객체 10이 나오는 포인터같은 역할이다. C언어처럼 변수 a에 10라는 값을 저장하는 것이 아니다. 다시 말해, 파이썬에서는 변수가 자신만을 위한 메모리를 가지는 것이 아니라 10이라는 값을 가진 객체를 가리키도록 되어있다는 것이다. 

## 1-1. Immutable/Mutable Objects
- Immutable Objects(불변객체) : 객체를 생성한 후 객체의 값이 수정 가능하고, 변수는 값이 수정된 같은 객체를 가리키게됨. 
```
ex)bool,int,float,tuple,str,frozenset
```
- Mutable Objects(가변객체) : 객체를 생성한 후 객체의 값이 수정 불가능하고, 변수는 해당 값을 가진 다른 객체를 가리키게됨.
```
ex)list,set,dict
```
```
Tip)쉽게 구별하는 방법은 변수에 대입한 값을 수정했을 때, 전후의 id 함수 리턴값을 비교해보는 것이다. 같으면 mutable 객체, 다르면 immutable 객체이다. 
```

## 1-2. Python Object Interning
Interning 이란 이미 생성된 객체를 재사용하는 것이다. 보통 Immutable 객체에 대해 Interning을 사용한다. 아주 많이 사용되는 Immutable 객체의 경우 Interning을 사용하게 되면 메모리를 줄일 수 있는 효과가 있다. 아래에 예시 코드가 있다.

- Python default Interning
기본이 되는 CPython의 경우 아래 조건에 해당될 경우 Object Interning 을 사용한다.
```
문자열:20자 미만의 공백을 포함하지 않는 문자열
정수:-5부터 256사이의 정수
```

> **>같은 id**
x=50
y=50
id(x) #140725377969488
id(y) #140725377969488

> **>다른 id**
x=300
y=300
id(x) #525660605936
id(y) #525660606288

우선 파이썬 언어에 대한 내용을 정리해 봤다. 배우면 배울수록 어려운 언어인 것 같고, 아직까지 헷갈리는 개념들이 많다.기초부터 차근차근 공부하면서 정리하겠다.
