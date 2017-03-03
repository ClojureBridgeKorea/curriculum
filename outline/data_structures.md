---
layout: default
title: Vectors and Maps
permalink: /outline/data_structures.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/data_structures.html

{% endcomment %}

<section>
자료구조
----------------------------------------
{: .slide-title .chapter}

* Vectors
* Maps
</section>

<section>
### 데이터 묶음 - Collections
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> 지금까지, 데이터 하나하나를 다뤘습니다:숫자,문자열,값.  프로그래밍시에는 데이터들의 묶음을 가지고 작업하는 경우가 더 많습니다.
{: ng-show="block11" .description}

> 클로저는 이러한 데이터들의 *collections*와 함께 작업할 수 있는 훌륭한 기능들을 갖추고 있습니다. 클로저는 네가지의 collections을 제공할 뿐만 아니라 이 모든 collection들을 함께 사용하는 일관된 방법을 제공합니다.
{: ng-show="block11" .description}
</section>

<section ng-controller="NarrativeController">
### Vectors
{: .slide_title .slide}

#### 순차적인 모음 <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> 벡터는 값들의 순차적인 모음입니다. 벡터는 비어있을 수 있습니다. 벡터는 다른 타입의 값들을 담을 수 있습니다. 벡터의 값들은 0에서부터 시작하고 이 숫자를 인덱스라고 합니다. 인덱스는 값들을 참조할 때 사용합니다.
{: ng-show="block21" .description}

#### 객실과 비슷한 구조 <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> 벡터를 상상하기 위해서는 일정한 크기의 칸으로 나누어진 박스를 상상해 보세요. 각각의 칸은 수를 가지고 있습니다. 각각의 칸에는 데이터들을 넣을 수 있고 번호가 있기 때문에 어디서 그 데이터를 찾아야 할 지 알 수 있습니다.
{: ng-show="block22" .description}

> 그 숫자는 0부터 시작되한다는 것을 주의하세요. 이상하게 보일 수도 있지만 프로그래밍시에는 0부터 계산해야 합니다.
{: ng-show="block22" .description}

![Vector](img/vector.png)

</section>

<section ng-controller="NarrativeController">
#### 문법 <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> 벡터는 원하는 개수의 값들을 []안에 공백으로 구분하여 써서 사용합니다.  다음은 벡터에 관한 예제들 입니다:
{: ng-show="block31" .description}

```clojure
[1 2 3 4 5]
[56.9 60.2 61.8 63.1 54.3 66.4 66.5 68.1 70.2 69.2 63.1 57.1]
[]
```
</section>

<section ng-controller="NarrativeController">
#### 사용 예 <button class="link" ng-bind-html="details" ng-model="block41" ng-click="block41=!block41"></button>

> 한쌍의 거북이들이 있을때, `(turtle-name)`명령은 벡터의 형태로 거북이의 이름을 리턴합니다.
{: ng-show="block41" .description}

```clojure
(turtle-names)
;=> [:trinity :neo :oracle :cypher]
```
</section>


<section ng-controller="NarrativeController">
#### 생성 <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> 다음 두 함수는 새로운 벡터를 만들 때 사용합니다. `vector`함수는 원하는 수의 값을 가져와서 새로운 벡터에 넣습니다. `conj`는 모든 자료구조에서 볼 수 있는 흥미로운 함수입니다. 벡터에는 벡터와 값을 가져와서 벡터의 맨 끝에 그 값을 추가한 새로운 벡터를 리턴합니다. `conj`는 왜 이름이 `conj`일까요? `conj`는 join or combine을 의미하는 conjoin을 짧게 쓴 것입니다. 이것이 바로 우리가 하는 일입니다:벡터에 새로운 값을 추가합니다.
{: ng-show="block61" .description}

```clojure
(vector 5 10 15)
;=> [5 10 15]

(conj [5 10] 15)
;=> [5 10 15]
```
</section>

<section ng-controller="NarrativeController">
#### 추출 <button class="link" ng-bind-html="details" ng-model="block81" ng-click="block81=!block81"></button>

> 다음 네개의 함수를 살펴봅시다. `count`는 벡터 안에 있는 값의 개수를 알려줍니다. `nth`는 벡터안의 n번째 값을 알려줍니다. 이때 0부터 세야한다는 것을 주의하세요. 따라서 이 경우에는 1과 함께 사용된 `nth`는 우리가 따로 프로그래밍 하지 않는다면 두번째 값을 알려줍니다. `first`는 벡터에서 첫번째 값을 리턴해줍니다. `rest`는 첫번째 값을 제외한 모든 값들을 리턴해줍니다. 혼란스러울 수 있으므로 `nth`와 동시에 생각하지 않도록하세요.
{: ng-show="block81" .description}

```clojure
(count [5 10 15])
;=> 3
(nth [5 10 15] 1)
;=> 10
(first [5 10 15])
;=> 5
(rest [5 10 15])
;=> (10 15)
```
</section>

<section>
#### EXERCISE 1: 거북이 이름 확인하기
{: .slide_title .slide}

1. 파일의 코드를 이용해서 거북이를 추가하세요.
  * `walk.clj`파일로 가세요
  * `walk.clj`파일의 맨 끝에 `(add-turtle :neo)`를 추가하세요
  * 이 줄을 선택하고 "Reload Selection"을 클릭하세요
2. (선택사항) REPL을 사용하여 거북이를 추가하세요
  * `(add-turtle :oracle)`을 하단 REPL창에 입력하세요.
3. 거북이 이름을 확인하세요.
  * 하단 REPL창에 `(turtle-names)`를 입력하고 결과를 확인하세요.
</section>

<section>
#### EXERCISE 2: 벡터 만들기
{: .slide_title .slide}

* `myproject`의 `core.clj`로 가고 InstaREPL을 실행하세요
* 당신이 살고 있는 마을에서 다음 7일 동안 고온의 벡터를 만드세요.
* 그런 다음 다음주 화요일의 고온을 얻기 위해 `nth`함수를 사용하세요.
</section>


<section ng-controller="NarrativeController">
### Maps

#### 키와 값의 쌍들 <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> 맵은 키값과 그에 관련된 value값의 집합이 들어있습니다. 이는 사전을 생각하면 됩니다:우리는 단어(keyworld)를 사용해서 뜻(value)을 찾아봅니다. 만약 다른 언어를 이용해서 프로그래밍한다면 dictionarie, hash, associative array와 같은 이름으로 맵과 유사한 것을 볼 수 있을것입니다.
{: ng-show="block101" .description}

![Map](img/map.png)
</section>

<section ng-controller="NarrativeController">
#### 문법 <button class="link" ng-bind-html="details" ng-model="block102" ng-click="block102=!block102"></button>

> 맵은 중괄호 안에 키와 값을 교대로 써서 만듭니다.
{: ng-show="block102" .description}

> 맵은 우리가 일반적으로 생각하는 방식으로 데이터를 저장할 수 있기 때문에 유용합니다. Sally Brown을 예로 들어봅시다. 맵은 그녀의 성과 이름, 주소, 좋아하는 음식 등의 정보를 저장할 수 있습니다. 이는 해당 데이터를 모으고 보기편하게 만드는 간단한 방법입니다. 마지막 예시는 비어있는 맵입니다. 이는 값을 저장할 준비는 되어있지만 아직 아무것도 없는 맵입니다.
{: ng-show="block102" .description}

```clojure
{:first "Sally" :last "Brown"}
{:a 1 :b "two"}
{}
```
</section>

<section ng-controller="NarrativeController">
#### 사용 예 <button class="link" ng-bind-html="details" ng-model="block103" ng-click="block103=!block103"></button>

> 거북이가 `forward`나 `right`같은 명령을 받으면 맵의맵 형태로 결과를 리턴해 줍니다.
{: ng-show="block103" .description}

```clojure
(forward 40)
;=> {:trinity {:length 40}}
(right 90)
;=> {:trinity {:angle 90}}
```
</section>

<section ng-controller="NarrativeController">
#### 생성 <button class="link" ng-bind-html="details" ng-model="block104" ng-click="block104=!block104"></button>

> `assoc`과 `dissoc`은 한쌍의 함수입니다:이것들은 맵에서 항목들을 연결하거나 연결을 끊습니다. `assoc`을 이용해서 어떻게 성"Brown"을 추가하고, `dissoc`을 이용해서 그것을 삭제하는지 알아봅시다. `merge`는 두개의 맵을 합쳐서 새로운 맵을 만듭니다. 
{: ng-show="block104" .description}

```clojure
(assoc {:first "Sally"} :last "Brown")
;=> {:first "Sally", :last "Brown"}

(dissoc {:first "Sally" :last "Brown"} :last)
;=> {:first "Sally"}

(merge {:first "Sally"} {:last "Brown"})
;=> {:first "Sally", :last "Brown"}
```
</section>

<section ng-controller="NarrativeController">
#### 추출 1 <button class="link" ng-bind-html="details" ng-model="block105" ng-click="block105=!block105"></button>

> `count`는 모든 collection들이 가지는 함수입니다. 왜 답이 2라고 생각하나요? `count`는 연결의 결과를 리턴해주기 때문입니다.
{: ng-show="block105" .description}

> 맵은 키-값의 쌍으로 이루어져있기 때문에 키는 맵에서 값을 얻기 위해서 사용이 됩니다. 다음은 클로저에서 종종 사용되는 방법입니다. 맵에서 값을 찾기 위해서 키는 함수처럼 사용될 수 있습니다. 마지막 예에선, `:MISS`라는 키를 제공하고있습니다. 이는 우리가 찾는 키값이 맵에 존재하지 않을 때 작동합니다. 
{: ng-show="block105" .description}

```clojure
(count {:first "Sally" :last "Brown"})
;=> 2

(get {:first "Sally" :last "Brown"} :first)
;=> "Sally"
(get {:first "Sally"} :last)
;=> nil


(get {:first "Sally"} :last :MISS)
;=> :MISS
```
</section>

<section ng-controller="NarrativeController">
#### 추출 2 <button class="link" ng-bind-html="details" ng-model="block106" ng-click="block106=!block106"></button>

> `keys`와 `vals`라는 간단한 함수들이 있습니다:맵에서 키들과 값들일 리턴합니다. 순서는 보장할 수 없기때문에 `(:first :last)`나 `(:last :first)`의 형태로 얻을 것입니다.
{: ng-show="block106" .description}

```clojure
(keys {:first "Sally" :last "Brown"})
;=> (:first :last)

(vals {:first "Sally" :last "Brown"})
;=> ("Sally" "Brown")
```
</section>

<section ng-controller="NarrativeController">
#### 업데이트 <button class="link" ng-bind-html="details" ng-model="block110" ng-click="block110=!block110"></button>

> 맵을 생성한 후 키에 새로운 값을 연결시키기를 원할 수 있습니다. `assoc`함수는 기존의 키에 새로운 값을 추가할 때 사용될 수 있습니다. 또, `update`라는 편리한 함수도 있습니다. `update`는 맵과 키를 함께 사용합니다. 특정한 키는 함수의 첫번째 인자가 됩니다. `update-in`함수는 `update`처럼 작동하지만 중첩된 맵의 경로에서 업데이트하기 위해 키의 벡터가 필요합니다.
{: ng-show="block110" .description}

```clojure
(def hello {:count 1 :words "hello"})

(update hello :count inc)
;=> {:count 2, :words "hello"}
(update hello :words str ", world")
;=> {:count 1, :words "hello, world"}


(def mine {:pet {:age 5 :name "able"}})

(update-in mine [:pet :age] - 3)
;=> {:pet {:age 2, :name "able"}}
```
</section>


<section>
### Collections of Collections

#### <button class="link" ng-model="block101" ng-click="block101=!block101">Intro</button>

> 수,키워드,문자열과 같은 값들만이 collection에 넣을 수 있는 것은 아닙니다. 다른 collections들도 collection에 넣을 수 있으므로 맵의 벡터, 벡터의 리스트와 같이 데이터에 맞는 조합을 가질 수 있습니다.
{: ng-show="block101" .description}
</section>

<section>
#### Vector of Maps
```clojure
(state-all)
;=> [{:trinity {:x -1.7484556000744965E-6, :y 39.99999999999996, :angle 90, :color [106 40 126]}}
{:neo {:x 21.213202971967114, :y 21.213203899225725, :angle 45, :color [0 64 0]}}
{:oracle {:x -49.99999999999981, :y -4.3711390001862375E-6, :angle 180, :color [43 101 236]}}]

(def states (state-all))
;=> #'clojurebridge-turtle.walk/states

(first states)
;=> {:trinity {:x -1.7484556000744965E-6, :y 39.99999999999996,
:angle 90, :color [106 40 126]}}
```
</section>

<section>
#### Map of Maps

```clojure
(def st (first states))
;=> #'clojurebridge-turtle.walk/st

st
;=> {:trinity {:x -1.7484556000744965E-6, :y 39.99999999999996,
;=>            :angle 90, :color [30 30 30]}}

(get st :trinity)
;=> {:x -1.7484556000744965E-6, :y 39.99999999999996,
;=>  :angle 90, :color [30 30 30]}

(get-in st [:trinity :angle])
;=> 90
```
</section>


<section>
#### EXERCISE 3: 거북이들의 상태 확인하기
{: .slide_title .slide}

* `walk.clj` 파일로 가세요
* 앞의 두 슬라이드의 예제를 REPL에서 실행하세요.
* 얻은 값을 확인하세요

> REPL에서 코드를 입력할 때 __enter__를 잊지 마세요.


```clojure
(state-all)
(def states (state-all))
(first states)
(def st (first states))
st
(get st :trinity)
(get-in st [:trinity :angle])
```
</section>

<section>
#### EXERCISE 4: 당신을 모델링하세요
{: .slide_title .slide}

* `myproject`의 `core.clj`와 InstaREPL을 사용하세요
* 당신을 표현하는 맵을 만드세요
* 이 맵에는 당신의 성과 이름이 들어있어야합니다.
* [assoc](http://grimoire.arrdem.com/1.6.0/clojure.core/assoc/)이나  [merge](http://grimoire.arrdem.com/1.6.0/clojure.core/merge/).를 사용해서 맵에 당신의 고향을 추가하세요.
</section>

<section>
#### EXERCISE 5 [BONUS]: 친구를 모델링하세요
{: .slide_title .slide}

* 첫번째로, 앞의 excercise에서 만든 당신에 대한 맵을 가져오세요.
* 당신 주위에 있는 두세명의 친구의 성,이름,고향을 담고있는 맵 벡터를 만드세요.
* 마지막으로 [conj](http://grimoire.arrdem.com/1.6.0/clojure.core/conj/)을 사용해서 당신의 맵을 그들의 정보에 추가하세요.
</section>

{% comment %}

:star2: 아래의 링크는 슬라이드 전용입니다. 대신 [README.md](../README.md)로 가세요 :star2:

{% endcomment %}

<section>
<a href="javascript:;" onClick="Reveal.slide(1);">first slide</a>로 돌아가거나 [curriculum outline](/curriculum/#/1)으로 가세요.
</section>
