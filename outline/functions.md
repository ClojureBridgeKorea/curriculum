---
layout: default
title: Functions
permalink: /outline/functions.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/functions.html

{% endcomment %}

<section>
함수
-------------------------------
{: .slide-title .chapter}

* 함수란?
* 함수명 정하기
* [보너스 섹션] 함수를 인자로 갖는 함수
    - `map`과 `reduce`
* [보너스 섹션] 익명 함수 Anonymous function
* [보너스 섹션] `let`으로 로컬 바인딩하기
</section>

<section ng-controller="NarrativeController">
### 함수란?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> `count`, `conj`, `first`,`rest` 같은 몇 가지 함수들을 살펴봤습니다.
> 마찬가지로, 우리가 사용한 모든 산술 연산도 함수입니다 : `+`, `-`, `*`, `/`
> 그렇다면 함수란 무엇일까요?
{: ng-show="block11" .description}

> *함수*란 독립적이고 개별적인 코드로, (*인자*라고 하는) 값을 받고 값을 반환합니다.
{: ng-show="block11" .description}

> 참고: [Basics of Function](http://clojurebridge.github.io/community-docs/docs/clojure/function-creation/)
{: ng-show="block11" .description}

* `count`, `conj`, `first`
* `+`, `-`, `*`, `/`
* 값을 받고 값을 반환하는 코드
</section>

<section ng-controller="NarrativeController">
#### 함수 예제 <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> * `defn`은 함수를 정의합니다.
> * `forward-right`은 이 함수의 *이름*입니다.
> * 다음 줄의 문자열은 함수의 기능을 설명합니다. 이는 선택사항입니다.
> * `[turtle]`은 *인자*의 리스트입니다. `turtle`이라는 한 개의 인자를 갖고 있습니다.
> * `(forward turtle 60) (right turtle 135)` 은 함수의 *바디*입니다. 함수를 사용할 때 실행되는 부분입니다.
{: ng-show="block21" .description}

```clojure
(defn forward-right
  "Moves specified turtle forward and tilts its head"
  [turtle]
  (forward turtle 60)
  (right turtle 135))
```
</section>

<section ng-controller="NarrativeController">
#### `forward-right` 함수 사용하는 법 <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> `forward-right`를 사용하기 위해선, 함수를 *호출*해야 합니다. 앞서 사용해본 함수들을 다뤘던 것처럼 말이죠.
{: ng-show="block31" .description}

```clojure
(forward-right :trinity)  ;=> {:trinity {:angle 135}}
(forward-right :neo) ;=> {:neo {:angle 135}}
```
</section>

<section ng-controller="NarrativeController">
#### 인자를 여러 개 갖는 함수 <button class="link" ng-bind-html="details" ng-model="block41" ng-click="block41=!block41"></button>

> 함수는 한 개 이상의 인자를 가질 수 있습니다.
> turtle과 길이를 인자로 갖는 `forward-right-with-len`함수를 만들어 보겠습니다.
{: ng-show="block41" .description}

```clojure
(defn forward-right-with-len
  "Given turtle and length, forward the turtle and tilts its head"
  [turtle len]
  (forward turtle len)
  (right turtle 135))

(forward-right-with-len :trinity 90) ;=> {:trinity {:angle 135}}
(forward-right-with-len :neo 80)  ;=> {:neo {:angle 135}}
```
</section>

<section>
#### 연습문제 1: 함수를 이용해 거북이 움직이기
{: .slide_title .slide}

1. 함수 작성하기
  * `walk.clj`로 이동합니다.
  * 편집기에서, 슬라이드에 있는 `forward-right` 함수를 작성합니다. (아래쪽)
  * (선택) `walk.clj`를 저장합니다.
  * `forward-right` 함수 전체를 선택하고 Eval Selection을 누릅니다.
2. 함수 사용하기
  * REPL 창 오른쪽에 `(forward-right :trinity)`를 입력합니다.
  * 위를 최소 8번 반복합니다.(위 화살표와 엔터를 사용하세요.)

```clojure
(defn forward-right
  "Moves specified turtle forward and tilts its head"
  [turtle]
  (forward turtle 60)
  (right turtle 135))
```
</section>

<section>
#### 연습문제 2: 인자를 가진 함수를 이용해 거북이 움직이기
{: .slide_title .slide}

* `walk.clj`로 이동합니다.
* 편집기에서, 3개의 인자를 갖는(turtle, len, and angle) `forward-right-with-len-ang` 함수를 작성합니다.(`forward-right-with-len`의 확장판)
* `forward-right-with-len-ang` 함수 전체를 선택하고 Reload Selection을 누릅니다.
* REPL 창에서, `(forward-right-with-len-ang :trinity 60 120)`를 씁니다.
* REPL에서 함수를 계산하면서 여러 번 반복합니다.

</section>


<section ng-controller="NarrativeController">
### 함수명 정하기
{: .slide_title .slide}

#### 이름은 심볼이다 <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> 함수명은 심볼입니다. 값에 이름을 할당할 때 `def`와 함께 사용했던 심볼들처럼 말이죠.
{: ng-show="block61" .description}

> 숫자가 아닌 문자로 시작해야합니다.
>  *, +, !, -, _, ?와 함께 영숫자 문자를 포함할 수 있습니다.
> 이러한 유연성은 우리가 사용하는 특정 관용구가 있기 때문에 함수에서 중요합니다.
{: ng-show="block61" .description}

#### 함수의 두 가지 유형 <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> 클로저는 두 가지 유형의 함수가 있습니다:
> 1. 값을 반환하는 함수,
> 2. 참거짓을 반환하는 함수.
> 두 번째 유형의 함수를 *조건자*라고 합니다.
{: ng-show="block62" .description}


##### 조건자 함수 예제 <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

> 클로저에서, `=`는 놀랍게도 조건자 함수입니다.
> 그 외에도, 다른 많은 컴퓨터 언어들처럼
> 클로저는 크기 비교를 위한 조건자 함수를 갖고 있습니다.
> 대부분의 조건자 함수는 `?`로 끝납니다.
{: ng-show="block63" .description}

> * `=`, `not=`
> * `>`, `<`, `>=`, `<=`
> * `true?`, `false?`, `empty?`, `nil?`, `vector?`, `map?`

</section>

<section ng-controller="NarrativeController">
#### [보너스 섹션]

### 함수를 인자로 갖는 함수
{: .slide_title .slide}

#### <button class="link" ng-model="block71" ng-click="block71=!block71">Intro</button>

> 컬렉션과 함께 사용할 수 있는 가장 강력한 함수들 중 몇몇은
> 다름 함수를 인자로 가질 수 있습니다.
> 클로저의 가장 마법같은 부분입니다. --다른 많은 프로그래밍 언어들도 그러하지만
> 복잡한 아이디어라 처음에 이해가 안 갈 수 있습니다.
> 예제를 보고 더 공부해봅시다.
{: ng-show="block71" .description}

> 참고: [Higher-order Function](http://clojurebridge.github.io/community-docs/docs/clojure/higher-order-function/)
{: ng-show="block71" .description}
</section>

<section ng-controller="NarrativeController">
#### `map` 함수

#### <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> `map`은 컬렉션과 함께 다른 함수를 인자로 취합니다.
> 컬렉션의 각 멤버에서 제공된 함수를 호출합니다.
> 그런 다음 해당 함수 호출의 결과와 함께 새로운 컬렉션을 반환합니다.
> 생소한 개념이지만, 일반적인 함수형 프로그래밍과 클로저의 핵심입니다.
{: ng-show="block101" .description}

```clojure
(map inc [1 2 3]) ;=> (2 3 4)
(map (partial + 90) [0 30 60 90]) ;=> (90 120 150 180)
```

> 참고:
> [partial](http://clojuredocs.org/clojure.core/partial)
</section>

<section ng-controller="NarrativeController">
#### `reduce` 함수

#### <button class="link" ng-bind-html="details" ng-model="block111" ng-click="block111=!block111"></button>

> 함수를 인자로 받는 또 다른 함수를 살펴봅시다.
> `reduce`함수가 있습니다. 컬렉션을 단일 값으로 변환할 때 사용합니다.
{: ng-show="block111" .description}

> `reduce`함수는 제공된 컬렉션의 처음 두 멤버를 받고 그 멤버들에게 제공된 함수를 호출합니다.
> 그 다음, 제공된 함수를 다시 한번 호출 합니다.--이번에는 다음 컬렉션 멤버와 함께 이전 함수 호출의 결과를 이용합니다.
> `reduce`함수는 이 과정을 컬렉션의 끝에 도달할 때 까지 반복하고 반복합니다.
{: ng-show="block111" .description}

```clojure
(reduce str (turtle-names)) ;=> ":trinity:neo:oracle:cypher"
(reduce + [30 60 90])       ;=> 180
```
</section>

<section>
#### 연습문제 3 [보너스]: 평균값 찾기
{: .slide_title .slide}

* 맵의 벡터를 받는 `average`라는 이름의 함수를 만듭니다.
* `[{:angle 30} {:angle 90} {:angle 50}]`를 입력으로 사용합니다.
* :angle의 평균값을 계산합니다.

* 힌트: `map`, `reduce`, `count`함수를 이용하세요.
</section>


<section ng-controller="NarrativeController">
#### [보너스 섹션]

### 익명 함수 Anonymous functions

#### 이름이 없는 함수 <button class="link" ng-bind-html="details" ng-model="block201" ng-click="block201=!block201"></button>

> 여태껏, 봐왔던 모든 함수들은 이름을 갖고 있었습니다. `+`, `str`, `reduce`처럼 말이죠.
> 하지만, 함수는 이름이 꼭 필요하지는 않습니다.
> 값이 이름을 가질 필요 없듯이요.
> 이렇게 이름이 없는 함수를 *익명 함수*라고 합니다.
> 익명 함수는 `fn`으로 생성됩니다. 이렇게 말이죠:
{: ng-show="block201" .description}

> 참고: [Anonymous Function](http://clojurebridge.github.io/community-docs/docs/clojure/anonymous-function/)
{: ng-show="block201" .description}


```clojure
(fn [s1 s2] (str s1 " " s2))
```

#### 익명 함수가 아닌 경우 <button class="link" ng-bind-html="details" ng-model="block202" ng-click="block202=!block202"></button>

> 진도 나가기 전에, 함수명은 _항상_ 자유롭게 지을 수 있다는 걸 이해해야합니다.
> 이름을 짓는 것엔 아무 문제가 없습니다.
> 하지만, 익명 함수로 이루어진 클로저 코드를 _앞으로_ 볼 것입니다.
> 때문에 익명 함수를 알고 있어야 합니다.
{: ng-show="block202" .description}

```clojure
(defn join-with-space
  [s1 s2]
  (str s1 " " s2))
```
</section>

<section ng-controller="NarrativeController">
#### 익명 함수 사용 예제 <button class="link" ng-bind-html="details" ng-model="block203" ng-click="block203=!block203"></button>

> 왜 익명 함수를 쓸까요?
> 익명 함수는 꽤나 유용합니다.
> 바로 함수 섹션에서 배운 `map`이나 `reduce`같은 함수들처럼 다른 함수를 인자로 갖는 함수를 가질 때 말입니다.
> 익명 함수의 사용 예제를 살펴봅시다.
{: ng-show="block203" .description}

```clojure
(map (fn [t] (forward t 45)) (turtle-names))
;=> ({:trinity {:length 45}} {:neo {:length 45}} {:oracle {:length
45}} {:cypher {:length 45}})

(reduce (fn [x y] (+ x y)) [1 2 3]) ;=> 6

(reduce (fn [a b] (str a ", " b)) (map name (turtle-names)))
;=> "trinity, neo, oracle, cypher"
```
</section>

<section ng-controller="NarrativeController">
#### [보너스 섹션]

### `let`으로 로컬 바인딩하기
{: .slide_title .slide}

#### <button class="link" ng-model="block301" ng-click="block301=!block301">Intro</button>

> 함수를 만들 때, 코드를 읽기 쉽게 하거나 값을 다시 사용하기 위해 값에 이름을 할당하고 싶을 수 있습니다.
> 하지만 함수 안에서는 함수 밖처럼 `def`을 사용해서는 _안됩니다_.
> 대신에 `let`이라고 불리는 특별한 양식을 사용해야합니다.
{: ng-show="block301" .description}
</section>

<section ng-controller="NarrativeController">
#### `let`으로 로컬 바인딩하기
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block305" ng-click="block305=!block305"></button>

> `let`을 `def`처럼 사용해서 값에 이름을 할당할 수 있습니다.
> 값에 이름을 할당하면, 그 이름을 *심볼*이라고 부릅니다.
{: ng-show="block305" .description}

> Reference: [Assignment let](http://clojurebridge.github.io/community-docs/docs/clojure/let/)
{: ng-show="block305" .description}

```clojure
(let [mangoes 3
      oranges 5]
  (+ mangoes oranges))
;=> 8
```
</section>

<section ng-controller="NarrativeController">
#### `let` 예제

<button class="link" ng-bind-html="details1" ng-model="block311" ng-click="block311=!block311"></button>
<button class="link" ng-bind-html="details2" ng-model="block312" ng-click="block312=!block312"></button>
<button class="link" ng-bind-html="details3" ng-model="block313" ng-click="block313=!block313"></button>
<button class="link" ng-bind-html="exercise" ng-model="block314" ng-click="block314=!block314"></button>

> 여태껏 봐왔던 것들 중에서 가장 복잡합니다. 각 단계를 진행해봅시다.
> 먼저, 함수의 이름과 함수를 설명하는 문자열과 인자를 갖고 있습니다. 다른 함수들과 같죠.
{: ng-show="block311" .description}

> 다음엔, `let`이 보입니다. `let`은 이름과 값이 번갈아 나오는 벡터를 받습니다.
> `t1`이 이름이고,`(이름)`의 결과를 `t1`에 할당합니다.
> 또 `(성)`의 결과를 `t2`에 할당합니다.
{: ng-show="block312" .description}

> 이름과 값의 벡터 다음에, `let`함수의 바디가 있습니다.
> 여타 함수의 바디처럼 실행하고 값을 반환합니다.
> `let`안에 `t1`과 `t2`가 정의되어있습니다.
{: ng-show="block313" .description}

> `walk.clj`로 이동해서 `opposite`함수를 작성합니다.
> 그런 다음, 함수 정의의 마지막 줄에서 `opposite`함수를 평가해봅니다.
> 또한, `opposite`함수의 사용 예제를 평가해봅니다.
{: ng-show="block314" .description}

```clojure
;; function definition
(defn opposite
  "Given a collection of turtle names, moves two of them in different directions."
  [names]
  (let [t1 (first names)
        t2 (last names)]
    (forward t1 40)
    (backward t2 30)))

;; function usage
(opposite (turtle-names))
```
</section>

{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신에 [README.md](../README.md)로 가세요.
instead. :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드로 돌아가거나</a>,
[curriculum outline](/curriculum/#/1)으로 가세요.
</section>
