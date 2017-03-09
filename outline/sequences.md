---
layout: default
title: Sequences
permalink: /outline/sequences.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/sequences.html

{% endcomment %}

<section>
[BONUS]

시퀀스
-------------------------
{: .slide-title .chapter}

* 시퀀스란?
* 시퀀스를 다루는 함수들
    * `doseq`
    * `dotimes`
</section>

<section ng-controller="NarrativeController">
### 시퀀스가 뭔가요?
{: .slide_title .slide}

#### 클로저의 자료구조 <button class="link" ng-bind-html="details" ng-model="block11" ng-click="block11=!block11"></button>

> 클로저에서는, 모든 자료구조를 시퀀스로 할 수 있습니다.
> 앞서, `벡터`와 `맵`이 전부 시퀀스라고 배웠습니다.
> 문자열도 역시 시퀀스이며, **seq로 다룰 수 있는 것**들은 전부 시퀀스입니다.
{: ng-show="block11" .description}

#### `first`함수 반환 유무 <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> **seq로 다룰 수 있는 것**이라면, 시퀀스의 첫 번째 아이템을 반환합니다.
> `first` 함수를 통해서 말이죠. 시퀀스인지 아닌지 테스트할 때 쓸만합니다.
{: ng-show="block12" .description}
</section>

<section ng-controller="NarrativeController">
#### `first`의 결과

```clojure
(turtle-names)
;=> [:trinity :neo :oracle :cypher] ; vector
(first (turtle-names))
;=> :trinity                        ; the first item

(:trinity (state))
;=> {:x 0, :y 0, :angle 90, :color [30 30 30]}  ; map
(first (:trinity (state)))
[:x 0]                                          ; the first item

(first "Hello, World!")  ; string
;=> \H                   ; the first item

(first :trinity)         ; keyword is not seq-able
;=> IllegalArgumentException Don't know how to create ISeq from:
clojure.lang.Keyword  clojure.lang.RT.seqFrom (RT.java:528)
```
</section>

<section ng-controller="NarrativeController">
### 시퀀스를 다루는 함수들
<button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> 클로저는 시퀀스를 *반복*할 때 아주 좋습니다.
> 시퀀스를 다루는 많은 함수들이 있습니다.
> 예를 들어, `doseq`, `dotimes`, `for`, `loop`, `doall`,`dorun` 함수들이 있습니다.
> `map`과 `reduce` 함수를 이미 "함수를 인자로 갖는 함수" 섹션에서 보았습니다.
> 이것들 또한 시퀀스를 다루는 함수 입니다.
{: ng-show="block21" .description}
</section>

<section ng-controller="NarrativeController">
#### `doseq`

<button class="link" ng-bind-html="details1" ng-model="block31" ng-click="block31=!block31"></button>
<button class="link" ng-bind-html="details2" ng-model="block32" ng-click="block32=!block32"></button>

> `doseq`(**do sequence**)는 시퀀스를 다루는 함수들 중 잘 쓰이는 함수들 중 하나입니다.
> `map`함수와 아주 비슷하게 기능합니다.
> 함수는 주어진 시퀀스에서 각 요소를 사용해 바디 부분을 반복적으로 실행합니다.
{: ng-show="block31" .description}

> `doseq`함수는 인자를 묶어서 취급합니다.
> 그 인자는 이상해 보이는 벡터일 수도 있습니다 : `[name의 시퀀스]`. 
> 시퀀스의 각 요소가 반복하면서, 하나씩 이름에 할당됩니다.
{: ng-show="block32" .description}

```clojure
;; doseq example
(doseq [n (turtle-names)] (forward n 40))
```
</section>

<section>
#### 연습문제 1

* [Turtles Walk](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md) (함수 스터디)
    - 섹션 5 이상
* [Snowflakes](https://github.com/ClojureBridgeSeoul/drawing/blob/korean/curriculum/create-something.md) (애니메이션)
    - 4단계 이상
* [Twinkle Twinkle Little Star](https://github.com/ClojureBridge/tones/blob/master/curriculum/01-piano-chords.md) (사운드 관련)
    - `chord` 함수 이상
</section>

<section ng-controller="NarrativeController">
#### `dotimes`

<button class="link" ng-bind-html="details1" ng-model="block41" ng-click="block41=!block41"></button>
<button class="link" ng-bind-html="details2" ng-model="block42" ng-click="block42=!block42"></button>

>`dotimes`(**do number of times**) 함수는 시퀀스를 다루는 함수들 중 잘 쓰이는 또 다른 함수입니다.
>`doseq`함수처럼 반복적으로 주어진 바디를 실행합니다.
> 차이점은 인자를 받는 방법입니다.
> `dotimes`는 `[name의 최대정수]`를 인자로 받습니다.
{: ng-show="block41" .description}


> `dotimes` 함수는 다른 프로그래밍 언어에서 for문과 가장 유사합니다.
> 이 함수는 `ntn`함수와 함께 주어진 시퀀스에 대한 인덱스 접근을 허용합니다.
{: ng-show="block42" .description}

```clojure
;; assuming there are multiple turtles
(def names (turtle-names))
(dotimes [n (count names)] (right (nth names n) (* 45 n)))
```
</section>

<section>
#### 연습문제 2

* [Turtles Walk](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md) (함수 스터디)
    - 섹션 6 이상
* [Snowflakes](https://github.com/ClojureBridgeSeoul/drawing/blob/korean/curriculum/create-something.md) (애니메이션)
    - 5-4단계 이상
* [Twinkle Twinkle Little Star](https://github.com/ClojureBridge/tones/blob/master/curriculum/01-piano-chords.md) (사운드 관련)
    - Twinkle Little Star 섹션 완료하기
</section>


{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신에 [README.md](../README.md)로 가세요.
instead. :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드로 돌아가거나</a>,
[curriculum outline](/curriculum/#/1)로 가세요.
</section>
