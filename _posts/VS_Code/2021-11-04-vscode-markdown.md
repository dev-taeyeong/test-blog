---
title: '블로그 포스트 작성할 때 머릿말 자동완성 기능!! (VS Code)'
excerpt: '깃허브 블로그 포스팅을 할 때 매번 Front Matter 를 작성하는 것은 매우 번거롭습니다. 원하는 형식을 만들어 자동완성 해 봅시다!'

categories:
  - Github Blog

tags:
  - [
      Github Blog,
      VS Code,
      Markdown,
      Front Matter,
      Insert Date String,
      extension,
      꿀팁,
    ]

toc: true
toc_sticky: true

date: 2021-11-04T23:04:04+0900
last_modified_at: 2021-11-05T11:43:15+0900

permalink: /:slugified_categories/:title/
---

<br>
<br>

블로그 포스트를 작성할 때마다 매번 공통적으로 Front Matter 를 작성해 주어야 하는데 이런 부분들을 **VS Code 사용자 코드 조각** 이라는 기능을 이용해 쉽고 빠르게 작성할 수 있습니다.

# 사용자 코드 조각

<img width="657" alt="스크린샷 2021-11-04 오후 11 24 34" src="https://user-images.githubusercontent.com/87692499/140331654-6be3b99e-1992-4804-aa52-6cbb58ba6ed7.png">

VS Code 하단 왼쪽 톱니바퀴 모양 버튼을 클릭하고 사용자 코드 조각 메뉴를 클릭합니다.

<br>

# markdown.json

<img width="754" alt="스크린샷 2021-11-04 오후 11 27 08" src="https://user-images.githubusercontent.com/87692499/140331834-562cdba2-baa6-4bde-ade9-8029f2e52089.png">

그러면 위에 이렇게 입력을 할 수 있는 창이 뜹니다. 저는 이미 markdown 코드 조각을 등록한 상태라 바로 이렇게 나오는데 저기서 markdown 을 검색하여 **markdown.json** 을 찾아 눌러주시면 됩니다.

<img width="1034" alt="스크린샷 2021-11-04 오후 11 32 59" src="https://user-images.githubusercontent.com/87692499/140332868-2fb61612-c846-42f6-bf60-750134c837b1.png">

이렇게 json 파일을 열어주고 주석은 한 번 읽어 보세요!

```json
{
  "Markdown Front Matter": {
    "prefix": "-",
    "body": [
      "---",
      "title: '$1'",
      "excerpt: '$2'\n",
      "categories: \n\t- $3 \n",
      "tags: \n\t- [$4]\n",
      "toc: true",
      "toc_sticky: true\n",
      "date: ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:${CURRENT_MINUTE}:${CURRENT_SECOND}+0900",
      "last_modified_at: ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:${CURRENT_MINUTE}:${CURRENT_SECOND}+0900",
      "---\n",
      "<br>",
      "<br>\n\n"
    ],
    "description": "Yaml Front Matter"
  }
}
```

그 다음 이렇게 작성하시면 됩니다.

한번 읽어보시면 어떻게 사용하는지 알 수 있으실 거에요~  
자신의 기본 Front Matter 설정에 맞춰 작성해 보세요!

여기서 `"prefix": "-"` 라는 코드는 이 양식을 사용할 단축키 라고 생각하시면 됩니다.  
`$1, $2, ...` 는 코드 조각이 만들어 진 후 커서의 위치입니다.  
처음 코드 조각을 만들면 $1 위치에 커서가 위치하게 되고 그 위치에 값을 작성하신 후 tab 키를 누르면 $2 위치로 커서가 옮겨지게 됩니다.  
`${CURRENT_YEAR}` 은 현재 년도를 나타내는 변수입니다. 나머지도 다 같은 날짜 관련 변수입니다!
{: .notice--info}

<br>

# 코드 조각 사용하기

<img width="988" alt="스크린샷 2021-11-04 오후 11 48 07" src="https://user-images.githubusercontent.com/87692499/140335655-41761da3-7225-459a-be81-be2f81882291.png">

.md 파일에 가서 아까 위에서 `prefix` 값으로 설정한 `-` 를 치고 **ctrl + space(window, MacOS)** 또는 **cmd + i(MacOS)** 단축키를 누르시면 이런 창이 뜨는데요. 엔터를 누르면

<img width="405" alt="스크린샷 2021-11-04 오후 11 52 21" src="https://user-images.githubusercontent.com/87692499/140336427-be0e9bc6-b191-4a89-a587-90a6205bf692.png">

이렇게 Front Matter 가 자동 완성 됩니다! 👏

만약 단축키가 작동하지 않는다면 설정(아래 톱니바퀴 모양의 버튼)을 누르고 바로가기 키(Keyboard Shortcuts) 메뉴를 누르신 후 **Trigger Suggest** 를 검색합니다.  
키가 잘 설정되어 있는지 확인 해보세요! 저는 잘 설정 되어 있었는데 똑같은 키 설정으로 다시 설정하니까 잘 작동 했습니다!  
{: .notice--info}

키 설정할 때 조심해서 하세요! 잘못해서 삭제하거나 그러면 엄청 고생합니다 ㅜㅜ 저는 실수로 스페이스바를 삭제했습니다 😱
{: .notice--warning}

<br>

# + 날짜 시간 자동입력 extension 설치하기!

포스트를 수정할 때 `last_modified_at` 을 수정하는 것이 정말 귀찮아서 현재 날짜와 시간을 자동 입력해주는 기능이 없나 찾아보다가 **Insert Date String** 이라는 extension 을 찾았습니다!

<img width="300" alt="스크린샷 2021-11-05 오전 11 33 24" src="https://user-images.githubusercontent.com/87692499/140448648-ebf516ab-41ad-481b-8562-9267f3cb856c.png">

사진에 보이는 extension 을 설치해주세요.

아래 설명을 읽어보면 macOS 는 **shift + cmd + i**, window 는 **shift + ctrl + i** 단축키를 사용하면 날짜와 시간이 입력 된다고 합니다.

하지만 제가 Front Matter 에 사용하는 형식이 아닙니다. 형식을 수정해봅시다.

<img width="613" alt="스크린샷 2021-11-05 오전 11 37 51" src="https://user-images.githubusercontent.com/87692499/140449182-a45072cc-90f1-47a6-bc26-043ca4ee93c2.png">

사진에 보이는 톱니바퀴 버튼을 클릭하고 확장 설정 메뉴를 눌러줍니다.

<img width="984" alt="스크린샷 2021-11-05 오전 11 40 04" src="https://user-images.githubusercontent.com/87692499/140449302-f7d98c36-64ba-4161-bc11-956bcfb7a9a2.png">

그리고 저랑 똑같이 입력해주시면 됩니다! (형식은 extension 세부 정보를 읽어보시면 잘 나와 있습니다.)

이제 **shift + cmd + i** 또는 **shift + ctrl + i** 단축키를 눌러주면 `2021-11-05T11:42:46+0900` 이렇게 잘 입력이 됩니다!
