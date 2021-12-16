---

title:  "[Project] MAMP 로컬 서버 구축하기"
excerpt: "🐘 MAMP 짱짱맨"

categories:
  - Project

last_modified_at: 2021-12-16T08:06:00-05:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true

---

<br />

## MAMP란?

![image](https://user-images.githubusercontent.com/42812764/146374451-059fdf3c-c971-4bcb-b9b3-617aa9e3b149.png)



MAMP를 사용하면 로컬에 PHP,웹 서버, MySQL서버 환경 구축을 한번에 할 수 있다.

이번 프로젝트를 진행할 때 MAMP를 사용하기로 결정!

<br />

<br />

## MAMP 설치

🐘 <a href="https://www.mamp.info/en/mamp/mac/" target="_blank">MAMP 홈페이지</a>에 가서 자신의 컴퓨터 환경에 알맞게 다운로드 한 뒤, pkg 파일을 설치하면 된다.

<img width="732" alt="스크린샷 2021-12-16 오후 9 16 57" src="https://user-images.githubusercontent.com/42812764/146371229-a4110a4b-cb3f-4bd5-af96-c0204013b5bb.png">

<br />

<br />

## MAMP 사용하기

설치한 뒤에 처음으로 열어보면, 아래와 같은 모습이다. 오른쪽의 start 버튼을 누르기 전에 Preferences에서 자신이 활용할 데이터 베이스 포트와 맞도록 연결시켜야 한다.

<img width="648" alt="스크린샷 2021-12-16 오후 9 46 58" src="https://user-images.githubusercontent.com/42812764/146374864-9a4b8d90-505d-43db-8887-c96b15f565ea.png">

Mysql를 사용할 계획이라 80이랑 3306으로 포트를 설정하였다. 

<img width="648" alt="스크린샷 2021-12-16 오후 9 47 06" src="https://user-images.githubusercontent.com/42812764/146375256-c6fe1930-5fdc-472a-b7e2-1b09eac7ffac.png">

그 후 start버튼을 누르면, 아래와 같은 페이지가 뜬다.

<img width="1494" alt="스크린샷 2021-12-16 오후 9 30 50" src="https://user-images.githubusercontent.com/42812764/146375559-efba25fc-b753-43ae-9e3a-37b5b964e958.png">

아직 아무것도 작성하지 않았기 때문에 로컬 페이지는 아래와 같이 뜨고, 

<img width="1352" alt="스크린샷 2021-12-16 오후 9 30 30" src="https://user-images.githubusercontent.com/42812764/146375800-8bdcdad7-c803-4412-ab1a-d3b7a75ac4d4.png">

phpMyAdmin에 database를 만들고 계획했던 테이블들을 만들어 주면 끝!

<img width="1352" alt="스크린샷 2021-12-16 오후 9 30 24" src="https://user-images.githubusercontent.com/42812764/146376072-30230415-e10a-40cc-ae70-d44bf6358a66.png">



<br />

<br />

<br />

<br />

P.S 데이터 베이스  ERD 그릴 때 📝<a href="https://aquerytool.com/" target="_blank">aquerytool</a>를 사용했다. 

그리기도 쉽고 그리고 나서 쿼리문 까지 다 만들어주기 때문이다.하지만 이번에 보니 유로로 바뀐 것 같다..ㅠ 혹시 체험판 사용할 수 있는지 확인해보고 사용하시는 걸 추천한다!

