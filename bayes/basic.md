# Bayes 이론

## 확률

* 조건부 확률
  * 조건 B 에 대해서 A가 참일 확률, p(A|B) 로 표현

* 결합 확률
  * 두가지에 대한 조건 A,B가 참이라고 말하는 방법, p(A and B)로 표현
  * A와 B가 독립적일 경우 p(A and B)=p(A)p(B)
    * p(B|A)=p(B), 조건 A 가 B 의 확률에 영향을 주지 않네.
  * A와 B가 독립적이지 않을 경우
    * p(B|A) > p(B)
  * 일반적으로는 p(A and B) = p(A)p(B|A)

## 쿠키 문제

* 두 그릇에 쿠키가 있다.
* 그릇1 에는 바닐라 쿠키 30개, 초코 쿠키 10개
* 그릇2 에는 바닐라 쿠키 20개, 초코 쿠키 20개
* *어떤 그릇인지 보지 않고 임의로 집은 쿠키가 바닐라 쿠키였다면, 이 쿠키가 그릇1에서 나왔을 확률은 얼마인가?*
* 그릇1에서 바닐라 쿠키가 나왔을 확률 (3/4) 는 구하기 쉽지만, 역으로 구하는 조건부 확률... 이 때 베이즈 이론 사용 (다음항에 정리)
* 풀이
```
A 확률이 그릇1에서 나온 확률, B 확률을 바닐라 쿠키를 집을 확률 이라고 하면
p(A) = 1/2
p(B) = 50/80 = 5/8
p(B|A) = 30/40 = 3/4
p(A|B) = ((1/2)*(3/4)) / (5/8) = 3/5
```

## 베이즈 이론

결합 확률과 조건부 확률을 활용

* p(A and B) = p(B and A)
* p(A and B) = p(A)p(B|A)
* p(B and A) = p(B)p(A|B)
* p(B)p(A|B) = p(A)p(B|A)
* p(A|B) = p(A)p(B|A) / p(B)


## 통시적 해석

* **데이터 D** 의 관점에서 봤을 때 **가설 H** 의 확률을 수정해준다 -> 통시적 (diachronic)
```
p(H|D) = p(H)p(D|H)/p(D)
```
* p(H) 는 데이터를 보기 전의 가설의 확률 **사전 확률**
* p(H|D) 는 데이터를 확인한 이후의 가설의 확률 **사후 확률**
* p(D|H) 는 데이터가 가설에 포함될 확률 **우도**
* p(D) 는 어떤 가설에든 포함되는 데이터의 비율 **한정 상수**

## 참고자료

* http://databaser.net/moniwiki/wiki.php/%EB%B2%A0%EC%9D%B4%EC%A6%88%EC%A0%95%EB%A6%AC