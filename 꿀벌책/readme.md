# Designing Elixir Systems With OTP
저자 : (JAMES EDWARD GRAY, II), and  (BRUCE A. TATE)\
출판사 : Pragmatic Bookshelf\
출간일 : 2019년

---

## 챕터별 분류

### 0. Introduction

### 1. Build Your Project in Layers

## Part 1. Do Fun Things...
파트 1은 레이어를 소개한다. 레이어에는 크게 3가지 종류가 있다.
1. 데이터 레이어
1. 비지니스 로직 레이어
1. 테스트 레이어

우리는 이 세가지를 레이어로 구분하여 사용할 것이다.\
그래야만 하는 이유는


### 2. Know Your Elixir Datatypes
### 3. Start with the Right Data Layer
### 4. Build a Functional Core
### 5. Test Your Core

## Part 2. ...with Big, Loud Worker-Bees
Part II addresses the layers we’ll implement
with Elixir’s OTP. We’ll deal with the second
part of the sentence “Do fun things with big,
loud worker-bees." When you hear "big, loud
worker-bees” think “boundaries, lifecycles,
and workers.”
These are the boundary layers. As a whole,
they represent the process machinery that
establishes processes (boundary), starts or
stops them (lifecycle) and divides work
(workers).

### 6. Isolate Process Machinery in a
### 7. Customize Your Lifecycle
### 8. Summon Your Workers
### 9. Assemble Your Components
### 10. Test the Boundary

---

## 소챕터별 분류

### 0. Introduction
#### 0.1 Worker -Bee-Driv en Design
#### 0.2 Who Should Read This Book
#### 0.3 Online Resources

### 1. Build Your Project in Layers
#### 1.1 We Must Reimagine Design Choices
이 책의 핵심은 레이어를 어떻게 구분해서 설계하고 그 레이어간 어떻게 상호작용을 해야하는지를 설명하는데 있다\
이 책은 설계애 대한 책이다. 엘릭서는 OTP를 매우 많이 쓰기 때문에 OTP프로그램들을 어떻게 레이어로 계층구조화 해야하는지를 안내할 것이다

#### 1.2 Choose Your Layers
레이어란 고정된 것은 아니다. 이것은 프로젝트별로 다르게 설계될 수 있다\
하지만 우리들은 다음의 6가지 기준으로 레이어를 나누는 것을 권장한다
1. 데이터 (상태 같은 것들을 말한다)
1. 비즈니스 로직
1. 유닛 테스트
1. 프로세스
1. 슈퍼바이저
1. 워커


#### 1.3 Begin with the Right Data types
#### 1.4 Build Your Functional Core
#### 1.5 Esta blish Your Boundaries
#### 1.6 Test Your Code
#### 1.7 Plan Your Lifecycle
#### 1.8 Invoke Your Workers
#### 1.9 Do Fun Things with Big , Loud Worker -Bees