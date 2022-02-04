---
title: CSS Layout
layout: post
post-image: /assets/images/TIL.jpeg
description: css layout display, float, position, flexbox
tags:
- css
- post
- test
---

# 📖 CSS layout
css에서 많이 사용되고 중요하지만 정!말! 헷갈리는 <br>레이아웃(display, float, position, flexbox) 부분에 대해 정리 해보도록 합시다.😁 

## 👉 <span style="background-color:#F15F5F; color:#fff;">Display</span>
**display : box type을 결정하는 css 속성**
block 면(영역) / inline 선(흐름) 으로 보면 이해가 쉬울 것 같다.

| 속성값 | 의미 | 종류 |
|:----------|:----------|:----------|
| block | - 한 줄에 하나씩 요소 배치 = 세로로 배치<br>- 기본 width 값이 100% <br> - width, height값을 가질 수 있음<br>- vertical-align 적용되지 않음<br>- text-align 적용되지 않음| div, h1~h6, p, ul, li, dl, table, td, <br>th, figure,hr, figcaption, caption,<br> header, nav, footer, section, article,<br> aside, blockqoute, form, fiedset...|
| inline | - 한 줄에 여러개 배치 = 가로로 나열되는 식으로 배치<br>- 기본 width 값은 컨텐츠 너비 값 <br> - width, height값을 가질 수 없음<br>- 자식요소로 또 다른 인라인 태그만 가능(p제외)| span, a, em, del, br, q, strong, input<br>textarea, select, img... |
| inline-block | - 한 줄에 여러 개 배치(인라인) + 너비높이 지정가능(블록)| 


### 💁‍♀️ <span style="background-color:#F2CB31; color:#2c2c2c;">block</span>
> - 길을 막는 성질을 가지고 있다.
- **width를 따로 선언하지 않은 경우**, width = 부모의 content-box의 100%
- **width를 따로 선언한 경우**, 남은 공간은 margin이 채워짐<br>(영역을 침범 당하지 않기 위해서)
- block의 경우 width, height, padding, border, margin을 모두 사용할 수 있다.
- block type을 **가운데 정렬하는 방법 : margin : 0 auto** 👉 margin top과 bottom은 0을 주고 right와 left는 auto (남는 px를 자동으로 채움)를 준다는 것이다. *별도로 margin left : auto;만 주면 block은 오른쪽 정렬이 된다.*

#### ✍️ 예시) 부모의 width가 1000px이라고 가정 후, 자식 width를 600px로 지정하면 남은 400px이 자동적으로 margin으로 채워진다.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">inline</span>
> - 수평으로 쌓인다.
- 가로, 세로 값 가질수 없다.
- text 작성과 동일한 맥락, 옆으로 더 쓸 공간이 없으면 자동적으로 밑 줄로 내려감
- margin과 padding의 top,bottom을 사용할 수 없다.
- **width, height, padding-top, padding-bottom, border-top, border-bottom, margin-top, margin-bottom** 사용이 **불가**하다.(위 아래의 크기를 변경하는것은 안된다 기존 영역을 덮어버리기 때문에)

#### 🧐 width가 안되는 이유 : 인라인 요소의 width를 부모 요소가 다 담을 수 없는 상황일 때 애매해지기 때문에 width가 있는데 인라인 요소를 끊어서 밑 줄에 내려 놓을 수도, 부모를 오버해서 나갈 수도 없기 때문이다.



### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">inline-block</span>
> - block의 장점과 inline의 장점을 가지고 있다.
- text에 특화되어 있지만, 가로/세로 값을 가질 수 있다. 
-margin과 padding의 top,bottom 값도 가질 수 있다.
- inline처럼 흐르지만 **width, padding-top, padding-bottom, border-top, border-bottom, margin-top, margin-bottom**이 사용 **가능**하다.

<br>

## 👉 <span style="background-color:#F15F5F; color:#fff;">Flexbox</span>
flexbox란 요소의 크기가 불분명할 때에도 내가 원하는 크기의 box 안에 items을 넣어서 동일한 간격과 사이즈로 배열하는 것이다.

flexbox를 사용할 때 주의해야 할 **4가지 요소**

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">flexbox 선언</span>

> - 내가 정렬을 하려고 하는 요소의 <span style="color:red;">**부모**</span>에게 flexbox선언을 해야한다. 
👉 display : flex; (box의 타입이며 기본적으로 block과 비슷하지만 block은 불가능한 요소도 있음)
- 만약 부모 요소가 inline 이라면 display : inline-flex로 지정해준다.

<br>

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">flex-direction </span>
flex items의 주축(main-axis)를 설정해준다.

| 속성값 | 의미 | 
|:----------|:----------:|
| row(default) | items를 왼쪽에서 오른쪽(수평축)으로 표시 <br> A,B,C |
| row-reverse | items를 row 반대축으로 표시 <br> C,B,A |
| column | items를 위쪽에서 아래쪽(수직축)으로 표시 <br> A<br>B<br>C |
| column-reverse | items를 column 반대 축으로 표시 <br>C<br>B<br>A |

<br>

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">flex-wrap </span>
items의 여러 줄 바꿈을 설정해준다.

| 속성값 | 의미 | 
|:----------|:----------|
| nowrap(default) | 모든 items이 한 줄에 배치가 된다. |
| wrap | items를 여러 줄로 배치해 넘치면 아래로 떨어지게 한다. (width,height 지정 가능) |
| wrap-reverse | items를 wrap의 역 방향으로 여러 줄로 배치. |

> #### flex-wrap : nowrap; (기본값) 👉 줄 바꾸지 않음
부모 width가 600px이고 자식이 300px씩 가지고 있다면, 기본적으로 300px+300px로 2개만 올 수 있지만 flex-wrap : nowrap;을 사용하면 감싸지 않고 자식의 사이즈를 줄여 한 줄로 정렬한다. (200px씩 한 줄로) 

#### flex-wrap : wrap; 👉 줄 바꿈
부모 width가 600px이고 자식이 300px씩 가지고 있다면 300px+300px로 2개가 오고 밑 줄에 300px이 떨어진다. 한 줄에 모두 정렬할 때 공간이 부족하면 여러 줄을 만든다.

** 🤔 값을 지정해주지 않을 경우 모든 요소들이 한 줄에 정렬되려고 하기 때문에 width 값을 주어 overflow 된 요소들은 밑으로 떨어지게 한다**

<br>

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">justify-content</span>
내가 선언한 flex-direciton과 같은 방향, 즉 주축을 기준으로 정렬 해주고 싶을 경우 

| 속성값 | 의미 | 
|:----------|:----------|
| flex-start(default) | items를 시작점으로 정렬 |
| flex-end) | items를 끝점으로 정렬 |
| center | items를 가운데 정렬 |
| space-between | 시작 item은 시작점에 마지막 item은 끝점에 정렬되고 나머지 사이 간격이 고르게 정렬 |
| space-around | item를 균등한 여백을 포함하여 정렬 |

<br>

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">align-items, align-content</span>
교자축을 기준으로 정렬 해주고 싶을 경우
🚨 flex-wrap을 통해 items가 2줄 이상이며 여백이 있는 경우만 가능

| 속성값 | 의미 | 
|:----------|:----------|
| stretch(default) | Container의 교자 축을 채우기 위해 items를 늘린다. |
| flex-start | items를 시작점으로 정렬 |
| flex-end | items를 끝점으로 정렬 |
| center | items를 가운데 정렬 |
| space-between | 시작 item은 시작점에 마지막 item은 끝점에 정렬되고 나머지 사이 간격이 고르게 정렬 |
| space-around | items를 균등한 여백을 포함하여 정렬 |

>- align-items : 하나의(각자의) flex line에 흐르는 교자축을 기준으로 정렬 <br>(flex wrap : nowrap, rap 모두 사용 가능) <br>*예외적으로 space-between, space-around는 space가 요소와 요소사이의 간격을 주는 것이기 때문에 사용 불가*
- align-content : 각자의 교자축을 기준으로 하는 것이 아닌 전체를 기준으로 하여 교자축을 정렬 할 때 사용(flex wrap : rap 일 경우 사용)<br>이때는  space-between과 space-around는 사용 가능

**📢 TIP** 먼저  align-items를 해보고 안되면 그 이후에 align-content를 사용하면 좋다.

## 👉 <span style="background-color:#F15F5F; color:#fff;">Float</span>
float를 사용하는 이유 : block요소들을 가로배치 하기 위해
요소를 좌우방향(수평정렬)으로 띄울 수 있게 하는 역할 (메뉴 또는 레이아웃을 구성한다.)

| 속성값 | 의미 | 
|:----------|:----------|
| none | 요소 간 띄움 없음(default) |
| left | 왼쪽에 요소를 띄운다  (1,2,3,4) |
| right | 오른쪽에 요소를 띄운다(4,3,2,1) * 오른쪽 정렬뿐만 아니라 우측에서 요소가 시작되어 순서가 바뀐다. |

## <span style="color:#2c2c2c;">🤔 float 사용하면 어떻게 변할까?</span>
> - 한 부모에 있는 자식(block)을 float 시킬 경우, 그 자식은 위로 붕뜨게 되며 부모에게 없는 취급을 받게 되고 나머지 자식들은 빈 공간을 채우게 되며,<br> **부모의 height 역시 빠진 자식만큼 줄어들게 된다.**
- left나 right로 지정 시 display속성은 무시되고 **block 태그 성질**을 가진다.(inline,inline block 모두 block으로 변경되어서 width와 height 값을 줄 수 있게된다.)
- 하지만 길을 막지 못하는 block이 된다.<br>- width 값을 주지 않은 상태에서 block을 float할 경우 가지고 있는 content만큼의 크기를 가지게 된다.<br>- float를 사용하면 block 사용 시 자동으로 들어오는 margin값도 들어오지 않게 된다.
- float 나만 볼 수 있다.(block안에 있는 content들은 float에 영향을 받고 layout이 무너져버린다.)


## <span style="color:#2c2c2c;">🤔 float 사용 후 붕괴된 레이아웃 복구하는 법</span>
float 속성이 적용된 요소의 주위로 다른 요소들이 흐르게 되는데 이를 방지하기 위해 속성을 **해제**해야한다.
🚨 float	 해지하지 않을 경우 요소가 겹처 다음에 오는 것을 뒤덮는 현상이 발생할 수 있다.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">clear : left/right/both</span>
- 다음으로 오는 형제 요소에 clear : left/right/both를 추가해 해제한다.
- 단, 다음으로 오는 형제 요소에는 float 속성이 적용 되어있지 않아야한다.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">overflow : hidden/auto</span>
- 부모에게 overflow : hidden을 적용하면 float로 인해 집나간 자식을 찾아온다.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">Clearfix</span>
- 가장 모범적으로 하는 방법 clear는 float로 인하여 망가진 속성을 고치기 위해 만들어진 것이다.(부모요소에 clearfix **class**를 추가 class=clearfix)
- clear : left 👉 left로 float된 요소를 찾아 영향을 받지 않는다.
- clear : both 👉 left, right 모두 찾아내서 영향을 받지 않겠다.
- clear은 display가 block인 요소에만 적용 가능하다.

#### 🙆‍♀️ <span style="color:#F15F5F;">float : left 사용시에는 clear : left, float : right 사용시에는 clear : right 해제</span>

<br>

## 👉 <span style="background-color:#F15F5F; color:#fff;">Position</span>
요소에 좌표값을 주어보다 자유롭게 배치가 가능하게 한다.

**🚨 주의할 점 2가지**
1. 내가 어떤 종류의 position을 사용하고 있는지
2. 내가 사용하는 포지션은 어떤 **기준**으로 요소를 위치시키는지

| 속성값 | 의미 | 
|:----------|:----------|
| static | (기본값) 위에서 아래로 흐름대로 위치 시킴 |
| relative | (상대적위치) 부모요소에 적용, 본래 위치하는 자리를 기준으로 좌표값 설정하여 위치시킴 |
| absolute | (절대적위치) 자식요소에 적용, 나를 포함하는 상위요소를 기준으로 하여 좌표값 설정하여 위치시킴 |
| fixed | viewport을 기준으로 좌표값을 설정하여 위치시킴 |
| sticky | 스크롤시 위치의 값을 인식해 fixed 속성을 적용시킴 (IE에서 지원하지 않아 많이 사용안됨) |

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">static</span>
- 모든 요소의 default 포지션 값

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">relative</span>
- **이동의 기준점** : 자기 자신이 본래 있었던 자리 / 사용하게되면 float처럼 붕 뜨는 것처럼 되지만, float와는 다르게 자신의 원래 위치를 기억하고 있음<br>
> position : relative; <br>top : 20px; 👉 top을 기준으로 20px 떨어짐.<br>right : 200px; 👉 right을 기준으로 200px 떨어짐.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">absolute</span>
- **자신이 정하고 싶은 기준점(부모)을 새로 정할 수 있음** <-> float는 부모를 자신이 고를 수 없고 자기 직계부모를 기준점으로 둔다.
- 선택의 기준 : position이 static이 아닌 요소를 기준으로 해서 자기 자신을 위치시킨다.
- 자신이 어떤 조상 요소를 기준으로 삼아서 이동할 것인지 기준점 설정이 반드시 필요하다. (대게 주변 요소에 아무런 영향을 끼치지 않는 relative를 설정한다)
<br>
> #### float와 유사한 점
- display가  block으로 바뀐다.
- 길을 막지 못하는 block(margin은 안생김)
- float 처럼 붕 뜬다 그래서 밑이나 옆에 있는 요소가 float처럼 기준이 되는 요소 자리로 올라온다.
- 자식이 absolute를 사용하는 순간 부모는 자식이 집 나갔다 생각하여 height를 줄인다.

### 💁‍♀️  <span style="background-color:#F2CB31; color:#2c2c2c;">fixed</span>
- absolute와 거의 동일하다.
- fixed와 absolute의 차이는 fixed는 명확한 기준점이 있다 = viewport<br>(viewport = 내가 보고 있는 브라우저 창의 전체)
- 브라우저상 아래 내용을 보기 위해 드래그로 내려도 fixed로 고정한 것은 계속 그 자리에 고정(ex. 퀵메뉴)

## <span style="color:#2c2c2c;">🤔 z-index</span>
position을 사용해서 해당 요소가 붕뜨게 되었을 경우, 자기 자신이 z축으로 어느 위치에 있는지를 설정하는 속성이다. 설정하는 이유는 2개의 요소를 position으로 띄운 경우 한 요소가 다른 한 요소의 일부분을 덮으려고 할 때 사용한다.
**z-index : 2/ z-index : 1 이 경우 2가 1보다 위에 있으므로 2가 1을 덮어버린다.**

#### 🙆‍♀️ <span style="color:#F15F5F;"> 특정 장소에 고정시켜 놓아야 한다 = position</span>

#### 🙆‍♀️ <span style="color:#F15F5F;">두 요소를 옆으로 배치시켜야 한다 = float</span>

<br>

## ❗️마치며❗️ 
레이아웃 파트는 할때마다 늘 새롭게 느껴져요 마치 처음 배우는 것 같은..
이해가 어느정도 되었다 생각해서 막상 코딩을 짜보면 제대로 사용하지 못하고 버벅거리기만 하니까 답답하네요 😢 그래도 포기하지말고 이해가 제대로 될 때까지 반복해서 공부합시다 화이팅..! 🙋‍♀️

