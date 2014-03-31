---
layout: post
title: "Rails-TDD : rspec matcher 이해하기"
date: 2014-03-28 13:56:50 +0900
comments: true
categories: 
---

현재 **Ruby on Rails, Korea 페이스북 그룹**에서 **[홈페이지 리뉴얼 프로젝트(오픈 소스)](https://www.facebook.com/groups/rorlabrenewal/)**를 진행 중에 있습니다.

오픈 소스 프로젝트인 만큼 TDD를 베이스로 작업을 하고 있고, Rspec을 활용하고 있습니다.

그 전에 Rspec에 대한 학습이 좀 필요한데요. Rspec의 matcher 부분을 확인해두면 기본적인 Spec을 활용할 수 있습니다.

[발표 자료](https://docs.google.com/presentation/d/1W-qIfc8Rb7MlCNLb7PwceZeeuQGxvmSurMuqAuhzQwM)

[샘플 예제 소스](https://github.com/plaredspear/ror_tdd_example)

*****

###1. Rspec Expectation 기본 구조

(* matcher는 Rspec Expectation의 모듈)

> expect(actual).to matcher(expected)

expect(actual) : actual이 실제 테스트할 값 또는 블록, expect 메소드를 통해 처리하게 됨.

matcher(expected) : expected가 예상하는 값 또는 블록, matcher 메소드가 actual값과 expected값을 비교.


###2. 기본 matchers(Built in matchers)

matcher     | summary |
:-----------:|:-----------|
"Be"  | 대상 object의 true, false
Be_within | 부동소수점(floating point)의 오차 허용 범위 판단
Equality | 두 object를 같은지 비교(reference, value, value with type casting)
Exist | exist? 또는 exists? 메소드가 존재하는 object의 경우 활용. (* predicate matcher와 동일한 역할을 하지만, 어휘적인 표현 때문에 예외시킨 것으로 보임)
Expect | from, to를 활용하여 object의 상태변화를 판단함.
Raise_error | error를 raise하는 경우에 대한 matcher.(* 발생 유무부터 메시지가 정확한지등)
Have(n).items | collection의 size를 판단.
Include | object가 actual을 가지는지에 대한 판단.
Match | 정규표현식
Operator | be matcher와 함께 사용하여 연산 결과를 판단.
Predicate | truthy한 결과를 나타내는 메소드를 'be_' 접두어를 붙여서 matcher로 활용.
Respond_to | 메소드의 존재 유무를 판단.
Satisfy | 특정 조건을 만족하는지를 판단.
Throw_symbol | catch-throw 구문 활용시 판단.
Specify types of objects | 클래스 혹은 instance 종류를 판단.
Yield | (* 파악하지 못하였습니다. 추후 업데이트 예정입니다.)
Cover | Range를 가지는 구문에서 expected 값을 포함하는지 판단.
End | expected 값으로 끝나는지 판단.
Start | expected 값으로 시작하는지 판단.

