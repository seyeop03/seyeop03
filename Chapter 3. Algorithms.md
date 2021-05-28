# Chapter 3. Algorithms





## 💡 INDEX

- __알고리즘__
  * 알고리즘 예시
  * 알고리즘 패러다임
- __Growth of Functions__
  * Big-O and other Notation
- __알고리즘 복잡도__                                          







### 알고리즘

#### 	💬 정의 : 알고리즘은 문제해결을 위해 정해진 일련의 절차이다.

* 컴퓨터 프로그래밍의 토대이다.
* 일반적으로, 알고리즘은 어떤 종류의 일을 수행하기 위한 __<span style="color:blue">명확한 프로세스</span>__를 의미한다.
* 컴퓨터 프로그램이란 단순히 컴퓨터가 이해할 수 있게끔 충분히 정밀하게 고안된 언어로 작성한 `알고리즘의 명세`이다.
* 프로그램은 그것의 알고리즘을 함축한다.



### 프로그래밍 언어

* 익히 알려진 프로그래밍 언어들:
  * 최신언어 : Java, C, C++, Visual Basic, JavaScript, Perl, Tcl, Pascal
  * 구식언어 : Fortran, Cobol, Lisp, Basic
  * low-level 언어 : Assembly language
* 이 챕터에서는 pseudo-code 로 표현함



### 알고리즘 예시

* Task : {a_i}=a_1, ⋯ , a_n (단, a_i ∈ N) 이 주어졌을 때, 주어진 sequence에서 가장 큰 수는?
* 알고리즘
  1. 임시 변수 v를 a_1의 값으로 설정한다.
  2. sequence 내의 다음 요소 a_2를 참조한다.
  3. 만약 a_2 > v 라면, 임시 변수 v를 a_2의 값으로 재할당한다.
  4. 다음요소를 봤을 때, sequence에 더 이상 요소가 없을 때까지 2/3단계를 반복한다.
  5. v를 리턴한다.



### 알고리즘 실행

* SW를 시작할 때, 우리는 __<span style="color:red">프로그램 or 알고리즘</span>__을 __<span style="color:red">실행한다(or 돌린다)</span>__ 라고 말한다.
* 알고리즘이 있으면, 이를 종이에 써가면서 이를 수행할 수도 있다.



> 2차 세계대전 이전에, 컴퓨터는 알고리즘을 수행하는 사람을 의미했다..!



### 알고리즘의 특성

* 알고리즘의 중요한 특성 7가지 :
  * 입력 : 들어가는 정보 혹은 데이터
  * 출력 : 나오는 정보 혹은 데이터
  * 명확함 : 각 단계는 __명확하게 정의 __되어야 한다.
  * 정확성 :  <u>입력 값의 각 집합</u>에 대해 __정확한 출력 값__ 을 만들어야 한다.
  * 유한성 : 영원히 실행되면 안된다. (반드시 끝나야 한다.)
  * 효율성 : <u>각</u> 단계는 유한한 시간내에 수행되야 한다.
  * 일반성 : 특정한 입력이 아닌 모든 가능한 입력에 대해서 동작해야 한다.



### Pseudo-code Language (의사코드 언어)

> 아래의 코드는 기본적인 의사코드 선언문을 정리한 것이다.

```  pseudocode
procedure	
	name(argument: type)
variable := expression 
informal statement
begin statements end
{comment}
if condition then
	statement [else
	statement]
for variable := initial value
	to final value
		statement
while condition statement
procname(arguments)
	Not defined in book:
return expression
```

#### procedure procname(arg: type)

* 다음의 문장들을 선언

  * procedure(함수): procname로 명명된 procedure(함수)
  * arg: arg로 명명된 arguments(인자)
  * type : 자료형

* 예시:

  * procedure maximum(L: list of integers)

    ​	[statements defining maximum... ]

#### variable := expression

* <u>할당문</u>은 <span style="color:red">표현식(expression)</span>을 계산한다. 그런 다음, <span style="color:red">변수(variable)</span>에 결과값을 재할당한다.
  - ex)    v := 3x+7 ( 만약 변수 x의 값이 2라면, 변수 v를 13으로 바꿈.)
* 의사코드에서 <u>표현식</u>은 비형식적일 수도 있다:
  - x := 배열 L에서 가장 큰 정수

#### informal statement

* "x를 찾는 알고리즘을 기술하라"고 했는데, "find x"라고 하는 것은 충분하지 않다..!
  - 알고리즘을 세부적인 단계로 기술해야 한다!!
* 궁극적으로는 알고리즘을 쓰고 이를 구현해야 한다.
* 가끔 "swap x and y." 처럼 그 의미가 명확하고 정밀하다면, 이러한 비형식적 선언을 쓸 수도 있다.

#### begin statements end

아래처럼 선언문들을 묶는 역할을 한다.

``` pseudocode
begin
	statement 1
	statement 2
	⋯
	statement n
end
```

#### { comment }

- 아무런 동작도 하지 않는다.
- 인간이 코드를 읽는데 도움이 되도록 설명해주는 것으로, `자연어`이다.
- 어떤 프로그래밍 언어에서는 `remark` 라고도 불린다

#### If condition then statement

- 명제적인 표현식으로 나타난 __조건(condition)__ 을 검사한다.
- 만약 조건이 참이라면, __선언문(statement)__ 을 실행하고, 그렇지 않다면 그냥 스킵하고 다음 선언문으로 넘어간다.
- ex)    if 조건 then 선언문1 else 선언문2  에서 조건이 거짓이면, 선언문1을 스킵하고 선언문2로 넘어간다.

