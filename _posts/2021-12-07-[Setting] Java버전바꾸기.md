---

title:  "[Setting] Java 버전 바꾸기"
excerpt: "☕️ Java 버전 바꾸는 방법 for Mac"

categories:
  - Setting

last_modified_at: 2021-12-07T08:06:00-05:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true

---



## 자바 버전 바꾸기

Mac OS에는 여러 버전의 자바를 설치하고, 상황에 따라 버전을 바꾸어 가며 사용할 수 있다.

<br />

## 자바 여러 버전 설치하는 방법

내가 사용 했던 방식은 총 두가지 이다.

- 홈페이지 가서 다운로드 받기
- homebrew로 설치하기

<br />

### 1. 홈페이지 가서 다운로드 받기

<a href="https://www.oracle.com/java/technologies/downloads/" target="_blank"> ☕️ Java 홈페이지 </a>에 가서 자신이 필요한 파일을 다운로드 받은 후, dmg를 설치하면된다. 

<br />

### 2. homebrew로 설치하기

아래의 명령어를 순차적으로 입력하면 된다.

```s
#brew update하기
$ brew update

#adoptopenjdk/openjdk 추가하기
$ brew tap adoptopenjdk/openjdk

#설치 가능한 모든 JDK 찾기
$ brew search jdk

#원하는 버전 설치 하기 
$ brew install --cask adoptopenjdk14
```

<br />

위의 두가지 방법으로 설치 하면 아래와 같은 결과를 얻을 수 있다. 

```s
#현재 설치된 자바 버전 보기
$ /usr/libexec/java_home -V
```

![image](https://user-images.githubusercontent.com/42812764/145034118-c086f252-8a67-40c3-97f3-55c2d968740e.png)



<br />

<br />

<br />

## 자바 버전 바꾸기

자바의 버전을 먼저 확인하고, 위에서 확인한 이미 필요한 버전을 확인한 후 변경해 주면 된다.

```s
#Java 버전 확인하기
$ java -version
```

![image](https://user-images.githubusercontent.com/42812764/145034000-aec5e92a-667a-45e9-92c1-3af1ea603ead.png)

<br />

그후 .zshrc를 수정해서 환경 변수를 수정해 주면 된다. 

```s
#.zshrc파일 열기
vi ~/.zshrc


#맨 아래에 추가해주기
export JAVA_HOME_11=$(/usr/libexec/java_home -v11)
export JAVA_HOME_14=$(/usr/libexec/java_home -v14)

export JAVA_HOME=$JAVA_HOME_14
export PATH="$PATH:$HOME/.rvm/bin"


# 적용시키기
$ source ~/.zshrc

```



그럼 아래과 같이 버전이 변경 된 것을 확인 할 수 있다! 

생각보다 간단해서 겁먹지 말고 슉슉 바꾸면 될 듯하다.

![image](https://user-images.githubusercontent.com/42812764/145031700-5546f61f-0ddb-4941-819f-92564fb1b2d4.png)

![image](https://user-images.githubusercontent.com/42812764/145032367-1363ba1a-430b-44b3-817d-13f3037bdf9f.png)



<br />

<br />

<br />

<br />

<br />





🌿 Reference

- <a href="https://llighter.github.io/install-java-on-mac/" target="_blank">llighter.github.io</a>
- <a href="https://yoonpunk.tistory.com/11" target="_blank">yoonpunk.tistory.com</a>

