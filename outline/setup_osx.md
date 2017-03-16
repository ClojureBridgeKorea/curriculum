OS X에서 설치하기
==========

* 터미널 열기
* Git 설치하기
* Git 설정하기
* Java 설치 확인하기
* Leiningen 설치하기
* Nightcode 설치하기
* 설정 확인하기

## 터미널 열기

이 설명과 수업을 진행하기 위해서는 터미널이 필요합니다.
터미널은 컴퓨터와 대화하기 위한 텍스트 기반의 인터페이스이며 `/Applications/Utilities`에 있는 Terminal.app을 실행하여 열 수 있습니다.
터미널을 사용해 본 적이 없다면, 이것을 읽어보시는 것도 좋습니다. [reading up on command-line basics](http://blog.teamtreehouse.com/command-line-basics)

지금 터미널을 열어봅니다. 터미널을 열면 이런 화면을 볼 수 있습니다.

![blank terminal](img/os_x/blank_terminal.png)

(명령어를 입력할) 프롬프트는 아마 다를겁니다: 프롬프트는 보통 컴퓨터 이름, 유저 이름, 그리고 현재 위치한 디렉터리의 위치를 보여줍니다.

앞으로 나올 설치 안내에서, 터미널에서 명령어를 실행하라는 말이 나올겁니다. 그 말인 즉슨, "명령어를 터미널에 입력하고 엔터키를 누르세요."라는 뜻입니다.

## Git 설치하기

git를 설치했는지 확인하려면: `git --version`을 입력하세요. `git version 1.9.3(Apple Git-50)` 이상의 버전이면 문제없습니다.

그렇지 않다면, [git-scm.com](http://git-scm.com/)으로 가서 "Downloads for Mac"을 누르세요.
Git 설치 관리자가 자동으로 다운로드를 시작할 것입니다. 그렇지 않다면, 수동으로 다운로드 링크를 누르세요.
다운로드가 완료되면, __~/Downloads__를 파인더에서 열고 다운받은 파일을 더블 클릭하세요. (__git-2.0.1-intel-universal-snow-leopard.dmg__와 비슷한 이름일 것입니다.)
그러면 디스크 이미지가 마운트되고 새로운 파인더 창이 열립니다. 설치 프로그램 패키지를 더블 클릭하세요. (__git-2.0.1-intel-universal-snow-leopard.pkg__와 비슷한 이름일 것입니다.)

확인되지 않은 개발자의 파일이라며 설치 프로그램이 열리지 않을 것입니다.
그렇다면, "승인"을 누른 다음에 파일을 마우스 오른쪽으로 클릭하고 "열기"를 누르세요.
확인되지 않은 개발자의 프로그램이라며 또 한번 경고가 나올 것입니다. 하지만 "열기" 옵션이 있을 것 입니다. "열기"를 누르세요.
이러면 설치 프로그램이 시작합니다. 설치 프로그램의 지시에 따르고, 암호를 입력하라는 메시지가 나오면 입력하세요.
이 과정을 마치면 Finder 사이드 바에있는 꺼내기 버튼을 클릭하여 디스크 이미지를 마운트 해제하고 다운로드 폴더에서 파일을 삭제하십시오.


## Git 설정 하기

이전에 Git를 사용하신 적이 있다면 이미 user.name과 user.email이 설정되어있을 것입니다.
그렇지 않다면, 터미널에 이렇게 입력하세요.

```bash
git config --global user.name "Your Actual Name"
git config --global user.email "Your Actual Email"
```
TIP: git, github, ssh의 이메일을 통일하세요.

터미널에서 다음을 입력하고 확인하세요:

`git config --get user.name`
Expected result:
`your name`

`git config --get user.email`
Expected result:
`your email address`


## Java 설치 확인하기


> OS X 버전 10.11 (El Capitan)를 이용하고 계신다면, Java가 설치되어있지 않을 것입니다.
> Java 또한 설치해야합니다.
> <http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>에서 Java를 다운로드하고 지시에 따르세요. 설치가 끝나면 `JAVA_HOME` 환경변수를 터미널에 등록하세요.
> `export JAVA_HOME=/usr/libexec/java_home -v 1.8`
>
> 문제가 있다면, 이 기사가 도움이 될 것입니다. <http://osxdaily.com/2015/10/17/how-to-install-java-in-os-x-el-capitan/>


`java -version`을 터미널에서 실행해보세요. Java가 설치되어있지 않으면, OS X는 설치하라는 신호를 보낼 겁니다.(OS X의 버전이 10.10 이상이라면) OS X의 모든 지시사항을 따르면 튜토리얼로 돌아와서 `java -version`을 다시 실행해보세요.

Java가 설치되면 터미널에서 이런 것을 볼 수 있습니다.

![Java version](img/os_x/java_version.png)

Java의 세부적인 버전은 위의 것과 다를 수 있습니다; 아무 문제 없습니다.

## Leiningen 설치하기

Leiningen은 클로저 프로젝트 관리를 위한 커맨드 라인 툴입니다.

`lein`을 설치하려면, 터미널에서 다음의 명령어를 실행하세요; `sudo`로 시작하는 첫 명령어에서 비밀번호를 입력하라고 할 것입니다.

```bash
% curl https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein > lein
% sudo mkdir -p /usr/local/bin/
% sudo mv lein /usr/local/bin/lein
% sudo chmod a+x /usr/local/bin/lein
```
다음의 명령어를 볼 수 있는지 확인하세요:
```bash
% which lein
/usr/local/bin/lein
```
 만약 위의 `/usr/local/bin/lein`이 보이지 않는다면, 다음을 해보세요:
```bash
% export PATH=$PATH:/usr/local/bin
```
이제 `which lein`을 실행하면 `lein`명령어를 보여야합니다.

Leiningen을 설치한 후에, `lein version` 명령어를 실행하세요. 처음에 필요한 리소스를 다운받기에 다소 시간이 걸릴 수 있습니다. 성공적으로 끝나면, 완벽합니다! 문제가 있다면 강사에게 도움을 요청하세요. 

## Nightcode 설치하기 

이곳으로 이동하세요[Nightcode releaes site](http://github.com/oakes/Nightcode/releases).
그 페이지에서 Nightcode-2.1.0.jar와 같은 버전 정보와 다운로드 링크를 발견할 수 있습니다.
`.jar`로 끝나는 링크를 누르면 `Nightcode-x.y.z.jar` 파일을 다운받을 수 있습니다.

> 특정 파일을 배포하는 플랫폼을 사용하지 마세요.
> jar 아카이브를 사용하세요.
> Jar 아카이브가 훨씬 쉽습니다.

다운로드가 끝나면, 편집기를 시작합니다.
시작하기위해 다운로드 폴더(혹은 파일을 저장한 경로)로 이동해서 `java` 명령어를 이용해 Nightcode-x.y.z.jar를 실행합니다.


터미널을 열어 아래의 명령어를 따라하세요:

```bash
cd ~/Downloads/
java -jar Nightcode-2.1.0.jar
```

![Nightcode](img/nightcode-startup.png)


## 설정 확인하기

Java, Leiningen, Nightcode, Git --워크샵 동안 사용할 모든 툴들을 컴퓨터에 설치하셨습니다. 시작하기 전에 이 툴들을 테스트할 필요가 있습니다.


#### Leiningen 테스트하기

새 터미널 창을 열어서 다음의 명령어를 실행하세요:

```bash
lein new myproject
```

`myproject`라는 새로운 프로젝트가 생성되었을 겁니다. `myproject`에는 클로저 프로젝트를 구성하는 여러 파일들이 담겨 있습니다.
일반적으로 클로저 코드는 이러한 클로저 프로젝트 안에 놓이게 됩니다.

다음의 명령어를 실행하세요:

```bash
cd myproject
lein repl
```

처음 실행될 때에는 시간이 조금 걸릴 수 있습니다.
Leiningen이 클로저를 실행하기 위해 필요한 라이브러리를 다운받기 때문입니다.
Leiningen이 시작하면, `user=>`라는 프롬프트가 터미널에 보일 것입니다.

![Testing lein repl](img/os_x/testing-lein-repl.png)

이제 __REPL__를 사용할 준비가 되었습니다. __REPL__에 대해선 앞으로 배울 것입니다.
클로저를 위한 특별한 터미널입니다.

REPL 프롬프트에서, `(+ 1 1)`을 입력하고 엔터키를 누르세요. `2`라는 값을 얻었다면 성공입니다!

leiningen 설치는 잘 마무리된 것 같습니다. 이제는, Ctrl+D를 누릅니다. 이 키는 클로저 REPL에서 원래의 터미널 프롬프트로 돌아가게 합니다. 그러면 터미널에선 다음의 메시지를 보여줄 것입니다:`user=> Bye for now!`


#### github 저장소 복제하기

또 다른 터미널을 열어서 아래의 명령어를 실행하세요:

```bash
git clone https://github.com/ClojureBridge/welcometoclojurebridge
```

이 명령어는 몇가지 클로저 앱을 포함하는 `welcometoclojurebridge` 저장소를 복제합니다. which includes sample Clojure apps.
터미널을 이와 비슷하게 보여질 것입니다.

![Testing git clone](img/os_x/testing-git-clone.png)

완료되면, 다음의 명령어를 같은 터미널에 입력하세요.

```bash
cd welcometoclojurebridge
ls
```

이러한 디렉터리의 리스트를 볼 수 있을겁니다.

```
README.md       outline         project.clj     resources       src
```


#### Nightcode 테스트하기

만약 Nightcode가 아직 시작하지 않거나 꺼져있다면, 터미널에서 다음의 명령어를 입력해 열어주세요:

```bash
java -jar Nightcode-2.1.0.jar
```

화면의 우측 하단에, `(+ 1 1)`을 입력하세요. 결과는 다음과 같습니다:

![Testing Nightcode](img/nightcode-repl.png)

결과값이 2로 나온다면 성공입니다!


#### 앱 테스트하기 - 클로저브릿지에 오신 것을 환영합니다

이제 Nightcode에서 샘플 클로저 앱을 열고 실행해보겠습니다.
좌측 상단에, "Import"를 누르고 `welcometoclojurebridge` 디렉터리를 찾습니다.
`git clone` 명령어를 통해 이미 만들어놨던 디렉터리입니다. "Open."을 누르세요.
좌측의 프로젝트 디렉터리에서 `src` - `welcometoclojurebridge` - `core.clj`를 누르세요. `core.clj`파일이 우측에 나타날 것입니다.
이것이 클로저 프로그램입니다.

![Testing apps - click import](img/nightcode-click-import.png)
![Testing apps - open welcometoclojurebridge](img/nightcode-open-project.png)
![Testing apps - core.clj](img/nightcode-welcometoclojurebridge-core.png)


다음 단계는 창에 있는 코드를 실행하는 것입니다.
하단의 "Run with REPL"를 누르세요.
시간이 다소 걸릴 수 있습니다. 관련된 앱의 코드를 다운받을 것입니다.
`Retrieving ...`으로 시작하는 라인을 볼 수 있습니다.
결국, REPL은 `user=>` 프롬프트를 보여주면서 시작합니다.
프롬프트가 보이면,"Reload" 버튼을 눌러보세요.


![Testing apps - start repl](img/nightcode-welcometoclojurebridge-run-with-repl.png)
![Testing apps - repl started](img/nightcode-repl-started.png)
![Testing apps - repl reload](img/nightcode-repl-reload.png)


재밌는 환영 메시지를 볼 수 있습니다.

![Testing apps - welcome](img/testing-welcomeclojurebridge.png)

#### 앱 테스트하기 - turtle walk

샘플 하나만 더 해봅시다.
좌측의 디렉터리에서
`welcometoclojurebridge` - `src` - `clojurebridge-turtle` -
`walk.clj`를 누르세요 . `walk.clj`파일은 오른쪽에 나타날 것입니다.
앞서 했던대로, "Reload" 버튼을 누르세요.

![Testing apps - walk code](img/nightcode-turtle-walk.png)
![Testing apps - walk reload](img/nightcode-turtle-walk-reload.png)


거북이의 초기 이미지가 나타날 것입니다.
중앙의 작은 삼각형이 *거북이*입니다.


`(forward 40)`를 하단의 repl에 입력하세요.
거북이가 위로 움직이는 것을 볼 수 있습니다.

![Testing apps - forward](img/nightcode-turtle-forward-40.png)



#### 성공!

축하드립니다! 첫번째 클로저 앱을 열어 실행해봤습니다. 또한 설치와 설정 모두 완료했습니다!


거북이(*작은 삼각형*)에 대해 더 궁금하시다면,
[Turtle App API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md)과
[How to Walk Turtles](https://github.com/ClojureBridgeSeoul/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)를 참고하세요