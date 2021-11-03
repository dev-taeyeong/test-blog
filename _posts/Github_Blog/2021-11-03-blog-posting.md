---
title: '블로그 글 작성하기'
excerpt: '기본적인 설정을 완료했으니 이제 블로그에 첫 글을 작성해봅시다!'

categories:
  - Blog

tags:
  - [Blog, jekyll, Github, Git, minimal mistakes, Post]

toc: ture
toc_sticky: true

date: 2021-11-01
last_modified_at: 2021-11-01
---

<br>
<br>

# 1. 폴더 생성하기

github.io 폴더 > \_posts 폴더
{: .notice--info}

<img width="784" alt="" src="https://user-images.githubusercontent.com/87692499/140019386-548452f8-0bb5-405e-bc81-cf46a88955b1.png">

이렇게 자신의 github.io 폴더 안에 \_posts 폴더를 만들어 줍니다.

저는 나중에 포스팅을 관리하기가 힘들 것 같아 각 카테고리를 추가적으로 폴더화 했습니다. (이렇게 하지 않으셔도 상관없습니다!)

<br>

# 2. Markdown 을 지원하는 에디터 준비

저는 원래 Visual Studio Code 를 사용해서 이걸로 작성했습니다.  
에디터를 실행하고 **github.io 폴더 > \_posts 폴더** 를 열어줍니다.

모든 포스트 파일은 \_posts 폴더 내에 위치해야 합니다.
{: .notice}

<br>

# 3. yyyy-mm-dd-title.md 형식의 파일을 만들기

포스트 파일의 확장자는 항상 `.md` 여야 합니다. yyyy-mm-dd 형식의 날짜 뒤에 -포스트 제목을 붙여줍니다. 포스트 제목은 영어로 쓰는 것을 추천합니다!

ex) 2021-11-01-first-post.md
{: .notice}

<br>

# 4. 머릿말(Front Matter) 작성하기

포스트 파일의 최상단에 **Front Matter** 라는 것을 작성해 주어야 합니다.  
**Front Matter** 는 포스트 내용을 작성하기 전에 이 포스트의 정보를 작성해 주는 것 입니다.

```md
---
title: '블로그 글 작성하기'
excerpt: '기본적인 설정을 완료했으니 이제 블로그에 첫 글을 작성해봅시다!'

categories:
  - Blog

tags:
  - [Blog, jekyll, Github, Git, minimal mistake]

toc: ture
toc_sticky: true

date: 2021-11-01
last_modified_at: 2021-11-01
---
```

이런식으로 작성하면 되는데 `---` 을 위 아래에 사용해 Front Matter 영역을 감싸주어야 합니다.

<div class="notice" markdown="1">
title: 화면에 보이는 제목입니다. title 을 적어주지 않으면 포스트 파일의 title 부분이 제목으로 업로도 됩니다.

excerpt: 포스트 목록에서 보여지는 소개 글입니다.

![](https://user-images.githubusercontent.com/87692499/140021709-777785ee-626f-49e9-ac84-7f62e5d0046b.png)

이런 식으로 제목 아래에 들어갑니다.

categories: 포스트의 카테고리 입니다. 나중에 카테고리 나누기에서 자세하게 알아보겠습니다!

tags: 태그와 카테고리의 차이점은 카테고리는 sub url 이 붙는 페이지가 있지만 태그는 없다는 것입니다. 카테고리보다 좀 더 세부적인 내용을 작성합니다.  
대괄호([]) 안에서 콤마(,)로 구분지어 여러개의 태그를 포스트에 지정해 주었습니다.

toc: Table of Contents 의 약자로 포스트의 헤더들을 테이블 형식으로 보여주는 목차를 사용할 것인지의 여부를 작성합니다. true 로 해주면 아래와 같이 포스트의 목차가 생성됩니다.

![](https://user-images.githubusercontent.com/87692499/140022492-cde8be4a-1982-43ca-9f79-5b7e27a01182.png)

toc_sticky: true 로 해주면 목차가 스크롤을 따라 움직이게 됩니다. 저는 목차가 항상 보이는 것이 좋아 true 로 해주었습니다.

date: 글을 처음 작성한 날짜입니다. yyyy-mm-dd 형식으로 작성합니다.

last_modified_at: 글을 수정한 날짜입니다.

</div>

이 밖에도 많은 설정들이 있는데 필요한 설정을 찾아서 사용하시면 됩니다!

머릿말에 쓰인 변수는 page Liquid 변수로 사용할 수 있습니다.  
예를들어 Liquid 언어 문법을 사용해 \{\{page.categories\}\} 를 본문에서 사용하면 머릿말에 적힌 categories 의 변수 값인 Blog 가 출력됩니다.

<br>

# 5. 포스트 작성

머릿말 이후의 영역은 포스트 본문 입니다. Jekyll 은 **HTML** 과 **Markdown** 을 지원하는데 사용하기 간편한 **Markdown** 으로 작성하면 됩니다.

<img width="891" alt="" src="https://user-images.githubusercontent.com/87692499/140023813-a589e176-3198-4705-bc30-c7afb263739c.png">

이런식으로 작성하면 됩니다.

혹시나 마크다운을 접해본 적이 없으신 분들은 어려워 보일 수 있는데 조금만 검색해 보시면 쉽게 작성할 수 있으실 겁니다!

<img width="298" alt="스크린샷 2021-11-03 오후 7 01 57" src="https://user-images.githubusercontent.com/87692499/140040912-5573cc52-08b3-40b2-96ab-e76f98002b24.png">

Visual Studio Code 를 사용하시는 분들은 동그라미 친 부분을 누르시면 (우측 상단에 있습니다.)

<img width="1406" alt="스크린샷 2021-11-03 오후 7 05 01" src="https://user-images.githubusercontent.com/87692499/140041347-2cd1acb9-46ea-4e58-bc5b-b4dec62e1500.png">

이렇게 실시간으로 확인하면서 작성이 가능합니다!

하지만 실제로 블로그에 포스팅 될 때는 차이가 있는 경우가 있기 때문에 꼭 로컬 서버에서 블로그를 실행시켜 확인을 해보고 push 하는 것이 좋습니다!
{: .notice}

<br>

# 6. 로컬 서버에서 블로그에 적용될 모습 확인하기

터미널을 실행하고 자신의 github.io 폴더로 이동합니다. 그 다음 `bundle exec jekyll serve` 명령어를 쳐주면 로컬 환경에서 Jekyll 서버가 작동됩니다.

작성중인 `.md` 파일을 저장한 후 웹 브라우저를 열고 [http://localhost:4000](http://localhost:4000) 으로 접속하면 서버에 올렸을 때 블로그가 어떻게 보여질 지 미리 확인해 볼 수 있습니다.

`git push` 하여 원격 서버에 반영한 후 확인하려면 길게는 5~10분 정도의 시간이 소요되니 꼭 로컬 환경에서 확인해보시고 push 하세요!

`bundle exec jekyll serve` 대신 `bundle exec jekyll serve --livereload` 명령어를 실행시키면 파일을 저장할 때마다 자동으로 페이지에 반영됩니다. 저는 이렇게 사용하는데 편하신대로 사용하시면 됩니다!  
반영이 잘 안되는 경우에는 control + c 로 로컬 서버를 종료하고 다시 실행시켜주시면 됩니다.
{: .notice--info}

<br>

# 7. 작성한 포스트 파일을 원격 저장소에 업로드 하여 Github Pages 서버에 업로드하기

**github.io 폴더** 의 변경사항을 `git push` 해서 Github Pages 원격 서버에 올려주어야 합니다.

깃 명령어를 사용하여 터미널에서 `git add, git commit, git push` 해도 되지만 VS Code 내에서 UI 로 Github 원격 서버에 업로드가 가능합니다.

<img width="378" alt="스크린샷 2021-11-03 오후 7 24 53" src="https://user-images.githubusercontent.com/87692499/140044264-a4b73f46-5a18-45a0-b9d5-7bd3a551d471.png">

왼쪽 메뉴에서 세번째 아이콘을 클릭하면 git 을 사용할 수 있는데 **모든 변경 내용 스테이징** 을 누르고

<img width="296" alt="스크린샷 2021-11-03 오후 7 26 44" src="https://user-images.githubusercontent.com/87692499/140044439-904cf70f-9f31-4706-8453-27e3f7ef8feb.png">

그 위에 **커밋** 버튼을 누르면 커밋할 메세지를 입력할 수 있습니다. 원하는 메세지를 입력한 다음 **변경 내용 동기화** 버튼을 눌러주시면 원격 저장소에 잘 업로드 될 것 입니다!

1분에서 길게는 5분 이상 걸릴때도 있으니 포스트가 보이지 않는다고 당황하지 말고 기다려주시면 됩니다.
{: .notice}
