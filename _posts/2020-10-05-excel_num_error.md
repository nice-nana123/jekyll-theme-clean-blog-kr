---
layout: post
permalink: /excel_num_error/
title: '엑셀 숫자인식 오류 해결법 4가지'
date: 2020-10-05 12:00:00 +09:00
feature: '/img/posts/05/thumb.png'
background: '/img/posts/05/head.png'
categories:
  - go_home
tags:
  - 칼퇴
  - 엑셀
  - OA스킬
  - 엑셀숫자
description: '숫자를 숫자라 부르지 못 할 때. 엑셀 숫자가 숫자로 인식이 안되는 오류 해결법 정리!'
---

### 엑셀에서 숫자인데 계산이 안돼요.

<br>
> 분명 수식으로 계산했는데, 결과값이 안뜨고 텍스트로 수식이 뜨거나 #VALUE! 오류가 뜨는 경우를 만날 수 있다.

![excel_error](/img/posts/05/number_error.gif)

웹에서 다운로드한 데이터가 변환 과정을 거치면서 이런 오류들이 나타날 수 있는데,
숫자 수식이나 함수 결과가 제대로 나타나지 않는 이유는 '숫자가 숫자로 인식 되고있지 않기' 때문이다.
숫자로 인식되지 않는 현상은 아래의 이유 때문이다.

1.  형식이 다른 무언가로 되어있거나
2.  숫자에 다른 무언가가 껴있거나


이제, 숫자를 숫자로 불러보자.


------------------------
<br>
![excel_number](/img/posts/05/number.png)
#### 1. 표시형식 오류 : 텍스트 -> 숫자

> 형식 오류를 해결하는 2가지 방법!

![excel_type](/img/posts/05/excel1.jpg)

홈 > 표시형식 > 숫자 로 되어있는지 확인 후 > 결과셀 더블클릭 후 엔터.
<br><small>(여러셀에 적용 해야 한다면 수식 복사)

![excel_type_gif](/img/posts/05/type_text.gif)

단순히 표시 형식만 텍스트에서 숫자로 바꿔주었더니, 수식으로 표시되던 부분이 계산 결과값으로 바뀌는 것을 확인할 수 있다.


<br>

#### 2. 형식 오류 : x1 해서 숫자로 변환하기

![excel_multiple](/img/posts/05/excel2.jpg)

위 방법으로 해결이 되지 않는 경우에는, 원래 값에 1을 곱해서 숫자 형식으로 변환해 줄 수 있다.

![excel_multiple_gif](/img/posts/05/multiple.gif)

표시 형식만 바꾸어 계산이 작동하지 않는 경우, 새로운 셀에 숫자로 인식되지 않는 열에 1을 곱해주면 숫자로 돌아오는 경우가 있다.


<br>

![ghost](/img/posts/05/ghost.png)

> 유령문자를 지우는 2가지 방법!

#### 3. 유령 문자👻 : Alt + 1,6,0

![ghost1](/img/posts/05/excel3.jpg)

웹에서 다운로드하거나 복사 붙여넣기를 하는 과정에서 간혹 유령 문자가 침투하는 현상이 생긴다.
셀 내용을 보게 되면 숫자 옆에 공백이 있는 것을 볼 수 있는데, 눈에 보이지 않는 공백을 확인하기위해 모든 셀을 확인할 수 없는 노릇.
유령문자 입력법과 바꾸기 기능(Ctrl + H)으로 유령문자를 지워보자.

![ghost1_gif](/img/posts/05/ghost.gif)

바꾸기 기능을 이용해서 유령 문자를 지워주면 되는데, 찾을 값에 Alt + 1,6,0을 쳐주면 공백이 생기는 것을 확인할 수 있다.
바꿀 값에는 아무것도 없는 상태로 바꾸기를 진행해주면 유령문자가 사라진다.

위 화면에는 유령문자의 위치를 확인해보려고 유령 이모지로 교체 해보았다.

<br>

#### 4. 유령 문자👻 : cells.replace ChrW(160),""

![excel_multiple2](/img/posts/05/excel4.jpg)

alt + 1,6,0이 안 먹히는 경우가 있을 수 있는데, 그럴 땐 Visual Basic을 이용해서 직접 실행을 해주면 된다.
* 1) Alt + F11 을 눌러 VBA를 켠다.
* 2) 하단부에 직접 입력 창(보기 > 직접실행 창)에
<br>[cells.replace ChrW(160),""]를 입력 후 엔터.
* 3)그리고 VBA창을 닫아주면 유령문자들이 제거된 것을 확인할 수 있다.

<small>실행이 되지 않고 alert창이 뜬다면 오타를 확인해볼 것!



![excel_multiple_gif2](/img/posts/05/ghost2.gif)

<br>[cells.replace ChrW(160),""] 는 시트 내 모든 셀에서 ChrW(160)을 ""(아무것도 없음)으로 교체하겠다는 명령이다.
즉, 유령문자를 없애는 방법이다.
이렇게 유령 문자들을 없애주면 수식의 결과가 원하는대로 나타나는 것을 확인할 수 있다.

<br>

------------------------


대부분의 숫자 인식 오류들은 위 방법으로 해결이 된다. 특히 외부 데이터를 받아 사용하는 경우 종종 이런 문제로 시간을 많이 잡아먹곤했는데, 이제 골치 아픈 엑셀 오류 정복하고 얼른 집으로 가자.


오늘도 칼퇴를 향해서!