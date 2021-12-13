---

title:  "[Project] Nuxt.js 프로젝트 시작하기"
excerpt: "😊 Nuxt.js 처음 사용해보기"

categories:
  - Project

last_modified_at: 2021-12-13T08:06:00-05:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true

---

<br />

친구와 프로젝트를 하나 시작해보려고 한다.😊

이번에 프론트앤드로 Nuxt.js를 사용하게 되었다. ex) <a href="https://nuxtjs.org/" target="_blank">NustJs 공식홈페이지</a>

그래서 처음으로 프로젝트를 생성하고 실행하는 과정을 정리해보고자 한다. 



<br />

## yarn 설치하기

```s
#brew로 yarn 설치하기
$ brew install yarn

#설치 되었는지 확인하기
$ yarn
```

![image](https://user-images.githubusercontent.com/42812764/145818656-96a25c2a-d2ac-4874-9d89-4791f3f0714f.png)

위와 같이 설치가 되었음을 알 수 있다.

<br />



## Next.js 프로젝트 만들기

```s
#프로젝트 만들기
#yarn create nuxt-app <프로젝트 이름>
$ yarn create nuxt-app bo-naem-front
```

![image](https://user-images.githubusercontent.com/42812764/145819369-e4c778b7-0c70-44ed-bcd5-09e306853f48.png)

중간에 필요한 옵션들을 설정해주면 아래와 같이 프로젝트가 생성됨을 확인 할 수 있다.

![image](https://user-images.githubusercontent.com/42812764/145819510-ee15ed25-66d5-44ad-b4aa-ef20084991f5.png)

<br />

<br />

## Next.js 프로젝트 만들기

```
#디레토리 이동
$ cd bo-naem-front

#프로젝트 실행
$ yarn dev
```

![image](https://user-images.githubusercontent.com/42812764/145838793-12656acb-affe-4170-a1ad-776cb2976e78.png)

위의 사진과 같이 실행이 되면,

아래 사진 처럼 주소창에 <a href="http://localhost:3000/" target="_blank">localhost:3000</a> 를 입력하면 Vuetify.js가 떠있는 것을 확인 할 수 있다. 

깔끔하게 프로젝트 생성 성공!✨

<img width="1480" alt="스크린샷 2021-12-13 오후 10 20 50" src="https://user-images.githubusercontent.com/42812764/145819959-2d257dd1-13d4-4b9a-a103-a30d292b7f64.png">

<br />

<br />

<br />



🌿 Reference

- <a href="https://fkkmemi.github.io/nuxt/nuxt-002-install/" target="_blank">fkkmemi.github.io</a>
- <a href="https://velog.io/@brviolet/Nuxt.js-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-1.-%EC%84%A4%EC%B9%98" target="_blank">velog.io/@brviolet</a>

