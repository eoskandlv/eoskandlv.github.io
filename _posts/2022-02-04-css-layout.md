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

# ๐ CSS layout
css์์ ๋ง์ด ์ฌ์ฉ๋๊ณ  ์ค์ํ์ง๋ง ์ !๋ง! ํท๊ฐ๋ฆฌ๋ <br>๋ ์ด์์(display, float, position, flexbox) ๋ถ๋ถ์ ๋ํด ์ ๋ฆฌ ํด๋ณด๋๋ก ํฉ์๋ค.๐ 

## ๐ <span style="background-color:#F15F5F; color:#fff;">Display</span>
**display : box type์ ๊ฒฐ์ ํ๋ css ์์ฑ**
block ๋ฉด(์์ญ) / inline ์ (ํ๋ฆ) ์ผ๋ก ๋ณด๋ฉด ์ดํด๊ฐ ์ฌ์ธ ๊ฒ ๊ฐ๋ค.

| ์์ฑ๊ฐ | ์๋ฏธ | ์ข๋ฅ |
|:----------|:----------|:----------|
| block | - ํ ์ค์ ํ๋์ฉ ์์ ๋ฐฐ์น = ์ธ๋ก๋ก ๋ฐฐ์น<br>- ๊ธฐ๋ณธ width ๊ฐ์ด 100% <br> - width, height๊ฐ์ ๊ฐ์ง ์ ์์<br>- vertical-align ์ ์ฉ๋์ง ์์<br>- text-align ์ ์ฉ๋์ง ์์| div, h1~h6, p, ul, li, dl, table, td, <br>th, figure,hr, figcaption, caption,<br> header, nav, footer, section, article,<br> aside, blockqoute, form, fiedset...|
| inline | - ํ ์ค์ ์ฌ๋ฌ๊ฐ ๋ฐฐ์น = ๊ฐ๋ก๋ก ๋์ด๋๋ ์์ผ๋ก ๋ฐฐ์น<br>- ๊ธฐ๋ณธ width ๊ฐ์ ์ปจํ์ธ  ๋๋น ๊ฐ <br> - width, height๊ฐ์ ๊ฐ์ง ์ ์์<br>- ์์์์๋ก ๋ ๋ค๋ฅธ ์ธ๋ผ์ธ ํ๊ทธ๋ง ๊ฐ๋ฅ(p์ ์ธ)| span, a, em, del, br, q, strong, input<br>textarea, select, img... |
| inline-block | - ํ ์ค์ ์ฌ๋ฌ ๊ฐ ๋ฐฐ์น(์ธ๋ผ์ธ) + ๋๋น๋์ด ์ง์ ๊ฐ๋ฅ(๋ธ๋ก)| 


### ๐โโ๏ธ <span style="background-color:#F2CB31; color:#2c2c2c;">block</span>
> - ๊ธธ์ ๋ง๋ ์ฑ์ง์ ๊ฐ์ง๊ณ  ์๋ค.
- **width๋ฅผ ๋ฐ๋ก ์ ์ธํ์ง ์์ ๊ฒฝ์ฐ**, width = ๋ถ๋ชจ์ content-box์ 100%
- **width๋ฅผ ๋ฐ๋ก ์ ์ธํ ๊ฒฝ์ฐ**, ๋จ์ ๊ณต๊ฐ์ margin์ด ์ฑ์์ง<br>(์์ญ์ ์นจ๋ฒ ๋นํ์ง ์๊ธฐ ์ํด์)
- block์ ๊ฒฝ์ฐ width, height, padding, border, margin์ ๋ชจ๋ ์ฌ์ฉํ  ์ ์๋ค.
- block type์ **๊ฐ์ด๋ฐ ์ ๋ ฌํ๋ ๋ฐฉ๋ฒ : margin : 0 auto** ๐ margin top๊ณผ bottom์ 0์ ์ฃผ๊ณ  right์ left๋ auto (๋จ๋ px๋ฅผ ์๋์ผ๋ก ์ฑ์)๋ฅผ ์ค๋ค๋ ๊ฒ์ด๋ค. *๋ณ๋๋ก margin left : auto;๋ง ์ฃผ๋ฉด block์ ์ค๋ฅธ์ชฝ ์ ๋ ฌ์ด ๋๋ค.*

#### โ๏ธ ์์) ๋ถ๋ชจ์ width๊ฐ 1000px์ด๋ผ๊ณ  ๊ฐ์  ํ, ์์ width๋ฅผ 600px๋ก ์ง์ ํ๋ฉด ๋จ์ 400px์ด ์๋์ ์ผ๋ก margin์ผ๋ก ์ฑ์์ง๋ค.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">inline</span>
> - ์ํ์ผ๋ก ์์ธ๋ค.
- ๊ฐ๋ก, ์ธ๋ก ๊ฐ ๊ฐ์ง์ ์๋ค.
- text ์์ฑ๊ณผ ๋์ผํ ๋งฅ๋ฝ, ์์ผ๋ก ๋ ์ธ ๊ณต๊ฐ์ด ์์ผ๋ฉด ์๋์ ์ผ๋ก ๋ฐ ์ค๋ก ๋ด๋ ค๊ฐ
- margin๊ณผ padding์ top,bottom์ ์ฌ์ฉํ  ์ ์๋ค.
- **width, height, padding-top, padding-bottom, border-top, border-bottom, margin-top, margin-bottom** ์ฌ์ฉ์ด **๋ถ๊ฐ**ํ๋ค.(์ ์๋์ ํฌ๊ธฐ๋ฅผ ๋ณ๊ฒฝํ๋๊ฒ์ ์๋๋ค ๊ธฐ์กด ์์ญ์ ๋ฎ์ด๋ฒ๋ฆฌ๊ธฐ ๋๋ฌธ์)

#### ๐ง width๊ฐ ์๋๋ ์ด์  : ์ธ๋ผ์ธ ์์์ width๋ฅผ ๋ถ๋ชจ ์์๊ฐ ๋ค ๋ด์ ์ ์๋ ์ํฉ์ผ ๋ ์ ๋งคํด์ง๊ธฐ ๋๋ฌธ์ width๊ฐ ์๋๋ฐ ์ธ๋ผ์ธ ์์๋ฅผ ๋์ด์ ๋ฐ ์ค์ ๋ด๋ ค ๋์ ์๋, ๋ถ๋ชจ๋ฅผ ์ค๋ฒํด์ ๋๊ฐ ์๋ ์๊ธฐ ๋๋ฌธ์ด๋ค.



### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">inline-block</span>
> - block์ ์ฅ์ ๊ณผ inline์ ์ฅ์ ์ ๊ฐ์ง๊ณ  ์๋ค.
- text์ ํนํ๋์ด ์์ง๋ง, ๊ฐ๋ก/์ธ๋ก ๊ฐ์ ๊ฐ์ง ์ ์๋ค. 
-margin๊ณผ padding์ top,bottom ๊ฐ๋ ๊ฐ์ง ์ ์๋ค.
- inline์ฒ๋ผ ํ๋ฅด์ง๋ง **width, padding-top, padding-bottom, border-top, border-bottom, margin-top, margin-bottom**์ด ์ฌ์ฉ **๊ฐ๋ฅ**ํ๋ค.

<br>

## ๐ <span style="background-color:#F15F5F; color:#fff;">Flexbox</span>
flexbox๋ ์์์ ํฌ๊ธฐ๊ฐ ๋ถ๋ถ๋ชํ  ๋์๋ ๋ด๊ฐ ์ํ๋ ํฌ๊ธฐ์ box ์์ items์ ๋ฃ์ด์ ๋์ผํ ๊ฐ๊ฒฉ๊ณผ ์ฌ์ด์ฆ๋ก ๋ฐฐ์ดํ๋ ๊ฒ์ด๋ค.

flexbox๋ฅผ ์ฌ์ฉํ  ๋ ์ฃผ์ํด์ผ ํ  **4๊ฐ์ง ์์**

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">flexbox ์ ์ธ</span>

> - ๋ด๊ฐ ์ ๋ ฌ์ ํ๋ ค๊ณ  ํ๋ ์์์ <span style="color:red;">**๋ถ๋ชจ**</span>์๊ฒ flexbox์ ์ธ์ ํด์ผํ๋ค. 
๐ display : flex; (box์ ํ์์ด๋ฉฐ ๊ธฐ๋ณธ์ ์ผ๋ก block๊ณผ ๋น์ทํ์ง๋ง block์ ๋ถ๊ฐ๋ฅํ ์์๋ ์์)
- ๋ง์ฝ ๋ถ๋ชจ ์์๊ฐ inline ์ด๋ผ๋ฉด display : inline-flex๋ก ์ง์ ํด์ค๋ค.

<br>

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">flex-direction </span>
flex items์ ์ฃผ์ถ(main-axis)๋ฅผ ์ค์ ํด์ค๋ค.

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------:|
| row(default) | items๋ฅผ ์ผ์ชฝ์์ ์ค๋ฅธ์ชฝ(์ํ์ถ)์ผ๋ก ํ์ <br> A,B,C |
| row-reverse | items๋ฅผ row ๋ฐ๋์ถ์ผ๋ก ํ์ <br> C,B,A |
| column | items๋ฅผ ์์ชฝ์์ ์๋์ชฝ(์์ง์ถ)์ผ๋ก ํ์ <br> A<br>B<br>C |
| column-reverse | items๋ฅผ column ๋ฐ๋ ์ถ์ผ๋ก ํ์ <br>C<br>B<br>A |

<br>

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">flex-wrap </span>
items์ ์ฌ๋ฌ ์ค ๋ฐ๊ฟ์ ์ค์ ํด์ค๋ค.

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------|
| nowrap(default) | ๋ชจ๋  items์ด ํ ์ค์ ๋ฐฐ์น๊ฐ ๋๋ค. |
| wrap | items๋ฅผ ์ฌ๋ฌ ์ค๋ก ๋ฐฐ์นํด ๋์น๋ฉด ์๋๋ก ๋จ์ด์ง๊ฒ ํ๋ค. (width,height ์ง์  ๊ฐ๋ฅ) |
| wrap-reverse | items๋ฅผ wrap์ ์ญ ๋ฐฉํฅ์ผ๋ก ์ฌ๋ฌ ์ค๋ก ๋ฐฐ์น. |

> #### flex-wrap : nowrap; (๊ธฐ๋ณธ๊ฐ) ๐ ์ค ๋ฐ๊พธ์ง ์์
๋ถ๋ชจ width๊ฐ 600px์ด๊ณ  ์์์ด 300px์ฉ ๊ฐ์ง๊ณ  ์๋ค๋ฉด, ๊ธฐ๋ณธ์ ์ผ๋ก 300px+300px๋ก 2๊ฐ๋ง ์ฌ ์ ์์ง๋ง flex-wrap : nowrap;์ ์ฌ์ฉํ๋ฉด ๊ฐ์ธ์ง ์๊ณ  ์์์ ์ฌ์ด์ฆ๋ฅผ ์ค์ฌ ํ ์ค๋ก ์ ๋ ฌํ๋ค. (200px์ฉ ํ ์ค๋ก) 

#### flex-wrap : wrap; ๐ ์ค ๋ฐ๊ฟ
๋ถ๋ชจ width๊ฐ 600px์ด๊ณ  ์์์ด 300px์ฉ ๊ฐ์ง๊ณ  ์๋ค๋ฉด 300px+300px๋ก 2๊ฐ๊ฐ ์ค๊ณ  ๋ฐ ์ค์ 300px์ด ๋จ์ด์ง๋ค. ํ ์ค์ ๋ชจ๋ ์ ๋ ฌํ  ๋ ๊ณต๊ฐ์ด ๋ถ์กฑํ๋ฉด ์ฌ๋ฌ ์ค์ ๋ง๋ ๋ค.

** ๐ค ๊ฐ์ ์ง์ ํด์ฃผ์ง ์์ ๊ฒฝ์ฐ ๋ชจ๋  ์์๋ค์ด ํ ์ค์ ์ ๋ ฌ๋๋ ค๊ณ  ํ๊ธฐ ๋๋ฌธ์ width ๊ฐ์ ์ฃผ์ด overflow ๋ ์์๋ค์ ๋ฐ์ผ๋ก ๋จ์ด์ง๊ฒ ํ๋ค**

<br>

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">justify-content</span>
๋ด๊ฐ ์ ์ธํ flex-direciton๊ณผ ๊ฐ์ ๋ฐฉํฅ, ์ฆ ์ฃผ์ถ์ ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ ํด์ฃผ๊ณ  ์ถ์ ๊ฒฝ์ฐ 

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------|
| flex-start(default) | items๋ฅผ ์์์ ์ผ๋ก ์ ๋ ฌ |
| flex-end) | items๋ฅผ ๋์ ์ผ๋ก ์ ๋ ฌ |
| center | items๋ฅผ ๊ฐ์ด๋ฐ ์ ๋ ฌ |
| space-between | ์์ item์ ์์์ ์ ๋ง์ง๋ง item์ ๋์ ์ ์ ๋ ฌ๋๊ณ  ๋๋จธ์ง ์ฌ์ด ๊ฐ๊ฒฉ์ด ๊ณ ๋ฅด๊ฒ ์ ๋ ฌ |
| space-around | item๋ฅผ ๊ท ๋ฑํ ์ฌ๋ฐฑ์ ํฌํจํ์ฌ ์ ๋ ฌ |

<br>

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">align-items, align-content</span>
๊ต์์ถ์ ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ ํด์ฃผ๊ณ  ์ถ์ ๊ฒฝ์ฐ
๐จ flex-wrap์ ํตํด items๊ฐ 2์ค ์ด์์ด๋ฉฐ ์ฌ๋ฐฑ์ด ์๋ ๊ฒฝ์ฐ๋ง ๊ฐ๋ฅ

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------|
| stretch(default) | Container์ ๊ต์ ์ถ์ ์ฑ์ฐ๊ธฐ ์ํด items๋ฅผ ๋๋ฆฐ๋ค. |
| flex-start | items๋ฅผ ์์์ ์ผ๋ก ์ ๋ ฌ |
| flex-end | items๋ฅผ ๋์ ์ผ๋ก ์ ๋ ฌ |
| center | items๋ฅผ ๊ฐ์ด๋ฐ ์ ๋ ฌ |
| space-between | ์์ item์ ์์์ ์ ๋ง์ง๋ง item์ ๋์ ์ ์ ๋ ฌ๋๊ณ  ๋๋จธ์ง ์ฌ์ด ๊ฐ๊ฒฉ์ด ๊ณ ๋ฅด๊ฒ ์ ๋ ฌ |
| space-around | items๋ฅผ ๊ท ๋ฑํ ์ฌ๋ฐฑ์ ํฌํจํ์ฌ ์ ๋ ฌ |

>- align-items : ํ๋์(๊ฐ์์) flex line์ ํ๋ฅด๋ ๊ต์์ถ์ ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ <br>(flex wrap : nowrap, rap ๋ชจ๋ ์ฌ์ฉ ๊ฐ๋ฅ) <br>*์์ธ์ ์ผ๋ก space-between, space-around๋ space๊ฐ ์์์ ์์์ฌ์ด์ ๊ฐ๊ฒฉ์ ์ฃผ๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ ์ฌ์ฉ ๋ถ๊ฐ*
- align-content : ๊ฐ์์ ๊ต์์ถ์ ๊ธฐ์ค์ผ๋ก ํ๋ ๊ฒ์ด ์๋ ์ ์ฒด๋ฅผ ๊ธฐ์ค์ผ๋ก ํ์ฌ ๊ต์์ถ์ ์ ๋ ฌ ํ  ๋ ์ฌ์ฉ(flex wrap : rap ์ผ ๊ฒฝ์ฐ ์ฌ์ฉ)<br>์ด๋๋  space-between๊ณผ space-around๋ ์ฌ์ฉ ๊ฐ๋ฅ

**๐ข TIP** ๋จผ์   align-items๋ฅผ ํด๋ณด๊ณ  ์๋๋ฉด ๊ทธ ์ดํ์ align-content๋ฅผ ์ฌ์ฉํ๋ฉด ์ข๋ค.

## ๐ <span style="background-color:#F15F5F; color:#fff;">Float</span>
float๋ฅผ ์ฌ์ฉํ๋ ์ด์  : block์์๋ค์ ๊ฐ๋ก๋ฐฐ์น ํ๊ธฐ ์ํด
์์๋ฅผ ์ข์ฐ๋ฐฉํฅ(์ํ์ ๋ ฌ)์ผ๋ก ๋์ธ ์ ์๊ฒ ํ๋ ์ญํ  (๋ฉ๋ด ๋๋ ๋ ์ด์์์ ๊ตฌ์ฑํ๋ค.)

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------|
| none | ์์ ๊ฐ ๋์ ์์(default) |
| left | ์ผ์ชฝ์ ์์๋ฅผ ๋์ด๋ค  (1,2,3,4) |
| right | ์ค๋ฅธ์ชฝ์ ์์๋ฅผ ๋์ด๋ค(4,3,2,1) * ์ค๋ฅธ์ชฝ ์ ๋ ฌ๋ฟ๋ง ์๋๋ผ ์ฐ์ธก์์ ์์๊ฐ ์์๋์ด ์์๊ฐ ๋ฐ๋๋ค. |

## <span style="color:#2c2c2c;">๐ค float ์ฌ์ฉํ๋ฉด ์ด๋ป๊ฒ ๋ณํ ๊น?</span>
> - ํ ๋ถ๋ชจ์ ์๋ ์์(block)์ float ์ํฌ ๊ฒฝ์ฐ, ๊ทธ ์์์ ์๋ก ๋ถ๋จ๊ฒ ๋๋ฉฐ ๋ถ๋ชจ์๊ฒ ์๋ ์ทจ๊ธ์ ๋ฐ๊ฒ ๋๊ณ  ๋๋จธ์ง ์์๋ค์ ๋น ๊ณต๊ฐ์ ์ฑ์ฐ๊ฒ ๋๋ฉฐ,<br> **๋ถ๋ชจ์ height ์ญ์ ๋น ์ง ์์๋งํผ ์ค์ด๋ค๊ฒ ๋๋ค.**
- left๋ right๋ก ์ง์  ์ display์์ฑ์ ๋ฌด์๋๊ณ  **block ํ๊ทธ ์ฑ์ง**์ ๊ฐ์ง๋ค.(inline,inline block ๋ชจ๋ block์ผ๋ก ๋ณ๊ฒฝ๋์ด์ width์ height ๊ฐ์ ์ค ์ ์๊ฒ๋๋ค.)
- ํ์ง๋ง ๊ธธ์ ๋ง์ง ๋ชปํ๋ block์ด ๋๋ค.<br>- width ๊ฐ์ ์ฃผ์ง ์์ ์ํ์์ block์ floatํ  ๊ฒฝ์ฐ ๊ฐ์ง๊ณ  ์๋ content๋งํผ์ ํฌ๊ธฐ๋ฅผ ๊ฐ์ง๊ฒ ๋๋ค.<br>- float๋ฅผ ์ฌ์ฉํ๋ฉด block ์ฌ์ฉ ์ ์๋์ผ๋ก ๋ค์ด์ค๋ margin๊ฐ๋ ๋ค์ด์ค์ง ์๊ฒ ๋๋ค.
- float ๋๋ง ๋ณผ ์ ์๋ค.(block์์ ์๋ content๋ค์ float์ ์ํฅ์ ๋ฐ๊ณ  layout์ด ๋ฌด๋์ ธ๋ฒ๋ฆฐ๋ค.)


## <span style="color:#2c2c2c;">๐ค float ์ฌ์ฉ ํ ๋ถ๊ดด๋ ๋ ์ด์์ ๋ณต๊ตฌํ๋ ๋ฒ</span>
float ์์ฑ์ด ์ ์ฉ๋ ์์์ ์ฃผ์๋ก ๋ค๋ฅธ ์์๋ค์ด ํ๋ฅด๊ฒ ๋๋๋ฐ ์ด๋ฅผ ๋ฐฉ์งํ๊ธฐ ์ํด ์์ฑ์ **ํด์ **ํด์ผํ๋ค.
๐จ float	 ํด์งํ์ง ์์ ๊ฒฝ์ฐ ์์๊ฐ ๊ฒน์ฒ ๋ค์์ ์ค๋ ๊ฒ์ ๋ค๋ฎ๋ ํ์์ด ๋ฐ์ํ  ์ ์๋ค.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">clear : left/right/both</span>
- ๋ค์์ผ๋ก ์ค๋ ํ์  ์์์ clear : left/right/both๋ฅผ ์ถ๊ฐํด ํด์ ํ๋ค.
- ๋จ, ๋ค์์ผ๋ก ์ค๋ ํ์  ์์์๋ float ์์ฑ์ด ์ ์ฉ ๋์ด์์ง ์์์ผํ๋ค.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">overflow : hidden/auto</span>
- ๋ถ๋ชจ์๊ฒ overflow : hidden์ ์ ์ฉํ๋ฉด float๋ก ์ธํด ์ง๋๊ฐ ์์์ ์ฐพ์์จ๋ค.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">Clearfix</span>
- ๊ฐ์ฅ ๋ชจ๋ฒ์ ์ผ๋ก ํ๋ ๋ฐฉ๋ฒ clear๋ float๋ก ์ธํ์ฌ ๋ง๊ฐ์ง ์์ฑ์ ๊ณ ์น๊ธฐ ์ํด ๋ง๋ค์ด์ง ๊ฒ์ด๋ค.(๋ถ๋ชจ์์์ clearfix **class**๋ฅผ ์ถ๊ฐ class=clearfix)
- clear : left ๐ left๋ก float๋ ์์๋ฅผ ์ฐพ์ ์ํฅ์ ๋ฐ์ง ์๋๋ค.
- clear : both ๐ left, right ๋ชจ๋ ์ฐพ์๋ด์ ์ํฅ์ ๋ฐ์ง ์๊ฒ ๋ค.
- clear์ display๊ฐ block์ธ ์์์๋ง ์ ์ฉ ๊ฐ๋ฅํ๋ค.

#### ๐โโ๏ธ <span style="color:#F15F5F;">float : left ์ฌ์ฉ์์๋ clear : left, float : right ์ฌ์ฉ์์๋ clear : right ํด์ </span>

<br>

## ๐ <span style="background-color:#F15F5F; color:#fff;">Position</span>
์์์ ์ขํ๊ฐ์ ์ฃผ์ด๋ณด๋ค ์์ ๋กญ๊ฒ ๋ฐฐ์น๊ฐ ๊ฐ๋ฅํ๊ฒ ํ๋ค.

**๐จ ์ฃผ์ํ  ์  2๊ฐ์ง**
1. ๋ด๊ฐ ์ด๋ค ์ข๋ฅ์ position์ ์ฌ์ฉํ๊ณ  ์๋์ง
2. ๋ด๊ฐ ์ฌ์ฉํ๋ ํฌ์ง์์ ์ด๋ค **๊ธฐ์ค**์ผ๋ก ์์๋ฅผ ์์น์ํค๋์ง

| ์์ฑ๊ฐ | ์๋ฏธ | 
|:----------|:----------|
| static | (๊ธฐ๋ณธ๊ฐ) ์์์ ์๋๋ก ํ๋ฆ๋๋ก ์์น ์ํด |
| relative | (์๋์ ์์น) ๋ถ๋ชจ์์์ ์ ์ฉ, ๋ณธ๋ ์์นํ๋ ์๋ฆฌ๋ฅผ ๊ธฐ์ค์ผ๋ก ์ขํ๊ฐ ์ค์ ํ์ฌ ์์น์ํด |
| absolute | (์ ๋์ ์์น) ์์์์์ ์ ์ฉ, ๋๋ฅผ ํฌํจํ๋ ์์์์๋ฅผ ๊ธฐ์ค์ผ๋ก ํ์ฌ ์ขํ๊ฐ ์ค์ ํ์ฌ ์์น์ํด |
| fixed | viewport์ ๊ธฐ์ค์ผ๋ก ์ขํ๊ฐ์ ์ค์ ํ์ฌ ์์น์ํด |
| sticky | ์คํฌ๋กค์ ์์น์ ๊ฐ์ ์ธ์ํด fixed ์์ฑ์ ์ ์ฉ์ํด (IE์์ ์ง์ํ์ง ์์ ๋ง์ด ์ฌ์ฉ์๋จ) |

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">static</span>
- ๋ชจ๋  ์์์ default ํฌ์ง์ ๊ฐ

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">relative</span>
- **์ด๋์ ๊ธฐ์ค์ ** : ์๊ธฐ ์์ ์ด ๋ณธ๋ ์์๋ ์๋ฆฌ / ์ฌ์ฉํ๊ฒ๋๋ฉด float์ฒ๋ผ ๋ถ ๋จ๋ ๊ฒ์ฒ๋ผ ๋์ง๋ง, float์๋ ๋ค๋ฅด๊ฒ ์์ ์ ์๋ ์์น๋ฅผ ๊ธฐ์ตํ๊ณ  ์์<br>
> position : relative; <br>top : 20px; ๐ top์ ๊ธฐ์ค์ผ๋ก 20px ๋จ์ด์ง.<br>right : 200px; ๐ right์ ๊ธฐ์ค์ผ๋ก 200px ๋จ์ด์ง.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">absolute</span>
- **์์ ์ด ์ ํ๊ณ  ์ถ์ ๊ธฐ์ค์ (๋ถ๋ชจ)์ ์๋ก ์ ํ  ์ ์์** <-> float๋ ๋ถ๋ชจ๋ฅผ ์์ ์ด ๊ณ ๋ฅผ ์ ์๊ณ  ์๊ธฐ ์ง๊ณ๋ถ๋ชจ๋ฅผ ๊ธฐ์ค์ ์ผ๋ก ๋๋ค.
- ์ ํ์ ๊ธฐ์ค : position์ด static์ด ์๋ ์์๋ฅผ ๊ธฐ์ค์ผ๋ก ํด์ ์๊ธฐ ์์ ์ ์์น์ํจ๋ค.
- ์์ ์ด ์ด๋ค ์กฐ์ ์์๋ฅผ ๊ธฐ์ค์ผ๋ก ์ผ์์ ์ด๋ํ  ๊ฒ์ธ์ง ๊ธฐ์ค์  ์ค์ ์ด ๋ฐ๋์ ํ์ํ๋ค. (๋๊ฒ ์ฃผ๋ณ ์์์ ์๋ฌด๋ฐ ์ํฅ์ ๋ผ์น์ง ์๋ relative๋ฅผ ์ค์ ํ๋ค)
<br>
> #### float์ ์ ์ฌํ ์ 
- display๊ฐ  block์ผ๋ก ๋ฐ๋๋ค.
- ๊ธธ์ ๋ง์ง ๋ชปํ๋ block(margin์ ์์๊น)
- float ์ฒ๋ผ ๋ถ ๋ฌ๋ค ๊ทธ๋์ ๋ฐ์ด๋ ์์ ์๋ ์์๊ฐ float์ฒ๋ผ ๊ธฐ์ค์ด ๋๋ ์์ ์๋ฆฌ๋ก ์ฌ๋ผ์จ๋ค.
- ์์์ด absolute๋ฅผ ์ฌ์ฉํ๋ ์๊ฐ ๋ถ๋ชจ๋ ์์์ด ์ง ๋๊ฐ๋ค ์๊ฐํ์ฌ height๋ฅผ ์ค์ธ๋ค.

### ๐โโ๏ธ  <span style="background-color:#F2CB31; color:#2c2c2c;">fixed</span>
- absolute์ ๊ฑฐ์ ๋์ผํ๋ค.
- fixed์ absolute์ ์ฐจ์ด๋ fixed๋ ๋ชํํ ๊ธฐ์ค์ ์ด ์๋ค = viewport<br>(viewport = ๋ด๊ฐ ๋ณด๊ณ  ์๋ ๋ธ๋ผ์ฐ์  ์ฐฝ์ ์ ์ฒด)
- ๋ธ๋ผ์ฐ์ ์ ์๋ ๋ด์ฉ์ ๋ณด๊ธฐ ์ํด ๋๋๊ทธ๋ก ๋ด๋ ค๋ fixed๋ก ๊ณ ์ ํ ๊ฒ์ ๊ณ์ ๊ทธ ์๋ฆฌ์ ๊ณ ์ (ex. ํต๋ฉ๋ด)

## <span style="color:#2c2c2c;">๐ค z-index</span>
position์ ์ฌ์ฉํด์ ํด๋น ์์๊ฐ ๋ถ๋จ๊ฒ ๋์์ ๊ฒฝ์ฐ, ์๊ธฐ ์์ ์ด z์ถ์ผ๋ก ์ด๋ ์์น์ ์๋์ง๋ฅผ ์ค์ ํ๋ ์์ฑ์ด๋ค. ์ค์ ํ๋ ์ด์ ๋ 2๊ฐ์ ์์๋ฅผ position์ผ๋ก ๋์ด ๊ฒฝ์ฐ ํ ์์๊ฐ ๋ค๋ฅธ ํ ์์์ ์ผ๋ถ๋ถ์ ๋ฎ์ผ๋ ค๊ณ  ํ  ๋ ์ฌ์ฉํ๋ค.
**z-index : 2/ z-index : 1 ์ด ๊ฒฝ์ฐ 2๊ฐ 1๋ณด๋ค ์์ ์์ผ๋ฏ๋ก 2๊ฐ 1์ ๋ฎ์ด๋ฒ๋ฆฐ๋ค.**

#### ๐โโ๏ธ <span style="color:#F15F5F;"> ํน์  ์ฅ์์ ๊ณ ์ ์์ผ ๋์์ผ ํ๋ค = position</span>

#### ๐โโ๏ธ <span style="color:#F15F5F;">๋ ์์๋ฅผ ์์ผ๋ก ๋ฐฐ์น์์ผ์ผ ํ๋ค = float</span>

<br>

## โ๏ธ๋ง์น๋ฉฐโ๏ธ 
๋ ์ด์์ ํํธ๋ ํ ๋๋ง๋ค ๋ ์๋กญ๊ฒ ๋๊ปด์ ธ์ ๋ง์น ์ฒ์ ๋ฐฐ์ฐ๋ ๊ฒ ๊ฐ์..
์ดํด๊ฐ ์ด๋์ ๋ ๋์๋ค ์๊ฐํด์ ๋ง์ ์ฝ๋ฉ์ ์ง๋ณด๋ฉด ์ ๋๋ก ์ฌ์ฉํ์ง ๋ชปํ๊ณ  ๋ฒ๋ฒ๊ฑฐ๋ฆฌ๊ธฐ๋ง ํ๋๊น ๋ต๋ตํ๋ค์ ๐ข ๊ทธ๋๋ ํฌ๊ธฐํ์ง๋ง๊ณ  ์ดํด๊ฐ ์ ๋๋ก ๋  ๋๊น์ง ๋ฐ๋ณตํด์ ๊ณต๋ถํฉ์๋ค ํ์ดํ..! ๐โโ๏ธ

