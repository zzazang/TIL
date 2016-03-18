# First Class Function?

https://en.wikipedia.org/wiki/First-class_function
http://rapapa.net/?p=2890
http://bestalign.github.io/2015/10/18/first-class-object/
http://javacan.tistory.com/entry/definition-of-first-class

In computer science, a programming language is said to have first-class functions if it treats functions as first-class citizens. Specifically, this means the language supports passing functions as arguments to other functions, returning them as the values from other functions, and assigning them to variables or storing them in data structures.[1] Some programming language theorists require support for anonymous functions(function literals) as well.[2] In languages with first-class functions, the names of functions do not have any special status; they are treated like ordinary variables with a function type.[3] The term was coined by Christopher Strachey in the context of “functions as first-class citizens” in the mid-1960s.[4]

정의를 풀면,

컴퓨터학에서 프로그래밍 언어가 first-class function을 가진다는 말은 function들을 최고 계층 시민(first-class citizen)으로 간주하는 경우를 말한다. 특별히, 언어가 function을 다른 function의 파라미터로 전달할 수 있거나, function의 리턴 값으로 사용할 수 있다거나, 변수에 저장되고, 구조체에 저장될 수 있는 것을 지원하는 경우를 말한다. 몇몇 프로그래밍 언어학자들은 Anonymous Function의 지원까지도 포함되어야 한다고 이야기한다. First-class functions을 지원하는 언어에서는 function의 이름이 특별한 상태를 가지는 것이 아니다. 그냥 함수 타입을 가지는 일반적인 변수일 뿐이다. first-class function이라는 용어는 1960대 중반 “functions as first-class citizens”이라는 문맥에서 Christopher Strachey가 처음 사용했다.


* Programming 언어가 First Class Function의 특성을 가지는 언어라고 하면 Function이 다음의 특성을 가지는 언어를 말한다. 

  1. 변수에 저장 가능하다.
  2. 함수의 파라미터로 전달 가능하다.
  3. 함수의 리턴값으로 사용 가능하다.
  4. 데이터 구조체에 포함될 수 있다. 
  5. (ObjectType의 Instance 중 하나이다.)
  6. (실행 타임에 구성할 수 있다.)
  7. (Property를 가질 수 있다.)

* 1급 시민(first class citizen)의 정의

  Christopher Strachey는 1967년 수업에 사용한 노트1에서 다음과 같이 1급 시민(first class citizen)과 2급 시민(second class citizen)을 소개했다. 아주 정확하게 정의한 것은 아니지만 ALGOL의 실수(real number)와 프로시져(procedure)를 비교하면서 설명하였다.

  In ALGOL a real number may appear in an expression or be assigned to a variable, and either may appear as an actual parameter in a procedure call. A procedure, on the other hand, may only appear in another procedure call either as the operator (the most common case) or as one of the actual parameters. There are no other expressions involving procedures or whose results are procedures. Thus in a sense procedures in ALGOL are second class citizens—they always have to appear in person and can never be represented by a variable or expression (except in the case of a formal parameter), while we can write (in ALGOL still)

  일반적으로 1급 시민의 조건을 다음과 같이 정의한다.

  * 변수(variable)에 담을 수 있다
  * 인자(parameter)로 전달할 수 있다
  * 반환값(return value)으로 전달할 수 있다
  
  대부분의 프로그래밍 언어에서 숫자는 1급 시민의 조건을 충족한다. 숫자는 변수에 저장할 수 있고 인자나 반환값으로 전달할 수 있다.
  
