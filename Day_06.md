---

## DAY_06

---

### [Objectives_학습 목표]

- 함수의 기본 구조를 이해하고 직접 함수를 정의할 수 있음
- 다양한 인자 전달 방식을 목적에 맞게 활용할 수 있음
- 재귀 함수의 개념과 동작 원리를 이해하고 간단한 문제를 재귀적으로 해결할 수 있음
- 다양한 내장 함수(len, max, sum)을 활용할 수 있음
- 지역 / 전역 변수의 개념과 변수의 유효 범위(Scope)를 설명할 수 있음
- 함수 이름 규칙과 단일 책임 원칙을 준수하여 가독성 좋은 함수를 작성할 수 있음
- 패킹  / 언패킹을 통해 가변 인자를 다룰 수 있음

---

### [Build_이론]

### 함수(Function)

: 특정 작업을 수행하기 위한 **재사용 가능한 코드 묶음**

: **재사용성**이 높아지고, 코드의 **가독성과 유지보수성** 향상

![image.png](attachment:a220e3d1-e8fa-49af-8858-a825eff90bc8:image.png)

→ 함수 호출(function call): 함수를 실행하기 위해 함수의 이름을 사용하여 해당 함수의 코드 블록을 실행하는 것

### 함수 구조

![image.png](attachment:60918910-7b32-4711-b487-f5b07d13ba5d:image.png)

- 함수 정의

: 함수 정의는 def 키워드로 시작

: def 키워드 이후 함수 이름 작성

: 괄호 안에 매개변수를 정의할 수 있음 → 매개변수(parameter)는 함수에 전달되는 값

- 함수 body

: 콜론(:) 다음에 들여쓰기 된 코드 블록

: 함수가 실행될 때 수행되는 코드를 정의

![image.png](attachment:70302834-0b4a-4cb1-8921-4bbd1e02515e:image.png)

- Docstring → 선택 사항

: 함수 body 앞에 선택적으로 작성 가능한 함수 설명서

![image.png](attachment:55e82670-6fa2-4d06-8cbc-afce947b925f:image.png)

- 함수 반환 값

: 함수는 필요한 경우 결과를 반환할 수 있음

: return 키워드 이후에 반환할 값을 명시

: return문은 함수 실행을 종료하고 결과를 호출 부분으로 반환

: 함수 내에서 return문이 없다면 None이 반환

![image.png](attachment:1ecc1bc5-fb22-418e-9e1a-15feb5c3ee07:image.png)

- 함수 호출

: 함수를 사용하기 위해서는 호출이 필요

: 함수의 이름과 소괄호를 활용해 호출

: 필요한 경우 인자(argument)를 전달해야 함

: 호출 부분에서 전달된 인자는 함수 정의 시 작성한 매개변수에 대입됨

![image.png](attachment:c99e893d-b1fb-4a5f-85cd-5976f1151ad3:image.png)

**함수와 반환 값**

⇒ print() 함수는 반환 값이 없음

: print() 함수는 화면에 값을 출력하기만 할 뿐, 반환(return)값이 없음

: 파이썬에서 반환 값이 없는 함수는 기본적으로 None을 반환한다고 간주되기 때문

→ 출력을 담당하는 함수는 결과를 ‘반환(return)’하지 않으므로, 내부적으로 아무 값도 반환하지 않는 함수와 마찬가지로 None이 나옴

![image.png](attachment:014a5736-3310-4240-8f34-1f9f5932f71a:image.png)

### 매개변수와 인자

- 매개변수(parameter) : 함수를 **정의**할 때 **함수가 받을 값**을 나타내는 변수
- 인자(argument) : 함수를 **호출**할 때 **실제로 전달되는 값**

![image.png](attachment:7b1c0707-658b-4d79-8f53-b936b54a8e12:image.png)

**인자의 종류**

1. Positional Arguments(위치 인자)

: 함수 호출 시 인자의 위치에 따라 전달되는 인자

: 위치 인자는 함수 호출 시 반드시 값을 전달해야 함

![image.png](attachment:ed033ab8-0dc4-4eb0-947a-2fd6523ab4d7:image.png)

1. Default Argument Values(기본 인자 값)

: 함수 정의에서 매개변수에 기본 값을 할당하는 것

: 함수 호출 시 인자를 전달하지 않으면 기본값이 매개 변수에 할당됨

![image.png](attachment:661750ec-2968-4253-970f-1995535b86e7:image.png)

1. Keyword Arguments(키워드 인자)

: 함수 호출 시 인자의 이름과 함께 값을 전달하는 인자

: 매개변수와 인자를 일치시키지 않고, 특정 매개변수에 값을 할당할 수 있음

: 인자의 순서는 중요하지 않으며 인자의 이름을 명시하여 전달

: **단, 호출 시 키워드 인자는 위치 인자 뒤에 위치해야 함**

![image.png](attachment:c370b626-661d-45b2-aa82-6315697d50ea:image.png)

1. Arbitrary Argument Lists(임의의 인자 목록)

: 정해지지 않은 개수의 인자를 처리하는 인자

: 함수 정의 시 매개변수 앞에 **’*’**를 붙여 사용

: 여러 개의 인자를 tuple로 처리(순서O, 불변)

![image.png](attachment:6e54930c-d048-45a7-9cb7-a161d99b9c56:image.png)

1. Arbitrary Keyword Argument Lists(임의의 키워드 인자 목록)

: 정해지지 않은 개수의 키워드 인자를 처리하는 인자

: 함수 정의 시 매개변수 앞에 ‘**’를 붙여 사용

: 여러 개의 인자를 dictionary로 묶어 처리(순서,중복 X)

![image.png](attachment:e53b36f1-b9b6-4dca-9b28-692004bc2159:image.png)

**함수 인자 권장 작성 순서**

: 위치 → 기본 → 가변 → 가변 키워드

: 호출 시 인자를 전달하는 과정에서 혼란을 줄일 수 있도록 함

: **단, 모든 상황에 적용되는 절대적인 규칙은 아니며 상황에 따라 유연하게 조정될 수 있음**

![image.png](attachment:756dc2c5-a9d0-43b4-8071-9955a02ee3ec:image.png)

![image.png](attachment:7e9b46af-35af-4fa2-9500-b5d2a8102c36:image.png)

⇒ 인자 자체에서 타입 강제 불가

---

### 재귀 함수

: 함수 내부에서 자기 자신을 호출하는 함수

**팩토리얼(!)**

: factorial 함수는 자기 자신을 재귀적으로 호출하여 입력된 숫자 n의 팩토리얼을 계산

: 재귀 호출은 n이 0이 될 때까지 반복되며, 종료 조건을 설정하여 재귀 호출이 멈추도록 함

: 재귀 호출의 결과를 이용하여 문제를 작은 단위의 문제로 분할하고 분할된 문제의 결과를 조합하여 최종 결과를 도출

![image.png](attachment:8042a2f8-4e3b-48c8-8917-41f710146143:image.png)

![image.png](attachment:59c0dfeb-d076-4ffd-9c2e-fe5ad695ea97:image.png)

![image.png](attachment:15a39f1b-4066-4f5c-b14b-6709eb2024dc:image.png)

: 특정 알고리즘 식을 표현할 때 변수의 사용이 줄어들며 코드의 가독성이 높아짐

: 1개 이상의 base case(종료되는 상황)가 존재하고, 수렴하도록 작성

→ 종료 조건을 명확히 할 것

→ 반복되는 호출이 종료 조건을 향하도록 할 것

- 재귀 함수는 메모리 사용량이 많고 느릴 수 있음
- 종료 조건이 잘못되면 스택 오버플로우 에러가 발생할 수 있음
- 복잡한 재귀 함수는 오히려 코드의 가독성을 저하시킬 수 있음

**재귀 함수를 사용하는 이유**

- 문제의 자연스러운 표현

: 복잡한 문제를 간결하고 직관적으로 표현 가능

- 코드 간결성

: 상황에 따라 반복문보다 알고리즘 코드가 더 간결하고 명확해질 수 있음

- 수학적 문제 해결

: 수학적 정의가 재귀적으로 표현되는 경우 직접적인 구현 가능

---

### 내장 함수(Built-in function)

: 파이썬이 기본적으로 제공하는 함수 → 별도의 import 없이 바로 사용 가능

: 내장 함수는 편리하지만, 이름이 같아도 다른 언어에서는 다르게 동작할 수 있기에 주의해야 함

: 단순히 함수를 사용하는 것에 그치지 않고, **내부 동작 원리**를 이해하면 문제 해결에 더 효과적으로 활용하고 성능 저하 같은 잠재적 문제를 피할 수 있음

![자주 사용되는 내장 함수 예시](attachment:424fc7e6-4dcc-4a4c-be51-97b74166ec65:image.png)

자주 사용되는 내장 함수 예시

![python docs 참고에서 문서들](attachment:e2b81223-28bc-4488-82f7-c608aeb19876:image.png)

python docs 참고에서 문서들

![image.png](attachment:8eb1cd32-e955-498d-bef8-42f4d5dbc8a0:image.png)

---

### 함수와 Scope

: 함수는 코드 내부에 **local scope**를 생성하며, 그 외의 공간인 **global scope**로 구분

**범위와 변수 관계**

- scope
    - global scope : 코드 어디에서든 참조할 수 있는 공간
    - local scope : 함수가 만든 scope(함수 내부에서만 참조 가능)
- variable
    - global variable : global scope에 정의된 변수
    - local variable : local scope에 정의된 변수

![num은 **local scope**에 존재하기 때문에 **global scope**에서 사용할 수 없음](attachment:4b06a25e-cad0-4cdb-9ff5-1887497b889c:image.png)

num은 **local scope**에 존재하기 때문에 **global scope**에서 사용할 수 없음

→ 변수의 **수명주기**와 연관이 있음

**변수 수명주기(lifecycle)**

: 변수의 수명주기는 변수가 선언되는 위치와 scope에 따라 결정됨

1. built-in scope
    
    : 파이썬이 실행된 이후부터 영원히 유지
    
2. global scope
    
    : 모듈이 호출된 시점 이후 혹은 인터프리터가 끝날 때까지 유지
    
3. local scope
    
    : 함수가 호출될 때 생성되고, 함수가 종료될 때까지 유지
    

**이름 검색 규칙(Name Resolution)**

: 파이썬에서 사용되는 이름(식별자)들은 특정한 이름공간(namespace)에 저장되어 있음

- LEGB Rule
    - Local scope: 지역 범위(현재 작업 중인 범위)
    - Enclosed scope: 지역 범위 한 단계 위 범위
    - Global scope: 최상단에 위치한 범위
    - Built-in scope: 모든 것을 담고 있는 범위(정의하지 않고 사용할 수 있는 모든 것)

![image.png](attachment:aaeb38b7-9f61-48a1-9683-00b51476d91f:image.png)

![image.png](attachment:9e089e86-cc3d-4996-bca5-bcf4e67ba519:image.png)

→ sum이라는 이름을 global scope에서 사용함으로써, 기존 built-in scope에 있던 내장함수 sum을 사용하지 못하게 됨

⇒ sum을 참조 시 LEGB Rule에 따라 global에서 먼저 찾기 때문

![image.png](attachment:8580d2db-b59f-4757-b529-7a8c4f3e33b6:image.png)

---

### global 키워드

: 변수의 스코프를 전역 범위로 지정하기 위해 사용

: 일반적으로 함수 내에서 전역 변수를 수정하려는 경우 사용

![image.png](attachment:7ac6027f-e3e1-4e15-a466-aa213c116550:image.png)

- global 키워드 선언 전에 참조 불가

![image.png](attachment:98582593-c187-499f-8fbb-ed39b544a2ca:image.png)

- 매개변수에는 global 키워드 사용 불가

![image.png](attachment:e30765bf-f406-49b9-8e5b-63fba529dea3:image.png)

---

### 함수 스타일 가이드

**함수 이름 작성 규칙**

: 소문자와 언더스코어(_) 사용

: 동사로 시작하여 함수의 동작 설명

: 약어 사용 지양

![image.png](attachment:44773476-e58b-436f-9b66-eb8abc805da3:image.png)

**함수 이름 구성 요소**

- 동사 + 명사
    
    : save_user()
    
- 동사 + 형용사 + 명사
    
    : calculate_total_price()
    
- get / set 접두사
    
    : get_username(), set_username()
    

**단일 책임 원칙(Single Responsibility Principle)**

: 모든 객체는 하나의 명확한 목적과 책임만을 가져야 함

**함수 설계 원칙**

- 명확한 목적
    - 함수는 한 가지 작업만 수행
    - 함수 이름으로 목적을 명확히 표현
- 책임 분리
    - 데이터 검증, 처리, 저장 등을 별도 함수로 분리
    - 각 함수는 독립적으로 동작 가능하도록 설계
- 유지보수성
    - 작은 단위의 함수로 나누어 관리
    - 코드 수정 시 영향 범위를 최소

![잘못된 예시(여러 책임이 섞인 함수)](attachment:4a24271f-3e93-46f9-9b77-361cf7339015:image.png)

잘못된 예시(여러 책임이 섞인 함수)

![올바른 예시(책임을 분리한 함수들)](attachment:151d273b-35c6-4b0a-ab56-014ef7d4d7b7:image.png)

올바른 예시(책임을 분리한 함수들)

---

### Packing & Unpacking

**Packing(패킹)**

 : 여러 개의 데이터를 하나의 컬렉션으로 모아 담는 과정

- 여러 개의 값을 하나의 튜플로 묶는 파이썬의 기본 동작
- 한 변수에 콤마(,)로 구분된 값을 넣으면 자동으로 튜플로 처리

![image.png](attachment:5bba4a17-8f2a-477d-a611-c42af31272c3:image.png)

1. ‘*’을 활용한 패킹(함수 매개변수 작성 시)
    
    : 남는 위치 인자들을 튜플로 묶기
    
    : *를 붙인 매개변수가 남는 위치 인자들을 모두 모아 하나의 튜플로 만듦
    
    ![image.png](attachment:d393e1fa-cf65-4fa3-9da6-77da736766c6:image.png)
    
2. ‘**’을 활용한 패킹(함수 매개변수 작성 시)
    
    : 남는 키워드 인자들을 딕셔너리로 묶기
    
    : **를 붙인 매개변수가 남는 키워드 인자들을 모두 모아 하나의 딕셔너리로 만듦
    
    ![image.png](attachment:3e3a331a-ab54-42ee-a734-824c10ca7086:image.png)
    

**print 함수의 패킹 예시**

![image.png](attachment:43a7c35f-9887-4937-a3fc-c88737711526:image.png)

→ print 함수에서 임의의 가변 인자를 작성할 수 있었던 이유

⇒ 인자 개수에 상관 없이 튜플 하나로 패킹 되어서 내부에서 처리

**Unpacking(언패킹)**

: 컬렉션에 담겨있는 데이터들을 개별 요소로 펼쳐 놓는 과정

- 튜플이나 리스트 등의 객체의 요소들을 개별 변수에 할당
- ‘시퀀스 언패킹(Sequence Unpacking)’ 또는 ‘다중 할당(Multiple Assignment)’이라고 부름

![image.png](attachment:9b50e2e0-eb34-4c86-9297-771ed5fdc4b2:image.png)

1. ‘*’을 활용한 언패킹(함수 인자 전달)
    
    : 리스트나 튜플 앞에 *를 붙여 각 요소를 함수의 개별 위치 인자로 전달
    

![image.png](attachment:83140668-596b-40f8-9135-63781311675e:image.png)

1. ‘**’을 활용한 언패킹(딕셔너리 → 함수 키워드 인자)
    
    : 딕셔너리 앞에 **를 붙여 {키:값} 쌍을 키 = 값 형태의 키워드 인자로 전달
    
    ![image.png](attachment:16a4a378-48b2-4531-956a-6e2d14bc7d65:image.png)
    

**Packing & Unpacking 정리**

![image.png](attachment:bf01b442-7c75-44bc-8e50-c537d0689db2:image.png)

---

### 참고

**함수의 return, 반환의 원칙**

: 파이썬 함수는 언제나 단 하나의 값(객체)만 반환할 수 있음

: 여러 값을 반환하는 경우에도 하나의 튜플로 패킹하여 반환

![image.png](attachment:472cc79b-fb02-43e1-aab9-86d05f48662e:image.png)

**파이썬 함수의 반환 핵심**

: 파이썬 함수는 오직 **하나의 값(객체)**만 return할 수 있음

: return a, b, c 처럼 콤마를 사용하면 파이썬이 값들을 하나의 튜플로 자동 패킹하여 반환

: 반환된 튜플은 각 변수에 언패킹하여 사용할 수 있음

**람다 표현식(Lambda expressions)**

: 익명 함수를 만드는 데 사용되는 표현식

: 한 줄로 간단한 함수를 정의

- lambda 키워드
    
    : 람다 함수를 선언하기 위해 사용되는 키워드
    
- 매개 변수
    
    : 함수에 전달되는 매개변수들
    
    : 여러 개의 매개변수가 있을 경우 쉼표로 구분
    
- 표현식
    
    : 함수의 실행되는 코드 블록으로 결과값을 반환하는 표현식으로 작성
    

![image.png](attachment:dbfa41d4-5784-44f0-a442-24ce7737145f:image.png)

: 간단한 연산이나 함수를 한 줄로 표현할 때 사용

: 함수를 매개변수로 전달하는 경우에도 유용하게 활용

![image.png](attachment:adb1cdff-10e4-4d18-a0d4-520ab090ad01:image.png)

---

### [Review_ 활동 정리]

- 함수(Function)
    
    : 재사용 가능한 코드 묶음
    
    ex) def add(a, b):
    
- 매개변수(Parameter)
    
    : 함수 정의 시 전달받는 변수
    
    ex) def add(x, y):의 x와 y
    
- 인자(Argument)
    
    : 함수 호출 시 전달하는 값
    
    ex) add(a, b)의 a와 b
    
- 재귀 함수(Recursive)
    
    : 자기 자신을 호출하는 함수
    
    ex) factorial(n-1)
    
- 스코프(Scope)
    
    : 변수가 유효한 범위
    
    ex) global num
    
- LEGB 규칙
    
    : 이름 공간 탐색 순서 규칙
    
- 패킹(Packing)
    
    : 여러 값을 하나로 묶는 것
    
    ex) *args
    
- 언패킹(Unpacking)
    
    : 묶음을 여러 값으로 푸는 것
    
    ex) a, b = my_tuple
    
- 람다 표현식(Lambda)
    
    : 한 줄로 만드는 익명 함수
    
    ex) lambda x : x**2
    

**함수(Fucntion)란?**

: 특정 작업을 수행하는 재사용 가능한 코드 묶음

: 반복되는 코드를 줄여주고, 코드 관리를 쉽게 만들어 줌

**함수 구조와 실행 흐름**

: def 키워드로 함수를 만들고 이름() 형식으로 호출하여 사용

: 함수를 정의할 때 받는 변수 → 매개변수 / 호출할 때 전달하는 실제 값 → 인자

: 반환(return) → 함수의 실행을 종료하고 결과를 돌려주는 것

**다양한 인자(Argument) 활용법**

: 위치 인자 → 순서에 맞춰 값을 전달

: 키워드 인자 → 순서와 상관없이 이름으로 값을 전달

: 기본 인자 값 → 인자를 전달하지 않을 때 사용될 기본값 설정

: 가변 인자 *args, **kwargs → 정해지지 않은 개수의 인자를 튜플(*)이나 딕셔너리(**)로 받음

**재귀함수**

: 함수가 자기 자신을 다시 호출하는 방식

: 반드시 종료 조건(base case)이 필요

**내장 함수**

: 파이썬이 기본으로 제공하는 함수

: 별도의 import 과정 없이 바로 사용 가능

: 내부 동작 원리를 이해하는 것이 중요

**변수의 유효 범위(Scope)**

: scope → 변수의 유효 공간, 함수 안(Local)과 밖(Global)으로 나뉨

: LEGB 규칙 → 파이썬은 변수를 찾을 때 Local → Enclosed → Global → Built-in 순서로 탐색

: global 키워드 → 함수 안에서 바깥의 전역 변수 값을 수정하고 싶을 때 사용

**함수 설계 원칙**

: 함수는 오직 한 가지 일만 해야함

: 기능별로 함수를 분리하면 유지보수성이 높아짐

**패킹(Packing)과 언패킹(Unpacking)**

: 패킹 → 여러 값을 하나로 묶기

: 언패킹 → 묶음을 여러 값으로 풀기