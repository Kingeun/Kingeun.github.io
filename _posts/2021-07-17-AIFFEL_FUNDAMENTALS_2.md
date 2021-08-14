---
layout: single
title:  "Python_기초2"
comments: true
categories: Python
---

예전부터 정리하려던 클래스(class)를 정리하려고 한다...클래스 개념이 이해하기 어려웠는데 퍼실님이 추천해주신 영상을 보고 조금은 이해가 됐다.

# 클래스
```
클래스란?
함수뿐만 아니라 다양한 변수를 포함한 큰 프로그램을 하나의 묶음으로 정의하는 것
```
> 클래스 사용 이유 : 일일이 변수를 정의하는 게 아니라 class를 선언해준 뒤에 비슷한 기능을 하는 것을 통일된 양식으로 저장해서 관리할 수 있기 때문이다. 예를 들어, 회사의 지원자들을 정리할 때 지원자들마다의 name과 age를 각각 변수로 지정해 주는 것이 아니라 class로 선언한 뒤에 지원자들의 이름만 각각 변수로 지정한뒤에 그 안에 name,age를 지정해서 관리하는 것이다.

## 문법
### 1.클래스 선언

```
>class Movie:  #클래스 선언
    pass

>class Movie():
    pass
>print(type(Movie))  #type유형의 객체
>print(type(Movie()))  #Movie()가 호출될 때 Movie 타입의 객체가 생성
```

### 2.클래스 사용
인스턴스화:선언한 클래스를 변수에 할당해서 객체화 시켜주는 것.
```
>movie=Movie()  #movie변수에 Movie클래스의 인스턴스를 할당했다.
```
클래스명 표기법은 아래 링크에 자세히 설명 되어 있다. 

[링크텍스트](https://www.python.org/dev/peps/pep-0008/)


### 3.클래스는 동작과 상태를 갖는다.
객체에는 속성과 메소드가 있다. 클래스도 객체이기 때문에 속성과 메소드를 가지고 있다.

- 클래스의 속성은 상태(state)를 표현하고, 변수로 나타낸다.
- 클래스의 메소드는 동작(behavior)을 표현하고, 키워드로 나타낸다.

```
>class Movie:
    name = 'About Time'  #속성
    
    def introduce(self):   #소개 메소드
        print("About Time은 명작입니다!")
    def information(self,genre,running_time):  #정보 메소드
        self.genre=genre
        self.running_time=running_time
        print("About Time 의 장르는 :",genre,"런닝타임은 :",running_time)
        
>movie = Movie()   #인스턴스화 
>movie.introduce()  #About Time은 명작입니다!
>movie.information('romantic comedy',124)  
#About Time 의 장르는 : romantic comedy 런닝타임은 : 124
```

### 4.생성자(____init____)

> ____init____ 함수
클래스를 선언하는 순간 실행되는 함수. 변수에 할당된 클래스가 실행되면 ____init____함수 안의 내용이 실행된다.

```
>class Movie2:
    def __init__(self,name):  #self 잊지 않기
        self.name = name
        
    def introduce(self):   
        print("About Time은 명작입니다")
        
    def information(self,genre,running_time):  
        self.genre=genre
        self.running_time=running_time
        print("About Time 의 장르는 :",genre,"런닝타임은 :",running_time)
        

>movie2=Movie2('Midnight In Paris')
>movie2.name  #'Midnight In Paris'
>movie2.introduce()  #Midnight In Paris은 명작입니다
>movie2.information('comedy',94)  
#About Time 의 장르는 : comedy 런닝타임은 : 94
```

### 5.상속
>상속 사용하기
- 메소드 추가하기(add)
- 메소드 재정의하기(override)
- 부모 메소드 호출하기(super())

```
>class NewMovie(Movie):  #Movie 클래스와 비슷한 기능과 속성을 유지한 채 country 속성만 추가
    country = 'UK'

>movie=NewMovie()
>movie.country  #'UK'

>class Movie:
    def __init__(self,name='About Time'):
        self.name='영화 이름 : ' + name
        

>class NewMovie(Movie):
    def __init__(self,name='About Time',country='UK'):
        super().__init__(name)  #부모 메소드 호출하기
        self.country = country
            
    def recommend(self):  #메소드 추가하기
        print('영화 추천해줘!')
        
    def introduce(self):  #메소드 오버라이드
        print('영화 보는 것은 즐겁다!')
        
>newmovie=NewMovie('About Time','UK')
>print(newmovie.name)  #영화 이름 : About Time
```

오늘 영상을 보고 노드를 따라가면서 정리를 해봤다. 머릿속에서 클래스가 정리가 된 것 같다. 아이펠 3주차가 지나갔다. 어떻게 지나간 건지 모르겠다. 3주차부턴 본격적인 인공지능을 공부했는데 생소한 개념들 뿐이어서 따라가기 벅찬 것 같다. 그래도 계속 하다보면 나아지겠지 하는 생각이 든다. 열심히 해야겠다. 
