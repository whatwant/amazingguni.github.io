---
layout: page
title: 두더지러시
permalink: /portfolio/molerush/
---
2013년 말 입사 전에 공모전 참가를 목표로 1~2주간 진행했던 `두더지러시` 라는 TV/Mobile 연동 게임에 대한 log입니다.

[스마트TV 글로벌 서밋 2013 수상 관련 기사](http://www.etnews.com/201311070673)

### 프로젝트를 시작한 이유

회사를 입사하기 전 5달의 시간이 있었는데, 그중 2달은 해외여행을 가기로 되어 있었고 2달간 할 것이 마땅히 없었다.  
마지막으로 학생 신분으로 뭔가를 해야겠다는 생각에 지원할만한 공모전이 있는지 찾아보다 `스마트TV 글로벌 서밋 2013`을 찾았다. 마침 삼성 Mobile/DTV 컨버전스 삼성과제를 몇개 진행한 경험이 있어 짧은 시간에 마무리 하기 좋아 보였기 때문에 해당 프로젝트를 진행하게 되었다.

### 주제는 왜 게임인지?

나는 TV와 Mobile의 성공적인 Convergence 시나리오는 `교육`이나 `게임`이 될꺼라고 생각해 왔었다. 그래서 본 프로젝트를 기획할 때에도 두가지 중 하나를 고민하게 되었다. 

`교육`을 위해서는 컨텐츠와 잘 디자인된 리소스가 필요할 것으로 보였는데, 주변에 디자인을 잘한다는 사람도 없었고 컨텐츠도 딱히 떠오르는 것이 없었다. 동화책을 TV로 보여주고 모바일을 통해 제어를 해볼까 했지만 리소스를 만들 디자이너가 없는 상태에서는 좋은 퀄리티를 기대하기 어려웠다.

> 그리고 대학교에서 `Unity3D`로 게임을 몇개 만든 경험이 있다 보니 상대적으로 진입장벽이 낮기도 했다.

그래서 `게임`을 목표로 몇몇가지 기획을 해보았었다. 

처음에는 그 때 마침 유행하던 `tvn 지니어스`에 나오는 보드게임들을 프로토타입 레벨로 구현해 보았지만 정적인 게임들이 대부분이였기 때문에 몰입도가 떨어져 재미가 없어 드롭했다.


> [더 지니어스 - 나무위키](https://namu.wiki/w/%EB%8D%94%20%EC%A7%80%EB%8B%88%EC%96%B4%EC%8A%A4)에서 프로그램에 대한 자세한 정보를 볼 수 있다.  
![지니어스 게임]({{site.url}}/images/note/molerush_genius.png)

이러한 과정 끝에 리얼타임으로 진행되는 속도감있는 게임이 컨버전스 시나리오에 어울린다는 판단을 하고 2일 정도의 회의 끝에 본 프로젝트를 기획/개발하게 되었다.


### 개요

`두더지러시`는 간단하게 말하면 멀티 유저(최대 4명)가 함께 즐기는 지뢰찾기라고 볼 수 있다.  
멀티 유저로 변경되면서 아래 2가지 게임성이 추가되었다:   

* 다른 사람이 차지한 땅은 지나갈 수 없는 `땅따먹기적 요소`가 추가되어 판단을 빠르고 정확하게 내려야 함
* 서로 아이템을 통해 방해할 수 있어 게임의 흐름에 변수가 생긴다.

기존 지뢰찾기와의 차별성은 아래와 같다: 

![지뢰찾기와의 차별성]({{site.url}}/images/note/molerush_table.png)

본 게임에서 Mobile과 TV는 아래와 같은 역할을 한다:

* Mobile
    * 각각의 플레이어가 지뢰인지 아닌지 판단하고 조작하고 아이템을 사용할 수 있는 컨트롤러
* TV
    * 전체 맵을 볼 수 있는 뷰어
    * 모바일에서는 전체맵이 아닌 부분만 볼 수 있으므로 다른 플레이어들의 상태(얼마나 지뢰를 찾았는지, 어느 방향으로 진출하는지)를 보는 화면이기도 하다.
    * 큰 화면을 통해 게임을 하는 플레이어 뿐만 아니라 관전자들도 즐길 수 있다.

### 사용기술

![develop tool]({{site.url}}/images/note/molerush_tool.png)

**TV쪽(웹 어플리케이션)**

* Samsung Smart TV SDK: 당연히 필요하다
* LG Smart TV SDK: 공모전에서 대상을 받기 위해 2개 티비를 다 지원해야 했다.
* crafty.js: layer나 몇몇 효과들을 사용하기 위해 사용한 2D 그래픽 라이브러리
* Allshare framework, NService: 모바일 기기와의 통신을 위해 사용했다. 지금도 있는지는..모르겠다.

**추가 서버**

* Node.js : LG TV에서 DNLA기반의 기술을 사용하는 방법을 찾지 못해 일단은 별도의 웹서버로 통신

    > 결국 이렇게 마무리 되긴 했지만.

**Android Mobile**

* Unity 3D: 2D/3D 가리지 않고 게임을 만들때 최고의 선택이라 생각하는 게임 엔진
* Samsung Allshare: 티비와의 통신을 위해

**그래픽툴?**

* Photoshop: Google에서 관련 이미지 검색 이후 많이 추상화해서 케릭터로 사용.

    > 디자이너가 아니였기 때문에 바닥부터 하기에는 무리가 있었다.

### 서비스 흐름도

또한 전체적인 서비스는 아래와 같이 흘러간다

![서비스 흐름도]({{site.url}}/images/note/molerush_flow.png)

### 그런데 왜 두더지를 골랐는지..?

[두더지 나오는 그림]()
지뢰찾기를 광산을 탐험하는 거라고 매핑하였고 케릭터는 광부라고 설정하였다. 그래서 광부가 미지의 영역들을 개척하다가 나오는 지뢰들을 뭐로 매핑할까 고민하다가, 포켓몬스터의 디그다...가 생각나서 두더지를 지뢰로 설정하였다.

> 테마별로 아주 귀엽게.. 했는데, 프로그래머가 그린거다 보니 그닥지 세련되지는..않았다 ㅠ_ㅠ

![디그다]({{site.url}}/images/note/molerush_digda.png)

### UI

TV와 Mobile이 각각 다른 UI를 가지고 있다.

#### TV

![두더지러시 티비 UI]({{site.url}}/images/note/molerush_ui_tv.png)

* Intro page: 처음 앱을 켰을 때 뜨는 시작 화면이다.
* Map 선택 popup: 사용자 접속을 기다리면서 맵을 선택할 수 있는 팝업이다. 총 2개 테마(일반, 크리스마스)의 맵을 선택할 수 있다.
* Game page: 두더지러시 게임을 시작한 페이지이다. 전체 맵에서 일어나는 영역 확장이나 아이템 사용등의 상태를 볼 수 있다.
* 결과 popup: 게임이 완료된 이후 플레이어들의 순위와 점수를 보여주는 팝업이다.

#### Mobile

![두더지러시 모바일 UI]({{site.url}}/images/note/molerush_ui_mobile.png)

Mobile은 게임에서 각각 플레이어의 컨트롤러 역할을 한다.

* Intro page: 처음 앱을 켰을 때 뜨는 시작 화면이다.
* Login page: 플레이어의 이름을 작성하고 로그인하는 화면이다.
* TV 선택 page: `allshare`를 통해 TV에 접속하는 화면이다.
* 대기 page: 한 TV 접속한 유저들끼리 대기하는 화면이다. 처음에 가지고 들어갈 아이템을 선택할 수 있으며 모든 유저가 준비 상태가 되면 게임이 시작된다.
* 게임 page: 두더지러시 게임을 시작한 페이지이다. 자신의 딸과 근접한 땅에 두더지가 있는지 없는지를 판별하면서 게임이 진행된다. 두더지를 잡는데 성공하면 눈물을 흘리는 두더지가 나오며, 실패했을 경우에는 미묘한 미소를 짓는 두더지가 튀어나온다.
* 게임 종료 page: 제한 시간이 끝나면 나오는 페이지이다.


### Item

두더지러시는 Item을 사용하여 더욱 재미를 더한다.

> 아 누가 나한테 공격 Item 사용했어!!! 같이..

Item은 방어 Item과 공격 Item으로 구성되어 있으며 각각 파란색과 빨간색으로 구분되어 있다.

![두더지러시 아이템]({{site.url}}/images/note/molerush_item.png)

### 리소스

이 프로젝트는 내가 처음으로 리소스를 만들었기 때문에 더욱 의미가 있었다.
비록 디테일은 굉장히 어설프지만, 나름 센스는 있지 않았나 생각이 들어 따로 항목을 만들었다.

게임에서 나오는 애니메이션들은 sprite로 구현하였으며 각각의 이미지를 따로따로 그려 한 이미지로 합쳐놓았다.

> 성능 상의 문제도 있지만 이렇게 하는 편이 작업하기 편했다.

![케릭터]({{site.url}}/images/note/molerush_character.png)

![두더지 애니메이션]({{site.url}}/images/note/molerush_tilemap.png)


### 나의 역할

* 프로젝트 리더
* TV <-> 모바일 인터페이스에 대한 정의
* 올쉐어, NService 모듈 개발
* Node.js 웹서버: 데모 수준의 간단한 서버(LG TV용)
* TV 게임 로직: 게임 룰을 TV에서 관리
* 리소스 제작: 50%의 시간을 쏟았다.

### 데모

<iframe width="560" height="315" src="https://www.youtube.com/embed/fFzxrAJX9wo" frameborder="0" allowfullscreen></iframe>

