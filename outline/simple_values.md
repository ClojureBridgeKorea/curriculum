---
layout: default
title: Simple Values
permalink: /outline/simple_values.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/simple_values.html

{% endcomment %}

<section>
Simple Values
----------------------------------------
{: .slide-title .chapter}

* Strings
* Booleans 과 nil
* Keywords
* Numbers
  - Arithmetic

* Assignment: `def`
</section>

<section>
## Simple Values

#### <button class="link" ng-model="block71" ng-click="block71=!block71">Intro</button>

> 프로그래밍언어에서 무언가를 하기 위해서는 값이 필요합니다.
> 클로저에서는 simple value로 number, boolean, nil, keyworld를 제공합니다.
{: ng-show="block71" .description}
</section>

<section ng-controller="NarrativeController">
### Strings
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> string은 무엇일까요? string은 문자열입니다. string을 만들기 위해서는
> " "로 문장을 감싸야 합니다.
> 다음 예제를 봅시다. 역슬래시는 문자열에서 " "을 어디에 두어야 하는지를 보여주고있습니다.
{: ng-show="block21" .description}

> 참조: [String](http://clojurebridge.github.io/community-docs/docs/clojure/string/)
{: ng-show="block21" .description}

```clojure
"Hello, World!"
"This is a longer string that I wrote for purposes of an example."
"Aubrey said, \"I think we should go to the Orange Julius.\""
```
</section>

<section ng-controller="NarrativeController">
### Booleans 과 nil
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> boolean은 참값 혹은 거짓값을 가지며 단순하게 `true` `false`를 입력하면 
> 됩니다.
> 프로그래밍에선 종종 "이번학기에 이 수업이 열리나요?"나 "오늘이 생일이니
> ?"와 같이 참 혹은 거짓을 물어볼 때가 있습니다.
> 이때 우리는 boolean값을 얻게 됩니다.
{: ng-show="block31" .description}

> 또다른 값으로는 `nil`이 있는데 이것은 __truthiness__라는 의미로 boolean
> 처럼 사용이 됩니다.
> 하지만 `nil`은 아무런 가치가 없고 단지 boolean이란 것만 의미합니다.
{: ng-show="block31" .description}

> 참조: [Truthiness](http://clojurebridge.github.io/community-docs/docs/clojure/truthiness/)
{: ng-show="block31" .description}


```clojure
true
false
nil
```
</section>

<section ng-controller="NarrativeController">
### Keywords
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block41" ng-click="block41=!block41"></button>

> keyworld는 기본적인 값들중 가장 이상한 타입입니다. 몇몇 컴퓨터언어에서도 
> 이와 비슷한 것을 가집니다. 하지만 number,string,boolean처럼 
> real world analog를 가지지는 않습니다.
> keyworld는 레이블처럼 사용되는 일종의 특별한 문자열이라고 생각하면 
> 됩니다.
> keyworld는 maps(자료구조;다음에 배울예정)의 key-value pair에서 키값으로
> 사용됩니다.
{: ng-show="block41" .description}


```clojure
:trinity
:first
:last
```
</section>

<section ng-controller="NarrativeController">
### Numbers

#### 정수 <button class="link" ng-bind-html="details" ng-model="block81" ng-click="block81=!block81"></button>

> 클로저는 여러종류의 숫자 타입을 가집니다.
{: ng-show="block81" .description}

> 첫번째는 정수타입입니다. 정수는 0을 포함한 양수,음수로 구성되어 있으며 
> 평상시에 쓰는것처럼 사용하면됩니다.
{: ng-show="block81" .description}

```clojure
0
12
-42
```
</section>

<section ng-controller="NarrativeController">
#### 소수 <button class="link" ng-bind-html="details" ng-model="block91" ng-click="block91=!block91"></button>

> 다음으로는 float라고도 불리는 소수가 있습니다. 여기에는 소숫점이 있는 모든 
> 수가 포함됩니다.
{: ng-show="block91" .description}

```clojure
0.0000072725
10.5
-99.9
```
</section>

<section ng-controller="NarrativeController">
#### 분수 <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> 마지막으로 ratio라고도 불리는 분수가 있습니다. 컴퓨터는 모든 소수를 완벽하
> 게 표현하지 못하지만 분수는 가능합니다.
> 분수는 다음과 같이 슬래시를 이용해서 표현합니다:
{: ng-show="block101" .description}

> 실제 수학과 마찬가지로 분수의 [분모](http//en.wikipedia.org/wiki/Fraction_%28mathematics%29)는 절대 0이 될 수 없음을 주의하세요.
{: ng-show="block101" .description}

```clojure
1/2
-7/3
```
</section>

<section>
### 산술연산
{: .slide_title .slide}

#### <button class="link" ng-model="block111" ng-click="block111=!block111">Intro</button>

> 우리는 수들을 더하고,빼고,곱하고 나누는 것이 가능합니다. 클로저에서는 이
> 러한 연산이 실제 우리가 종이에 쓰는 방식과는 조금 차이가 있습니다. 다음 예
> 제를 봅시다:  
{: ng-show="block111" .description}

```clojure
(+ 1 1)  ;=> 1 + 1 = 2
(- 12 4) ;=> 12 - 4 = 8
(* 13 2) ;=> 13 * 2 = 26
(/ 27 9) ;=> 27 / 9 = 3
```
</section>

<section ng-controller="NarrativeController">
### Infix vs. prefix 표기법
{: .slide-title .slide}

<button class="link" ng-bind-html="details1" ng-model="block121" ng-click="block121=!block121"></button>
<button class="link" ng-bind-html="details2" ng-model="block122" ng-click="block122=!block122"></button>

> 클로저에서는 `+`,`-`,`*`,`/`가 피연산자들 앞에 위치합니다. 이런 것을 _pre
> fix 표기법_이라고 합니다. 우리가 주로 보는 두 피연산자 사이에 연산자가 위
> 치하는 것은 _infix 표기법_이라고 합니다.
{: ng-show="block121" .description}

> **JavaScript**같은 것은 **infix**표기법을 사용합니다.
> **Clojure**에선 **prefix**표기법만을 사용합니다.
> Prefix 표기법은 많은 이유에서 유용합니다. 다음 예제는 infix표현과 그와 동
> 일한 prefix표현을 보여줍니다:
{: ng-show="block122" .description}

```clojure
Infix:  1 + 2 * 3 / 4 + 5 - 6 * 7 / 8 + 9

Prefix: (+ (- (+ (+ 1 (/ (* 2 3) 4)) 5) (/ (* 6 7) 8)) 9)
```
</section>

<section ng-controller="NarrativeController">
### Why prefix is better?

#### 명확한 우선순위 <button class="link" ng-bind-html="details" ng-model="block131" ng-click="block131=!block131"></button>

> 명확하게 보이지는 않지만 prefix버전에서 우린 더이상 연산자의 우선순위를
> 생각 할 필요가 없다는 것에 주목하세요. 
> 모든 표현식이 모든 피연산자 앞에 연산자를 가지며 전체 표현식이 괄호 안
> 에 싸여있기 때문에 모든 우선순위가 명시적입니다.
{: ng-show="block131" .description}

```clojure
Infix:  1 + 2 / 3
Prefix: (+ 1 (/ 2 3))
```

#### 적은 반복 <button class="link" ng-bind-html="details" ng-model="block132" ng-click="block132=!block132"></button>

> prefix 표기법이 더 좋은 다른 이유는 긴 표현을 덜 반복적으로 만들 수 있
> 다는 것입니다.
> 만약 다수의 피연산자에 대해 동일한 연산을 하려할 때 prefix표기법에선 연
> 산자들을 반복해서 쓸 필요가 없습니다.
{: ng-show="block132" .description}

```clojure
Infix:  1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9
Prefix: (+ 1 2 3 4 5 6 7 8 9)
```
</section>

<section ng-controller="NarrativeController">
### 모든 수에 대한 산술연산

<button class="link" ng-bind-html="details" ng-model="block141" ng-click="block141=!block141"></button>

> 지금까지 정수에 대해서만 산술연산을 해보았습다.
> 하지만 이러한 연산자들을 소수와 분수에 대해서 사용하기도 합니다.
> 다음 예를 봅시다:
{: ng-show="block141" .description}

```clojure
(+ 4/3 7/8)   ;=> 53/24
(- 9 4.2 1/2) ;=> 4.3
(/ 27/2 1.5)  ;=> 9.0
```
</section>


<section ng-controller="NarrativeController">
## 할당: `def`

#### <button class="link" ng-model="block161" ng-click="block161=!block161">Intro</button>

> 만약 같은 값을 반복해서 입력해야 한다면 프로그램을 작성하는 것이 매우
> 어려울 것입니다. 그렇기 때문에 값에 대한 이름이 필요하고 우리가 기억할 수
> 있는 방식으로 그것들을 참조할 수 있습니다. 이것을 할당한다라고 합니다.
{: ng-show="block161" .description}
</section>

<section ng-controller="NarrativeController">
#### 값에 이름 지정하기: `def`

#### <button class="link" ng-bind-html="details" ng-model="block171" ng-click="block171=!block171"></button>

> `def`를 사용해서 값에 이름을 붙일 수 있습니다.
> 값에 붙여지는 이름을 *symbol*이라고 합니다.
{: ng-show="block171" .description}

> 참조: [Assignment def](http://clojurebridge.github.io/community-docs/docs/clojure/def/)
{: ng-show="block171" .description}

```clojure
(def mangoes 3)
(def oranges 5)
(+ mangoes oranges)
;=> 8
```
</section>

<section ng-controller="NarrativeController">
#### 결과값에 symbol지정하기 <button class="link" ng-bind-html="details" ng-model="block181" ng-click="block181=!block181"></button>

> symbol에는 단순한 값 이상을 할당할 수 있습니다. 다음을 봅시다.
> 다음줄에서는 값을 참조하는데 어떻게 symbol을 사용하는지를 보여주고있습니다.
{: ng-show="block181" .description}

```clojure
(def fruit (+ mangoes oranges))
(def average-fruit-amount (/ fruit 2))
average-fruit-amount
;=> 4
```
</section>

<section>
#### 연습문제 1: Basic arithmetic

* 오늘 워크샵에 도착한 이후로 몇분이나 지났나요?
* 이 값을 분에서 초로 변환하세요.
</section>

<section>
#### 연습문제 2 [BONUS]: Minutes and seconds

* 1000초를 분과 초로 변환하세요.
* 분과 초는 별도의 숫자가 됩니다.
* `(quot x y)`는 y로 나눈 x의 몫을 구해줍니다.
* `(rem x y)`는 y로 나눈 x의 나머지를 구해줍니다.
</section>

{% comment %}

:star2: 다음 링크는 슬라이드만 있습니다. 대신 [README.md](../README.md)로 가세요.:star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드</a>로 돌아가거나, [curriculum outline](/curriculum/#/1)로 가세요.
</section>
