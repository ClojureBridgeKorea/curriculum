---
layout: default
title: Flow Control
permalink: /outline/flow_control.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/flow_control.html

{% endcomment %}

<section>
조건문
-------------------------
{: .slide-title .chapter}

* `if`
* `cond`
* 불 연산
</section>

<section ng-controller="NarrativeController">
### 조건문이란?
{: .slide_title .slide}

#### 어떻게 반응할지 결정하기 <button class="link" ng-bind-html="details" ng-model="block11" ng-click="block11=!block11"></button>

> "조건문"은 주어진 상황에서 어떻게 반응할지를 결정하는 프로그래밍 용어입니다. 우리는 항상 결정을 내립니다. *만약* 날씨가 좋다*면*  공원에 가자;*그렇지 않다면* 실내에서 보드게임을 하자. *만약* 연료가 다 떨어진다*면* 주유소에 가자;*그렇지 않다면* 계속 목적지를 향해 가자.
{: ng-show="block11" .description}

#### 반응하기 위해 조건 평가하기 <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> 소프트웨어 역시 이러한 결정들로 가득 차있습다. *만약* 사용자의 입력이 유효하다*면* 그 데이터를 저장해야 한다;*그렇지 않다면* 에러메세지를 보여준다. 여기에 공통된 패턴은 조건을 테스트하고 그 조건이 *참*인지 *거짓*인지에 기반하여 다른 반응을 보인다는 것입니다.
{: ng-show="block12" .description}
</section>

<section ng-controller="NarrativeController">
### `if`
{: .slide_title .slide}

<button class="link" ng-bind-html="details1" ng-model="block21"
ng-click="block21=!block21"></button>
<button class="link" ng-bind-html="details2" ng-model="block22" ng-click="block22=!block22"></button>

> 클로저에서 조건문을 쓸 때, 가장 기본적으로 `if`연산자를 사용합니다.
> 다음은 데이터의 유효성을 검증하는 코드의 예제입니다.
{: ng-show="block21" .description}

> 만약 `y`에 40을 더한 값이 여전히 150 미만이라면 `(+ y 40)을 반환하고 그렇지 않다면 -150을 반환하세요. (거북이 앱의 프레임에서 y축은 위로는 150, 아래로는 -150을 가집니다.) 
{: ng-show="block22" .description}

> 참조: [Conditional `if`](http://clojurebridge.github.io/community-docs/docs/clojure/if/)
{: ng-show="block22" .description}

```clojure
(if (< (+ y 40) 150)
  (+ y 40)
  -150))
```
</section>

<section ng-controller="NarrativeController">
#### `if` 연산자의 일반적인 형태

```clojure
(if conditional-expression
  expression-to-evaluate-when-true
  expression-to-evaluate-when-false)
```
</section>

<section ng-controller="NarrativeController">
#### `if` 예제

```clojure
(if (> 3 1)
  "3 is greater than 1"
  "3 is not greater than 1")
;=> "3 is greater than 1"

(if (> 1 3)
  "1 is greater than 3"
  "1 is not greater than 3")
  ;=> "1 is not greater than 3"
```
</section>

<section ng-controller="NarrativeController">
#### Truthiness <button class="link" ng-bind-html="details" ng-model="block51" ng-click="block51=!block51"></button>

> 조건문의 참거짓을 판단할 때, 클로저는 `nil`과 `false`를 거짓으로 생각하고 그밖의 모든 것을 참으로 판단합니다.
> 다음예제를 확인하세요:
{: ng-show="block51" .description}

> 참조: [Truthiness](http://clojurebridge.github.io/community-docs/docs/clojure/truthiness/)
{: ng-show="block51" .description}


```clojure
(if "anything other than nil or false is considered true"
  "A string is considered true"
  "A string is not considered true")
;=> "A string is considered true"

(if nil
  "nil is considered true"
  "nil is not considered true")
;=> "nil is not considered true"

(if (get {:a 1} :b)
  "expressions which evaluate to nil are considered true"
  "expressions which evaluate to nil are not considered true")
;=> "expressions which evaluate to nil are not considered true"
```
</section>

<section>
#### 연습문제 1: 프레임 안의 Y값
{: .slide_title .slide}

* y(세로좌표)를 인자로 가지는 `y-within-frame`함수를 만드세요.
* 슬라이드의 예제를 사용하세요.
* `y-within-frame`함수는 150을 넘지않는다면 y값을 반환해야 합니다.

    - 참고: [x와 y의 절대치](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md#x-and-y-in-absolute-values)

```clojure
;; if example
(if (< (+ y 40) 150)
  (+ y 40)
  -150))
```

```clojure
;; usage of y-within-frame function
(y-within-frame 80)    ;=> 120
(y-within-frame 180)   ;=> -150
```
</section>

<section ng-controller="NarrativeController">
### `cond`
{: .slide_title .slide}

<button class="link" ng-bind-html="details1" ng-model="block61" ng-click="block61=!block61"></button>
<button class="link" ng-bind-html="details2" ng-model="block62" ng-click="block62=!block62"></button>

> `if`연산자는 한개의 조건만을 가집니다.
> 다수의 조건을 사용하고 싶을 때, `if`는 좋은 선택이 아닙니다.
> 이 경우에는 아주 많이 중첩된 `if`문을 사용해야 합니다.
> 다수의 상황들을 묶기 위해서는 `cond` 연산자가 적합합니다.
{: ng-show="block61" .description}

> 예제를 봅시다. 만약 y에 40을 더한 값이 150을 초과할 경우 첫번째 형태를 계산하세요. 이 경우에는 -150을 반환합니다. 만약 y에 40을 더한 값이 -150 미만일 경우에는 두번째 형태를 계산하세요. 이 경우에는 150을 반환합니다. 만약 두 조건 모두 거짓일 경우, `:else`를 계산하세요. 이 경우에는 y에 40을 더한 값을 반환합니다. 만약 이 함수를 거북이 앱에서 사용할 경우 우리는 거북이를 프레임의 세로축내에서만 있도록 할 수 있습니다.

{: ng-show="block62" .description}

> 참조: [Conditional `cond`](http://clojurebridge.github.io/community-docs/docs/clojure/cond/)
{: ng-show="block62" .description}

```clojure
(cond
  (> (+ y 40) 150) -150
  (< (+ y 40) -150) 150
  :else (+ y 40)))
```
</section>

<section ng-controller="NarrativeController">
#### `cond` 연산자의 일반적인 형태

```clojure
(cond
  predicate1 expression-to-evaluate-when-predicate1-is-true
  predicate2 expression-to-evaluate-when-predicate2-is-true
  ...
  :else expression-to-evaluate-when-all-above-are-false)
```
</section>

<section>
#### 연습문제 2: 프레임안의 Y값 - part 2
{: .slide_title .slide}

> 앞의 excercise에서 작성한 `y-within-frame`함수에는 문제가 있습니다. 만약 주어진 y값이 -1000일경우 함수는 -960을 반환합니다. 프레임에서 가장 아래의 y값은 -150이므로 -960은 이를 넘습니다. 거북이는 보이지 않는 영역으로 가게 될 것입니다. 거북이를 실제 프레임 내에서만 있게하도록 `cond`를 사용해 봅시다.

* y(세로좌표)를 인자로 갖는 `y-witin-frame-cond`함수를 만드세요.
* 슬라이드의 `cond`예제를 사용하세요.
* 함수는 -150과 150사이의 값만을 반환해야 합니다.

	- 참고: [x와 y의 절대치](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md#x-and-y-in-absolute-values)

```clojure
;; usage of y-within-frame-cond function
(y-within-frame-cond 200)    ;=> -150
(y-within-frame-cond -200)   ;=> 150
(y-within-frame-cond 0)      ;=> 40
```
</section>

<section ng-controller="NarrativeController">
### `and`, `or`, `not`을 사용한 불연산
{: .slide_title .slide}

#### <button class="link" ng-model="block81" ng-click="block81=!block81">Intro</button>

> `if`는 오직 한가지만 평가할 수 있다는 한계가 있습니다. 불 연산을 사용한다면 여러개의 조건을 평가할 수 있습니다. __불 연산__은 조건들을 `and`,`or`,`not`을 이용하여 묶어서 값을 평가합니다. 
{: ng-show="block81" .description}

> 이전에 프로그래밍할 때 이 개념을 본 적이 없다면 이것이 당신이 평소에 사물을 바라보는 것과 같은 방식을 따른다는 것을 기억하세요. __and__는 모든게 참일때 참입니다. __or__는 하나--혹은 둘다--가 참일때 참입니다. __not__은 조건이 거짓일때 참입니다.
{: ng-show="block81" .description}
</section>

<section ng-controller="NarrativeController">
### 진리표 <button class="link" ng-bind-html="details" ng-model="block91" ng-click="block91=!block91"></button>

> `and`, `or`, `not`은 다른 함수들처럼 행동합니다.(정확히는 함수는 아니지만 함수처럼 행동합니다.) 그렇기 때문에 이것들은 앞서 산술연산에서 본  _prefic 표기법_을 따릅니다.
{: ng-show="block91" .description}

| x     | y     | (`and` x y) | (`or` x y) | (`not` x) | (`not` y) |
| ----- | ----- | --------- | -------- | ------- | ------- |
| false | false | false | false | true  | true  |
| true  | false | false | true  | false | true  |
| true  | true  | true  | true  | false | false |
| false | true  | false | true  | true  | false |

</section>

<section ng-controller="NarrativeController">
#### `and`, `or`, `not` 조합 <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> `and`, `or`, `not`은 조합해서 사용할 수 있으며 이 경우에는 읽기 어려울 수 있습니다.
> 다음 예제를 봅시다:
{: ng-show="block101" .description}

```clojure
(defn leap-year?
  "Every four years, except years divisible by 100, but yes for years divisible by 400."
  [year]
  (and (zero? (mod year 4))
       (or (zero? (mod year 400))
           (not (zero? (mod year 100))))))
```
</section>

<section ng-controller="NarrativeController">
#### [보너스] `cond`, `and`, `or`, `not` 조합 <button class="link" ng-bind-html="details" ng-model="block110" ng-click="block110=!block110"></button>

> 지금까지 `cond`,`and`,`or`,`not`을 배웠습니다. 이것들을 조합해서 만들 수 있는 함수는 무엇이 있을 지 생각해봅시다.
> 다음 예제를 봅시다.
{: ng-show="block110" .description}

```clojure
(defn true-or-false?
  "Given op, returns true or false"
  [op]
  (let [x true
        y false]
    (cond
      (= op :and) (and x y)
      :else false)))

(defn correct?
  "Given op and ans, returns message whether ans was corret or not"
  [op ans]
  (if (= ans (true-or-false? op))
      "You won"
      "You lost"))
```
</section>

<section>
#### 연습문제 3: [보너스] `true-or-false?` 함수 완성하기
{: .slide_title .slide}

> 앞 슬라이드에 나오는 `true-or-false?`함수는 `:and`만을 사용했습니다. 함수에 `:or`, `:not`연산자를 추가해 봅시다.

* `myproject`의 `core.clj`와 InstaREPL을 사용하세요.
* `cond`안에`(= op :or)`과 `(= op :not)`을 추가하세요.
* `:not`에는 인수에 대해 x와 y중 하나를 택하세요.

```clojure
;; usage of correct? function
(corret? :and false)   ;=> "You won"
(corret? :or false)    ;=> "You lost"
(corret? :not true)    ;=> "You won"  (this may be "You lost")
```
</section>

{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신[README.md](../README.md)로 가세요 :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드</a>로 돌아가거나 [curriculum outline](/curriculum/#/1)으로 가세요.
</section>
