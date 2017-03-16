windows 7 설치
===============

* 명령 프롬프트 열기
* Git 설치하기
* Git 환경설정하기
* Java 설치하기
* Leiningen 설치하기
* Nightcode 설치하기
* 설치 확인하기
* 문제 해결하기

## 명령 프롬프트 열기
이 설명과 수업을 진행하기 위해서는 명령 프롬프트를 열어야 합니다. 명령 프롬프트는 컴퓨터에 명령하기 위한 텍스트 기반의 인터페이스입니다. 시작메뉴에서 검색창에 "command"를 입력하고 다음 스크린샷에 보이는 것처럼 "Command Prompt"프로그램을 선택하세요:

![명령 프롬프트 열기](img/win7/starting-command-prompt.png)

"Command Prompt"를 선택하면 화면이 다음과 비슷하게 보일겁니다.

![명령 프롬프트](img/win7/command-prompt.png)

이전에 명령 프롬프트를 써본 적이 없다면 [명령 프롬프트 기본내용](http://dosprompt.info/)을 읽고오세요. 남은 설치를 위해 명령 프롬프트에서 명령을 실행하라고 지시할 것입니다. 이 말은 "명령 프롬프트에 명령을 입력하고 엔터키를 누르세요"라는 뜻입니다.

다른 운영체제에서 명령 프롬프트는 터미널이라고도 불립니다. 우리는 터미널, 명령  프롬프트, 명령줄을 같은 의미로 사용할 것입니다.

## Git 설치하기

명령 프롬프트에서 `git --version`명령어를 이용해서 Git이 이미 설치되어 있는지 확인하세요.
만약 설치되어 있지 않다면 [git-scm.com Windows 다운로드 페이지](http://git-scm.com/download/win)에서 다운받아서 설치하세요.

설치 후에 새로운 명령 프롬프트에서 `git --version`명령을 실행하세요. 버전 넘버가 보인다면 제대로 설치된 것입니다.

`'git' is not recognized as an internal or external command`라는 메시지가 보인다면, 
PATH 변수를 적절히 업데이트하기 위해 다음 스텝을 따라하세요:
* "My Computer"을 우클릭 한 후 "Properties"를 선택하세요.
* "Advanced Tab"을 클릭한 다음 "Environment Variables"를 클릭하세요.
* PATH 항목을 선택한 다음 "Edit"을 클릭하세요.
* 밑으로 스크롤 하면서 "...\Git..."을 포함하는 파일 경로가 있는지 체크하세요.
* 경로가 존재한다면:
  * "My Computer"창이 닫힐 때까지 "Okay"를 클릭하세요.
  * 새로운 명령 프롬프트 창을 열어서 `git --version`을 다시 실행해보세요. 만약 실패한다면 컴퓨터를 다시 시작해서 재시도 해보세요.
* 경로가 존재하지 않는다면:
  * 설치 중에 git의 설치 위치를 변경하지 않았다면 줄의 끝에 ";C:\Program Files (x86)\Git\cmd"를 추가하세요. 파일 경로 사이에 세미콜론을 추가하세요. 줄 사이에는 공백이 없어야 합니다.
  * "My Computer"창이 닫힐 때까지 "Okay"를 클릭하세요.
  * 새로운 명령 프롬프트 창을 열어서 `git --version`을 다시 실행해보세요. 만약 실패한다면 컴퓨터를 다시 시작해서 재시도 해보세요.

## Git 환경설정하기

Git을 써본 적이 있다면 이미 user.name과 user.email이 설정되어 있을 것입니다.
그렇지 않다면, 다음을 명령 프롬프트에 입력하세요:

```
git config --global user.name "Your Actual Name"
git config --global user.email "Your Actual Email"
```
팁: git, github, ssh에서 같은 이메일주소를 사용하세요.

명령 프롬프트에 다음 내용을 입력하여 확인하세요:

`git config --get user.name`
Expected result:
`your name`

`git config --get user.email`
Expected result:
`your email address`


## Java 설치하기

[Leiningen Windows 설치 사이트](http://leiningen-win-installer.djpowell.net/)에 들어가세요. Java설치를 위한 링크 하나와 "leiningen-win-installer"를 위한 링크 하나가 보여야 합니다. Java 링크를 클릭하세요. 다음과 같은 화면이 보일 것입니다:

![Java 다운로드 첫 페이지](img/win/java-download1.png)

그림에서 보이듯이 "Java Platform (JDK)" 위의 버튼을 클릭하세요. 그러면 다음 표가 있는 페이지로 이동할 것입니다:

![Java 다운로드 두번째 페이지](img/win/java-download2.png)

라디오 버튼을 클릭하여 사용권 계약에 동의하고 두가지 윈도우중 하나를 선택하여 다운로드하세요. 32비트 윈도우를 사용한다면 "Windows x86"을 선택하세요. 64비트 윈도우를 사용한다면 "Windows x64"를 선택하세요.

사용하는 윈도우가 32비트인지 64비트인지 모른다면 Control Panel (시작메뉴-Control Panel)에 들어가서 "System and Security"를 선택한 다음 "System"을 선택하세요. 다음과 같은 창을 볼 수 있을 것입니다:

![내 컴퓨터 속성](img/win7/system-properties.png)

"System Type" 옆에서 32비트 또는 64비트 중 어느 것을 사용하고 있는지 확인하세요.

올바른 Java버전을 다운받았다면 다운받은 실행 파일을 실행하여 Java를 설치하세요. 설치마법사를 따라하세요.

## Leiningen 설치하기

Leiningen은 명령 프롬프트에서 클로저 프로젝트를 관리하기 위해 사용하는 툴입니다. 
[Leiningen Windows 설치 사이트](http://leiningen-win-installer.djpowell.net/)에 돌아가서 "leiningen-win-installer" 파일을 다운받으세요. 실행파일을 실행하고 Leiningen Windows Installer 사이트의 "Detailed installation" 섹션을 따라하세요. 설치가 끝나면 "Finish"를 클릭하기 전에 "Run a Clojure REPL"을 체크하세요. Leiningen Windows installer 사이트에서 본 창과 비슷한 터미널창이 열린다면 성공한 것입니다.

## Nightcode 설치하기

[Nightcode 공개 사이트](http://github.com/oakes/Nightcode/releases)에 들어가세요. 페이지에서 Nightcode-2.1.0.jar와 같이 버전 번호와 특정 버전의 Nightcode를 다운받기 위한 링크를 볼 수 있을 것입니다. `.jar`로 끝나는 링크를 클릭하면 `Nihtcode-x.y.z.jar`파일을 다운로드할 것입니다.
 
> 특정 프로그램을 배포하는 플랫폼을 이용하지 마세요.
> Jar 아카이브를 사용하세요.
> Jar 아카이브는 시작하기 훨씬 쉽습니다.

다운로드가 끝나면 에디터를 실행하세요.
에디터를 실행하기 위해서는 다운로드 폴더(혹은 당신이 파일을 저장한 곳)로 들어가서 `java` 명령어를 사용해서 Nightcode-x.y.z.jar 파일을 실행하세요.


명령 프롬프트창을 열어 다음 명령들을 입력하세요.

```bash
cd Downloads
java -jar Nightcode-2.1.0.jar
```

![Nightcode](img/nightcode-startup.png)


## 설치 확인하기

이 워크샵동안 필요한 Java, Leiningen, Nightcode, Git을 설치해보았습니다. 시작하기 전에 이것들을 테스트해 봅시다.

#### Leiningen 테스트하기

새로운 명령 프롬프트창을 열어 다음 명령을 실행해 보세요:

```bash
lein new myproject
```

이 명령어는 `myproject`라는 클로저프로젝트를 구성하는 파일이 있는 새로운 프로젝트를 생성합니다. 
보통 클로저 코드는 이러한 클로저 프로젝트 안에 존재합니다.

다음 명령을 실행해 보세요:

```bash
cd myproject
lein repl
```
처음에는 시작하는데 시간이 오래 걸릴 수 있습니다.
Leiningen은 클로저를 실행하는데 필요한 라이브러리들을 다운로드합니다.
Leiningen이 실행되면 터미널에서 `user=>` 프롬프트를 볼 수 있을 것입니다.

![lein repl 테스트하기](img/win/testing-lein-repl.png)

이제 우리는 곧 배울 __REPL__을 사용할 준비가 되었습니다.
REPL은 클로저를 위한 특별한 터미널입니다.

REPL 프롬프트에서 `(+1 1)`을 입력하고 엔터키를 눌러보세요. 정답인 `2`를 얻었나요? 훌륭합니다!

당신의 leiningen 설치는 괜찮아보입니다. 이제 키보드에서 컨트롤버튼과 D버튼을 동시에 눌러보세요(단축키 : Ctrl+D). 이 단축키는 클로저 REPL에서 나와 원래의 터미널 프롬프트로 되돌려줍니다. 그러면 터미널에서는 다음 메세지를 표시할 것입니다: `user=> Bye for now!`


#### github 저장소 복제하기

새로운 명령 프롬프트창을 열어 다음 명령을 실행해 보세요:

```bash
git clone https://github.com/ClojureBridge/welcometoclojurebridge
```

이 명령은 클로저의 샘플 앱들을 포함하고 있는 `welcometoclojurebridge` 저장소를 복제합니다.
명령 프롬프트는 다음과 비슷해야 합니다:

![git 복제 테스트](img/win/testing-git-clone.png)

복제가 끝나면 같은 창에 다음 명령을 입력하세요.

```bash
cd welcometoclojurebridge
dir
```

다음과 같이 폴더/파일의 리스트를 볼 수 있을 것입니다:

```
README.md       outline         project.clj     resources       src
```


#### Nightcode 테스트하기

Nightcode가 아직 실행되어있지 않거나 닫혀있다면, 터미널에 다음 명령을 입력하여 실행하세요:

```bash
java -jar Nightcode-2.1.0.jar
```

화면 오른쪽 하단에 `(+1 1)`을 입력하세요. 다음과 같이 보여야 합니다.

![Nightcode 테스트하기](img/nightcode-repl.png)

결과로 2가 나온다면 훌륭합니다!


#### 앱 테스트하기

이제 우리는 Nightcode에서 클로저의 샘플 앱들을 열고 실행해 볼 것입니다.
왼쪽 상단 구석에서 "Import"를 클릭하고 `git clone`명령을 실행할 때 생성 된 `welcometoclojurebridge`의 디렉토리를 찾고 "Open"을 클릭하세요. 왼쪽의 프로젝트 폴더 트리에서 `src` - `welcometoclojurebridge` - `core.clj`를 클릭하세요. `core.clj`파일은 오른쪽에 열릴 것입니다.
이것이 클로저 프로그램입니다.

![Testing apps - click import](img/nightcode-click-import.png)
![Testing apps - open welcometoclojurebridge](img/nightcode-open-project.png)
![Testing apps - core.clj](img/nightcode-welcometoclojurebridge-core.png)


다음 단계는 창에 보이는 코드를 실행해 보는 것입니다.
하단의 "Run with REPL"를 클릭하세요.
시간이 조금 걸릴 수 있습니다.
REPL이 시작되면 `user=>` 프롬프트가 나타날 것입니다.
일단 프롬프트가 표시되면 "Reload"버튼을 클릭하세요.


![Testing apps - start repl](img/nightcode-welcometoclojurebridge-run-with-repl.png)
![Testing apps - repl started](img/nightcode-repl-started.png)
![Testing apps - repl reload](img/nightcode-repl-reload.png)


재미있는 환영 메세지를 보게 될 것입니다.

![Testing apps - welcome](img/testing-welcomeclojurebridge.png)


샘플 하나만 더 해봅시다.
왼쪽의 디렉토리 트리에서 `welcometoclojurebridge` - `src` - `clojurebridge-turtle` - `walk.clj`를 클릭하세요. `walk.clj` 파일이 오른쪽에 열릴 것입니다.
앞에서 해본 대로 "Reload" 버튼을 눌러보세요.

![Testing apps - walk code](img/nightcode-turtle-walk.png)
![Testing apps - walk reload](img/nightcode-turtle-walk-reload.png)

거북이 앱의 초기 이미지가 나타날 것입니다.
중앙에 있는 작은 삼각형이 *거북이*입니다.


창 하단의 repl에 `(forward 40)`을 입력하세요.
거북이가 위로 움직이는 것을 볼 수 있을 것입니다:

![Testing apps - forward](img/nightcode-turtle-forward-40.png)


#### 성공!

축하합니다! 처음으로 클로저 응용 프로그램을 열고 실행해 보았고, 설치와 설정이 모두 끝났습니다!

거북이(작은 삼각형)가 무엇을 할 수 있는지 더 알고싶다면 [Turtle App API](https://github.com/ClojureBridge/welcometoclojurebridge/blob/master/outline/TURTLE.md) 와 [How to Walk Turtles](https://github.com/ClojureBridgeSeoul/welcometoclojurebridge/blob/master/outline/TURTLE-SAMPLES.md)을 읽어보세요.


## 문제 해결하기

  Windows 7을 사용하는 학생들은 처음 `lein repl`을 실행할 때 아래의 오류가 발생할 수 있습니다.

  ```
  Address family not supported b y protocol family: connect
  ```

  에러메세지가 다음과 같다면 <http://stackoverflow.com/a/21383865>를 확인하세요.
  

  이 에러는 Relevant Knowledge라고 불리는 일종의 스파이웨어가 트래픽을 차단하면서 `lein`명령이 필요한 내용을 다운로드 할 수 없기 때문에 발생합니다.
  이 문제를 해결하기 위해서는 Relevant Knowledge를 삭제해야 합니다.
  이는 유저(소유자 혹은 관리자)의 비밀번호가 필요합니다.
  종종 학생들은 이러한 권한에 대해서 들어본 적이 없을 수 있습니다.
  이에 대비하세요.
  
