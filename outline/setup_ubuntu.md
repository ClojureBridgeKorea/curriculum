우분투 설정
==========

* 터미널 시작하기
* Git 설치하기
* Git 설정하기
* Java 설치하기
* Leiningen 설치하기
* Nightcode 설치하기
* 설정 테스트하기


## 터미널 시작하기

이 강의와 앞으로의 수업을 진행하기에 앞서, 먼저 터미널(또는 명령창)을 실행할 필요가
있습니다. 터미널은 텍스트 기반의 프로그램으로, 컴퓨터에 명령을 내릴 때
사용합니다. 터미널을 실행하려면, 화면의 좌측 최상단에 위치한 "Dash Home" 버튼을 클릭한 후,
`Terminal`을 타이핑합니다. 그렇지 않으면, 언제든 `CTRL-ALT-T`를 눌러 터미널을 직접 실행할
수도 있습니다. 이전에 터미널을 사용해 본 적이 없으면, [커맨드 라인 기본
학습하기](http://blog.teamtreehouse.com/command-line-basics)를 참조해 주십시오.

지금 직접 터미널을 실행해 보세요. 다음과 같은 모습이 보일 겁니다.

![blank terminal](img/ubuntu/blank_terminal.png)

프롬프트(이 뒤에 명령을 입력하게 된다)의 모양은 다를 수 있습니다. 하지만 일반적으로는
컴퓨터명과 사용자명 그리고 현재 사용자가 위치하고 있는 폴더나 디렉토리 명이 표시됩니다.
 
이후로 터미널에서 명령을 실행하라는 의미는, 터미널에 명령을 타이핑한 후 리턴 키를 누르라는
의미로 이해하면 됩니다.


## Git 설치하기

`git version` 명량을 실행해, Git이 이미 설치되어 있는지 확인해 보세요. "`git` 명령을 찾을
수 없습니다."라는 메시지가 보이면. 터미널에서 다음 명령을 실행해 `git`을 설치해 줍니다.

 
```bash
sudo apt-get install git
```

## Git 설정하기

이전에 Git을 사용해 본 적이 있다면, `user.name`과 `user.email`이 이미 설정되어 있겠지만,
그렇지 않으면 터미널에서 다음과 같이 입력해 줍니다.
  
```bash
git config --global user.name "Your Actual Name"
git config --global user.email "Your Actual Email"
```

팁: git과 github, ssh에 동일한 이메일 주소를 사용하세요.


터미널에서 다음과 같이 입력해, 입력 내용을 확인해 보세요.
 
`git config --get user.name`
기대하는 결과 
`여러분의 이름`

`git config --get user.email`
기대하는 결과:
`여러분의 이메일 주소`


## Java 설치하기

우분투에는 기본적으로 OpenJDK가 이미 설치되어 있습니다만, 새로운 버전의 Nightcode가
OpenJDK에서는 잘 실행되지 않는 문제가 있습니다. 따라서 앞으로 설명할 내용을 익히려면,
다음과 같이 Oracle JDK 8을 별도로 설치해 주어야 합니다.

```bash
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
(follow the instruction)
```

이제 우분투에 Oracle JDK 8이 설치되었으니, 새로 설치된 Oracle JDK 8을 사용할 수 있도록 다음의 명령을 한번 더 실행해 주어야 합니다. 

```bash
sudo update-alternatives --config java
(choose /usr/lib/jvm/java-8-oracle/jre/bin/java)
```

터미널에서 `java -version`을 실행해 보세요. 다음과 같은 모습이 보일 겁니다.

![Java version](img/ubuntu/ubuntu-java-version.png)

마이너 버전 넘버는 여러분이 보는 것과 다를 수 있습니다. 하지만, `1.8.0` 부분은 같을
겁니다. 아울러 `Java(TM) SE Runtime Environment`라는 메시지도 보일 겁니다.

또 다른 방법으로, 자바 개발자 도구(JDK)를 [Java SE
Downloads](http://www.oracle.com/technetwork/java/javase/downloads/index.html)에서 직접
다운로드 받을 수도 있습니다. 이 경우에는 설치한 후에 `JAVA_HOME`과 `PATH` 환경 변수를
적절하게 설정해 줄 필요가 있습니다.


## Leiningen 설치하기

Leiningen은 클로저 프로젝트를 관리하기 위한 커맨드 라인 툴입니다.

먼저 [Leiningen 웹사이트](http://leiningen.org/)로 갑니다. "Install" 항목 아래에 `lein
script` 링크가 보일 겁니다. 이 링크에서 마우스 오른쪽 버튼을 클릭한 후, "Save Link As..."
메뉴를 선택합니다. 이제 그 파일을 여러분의 다운로드 디렉토리에 저장하시면 됩니다

![Leiningen site](img/leiningen_site.png)
![Leiningen site](img/lein_install.png)

그 후에 터미널에서 다음의 명령을 실행하세요. 여러분의 패스워드를 입력하라는 메시지가 나올
겁니다.
 
```
sudo mkdir -p /usr/local/bin/
sudo mv ~/Downloads/lein* /usr/local/bin/lein
sudo chmod a+x /usr/local/bin/lein
export PATH=$PATH:/usr/local/bin
```

위의 명령을 실행한 후에, `lein version` 명령을 실행해 봅니다. 이 명령을 처음 실행할 때는,
Leiningen이 필요로 하는 파일들을 먼저 다운로드해야 해서, 명령을 수행하는데 시간이 좀
걸립니다. 성공적으로 설치를 마쳤다면 운이 좋으신 겁니다! 그렇지 않은 경우에는 조교에게
도움을 요청하세요.

 
## Nightcode 설치하기

먼저 [Nightcode 배포 사이트](http://github.com/oakes/Nightcode/releases)로 갑니다. 이
페이지에는, 예를 들면 Nightcode-2.1.0.jar와 같은, 다양한 버전의 Nightcode를 다운로드할 수
있는 링크들을 볼 수 있습니다.

> 특정 운영체제를 위한 바이너리 버전은 다운로드하지 마세요.
> jar로 끝나는 링크를 선택하세요.
> jar 파일을 다운로드하는 것이 시작하기에 더 쉽습니다.

다운로드가 끝나면 에디터를 시작하세요. 에디터를 시작하려면, 여러분의 다운로드
디렉토리(브라우저에서 파일을 다운로드 받은 곳)로 가서, `java` 명령을 사용해
`Nightcode-x.y.z.jar` 파일을 실행합니다.


터미널을 연 후, 다음의 명령을 실행해 줍니다. 

```bash
cd ~/Downloads/
java -jar Nightcode-2.1.0.jar
```

![Nightcode](img/nightcode-startup.png)


## 설정 테스트하기

여러분은 지금까지 이 강의를 위해 필요한 모든 도구들, 즉 Java와 Leiningen, Nightcode, Git을
컴퓨터에 설치했습니다. 본격적으로 시작하기 전에, 먼저 설치한 모든 도구들을 테스트해
봅니다.


#### Leiningen 테스트하기

터미널을 열고 다음의 명령을 실행합니다.

```bash
lein new myproject
```

`myproject`라는 새로운 프로젝트가 생성되었을 겁니다. `myproject`에는 클로저 프로젝트를
구성하는 여러 파일들이 담겨 있습니다. 일반적으로 클로저 코드는 이러한 클로저 프로젝트 안에
놓이게 됩니다.

다음의 명령을 실행합니다.

```bash
cd myproject
lein repl
```

위의 명령이 처음 실행될 때는 시간이 좀 걸릴 수 있습니다. Leiningen이 클로저를 실행하는데
필요로 하는 라이브러리 파일들을 먼저 다운로드하기 때문입니다. Leiningen이 시작되면
터미널에 `user=>`라는 프롬프트가 다음과 같이 보일 겁니다.

![Testing lein repl](img/ubuntu/testing-lein-repl.png)

이제 여러분은 앞으로 배우게 될 __REPL__을 사용할 준비가 되었습니다. 

REPL 프롬프트에서 `(+ 1 1)`을 입력한 후 리턴 키를 눌러 보세요. `2`라는 답이 보이나요?
좋습니다!
  
Leiningen 설치는 잘되었습니다. 이제 Control 키와 D 키를 동시에 눌러 보세요(Ctrl+D로
표기). 그러면 클로저 REPL을 빠져 나와, 터미널 프롬프트로 돌아오게 됩니다. 이때 REPL은
`user=> Bye for now!`라는 메시지를 보여 줍니다.
  

#### github 저장소 복제하기

터미널을 열고 다음 명령을 실행합니다.

```bash
git clone https://github.com/ClojureBridge/welcometoclojurebridge
```

그러면 샘플 클로저 앱 코드가 담겨 있는 `welcometoclojurebridge` 저장소가 자신의 컴퓨터로
복제됩니다. 터미널은 다음과 같은 모습일 겁니다.

![Testing git clone](img/ubuntu/testing-git-clone.png)

그 다음에 같은 터미널에서 다음의 명령을 입력해 보세요.

```bash
cd welcometoclojurebridge
ls
```

디렉토리와 파일들의 리스트가 다음과 같이 보일 겁니다.

```
README.md       outline         project.clj     resources       src
```


#### Nightcode 테스트하기


Nightcode를 아직 시작하지 않았거나 또는 이미 닫은 상태라면, 터미널에서 다음의 명령을
입력해 시작해 줍니다.
 
```bash
java -jar Nightcode-2.1.0.jar
```

화면의 우측 하단 창에 `(+ 1 1)`라고 입력해 보세요. 다음과 같은 모습으로 보일 겁니다.

![Testing Nightcode](img/nightcode-repl.png)

`2`라는 결과가 보인다면, Nightcode가 제대로 작동하고 있는 겁니다. 축하합니다!
 

### 앱 테스트하기

이제 Nightcode에서 샘플 클로저 앱을 열고 실행해 보겠습니다.  상단 좌측 구석의 "Import"
메뉴를 클릭한 후, 샘플 코드가 있는 디렉토리 `welcometoclojurebridge`를 선택하세요. 이
디렉토리는 `git clone` 명령을 통해 이미 앞에서 만들어 놓았던 디렉토리입니다.

"Open." 메뉴를 클릭한 후, 좌측의 프로젝트 디렉토리 트리에서 `src` -
`welcometoclojurebridge` - `core.clj` 파일을 선택하세요. `core.clj` 파일이 우측 창에서
열릴 겁니다. 이 파일의 내용이 바로 클로저 코드의 모습입니다.

![Testing apps - click import](img/nightcode-click-import.png)
![Testing apps - open welcometoclojurebridge](img/nightcode-open-project.png)
![Testing apps - core.clj](img/nightcode-welcometoclojurebridge-core.png)

다음 단계는 창 안에 보이는 코드를 실행해 보는 것입니다. 아래의 "Run with REPL"을 클릭해
보세요. 시간이 좀 걸리겠지만, REPL이 시작되고 `user=>` 프롬프트가 보일 겁니다. 프롬프트가
보이면 "Reload" 버튼을 클릭해 보세요.

![Testing apps - start repl](img/nightcode-welcometoclojurebridge-run-with-repl.png)
![Testing apps - repl started](img/nightcode-repl-started.png)
![Testing apps - repl reload](img/nightcode-repl-reload.png)

다음과 같은 재미있는 환영 메시지가 보일 겁니다.

![Testing apps - welcome](img/testing-welcomeclojurebridge.png)

샘플을 한 개 더 보도록 합니다. 좌측의 디렉토리 트리에서 `welcometoclojurebridge` - `src` -
`clojurebridge-turtle` - `walk.clj`를 선택하세요. 우측 창에 `walk.clj` 파일이 열릴
겁니다. 앞에서 했던 것처럼, "Reload" 버튼을 누릅니다.

![Testing apps - walk code](img/nightcode-turtle-walk.png)
![Testing apps - walk reload](img/nightcode-turtle-walk-reload.png)

거북이의 초기 이미지가 화면에 나타날 겁니다. 중앙에 있는 작은 삼각형이 *거북이*입니다.

창 하단의 REPL에 `(forward 40)`을 입력해 보세요. 거북이가 위로 움직이는 것을 볼 수 있습니다.

![Testing apps - forward](img/nightcode-turtle-forward-40.png)



#### 성공입니다!

축하합니다! 여러분은 처음으로 클로저 앱을 열고 실행해 보았고, 설치와 설징 모두를
끝냈습니다!

거북이(*작은 삼각형*)가 어떤 동작을 할 수 있는지 그리고 움직이는 방법에 대해 더 알고
싶으면, [Turtle App
API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md)와
[How to Walk
Turtles](https://github.com/ClojureBridgeSeoul/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)를
참조하세요.