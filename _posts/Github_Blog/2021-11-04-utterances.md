---
title: '깃허브 블로그에 댓글 기능 추가하기 (utterances)'
excerpt: '블로그는 개인 기록용 공간이기도 하지만 소통을 위한 공간이기도 하죠? 댓글 기능을 추가해 다른 개발자들과 소통해 봅시다!'

categories:
  - Github Blog

tags:
  - [Github Blog, Jekyll, Minimal Mistakes, Utterances]

toc: ture
toc_sticky: true

date: 2021-11-04
last_modified_at: 2021-11-06T14:50:30+0900
---

<br>
<br>

블로그를 공부한 것을 기록하는 공간으로만 사용하는 분들도 있겠지만 다른 개발자 분들과 소통을 하고 싶은 분들도 있으실 겁니다.

소통을 하기 위해 깃허브 블로그에 댓글 기능을 추가해 봅시다!

<br>

# 댓글 기능 플랫폼

블로그에서 댓글 기능을 추가하기 위해 disqus, discourse, facebook, staticman, staticman_v2, utterances, custem 등 여러가지 플랫폼을 사용할 수 있습니다.  
보통 disqus 와 utterances 를 많이 사용하시는 것 같습니다.

disqus 는 무겁고 광고가 많이 달린다는 단점이 있다고 합니다.

**utterances** 는

- 광고가 없고 가볍다고 합니다.
- Github 계정 로그인을 통해 댓글을 달 수 있고, 댓글이 달리면 알림이 Github Repository 의 Issue 로 올라옵니다.

개발 공부 기록을 하는 블로그이기 때문에 들어오시는 분들 대부분이 Github 계정이 있으실 것으로 생각되어 큰 문제가 없을 것 같습니다.

<br>

# 블로그에 utterances 적용시키기

## 1. 댓글 알림 Issue 가 올라올 저장소를 정하거나 새로 생성합니다.

자신의 깃허브 블로그 Repository 에 하거나 새로 하나 만드시면 되는데

![스크린샷 2021-11-04 오후 5 06 36](https://user-images.githubusercontent.com/87692499/140278629-3a9b0f1e-9461-4bcf-b149-a58a551c52a5.png)

저는 이렇게 comments 라는 Repository 를 하나 생성 했습니다.

## 2. utterance 를 설치하기

[https://github.com/apps/utterances](https://github.com/apps/utterances){: target="\_blank"} 이 링크에 들어가면

![스크린샷 2021-11-04 오후 5 13 47](https://user-images.githubusercontent.com/87692499/140279631-c3468c5c-362a-4fa2-b1c2-3d474d038787.png)

이런 화면이 나오는데 아직 설치하지 않으셨다면 Configure 대신에 Install 버튼이 있으실 겁니다.

<br>

<img width="1001" alt="1" src="https://user-images.githubusercontent.com/87692499/140280076-d8b6d2b7-216d-49f9-8769-d2433be11883.png">

버튼을 누르고 Select repositories 에서 댓글 알림을 issue 로 관리할 저장소를 선택해주시면 됩니다!

저같은 경우에는 comments repository 입니다.
{: .notice--info}

<br>

![스크린샷 2021-11-04 오후 5 23 53](https://user-images.githubusercontent.com/87692499/140281015-1af7a465-4ffa-4ee8-ae08-b447751f2b8a.png)

repo 에는 **github 아이디/저장소 이름** 을 입력하시면 됩니다.

<br>

![스크린샷 2021-11-04 오후 5 26 37](https://user-images.githubusercontent.com/87692499/140281422-bcf0c40f-b112-4d96-95b8-42fd0ab9fa63.png)

label 항목은 작성하지 않으셔도 상관 없고 Theme 는 원하는 테마를 골라주시면 됩니다!

저희는 minimal mistakes 테마를 사용하고 있기 때문에 코드를 복사할 필요가 없고 **\_config.yml** 파일을 수정해주면 됩니다.

아래의 사진을 참고하여 수정해주세요!

<img width="694" alt="스크린샷 2021-11-04 오후 5 29 43" src="https://user-images.githubusercontent.com/87692499/140281993-90476a7f-7771-4d99-b963-662900b8ffc2.png">

그 다음에 **\_config.yml** 쭉 내려보시면 defaults 설정이 있는데 거기서 comments 를 true 로 바꾸어 줍니다.

<img width="268" alt="스크린샷 2021-11-04 오후 5 33 54" src="https://user-images.githubusercontent.com/87692499/140282521-fb9631ec-1ea7-44bc-a3d3-420d24964ef7.png">

이렇게 다 수정 하셨으면 `git push` 해주시면 됩니다!

댓글 기능은 로컬 서버에서 확인이 불가능하니 push 를 해주신 후 5~10분 정도 기다리시면 깃허브 블로그에서 확인하실 수 있습니다.

<br>

# 테스트 및 설정

## 테스트 해보기

![스크린샷 2021-11-04 오후 5 39 21](https://user-images.githubusercontent.com/87692499/140283129-31919623-8d0a-4321-b78e-3ab0c1ebceee.png)

블로그에서 테스트용 댓글을 달아보면 블로그 댓글 알림이 지정해준 Repository Issues 탭에 잘 올라오는 것을 확인할 수 있습니다!

## 메일 알림 설정

![스크린샷 2021-11-04 오후 5 44 06](https://user-images.githubusercontent.com/87692499/140283856-f3df18f8-2aa7-4622-a397-3f10e271c59e.png)

Github Repository 의 Settings 에서 Notifications 에 들어가서 이메일을 등록하면 댓글 알림을 메일로 받으실 수 있습니다!

## utterances 댓글 창 너비 조절

```
.utterances {
  max-width: 100% !important;
}
```

이렇게 하면 댓글 창의 너비가 늘어난다는데 저는 더 늘어나지 않았습니다.  
아마도 minimal mistakes wide layout 을 사용하시는 분들에게 적용되는 내용인 것 같습니다.

<br>

# Reference

- [평생 공부 블로그](https://ansohxxn.github.io/blog/utterances/){: target="\_blank"}
