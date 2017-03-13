클로저브릿지 코치 가이드
=============================

클로저브릿지 자료를 가르치는 데는 여러 가지 방법이 있지만, 정해진 방법이 따로 있는 것은 아닙니다. 다음은 일부 워크숍 주최자 및 코치의 경험을 토대로 참가자들과 함께 커리큘럼을 작성하기 위한 방법입니다.

커리큘럼은 6개의 항목으로 나누어져 있습니다: 커리큘럼
[슬라이드와 내레이션](http://clojurebridge.github.io/curriculum),
과 캡스톤 앱 part.1:
[선 그리기](https://github.com/ClojureBridgeSeoul/drawing/blob/korean/curriculum/first-program.md).
캡스톤 앱을 위한 part. 2,
[거북이 걸음](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)
(함수 학습),
[눈꽃 그리기](https://github.com/ClojureBridgeSeoul/drawing/blob/korean/curriculum/create-something.md)
,
[반짝 반짝 작은별](https://github.com/ClojureBridge/tones/blob/master/curriculum/01-piano-chords.md) (소리 만들기),
[글로벌 성장](https://github.com/ClojureBridge/global-growth)  (web app with REST API),
[카이사르 암호](http://clojurebridge.github.io/community-docs/docs/exercises/caesar-cipher/)
(시저 암호, 문자열과 문자 연습).

워크샵 진행 상황에 따라 보너스 섹션을 건너 뛰거나 모듈을 조정할 수 있습니다. 그러나 Part. 2에 해당하는 캡스톤 앱들의 일부 보너스 섹션들은 진행하는 것이 좋습니다. 예를 들면, ‘거북이 걸음’, ‘반짝 반짝 작은 별’, 그리고 ‘눈꽃 그리기’의 나중 스텝은 ‘시퀀스’와 ‘바인딩'을 사용합니다. 만약 당신의 참가자들이 이 앱 프로젝트들을 수행했다면, 주 커리큘럼 과정으로 돌아가는 것이 좋습니다.

‘눈꽃 그리기’ 앱의 1-3 스텝은 도전하기 가장 좋은 스텝입니다. 단지Part. 1 앱에 추가적으로 흐름 제어가 필요할 뿐입니다. 반면 ‘글로벌 성장’ 앱은 상당한 수준의 앱으로 매우 수준 높은 참가자들을 위한 앱입니다. 코드를 복사해서 옮기는 것은 그다지 오래 걸리지 않습니다만, ‘REST API’와 ‘ring/compojure’에 대한 지식을 필요로 합니다. ‘눈꽃 그리기’ 앱과 ‘반짝 반짝 작은 별’ 앱은 재미있고 시도할만한 가치가 있는 앱 입니다.

슬라이드와 내레이션 커리큘럼은 정확히 같은 파일입니다. 슬라이드 형식들은 방 앞에서 출력 되고 있는 것과 동일한 반면, 내레이션 형식들은 슬라이드 안에 소개된 자세한 설명으로 읽기 쉽습니다. 참가자들은 내레이션에 따라 본인들의 컴퓨터에 작업하거나 또는 작업하기 위해 내레이션을 사용합니다.

커리큘럼
----------
챕터의 깃헙 계정(또는 개인 깃헙 계정)을 사용해서 커리큘럼 포크 합니다. [리포지토리](https://github.com/ClojureBridge/curriculum) 워크샵을 위해 내용을 수정하거나 커리큘럼에 대한 조정을 포크한 곳에 반영할 수 있습니다. 만약 수정한 내용이 누구에게나 가치있는 내용이라면, 주 커리큘럼에 pull request를 통해 반영할 수 있도록 고려해 보시길 바랍니다.

스케줄
--------
금요일 저녁: 인스톨페스트 - 온라인에서 설정 가져오기
토요일: 워크샵 – 커리큘럼

준비
-----------
[마크다운 페이지](outline/cheatsheet.md) 또는 [PDF 파일](ClojurebridgeCheatsheet-v2.pdf)을 인쇄해서 토요일에 행사가 시작되면 나누어 주십시오.

행사장 설치
----------
참가자들이 테이블을 마주보고 서로 마주보는 것이 가장 효과적입니다. 이것은 참가자들이 서로 돕도록 격려하고 조교들이 행사장을 돌아다니면서 질문에 답하기 쉽도록 하기 위함입니다.

프리젠테이션
----------------------------
대부분의 워크샵에는 코치와 조쿄들이 있습니다. 코치들은 앞에서 프리젠테이션을 하고, 조교들과 코치들은 참가자들이 그들의 동료와 함께 연습을 통해 작업을 해나갈 수 있도록 돕습니다.

이것이 프리젠테이션을 위한 유일한 방법은 아닙니다. 단지 지금까지 대부분의 워크샵에서 우리가 시행해 온 방법일 뿐입니다. 부담없이 실험해 보시길 바랍니다.


오라클 JDK 8
-------------

#### 우분투
주 커리큘럼과 다른 자료의 대부분은 ‘Nightcode 2.1.0’을 사용합니다. 이 버전은 오라클 JDK 8을 필요로 합니다. 리눅스 OS들은 보통 OpenJDK가 설치되어 있습니다. 리눅스 OS를 사용하는 참가자들은 오라클 자바 설치가 필요합니다. 설치 문서는 오직 ‘apt-get’에 의한 방법만 설명되어 있습니다. 그러나 그들은 JDK를 다운로드 받아 환경변수에 ‘JAVA_HOME/PATH’를 설정하는 방법을 선택할 수도 있습니다. 새로운 쉘에 이 환경변수를 적용하기 위해서는 한번은 로그아웃 해야할지도 모릅니다.

#### 엘 카피탄
OSX 엘 카피탄은 더 이상 자바 번들이 설치되어 있지 않습니다. 엘 카피탄을 사용하는 참가자들은 오라클 JDK 8을 설치해야만 합니다. 설치 과정은 윈도우즈와 같고 꽤 쉽습니다. 그러나 설치 후에, ‘JAVA_HOME’ 환경변수를 설정해야 합니다. ‘export JAVA_HOME=/usr/libexec/java_home -v 1.8’이라는 명령은 ‘JAVA_HONE’을 설정하는데 유용합니다. 또한 ‘JAVA_HOME’ 설정이 ‘.bash_profile ‘ 또는 일부 다른 쉘 설정 파일에 있어야 합니다.


Nightcode
---------

2016년 9월, 클로저브릿지 자료들은 Nightcode 2.1.0을 기반으로 만들어졌습니다. 이 버전은 하단에 오직 하나의 REPL만 존재하는데 이를 ‘InstaREPL’ 이라고 합니다. 그러나 ‘InstaREPL’에서는 ‘Quil’과 ‘Overton’ 앱들이 잘 동작하지 않습니다. 단지 클로저의 주요한 부분을 연습하기 위해서, 참가자들은 ‘myproject’(이 프로젝트는 ‘leingen’을 설정하는 동안 만들어져야 합니다.)와 ‘InstaREPL’을 사용할 수 있습니다.

#### Jar 아카이브 사용

NightCode 2.0.x 부터 설치 프로그램을 얻을 수 있습니다. 그러나 jar 아카이브는 설치하기 매우 쉽습니다. 자바 명령어 하나로 모든 것을 설치할 수 있습니다. 참가자들에게 jar 아카이브를 다운로드 하라고 말해주시길 바랍니다.

#### 파일 또는 REPL 안에 코드

참가자들은 어느 곳에 코딩 해야 할지 혼란스러워 할지 모릅니다.  REPL은 편리하지만, 코드를 저장하지 않습니다. 또한 여러 줄을 코딩해야 할때, 코드는 편집기 안에 타이핑 되어 집니다.  Nightcode는 기본적으로 자동-저장 되도록 설정되어 있지만, 저장 버튼을 누르는 것은 좋은 연습이 될 것입니다.

[배경지식] 클로저브릿지는 이전에 ‘LightTable’을 사용했기 때문에 InstaREPL을 사용하여 편집기에서 모든 것을 처리 할 수 있었습니다.

#### 단축키

자료들은 단축키를 언급하지 않습니다. 아직까지는 ‘Nightcode’에 대한 많은 경험을 가지고 있지는 않아서, 우리는 모든 플랫폼에서 동작하는 동일한 단축키에 대해 확신할 수 없습니다. 만약 그러한 것이 확인된다면, 우리는 자료에 추가할 것 입니다. 저희에게 알려주세요.


초급 및 고급 트랙
----------------------------
참가자가 자신의 프로그래밍 경험에 대한 수준을 찾는 인스톨페스트를 진행하는 동안이나 그 이전에 참가자에 대한 조사를 할 수 있습니다. 만약 여러명의 코치가 있는 경우, 각각의 방에서 다른 속도로 자료를 발표하거나 별도의 자료를 제출할 수 있습니다. 또는, 같은 방에서 모든 참가자들을 모아놓고 전달할 수도 있습니다. 그러나 수준에 따라 다른 테이블에 앉도록 해야 합니다.

연습
---------
연습을 위한 충분한 시간을 제공해 주시길 바랍니다. 진정한 재미를 느낄 수 있도록 하기 위함입니다. 조교들은 참가자들이 연습하고 있을때 참가자와 함께 앉거나 또는 테이블 주변에 둘러앉아 주시길 바랍니다.

캡스톤 앱
------------
워크샵날 마지막에는 Part 2 프로젝트를 위한 시간이 충분하도록 시간을 배분하시길 바랍니다.

개요
-------
해야 할 일: 각 표제 아래 팁 추가.

* [설정 가져오기](outline/setup.md)
* [클로저 프로그래밍 소개](outline/intro.md)
  - 20 분
* [단순 값](outline/simple_values.md)
  - 30 분
* [자료구조](outline/data_structures.md)
  - 60 분
* [함수](outline/functions.md)
  - 45-60 분
* [캡스톤 앱 1](https://github.com/ClojureBridgeSeoul/drawing/blob/korean/curriculum/first-program.md)
  - 60 분
* [흐름 제어](outline/flow_control.md)
  - 20 분
* [[보너스] 시퀀스](outline/sequences.md)
  - 10 분

* [캡스톤 앱 Pt. 2]
  - 각 60 - 90분


도움 자료
--------------------
* [참가자 차트시트](outline/cheatsheet.md) | [PDF](ClojurebridgeCheatsheet-v2.pdf)
* [슬라이드](http://clojurebridge.github.io/curriculum)


다른 커리큘럼
---------------
주 [커리큘럼](https://github.com/ClojureBridge/curriculum)은 충분히 테스트 되었지만, 다른 커리큘럼이 많이 있습니다. 자유롭게 사용해보시길 바랍니다.

* [미니애폴리스 잡담](https://github.com/clojurebridge-minneapolis/track1-chatter)
* [미니애폴리스 쓰레딩](https://github.com/clojurebridge-minneapolis/track2-threading)
* [미니애폴리스 생존](https://github.com/clojurebridge-minneapolis/track2-surviving)
* 더 많이! 추가해 주시길 바랍니다.
