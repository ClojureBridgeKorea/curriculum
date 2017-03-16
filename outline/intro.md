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

> 여러분이 예전에 프로그래밍을 해본 적이 없으시면, 프로그래밍 언어들이 많다는 것도 모르실 겁니다.
> 혹은 C, 자바스크립트, 파이썬, 자바같은 언어는 이미 들어 보셨을 수도 있습니다. (아니면 앞으로 듣게 되실 겁니다.)
{: ng-show="block11" .description}

> 그런데 왜 클로저를 가르칠까요? 클로저는 아직 저 언어들만큼 유명하지는 않습니다.
> 그럼에도 우리는 클로저를 사용합니다. 왜냐하면 클로저는 3가지 뛰어난 점이 있기 때문입니다.
> 이 특징들 때문에 클로저는 프로그래밍 초심자가 1순위로 배우기 쉬운 언어가 됩니다.
> 마찬가지로 이 때문에 클로저는 기존 프로그래머가 추가로 배우기 쉬운 언어이기도 합니다.
{: ng-show="block11" .description}

#### 클로저는 간결하다 <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> 클로저는 간결합니다. 강력하지 않다고 말하는 것이 아닙니다. 클로저는 강력합니다.
> 클로저 프로그래밍을 위해 배워야 하는 개념들은 그 숫자가 매우 적습니다. 그러면서도 이해하기는 수월합니다.
> 여러분이 클로저를 익혀 나갈 수록, 클로저 언어의 작은 일부분만 갖고도 생산적인 일을 할 수 있게 됩니다.
{: ng-show="block12" .description}

#### 클로저는 범용 언어다 <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button>

> 클로저는 범용 언어입니다. 어떤 언어들은 정해진 용도를 가집니다.
> 예를 들어, 자바스크립트는 점차 달라지고는 있지만 전통적으로 웹페이지에 사용되었습니다.
> Objective-C 언어는 주로 아이폰 앱에 쓰였죠.
> 오늘은 클로저로 그리기 애플리케이션을 만들겠지만, 어떠한 종류의 응용 프로그램도 클로저로 쉽게 만들 수 있답니다.
{: ng-show="block13" .description}

#### 클로저는 재밌다 <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> 클로저는 재밌습니다. 물론 견해 차이가 있을 수 있지만 우리는 사실이라고 생각합니다.
> 이 수업이 진행되는 동안 클로저 프로그램이 모여서 놀랍고도 강력한 일을 해내는 것을 보면서 재미를 느꼈으면 좋겠습니다.
{: ng-show="block14" .description}
</section>

<section ng-controller="NarrativeController">
## 클로저의 장점은?
{: .slide_title .slide}

#### <button class="link" ng-model="block21" ng-click="block21=!block21">Intro</button>

> 앞에서 우리는 클로저가 범용 언어라고 했습니다.
> 그것이 클로저가 뛰어난 면이 없다는 의미는 아닙니다.
{: ng-show="block21" .description}

#### 데이터 처리 <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> 클로저는 데이터 처리에 좋다고 알려져 있습니다. 왜냐하면 클로저가 좋은 자료 구조를 가지고 있기 때문입니다.
> 달리 말하면, 클로저는 데이터를 표현하는 사용이 쉽고 강력한 여러가지 방법들을 내장하고 있습니다.
{: ng-show="block22" .description}

#### 동시성 <button class="link" ng-bind-html="details" ng-model="block23" ng-click="block23=!block23"></button>

> 클로저는 동시성으로도 유명합니다. 네 사람이 오두막을 조립하는 지침을 작성한다고 생각해보세요.
> 네 사람이 한 번에 한 단계씩 끝내도록 작성하는 대신, 각자가 일을 부분적으로 나누어 맡도록 합니다.
> 그 다음, 네 사람은 자신의 작업물을 적절한 시점에 합쳐 더 큰 작업물로 만듭니다.
> 이 과정을 계속해서 반복합니다. 모든 작업물들이 다 합쳐져 완성될 때까지 말입니다.
> 이 과정은 정말 복잡해서 글로 작성하기 어렵습니다. 읽는 것도 힘들겁니다.
> 클로저는 컴퓨터에게 내리는 이런 종류의 명령을 쉽게 작성하는 방법을 제공합니다.
{: ng-show="block23" .description}

#### 다 좋습니다! <button class="link" ng-bind-html="details" ng-model="block24" ng-click="block24=!block24"></button>

> 또한 클로저는 Quil를 이용해 그리기 애플리케이션을 만드는 데에도 좋습니다. 이 작업은 우리가 함께 해보게 될 겁니다.
> [Quil](https://github.com/quil/quil)
{: ng-show="block24" .description}
</section>

<section ng-controller="NarrativeController">
## 클로저는 어떻게 생겼나?
{: .slide_title .slide}

```clojure
(print-str "Hello, World!")
(+ 3 4)
(forward :trinity 40)
```

#### 괄호 <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> 괄호를 주목하세요. 클로저에서 괄호는 명령문을 묶습니다.
> 여는 괄호는 명령문의 시작이고, 짝이 맞는 닫는 괄호는 명령문의 끝입니다.
> 보통, 클로저 코드는 중첩 괄호를 많이 가집니다.
> 혹은 다른 말로, 중첩 닫힌 명령문을 많이 가집니다.
{: ng-show="block31" .description}

#### 함수  <button class="link" ng-bind-html="details" ng-model="block32" ng-click="block32=!block32"></button>

> 괄호 옆에 나오는 컴퓨터에 주는 명령문을 볼 수 있습니다
> 그 명령문을 보통 우리는 함수라고 합니다. 클로저에서는 함수가 온갖 일들을 다 합니다.
> `print-str`, `+` 그리고 `forward` 이것들 모두가 함수입니다.
> 이러한 함수들이 실행되면, 어떠한 타입의 값을 반환합니다.
> 클로저 함수는 항상 값을 반환합니다.
{: ng-show="block32" .description}

#### 인자 <button class="link" ng-bind-html="details" ng-model="block33" ng-click="block33=!block33"></button>

> 많은 함수들이 인자를 취합니다. 인자란 함수 뒤에 오는 괄호 안에 있는 모든 것들입니다.
> `print-str`은 "Hello, World!"를 인자로 취하여 문자열을 반환합니다.
> `+`은 3과 4를 인자로 취하여, 이들을 더하고, 7을 반환합니다.
> `forward`는 :trinity와 40을 인자로 취하여, 거북이를 40만큼 이동시키고 결과를 반환합니다.
{: ng-show="block33" .description}
</section>

<section ng-controller="NarrativeController">
### 주석

<button class="link" ng-bind-html="details1" ng-model="block41" ng-click="block41=!block41"></button>
<button class="link" ng-bind-html="details2" ng-model="block42" ng-click="block42=!block42"></button>

> 코드를 작성할 때, 우리는 가능한 한 명확하게 쓰려고 노력합니다.
> 이런 노력은 대부분 우리보다는 다른 사람들이 코드를 읽을 때 큰 도움이 됩니다.
> 혹은 우리가 나중에 정확한 상세의미를 잊기 쉬운 지점의 코드를 다시 읽을 때에도 큰 도움이 됩니다.
> 코드의 의미를 명확히 밝히는 한 가지 방법이 주석을 다는 것입니다.
> 주석은 우리 자신을 위하여 우리가 코드에 추가하는 메모입니다. 컴퓨터는 주석을 무시합니다.
{: ng-show="block41" .description}

> 클로저에서는, 주석이 세미콜론(;)으로 시작합니다.
> 세미콜론 뒤부터 그 줄의 끝까지가 컴퓨터가 무시하는 주석이 됩니다.
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

## REPL이란?
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Intro</button>

> "REPL"은 Read-Eval-Print-Loop"(읽기-평가-출력-반복)를 나타내는데, 맥락없이는 제대로 이해되지 않을겁니다.
> 클로저를 포함한 많은 프로그래밍 언어들은 대화식으로 코드를 실행하여 사용자가 즉각적인 피드백을 받는 방식을 취합니다.
> 달리 말하면, 코드가 읽히고, 그리고나서 평가되고, 그리고나서 결과가 출력되고, 
> 그리고 다시 사용자의 차례가 됩니다. 따라서 반복인 것이죠.
{: ng-show="block51" .description}

**R**ead, **E**val, **P**rint, **L**oop

![Nightcode's repl](img/repl.png)

</section>

<section ng-controller="NarrativeController">
## 실전에서의 REPL
{: .slide_title .slide}


#### Nightcode InstaREPL <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> 클로저와 상호작용하려면, Nightcode의 InstaREPL 기능을 쓸 수 있습니다.
> 클로저와 상호작용할 수 있는 멋진 방법이죠.
{: ng-show="block61" .description}


#### REPL 사용하기 <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> Nightcode 하단에 REPL 프로젝트 설정이 있습니다.
> "Run with REPL"버튼을 누르면, REPL이 시작합니다.
{: ng-show="block62" .description}

> 다른 방법으로는, leiningen을 사용해 터미널에서 REPL을 시작할 수 있습니다. 이 방법은 Nightcode가 없어도 됩니다.
> 터미널에서, `lein repl`을 치면, REPL이 시작합니다.
> 프로젝트 디렉터리 내부에서 `lein repl` 명령어를 치면 leiningen이 프로젝트 설정을 인지합니다.
{: ng-show="block62" .description}


#### 프로그램 평가 및 줄 단위 평가 <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

<!-- TODO project_name should probably be defined somewhere, right? -->
> Nightcode는 하나의 파일 전체 내지는 하나의 프로그램 전체로 또는 줄 단위로도 평가하게 해줍니다.
> Nightcode에서, REPL이 시작된 후, "Realod File" 과 "Reload Selection"이 작동합니다.
{: ng-show="block63" .description}
</section>

<section>
#### 연습문제 1: Nightcode InstaREPL 기능 해보기

1. Nightcode를 시작합니다.
2. 여러분이 leiningen 설정을 실험하면서 만든 `myproject`를 들여옵니다.
3. `core.clj`를 엽니다. <br/>(`myproject` -> `src` -> `myproject` -> `core.clj`)
4. __InstREPL__ 버튼을 클릭합니다.
5. 밑에 있는 클로저 함수들을 타이핑하시고 나타나는 결과들을 지켜봅니다.

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
* 편집기에서 `walk.clj`의 마지막 라인에 `(forward 40)`를 타이핑합니다. 그 라인을 선택하고 "Reload Selection"을 눌러 라인을 평가합니다.
* 결과를 지켜봅니다.

(연습문제 3에서 계속)
</section>

<section>
#### 연습문제 3: 파일과 라인 평가하기 - Part 2

(연습문제 2가 끝났다는 가정 하에)

* `(right 90)`을 쓰고 REPL 창 하단의 "enter"를 누릅니다![Run with REPL pane](img/run-with-repl.png)
* 거북이가 어떻게 되는지 확인합니다.
* 이 둘을 살펴보고 [Turtles App API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md)와
[How To Walk Turtles](https://github.com/ClojureBridgeSeoul/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)
[section 1 and 2], 거북이를 움직이게 할 명령어를 시도해봅니다.
</section>

<section>
#### 연습문제 4: 클로저 설명서 살펴보기

* REPL창 아래에, 사용한 함수에 대한 설명서를 살펴봅니다.
* `(doc function-name)` 명령어를 쓸 수도 있습니다.
* `(doc +)`와 `(doc forward)`를 REPL에서 사용해봅니다.
* `-`, `*`, 또는 `doc`와 같은 여태껏 써왔던 다른 함수들을 사용해봅니다.
</section>

{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신에 [README.md](../README.md)로 가세요.
instead. :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">첫번째 슬라이드로 가거나</a>,
[curriculum outline](/curriculum/#/1)로 가세요.
</section>
