# elixir in action (2nd edition)

저자 : SAŠA JURIC´\
출판사 : manning\
발매일 :

---

# 챕터별 분류
## 1 ■ 얼랭과 엘릭서 소개 (First steps) 1
엘릭서는 얼랭을 변형한 언어이다. 따라서 엘릭서를 이해하려면 얼랭을 이해해야 한다. 얼랭은 통신회사에서 만든 언어이다. 어떤 상황에서도 서버가 뻗지 않고 계속 실행되는 고가용성 소프트웨어를 만들기 위해 만들어진 언어다. 20년이상 거대 시스템에서 그 안정성을 입증받았다. 엘릭서는 얼랭 플랫폼인 BEAM기반으로 작동하는 얼랭의 방언이다. 얼랭보다 더욱 효율적인 개발을 하는 것을 목표로 설계되었다

## 2 ■ Building blocks 16
이번 장을 다음을 다룬다
1. iex(interactive-elixir-shell)의 개념
1. 변수 : 엘릭서의 데이터는 불변이다. 따라서 수정할 수 없다. 함수가 인자를 수정하여 리턴한 경우 리턴값은 인자와 다른 메모리 주소에 저장된다. 이 수정된 리턴값은 가능한 많은 부분을 원래 데이터와 공유한다. 이를 persistent data 라고 한다\
1. 모듈 : 엘릭서의 코드는 모듈과 함수로 나뉘어진다. 모듈의 이름은 아톰으로 취급된다
1. 함수 : 함수는 1급 시민이다. 즉 변수처럼 쓸 수 있다. 다시말해 함수가 변수에 할당이 되고 함수를 다른함수의 인자로 넣을 수도 있다.
1. 엘릭서의 타입 : 엘릭서는 다이나믹 언어다. 따라서 변수의 타입은 그것에 값이 할당될 때 결정된다.\
가장 중요한 원시타입 3가지를 꼽으라면 넘버(number), 아톰(atom), 바이너리(binary)가 있다\
별도의 부울 타입은 없고 true와 false는 아톰으로 구현되었다.\
문자열(string) 타입은 없다. 대신 바이너리나 리스트를 이용하여 문자열을 구현한다\
빌트인 복합 타입은 3가지가 있는데 각각 `튜플`, `리스트`, `맵`이다\
다른 언어에 있는 null이라는 타입은 없다. 대신 nil이라는 아톰값을 null 대용으로 쓸 수 있다
1. 엘릭서의 연산자들



## 3 ■ (제어 흐름) (Control flow) 63
이번 장은 다음을 다룬다
1. 패턴 매칭 : 패턴 매칭은 왼쪽과 오른쪽의 패턴이 일치하는지 검증하는 작업이다. 일치하지 않을 경우 에러를 던진다.\
함수의 인자도 패턴이다. 따라서 함수에 인자는 패턴 매칭의 대상이 된다. 패턴이 매치되는 함수의 몸체가 실행된다.
1. if문이나 case문 대신 다중 정의된 함수 (multiclause functions) 사용하기
1. 조건문 사용하기 (그닥 권장되는 않음)
1. 루프 사용하기 (그닥 권장되는 않음)
1. generic iteration functions
1. Comprehensions
엘릭서에서 재귀는 루프를 수행하는 일반적인 방법이다. 꼬리 재귀라는 메커니즘이 BEAM에 구현되어 있어서 메모리 사용량을 줄일 수 있다.
## 4 ■ 데이터 추상화 (Data abstractions) 102
1. 모듈 추상화하기
1. 계층적 데이터로 일하기
1. 다형성과 프로토콜

## 5 ■ 병행성 (Concurrency primitives) 129
1. BEAM의 병행성 원칙 이해하기
1. 프로세스와 함께 일하기
1. 상태를 가진 서버 프로세스 (stateful server processes)와 일하기
1. 런타임시에 고려할 사항들

## 6 ■ 제네릭 서버 프로세스 (gen_server, Generic server processes) 159
## 7 ■ 병행성 시스템 설계하기 (Building a concurrent system) 179
## 8 ■ 폴트 톨러런스 (Fault-tolerance basics) 201
## 9 ■ 에러이펙트를 고립하기 (Isolating error effects) 224
## 10 ■ GenServer 그 이상으로 (Beyond GenServer) 251
## 11 ■ 컴포넌트로 일하기 (Working with components) 277
## 12 ■ 분산시스템 설계하기 (Building a distributed system) 305
## 13 ■ 시스템 운영하기 (Running the system) 334

---

# 소 챕터별 분류

## 1 First steps 1
### 1.1 About Erlang 1
### 1.2 About Elixir 8
### 1.3 Disadvantages 13

## 2 Building blocks 16
### 2.1 The interactive shell 17
### 2.2 Working with variables 18
엘릭서는 동적타입 언어다. 따라서 명시적으로 타입을 지정할 필요도 없다. 그리고 파이썬과 마찬가지로 변수를 선언할 필요조차 없다.\
엘릭서에서는 변수에 값을 할당하는 행위를 바인딩이라고 한다. 이미 값이 할당된 변수에 다시 바인딩을 하는 행위는 허용되지만 기존의 메모리 값을 수정하지 않는다. 새로운 메모리 주소를 확보하여 값을 새로 할당한다. 특정 메모리 주소에 할당된 값은 절대로 다시 변하지 않는다\
엘릭서는 다른 현대적인 언어처럼 가비지 컬렉션을 지원한다\
### 2.3 Organizing your code (20p)
엘릭서에서 하나의 거대한 프로젝트를 구성하는 단위는 모듈이다. 몇몇 언어들은 파일이 곧 하나의 모듈이지만 엘릭서는 하나의 파일 내에서도 여러가지 모듈을 만들 수 있다.\
하나의 모듈은 여러 함수로 이루어진다. 예를들어 `IO`는 입출력 관련 모듈인데 이 모듈 내부에 여러가지 함수가 있다. 그 중 하나가 put이고 이 함수는 입력값을 받아 표준 출력을 시도한다. 예를들면 아래와 같다\
```dotnetcli
iex(1)> IO.puts("hell world")
hell world
:ok
```
위의 코드는 REPL에서 코드를 실행한 결과를 보여준다. IO모듈의 puts함수를 실행한 결과가 표준 출력으로 나타났다. 마지막 줄의 `:ok`는 puts함수의 리턴값이다.\
\
모듈 선언하기\
모듈선언 방법은 생략한다. 생성한 모듈이 포함된 ex파일을 iex의 인자로 집어넣으면 곧바로 불러올 수 있다. 가령 아래와 같다\
`iex SomeFile.ex`\
\
함수\
함수를 정의하는 방법은 생략한다\
함수를 정의할 때 파라메터가 없는 없는 경우 괄호를 생략해도 좋다. 하지만 파라메터가 있는 경우는 괄호를 생략할 수 없다\
함수의 리턴값은 마지막 줄의 표현식이다. 별도로 return이라는 키워드를 삽입하지 않아도 된다\
\
함수의 호출\
엘릭서는 함수를 호출할 때 괄호를 생략해도 된다. 가령 `f`라는 함수가 있고 `arg1, arg2`를 각각 인자로 넣어 호출할 때 다른 언어들과 마찬가지로 `f(arg1, arg2)`라고 호출해도 되지만 `f arg1 arg2`라고 호출해도 된다. 함수형 언어에서 함수를 호출할 때 괄호를 생략하는 관습은 흔하다\
\
파이프라인 연산자\
생략한다\
\
원라인 함수로 정의하기\
원라인 함수는 다음과 같은 방식으로 정의한다\
`def multiply(a, b), do: a * b`\
파라메터와 do사이에 콤마가 추가되었고, do와 함수몸체 사이에 `:`가 추가되었다\
\
함수 오버로딩을 활용하기\
대부분의 경우 엘릭서에서 이름은 같고 변수의 갯수만 다른 함수가 있는 경우는 `위임`패턴을 사용하는 경우다\
예를 들어 sum을 게산하는 함수가 있다고 하자. 이 함수는 2개의 인자를 받아서 각각의 값을 더한 결과값을 리턴한다. 그런데 인자가 한개로 들어오는 경우가 있을 수 있다. 이런 함수가 호출될 때 인자가 1개인 함수가 정의되어 있지 않다면 에러를 출력할 것이다. 그러나 엘릭서는 fault-tolerance를 지향하는 언어이므로 에러가 나서 뻗는 상황은 가급적 피하고 싶다. 따라서 1개의 인자를 가지는 sum함수를 정의하고 함수 내부에서 인자가 2개인 함수를 호출하는 방식으로 작성할 수 있다. 에를들어 아래와 같다
```dotnetcli
def sum(a) do
    sum(a, 0)
end
```
위의 함수는 1개의 인자를 받지만 내부에서 `sum(a,0)`를 다시 호출한다. 입력되지 않은 나머지 인자를 0으로 처리하고 원래 의도한 대로 2개 인자를 가지는 sum함수를 호출한 것이다. 이렇게 작성했을 경우 `sum(1)`처럼 1개의 인자로만 호출해도 에러를 던지지 않는다\
\
private function\
객체지향 언어와 비슷한 방식으로 엘릭서도 함수의 접근 권한을 설정할 수 있다.\
def키워드 대신 `defp` 키워드로 작성된 함수는 private속성을 가진다. 이 속성이 붙으면 모듈 외부에서 호출이 불가능하다\
\
모듈에서 다른 모듈 임포트하기\
다른 언어들과 마찬가지로 엘릭서도 모듈 내에서 다른 모듈을 임포트할 수 있다. 이는 자바스크립트로 치면 `require`나 `import` 구문에 해당한다\
문법은 간단하다. defmodule로 정의한 모듈 내부에서 `import 모듈이름` 과 같은 문법으로 불러올 수 있다. 불러온 모듈은 네임스페이스가 벗겨지므로 앞에 모듈의 이름을 써가면서 호출할 필요가 없다. 가령 `IO.puts`함수를 호출할 때는 `puts`만으로도 호출할 수 있다. 자바스크립트의 그것과 똑같다\
\
모듈의 어트리뷰트 (Module attributes)\
# 이 챕터는 작성중입니다

### 2.4 Understanding the type system 30
### 2.5 Operators 55
### 2.6 Macros 56
### 2.7 Understanding the runtime 57
## 3 Control flow 63
### 3.1 Pattern matching 64
### 3.2 Matching with functions 72
### 3.3 Conditionals 79
### 3.4 Loops and iterations 86
## 4 Data abstractions 102
### 4.1 Abstracting with modules 104
### 4.2 Working with hierarchical data 114
### 4.3 Polymorphism with protocols 124
## 5 Concurrency primitives 129
### 5.1 Concurrency in BEAM 130
### 5.2 Working with processes 132
### 5.3 Stateful server processes 139
### 5.4 Runtime considerations 153
## 6 Generic server processes 159
### 6.1 Building a generic server process 160
### 6.2 Using GenServer 166
## 7 Building a concurrent system 179
### 7.1 Working with the mix project 180
### 7.2 Managing multiple to-do lists 182
## 7.3 Persisting data 189
### 7.4 Reasoning with processes 199
## 8 Fault-tolerance basics 201
### 8.1 Runtime errors 202
### 8.2 Errors in concurrent systems 207
### 8.3 Supervisors 211
## 9 Isolating error effects 224
### 9.1 Supervision trees 225
### 9.2 Starting processes dynamically 241
### 9.3 “Let it crash” 246
## 10 Beyond GenServer 251
### 10.1 Tasks 252
### 10.2 Agents 256
### 10.3 ETS tables 263
## 11 Working with components 277
### 11.1 OTP applications 278
### 11.2 Working with dependencies 286
### 11.3 Building a web server 291
### 11.4 Configuring applications 300
## 12 Building a distributed system 305
### 12.1 Distribution primitives 307
### 12.2 Building a fault-tolerant cluster 317
### 12.3 Network considerations 330
## 13 Running the system 334
### 13.1 Running a system with Elixir tools 335
### 13.2 OTP releases 339
### 13.3 Analyzing system behavior 346