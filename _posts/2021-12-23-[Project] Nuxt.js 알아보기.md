---

title:  "[Project] Nuxt.js 구조 알아보기"
excerpt: "Nuxt.js 천천히 해보자능"

categories:
  - Project

last_modified_at: 2021-12-23T08:06:00-05:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true
---

## 디렉토리 구조 알아보기

+수정 중.... 내가 이해한대로 정리하는 중 미완성..

<br /><br />

<div align=center>
<img src="https://user-images.githubusercontent.com/42812764/147208925-6f42ca41-23b0-44d0-b504-7571da8d19c5.png" alt="image" style="zoom:40%;"/>
</div>



#### 1. assets

**: css 파일, sccs 파일 담아 놓는 곳**

scss는 css와 비슷하지만, 구조에 맞에 괄호 맞게 사용 할 수 있어서 상대적으로 구조 파악에 훨씬 쉽다.

즉, 컴포넌트 이해가 쉽다. 안에 내용물은 css랑 똑같지만 형식만 다르다고 보면 된다. 

아직 처음이여서 지금 프로젝트는 vue 파일 안에 template, script, style을 한번에 다 쓰지만, 

나중에 분리할 때 assets으로 파일화 해서 옮기면 된다.



#### 2. pages

**: Router의 url 같은 것** 

그냥 vue.js를 쓰면 설정 파일에서  일일이 설정해 줘야 하는데 nuxt를 사용하면 하지 않아도 페이지가 해준다.

즉, 라우팅이 알아서 다 된다고 보면 된다.



![image](https://user-images.githubusercontent.com/42812764/147213486-3b56de9f-f99e-4131-b92e-21d9713de4d4.png)



index.vue에 코드를 다 짜면 복잡해 지니깐, 여기 내용들을  components에 저장을 한다. 

그렇기 하기 위해 components 폴더 아래에 같은 파일 구조를 만들어서 저장하면 된다.

template에서 쓰려면  components에 등록을 미리 해놓은 뒤, Login 컴포너트를 불러와라라고 template에서 말을 하면 script에서 임포트 하는 방식으로 진행된다.

![image-20211223174915160](/Users/juhuihan/Library/Application Support/typora-user-images/image-20211223174915160.png)

vue파일 안에서 변수를 쓰려면, script의 data에 미리 설정을 해야 한다. 즉 변수를 모아놓는 것이다.

method는 뭔가를 클릭하거나 함수를 실행할때 필요한 함수들을 모아놓는 것!



3. content, layout

:은 이후에 추가하도록 하자.



plugin이 조금 중요하다!

모바일 기기인지 아닌지 판단할때 슨느 것 

mixins의 안에 js파일들이 주르륵 생기는데 여기서 쓰는 함수는 전역적으로 쓸 함수들을 모아 놓는 곳이라고 보면 된다.

용도에 맞게 쓰는것. 그래서 로그인에 필요한 함수들을 모아 놓거나 이런 방식으로! 



예를 들어  Common.js는 디바이스가 무엇인지 판별해서 그에 맞는 화면을 보여 주도록 하는 것@]

computed는 변수를 모아 놓는 곳이긴 한데, 처음에 랜더링 할때 마운티드가 있는데

Nuxt의 라이프 사이클이 mounted가 먼저되고 그다음에 computed가 된다 

마운티드는 처음 모습 한번하는 것이 computed는 변화가 있을때 변화를 계속 인지해서, 계속 확인해가지고 기기에 맞게 보여주도록 하는 것



![image-20211223161628126](/Users/juhuihan/Library/Application Support/typora-user-images/image-20211223161628126.png)

처음 화면 보여주는 곳.



플러그인에 mixins를 추가하려면, 

Next.config.js의 ![image-20211223161804901](/Users/juhuihan/Library/Application Support/typora-user-images/image-20211223161804901.png)



여기다 추가하면된다. 이렇게 하면 나중에 과부하가 걸릴 수 있지만 일단 초반이라서 이렇게 하도록 하겠다 이후에 import로!

staitc이랑 store은 나중에 추가하는 것으로





<br />

<br />

<br />

<br />



