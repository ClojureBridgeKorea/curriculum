---
layout: default
title: Introduction
permalink: /outline/intro.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/intro.html

{% endcomment %}

<section>
클로저 프로그래밍 소개
----------------------------------------
{: .slide-title .chapter}

* 왜 클로저인가?
* 클로저의 장점은?
* 클로저는 어떻게 생겼을까?
    - 주석
* REPL이란?
* 실전에서의 REPL
</section>

<section ng-controller="NarrativeController">
## 왜 클로저인가?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> 프로그래밍을 해본 적이 없다면, 아주 많은 프로그래밍 언어가 있다는 것을 모를겁니다.
> 그 많은 언어 중 몇개는 C, 자바스크립트, 파이썬 그리고 자바같은 언어로 들어본 적이 있거나(앞으로 들을 것입니다.)
{: ng-show="block11" .description}

> 그런데 왜 클로저를 가르칠까요? 위 처럼 유명한 언어들이 많은데도 불구하고 우리는 3가지 특성 때문에 클로저를 사용합니다.
> 클로저는 첫번째로 배우기 쉬운 이상적인 언어입니다.
> 또는 이미 알고 있는 다른 언어들 이외에도 추가적으로 배우기 좋은 언어입니다.
{: ng-show="block11" .description}

#### 클로저는 _간단하다_ <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> 클로저는 _간단합니다_. 강하지 않다는 말이 아닙니다. 클로저는 강합니다.
> 클로저 프로그래밍에 필요한 개념의 수는 적지만 이해하기 쉽습니다.
> 클로저는 여러분이 배울 수록 거대해지고, 작은 부분으로도 생산적인 일을 할 수 있습니다.
{: ng-show="block12" .description}

#### 클로저는 _범용 언어다_ <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button>

> 클로저는 _범용 언어입니다_. 특정 목적에 집중한 언어가 몇 개 있습니다.
> 예를 들어, 자바스크립트는 예전부터 웹페이지에만 사용됐습니다.(약간의 변화는 있지만)
> Objective-C 언어는 주로 아이폰 앱에 쓰였죠.
> 오늘 드로잉 애플리케이션을 만들건데,
> 클로저를 이용해 어떠한 종류의 응용 프로그램도 쉽게 만들 수 있습니다.
{: ng-show="block13" .description}

#### 클로저는 _재밌다_ <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> 클로저는 _재밌습니다_. 물론 개인차가 있지만, 사실이라고 생각합니다.
> 이 수업이 진행되는 동안 클로저 프로그램이 모여서 놀랍고도 강력한 것을 만들어 내는 재미를 느꼈으면 좋겠습니다.
{: ng-show="block14" .description}
</section>

<section ng-controller="NarrativeController">
<<<<<<< HEAD
## 클로저로 하기 좋은 것
=======
## 클로저의 장점은?
>>>>>>> korean
{: .slide_title .slide}

#### <button class="link" ng-model="block21" ng-click="block21=!block21">Intro</button>

> 따라서, 클로저는 다목적 언어라고 말할 수 있습니다.
> 하지만 그렇다고 해서 강력하지 않은 것은 아닙니다.
{: ng-show="block21" .description}

#### 데이터 처리 <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> 클로저는 데이터 처리에 좋다고 알려져 있습니다. 그 이유는,
> 자료 구조가 좋기 때문입니다. --즉, 데이터를 표한하는 내장된 몇가지 방법이 쉽고 강력합니다.
{: ng-show="block22" .description}

#### 동시성 <button class="link" ng-bind-html="details" ng-model="block23" ng-click="block23=!block23"></button>

> 클로저는 동시성으로도 유명합니다. 4명의 친구에게 오두막을 조립하는 과정을 써내려간다고 생각해보세요.
> 하지만 한 번에 한 단계씩 쓰는 대신에, 친구들이 각자의 일을 해냅니다.
> 그런 다음, 친구들은 자신의 작업물을 적절한 때에 합쳐 더 큰 작업물을 만듭니다.
> 그리고 이 작업물이 다 합쳐져서 완성될 때까지 반복합니다.
> 이 과정은 글로 쓰기 어렵고 복잡합니다.--읽는 것도 힘들죠.
> 클로저는 이런 처리를 컴퓨터가 이해하기 쉽게 쓰는 언어입니다.
{: ng-show="block23" .description}

#### 다 좋습니다! <button class="link" ng-bind-html="details" ng-model="block24" ng-click="block24=!block24"></button>

> 또한 클로저는 우리가 앞으로 사용할 Quil를 이용해 드로잉 애플리케이션을 구현하는데에도 적합합니다.
> [Quil](https://github.com/quil/quil)
{: ng-show="block24" .description}
</section>

<section ng-controller="NarrativeController">
<<<<<<< HEAD
## 클로저의 생김새
=======
## 클로저는 어떻게 생겼나?
>>>>>>> korean
{: .slide_title .slide}

```clojure
(print-str "Hello, World!")
(+ 3 4)
(forward :trinity 40)
```

#### 괄호 <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> 괄호를 주목하세요. 클로저에서 괄호는 명령문을 묶습니다.
> 여는 괄호는 명령문의 시작이고, 짝이 맞는 닫는 괄호는 명령문의 끝입니다.
> 일반적으로, 클로저는 아주 많은 중첩 괄호을 가집니다.
> 혹은 다른 말로, 중첩 닫힌 명령문이라고도 합니다.
{: ng-show="block31" .description}

#### 함수  <button class="link" ng-bind-html="details" ng-model="block32" ng-click="block32=!block32"></button>

> 괄호 옆에, 컴퓨터에 주는 명령문들을 볼 수 있습니다
> computer. 그 명령문을 보통 우리는 _함수_라고 합니다.
> `print-str`, `+` 그리고 `forward` 이것들 모두가 함수입니다.
> 이러한 함수들이 실행되면, 어떠한 타입의 값을 반환합니다.
> 클로저 함수는 항상 값을 반환합니다.
{: ng-show="block32" .description}

#### 인자 <button class="link" ng-bind-html="details" ng-model="block33" ng-click="block33=!block33"></button>

> 많은 함수들이 _인자_를 가집니다.--함수 뒤에 오는 괄호 안에 있는 모든 것--
> `print-str`은 "Hello, World!"를 인자로 가지고 문자열을 반환합니다.
> `+`은 3과 4를 인자로 가지고, 더하고, 7을 반환합니다.
> `forward`는 :trinity와 40을 인자로 가지고, 거북이를 40만큼 옮겨 결과를 반환합니다.
{: ng-show="block33" .description}
</section>

<section ng-controller="NarrativeController">
### 주석

<button class="link" ng-bind-html="details1" ng-model="block41" ng-click="block41=!block41"></button>
<button class="link" ng-bind-html="details2" ng-model="block42" ng-click="block42=!block42"></button>

> 코드를 쓸 때, 가능한 명확하게 쓰려고 노력합니다.
> 이런 노력은  코드를 다른 사람이 읽을 때(우리보다 더!) 큰 도움을 얻을 수 있습니다.
> 혹은 나중에 코드를 다시 읽을 때, 코드의 자세한 부분을 잊었을 때에도 큰 도움이 됩니다.
> 코드를 명확하게 쓰는 법 중 하나는 주석을 쓰는 것입니다.
> 주석은 컴퓨터는 무시하는 우리가 코드에 추가한 메모입니다.
{: ng-show="block41" .description}

> 클로저에서는, 주석이 세미콜론(;)으로 시작합니다.
> 세미콜론 뒤의 그 줄의 모든 것은 주석 처리되어 컴퓨터는 무시합니다.
> 세미콜론 하나면 충분하지만, 취향에 따라 세미콜론 2개를 연달아 쓸 수 있습니다.
{: ng-show="block42" .description}

> 참고: [Comment](http://clojurebridge.github.io/community-docs/docs/clojure/comment/)
{: ng-show="block42" .description}

```clojure
;; example functions from a previous slide
(print-str "Hello, World!")  ; a well-known hello world
(+ 3 4)                      ; why not 3 + 4? figure out later
```
</section>

<section>
<<<<<<< HEAD
## REPL이 뭘까?
=======
## REPL이란?
>>>>>>> korean
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Intro</button>

> "REPL"은 Read-Eval-Print-Loop"(읽기-계산-출력-반복)의 약자로, 문맥없이는 의미를 가질 수 없습니다.
> 클로저를 포함한 많은 프로그래밍 언어들이
> 빠른 피드백을 받기위해 양방향으로 코드를 실행합니다.
> 다시 말해, 코드가 읽히고, 계산된 후, 결과가 출력되고, 처음으로 돌아갑니다--때문에 반복이라 함.
> then the result is printed, and you begin again--thus, a loop.
{: ng-show="block51" .description}

**R**ead, **E**val, **P**rint, **L**oop

![Nightcode's repl](img/repl.png)

</section>

<section ng-controller="NarrativeController">
## 실전에서의 REPL in action
{: .slide_title .slide}


#### Nightcode InstaREPL <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> 클로저와 상호작용하려면, Nightcode의 InstaREPL 기능을 쓸 수 있습니다.
> 클로저를 활발히 쓸 수 있는 좋은 방법입니다.
{: ng-show="block61" .description}


#### REPL 사용하기 <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> Nightcode 하단에 REPL 프로젝트 설정이 있습니다.
> "Run with REPL"버튼을 누르면, REPL이 시작합니다.
{: ng-show="block62" .description}

> 다른 방법으로는, leiningen을 사용해(Nigthycode 없이) 터미널에서 REPL을 시작할 수 있습니다.
> 터미널에서, `lein repl`을 치면, REPL이 시작합니다.
>  프로젝트 디렉터리 안에서 `lein repl` 명령어를 치면 프로젝트를 세팅합니다.
{: ng-show="block62" .description}


#### 프로그램 및 라인 평가 <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

<!-- TODO project_name should probably be defined somewhere, right? -->
> Nightcode는 또한 전체 파일(프로그램)이나 라인을 평가할 수 있게 합니다.
> Nightcode에서, REPL가 시작된 후, "Realod File" 와 "Reload Selection"가 작동합니다.
{: ng-show="block63" .description}
</section>

<section>
#### 연습문제 1: Nightcode InstaREPL 기능 해보기

1. Nightcode룰 시작한다.
2. `myproject`를 들여온다.<br/> (which you created while testing leiningen setup)
3. `core.clj`를 연다. <br/>(`myproject` -> `src` -> `myproject` -> `core.clj`
4. __InstREPL__ 버튼을 클릭한다.
5. 아래에 클로저 함수를 쓰고 지켜본다.

```clojure
(print-str "Hello, World!")
(print-str "Hello, World!" " " "from Clojure")
(+ 3 4)
(- 3 4)
(* 3 4)
```
> 위의 라인을 <em>정확히</em> 지켜서 썼는지 확인하세요.
> 괄호의 위치를 주의하세요.
</section>

<section>
#### 연습문제 2: 파일과 라인 평가하기 - Part 1

* `welcometoclojurebridge/src/clojurebridge_turtle/walk.clj`를 엽니다.
* "Run with REPL"을 누른 다음에 "Reload File"을 눌러 전체 파일을 평가합니다.
* 결과를 지켜봅니다.
* 편집기에서 `walk.clj`의 마지막 라인에 `(forward 40)`를 타이핑한다. 라인을 선택하고 "Reload Selection"을 눌러 라인을 평가합니다.
* 결과를 지켜봅니다.

(연습문제 3에서 계속)
</section>

<section>
#### 연습문제 3: 파일과 라인 평가하기 - Part 2

(연습문제 2가 끝났다는 가정 하에)

* `(right 90)`을 쓰고 REPL 창 하단의 "enter"를 누릅니다![Run with REPL pane](img/run-with-repl.png)
* 거북이가 어떻게 되는지 확인합니다.
* 이 둘을 살펴보고 [Turtles App API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md)와
[How To Walk Turtles](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)
[section 1 and 2], 거북이를 움직이게 할 명령어를 시도해봅니다.
</section>

<section>
#### 연습문제 4: 클로저 설명서 살펴보기

* REPL창 아래에, 사용한 함수에 대한 설명서를 살펴봅니다.
* `(doc function-name)` 명령어를 쓸 수도 있습니다.
* `(doc +)`와 `(doc forward)`를 REPL에서 사용해봅니다.
* T `-`, `*`, 또는 `doc`와 같은 여태껏 써왔던 다른 함수들을 사용해봅니다.
</section>

{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신에 [README.md](../README.md)로 가세요.
instead. :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드로 가거나</a>,
[curriculum outline](/curriculum/#/1)로 가세요.
</section>
