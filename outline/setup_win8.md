Windows 8 설정
===============

* 명령 프롬프트 실행
* Git 설치
* Git 설정
* Java 설치
* Leiningen 설치
* Nightcode 설치
* 설정 테스트
* Troubleshooting

## 명령 프롬프트 실행

이번 안내에서, 그리고 많은 수업에서 명령 프롬프트를 실행해야 합니다. 명령 프롬프트는 텍스트 기반의 컴퓨터에 인터페이스입니다. "Windows" 화면("시작 화면"")에서 "command" 를 입력하세요. 화면과 같이 "명령 프롬프트"를 선택하세요.

![Starting a command prompt](img/win8/starting-command-prompt.png)


"명령 프롬프트"를 선택하면, 아래와 같은 화면이 나옵니다:

![Command prompt](img/win8/command-prompt.png)

전에 명령 프롬프트를 사용해본 적이 없다면, [reading up on command prompt basics](http://dosprompt.info/)를 읽어보길 바랍니다. 앞으로 설정할 때는, 명령 프롬프트에서 명령을 실행하십시오. 명령을 실행하라고 할 때, "명령 프롬프트에 명령을 입력하고 Return 키를 누르세요"

다른 운영체제에는, 명령 프롬프트를 터미널이라 부릅니다. 터미널, 명령 프롬프트, 그리고 커맨드 라인이라는 단어를 같은 의미로 사용할 것 입니다.

## Git 설치

이미 Git 이 설치되어 있다면 새 명령 프롬프트에 'git --version' 명령을 확인해보세요.
설치되어 있지 않다면, [git-scm.com Windows download page](http://git-scm.com/download/win) 에서 다운로드 받아 설치합니다.

설치 후, 'git --version' 명령을 명령 프롬프트에 시도해보세요. 버전이 확인한다면, Git 이 제대로 설치된 것 입니다.

`'git' is not recognized as an internal or external command` 이런 메세지를 보면, PATH 변수를 올바르게 수정해봅시다.
* "내 컴퓨터"를 우클릭하고 "속성"을 선택하세요.
* "Advanced Tab" 을 클릭하고 "환경 변수" 버튼을 클릭하세요.
* Path 항목을 선택하고 "수정"을 클릭하세요.
* Path 값의 끝으로 스크롤하고 그 끝에 "...\Git..." 을 포함하는 파일 경로가 있는지 확인해봅니다.
* 경로가 있다면,
  * "확인" 을 눌러 "내 컴퓨터" 대화상자를 닫습니다.
  * 새 명령 프롬프트를 열고 `git --version` 명령을 다시 실행합니다. 실패한다면, 컴퓨터를 재시작하고 다시 시도해보세요.
* 경로가 없다면,
  * Git 설치 중에 설치 경로를 바꾸지 않았다면, ";C:\Program Files (x86)\Git\cmd" 를 라인 끝에 추가하세요. 라인에 공백이 있어선 안되고 라인과 파일 경로 사이에 세미콜론을 추가하는 것을 확실히 확인하세요.

  * "확인" 을 눌러 "내 컴퓨터" 대화상자를 닫습니다.
  * 새 명령 프롬프트를 열고 `git --version` 명령을 다시 실행합니다. 실패한다면, 컴퓨터를 재시작하고 다시 시도해보세요.

Git 를 사용한 적이 있다면, 이미 user.name 과 user.email 이 설정되었을 것 입니다.
아니라면, 명령 프롬프트에 아래와 같이 해보세요.

## Git 설정

```
git config --global user.name "이름"
git config --global user.email "메일주소"
```
팁: 깃, 깃헙 그리고 ssh 에 같은 메일 주소를 사용하세요.

명령 프롬프트에 아래와 같이 입력하여 확인해보세요.

`git config --get user.name`
예상되는 결과:
`이름`

`git config --get user.email`
예상되는 결과
`메일주소`


## Java 설치

[the Leiningen Windows installer site](http://leiningen-win-installer.djpowell.net/)로 이동하세요. 링크가 2개 있을텐데, 하나는 Java 설치이며, 다른 하나는 "leiningen-win-installer" 입니다. Java 링크를 클릭하세요. 그럼 아래와 같은 화면을 보게 됩니다.

![First page of Java download](img/win/java-download1.png)

위 화면과 보이는 것과 같이 "Java Platform (JDK)" 위에 버튼을 클릭하세요. 그럼 아래 표와 같은 페이지로 이동할 것 입니다.

![Second page of Java download](img/win/java-download2.png)

라이센스 약관에 동의하는 라디오 버튼을 클릭하고 두 Windows 중 하나를 선택해 다운로드하세요. 32-bit Windows 라면 "Windows x86" 를 선택하세요. 64-bit Windows 라면 "Windows x64"를 선택하세요.

32-bit 인지 64-bit 인지 모른다면, "Windows" 화면("시작 화면")에서 "system" 이라 입력하여 "시스템" 을 선택하세요(잘 되지 않으면, "Contorl Panel" 이라 입력하고 "제어판" 화면에서 "시스템" 을 선택하세요.). 그럼 아래와 같은 화면을 보게 됩니다.

![Windows My Computer properties](img/win8/system-properties.png)

"시스템 종류" 옆에 32-bit 인지 64-bit 인지 확인해야 합니다.

올바른 Java 버전을 다운로드가 끝나면 실행하여 Java 를 설치하세요. 설치 안내대로 따르세요.

## Leiningen 설치

Leiningen 은 Clojure 프로젝트를 관리하기 위해 커맨드 라인에 사용되는 툴입니다.

> Leiningen 설치를 위해 troubleshooing 을 보세요.

다음으로, [the Leiningen Windows installer site](http://leiningen-win-installer.djpowell.net/)으로 돌아가 "leiningen-win-installer" 로 링크된 파일을 다운받으세요. 실행 파일을 실행하고 Leiningen Windows Installer 사이트에 "Detailed installation" 을 따르세요. 설치 끝 무렵에, "Finish" 를 누르기 전에 "Run a Clojure RERL" 이 체크된 상태로 두세요. Leiningen Windows installer 사이트의 것과 같이 터미널 창이 열린다면, 잘 설치된 것 입니다.


## Nightcode 설치

[Nightcode releaes site](http://github.com/oakes/Nightcode/releases) 로 이동하세요.
해당 페이지가 열리면, Nightcode-2.1.0.jar 와 같이 버전 넘버와 Nightcode 의 특정 버전의 다운로드 링크를 볼 수 있습니다,
`.jar`로 끝나는 링크를 클릭하고 다운로드 받으세요, `Nightcode-x.y.z.jar`.

> 플랫폼에 특정한 바이너리를 다운받지 마세요.
> Jar archive 를 사용하세요.
> Jar archive 가 시작하기엔 더욱 쉽습니다.

다운로드가 끝나면, 실행해보겠습니다.
다운로드 폴더(또는 별도로 저장한 곳)로 가서 Nightcode-x.y.z.jar file 를 `java` 명령을 이용해 실행하세요.

명령 프롬프트를 열고 아래 명령을 실행합니다.

```bash
cd ~/Downloads/
java -jar Nightcode-2.1.0.jar
```

![Nightcode](img/nightcode-startup.png)


## 설정 테스트

java, Leiningen, Nightcode 그리고 Git 까지 이번 워크샵에 필요한 모든 툴을 설치하였습니다. 시작하기 전에 툴을 테스트해보겠습니다.

#### Leiningen 테스트

새 터미널을 열고 아래 명령을 실행하세요.

```bash
lein new myproject
```

Clojure 프로젝트를 구성하는 파일이 있는 `myproject` 라는 새 프로젝트가 생성됩니다.
보통, Clojure 코드는 이런 Clojure 프로젝트 내에 존재합니다.

아래 명령을 실행하세요:

```bash
cd myproject
lein repl
```

처음에는 실행하는데 오래 걸릴 수 있습니다.
Leiningen 이 Clojure 를 실행하기 위한 라이브러리를 다운로드합니다.
Leiningen 이 시작되면, 터미널에 `user=>` 프롬프트가 보일 것 입니다.

![Testing lein repl](img/win/testing-lein-repl.png)

이제, 곧 배울 __REPL__ 를 사용할 준비가 되었습니다.
REPL 은 Clojure 를 위한 특별한 터미널입니다.


REPL 프롬프트에서, `(+ 1 1)` 를 입력하고 리턴을 눌러보세요. `2` 라는 응답을 받았나요? 대단합니다!

Leiningen 설치가 잘 되었습니다. 이제 Control 버튼과 D 버튼을 함께 누르세요(줄여서 Ctrl+D). Clojure REPL 에서 나오고 일반 터미널 프롬프트로 돌아갈 것 입니다. 그리고, 터미널에 다음과 같은 메세지를 볼 것 입니다: `user=> Bye for now!`

#### Github 리포지토리 클론하기

명령 프롬프트로 가서 아래와 같은 명령을 실행하세요:


```bash
git clone https://github.com/ClojureBridge/welcometoclojurebridge
```

이 명령은 샘플 clojure apps 를 포함하고 있는 `welcometoclojurebridge` 리포지토리를 클론합니다.
명령 프롬프트는 아래 사진과 비슷하게 보일 것 입니다:

![Testing git clone](img/win/testing-git-clone.png)

작업이 끝나면, 같은 터미널에서 아래 명령을 실행합니다.

```bash
cd welcometoclojurebridge
dir
```

아래와 같은 폴더/파일 목록을 볼 것 입니다:

```
README.md       outline         project.clj     resources       src
```


#### Nightcode 테스트

Nightcode 를 아직 열어보지 않았거나 닫지 않았다면, 명령 프롬프트에 아래 명령을 입력하여 Nightcode 를 열으세요:

```bash
java -jar Nightcode-2.1.0.jar
```

화면 아래에, `(+ 1 1)` 를 입력하세요. 아래 이미지와 같이 보일 것 입니다.

![Testing Nightcode](img/nightcode-repl.png)

결과로 2 를 봤다면, 잘 동작하는 것 입니다, 대단합니다!


#### Apps 테스트

이재 Nightcode 에서 샘플 Clojure 앱을 열어 실행해보겠습니다. 왼쪽 상단에, "Import" 를 클릭하여 `git clone` 명령을 실행할 때 생성된 `welcometoclojurebridge` 디렉토리를 찾으세요. "Open" 을 클릭하세요. 왼쪽에 프로젝트 디렉토리 트리에서, `src` - `welcometoclojurebridge` - `core.clj` 를 클릭하세요. `core.clj` 파일이 오른쪽에 열릴 것 입니다. 이게 Clojure 프로그램 입니다.

![Testing apps - click import](img/nightcode-click-import.png)
![Testing apps - open welcometoclojurebridge](img/nightcode-open-project.png)
![Testing apps - core.clj](img/nightcode-welcometoclojurebridge-core.png)


다음으로 지금 코드를 실행하겠습니다. 아래에서 "Run with REPL" 를 클릭하세요. 잠시 시간이 걸릴 수 있습니다. 마침내, REPL 이 실행되고 `user=>` 프롬프트가 보일 것 입니다. 프롬프트가 보이면 "Reload" 버튼을 클릭하세요.


![Testing apps - start repl](img/nightcode-welcometoclojurebridge-run-with-repl.png)
![Testing apps - repl started](img/nightcode-repl-started.png)
![Testing apps - repl reload](img/nightcode-repl-reload.png)


재밌는 초대 메세지를 볼 수 있을 껍니다.

![Testing apps - welcome](img/testing-welcomeclojurebridge.png)


다른 샘플도 열어보겠습니다. 왼쪽에 디렉토리 트리에 `welcometoclojurebridge` - `src` - `clojurebridge-turtle` - `walk.clj` 를 클릭하세요. `walk.clj` 가 오른쪽 화면에 열릴 것 입니다. 이전과 마찬가지로, "Reload" 버튼을 클릭하세요.
Like we did before, click "Reload" button.

![Testing apps - walk code](img/nightcode-turtle-walk.png)
![Testing apps - walk reload](img/nightcode-turtle-walk-reload.png)

거북이 앱의 초기 이미지가 나타날 것 입니다. 중앙에 작은 화살표가 *거북이* 입니다.

화면 아래 repl 에 `(forward 40)` 입력하세요. 거북이가 위로 이동한 것을 볼 수 있습니다.

![Testing apps - forward](img/nightcode-turtle-forward-40.png)


#### 성공!

축하합니다! 첫 Clojure 앱을 열어 실행하였고, 설치와 설정이 모두 완료되었습니다!

거북이(*작은 화살표*)가 무엇을 할 수 있는지 알고 싶다면, [Turtle App API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md) 와 [How to Walk Turtles](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md) 를 보도록 하세요.

### Troubleshooting

* Leiningen Windows Installer 는 lein.bat 를 정상적으로 설치하지 않는 이슈가 있습니다. 이는 curl.exe 가 아래 오류로 다운로드하지 못하기 때문입니다. Leiningen Windows Installer 를 생략하세요. leiningen.org 에서 lein.bat 를 다운받아 자체 설치를 실행하세요.

> error:0307A071:bignum routines:BN_rand_range:too many iterations.
