My Sass Style Guide
-------


UI Frameworks를 베이스로 사용하지 않을 때 일반 스타일 가이드 입니다.  
형식과 구조는 작업시 최대한 준수하고 있으며, 새롭게 알게되는 부분은 즉시 반영합니다.  

형식
====
1. 들여쓰기(indent)는 기본 space 2칸을 기준으로 사용합니다. (예외: JavaScript의 경우 - 4칸)  
2. ID 선택자는 사용을 지양합니다.  
3. Class Naming은 BEM(Block-Element-Modifier) 방식을 바탕으로 하되, OOCSS(Object Oriented CSS)을 혼용해서 사용이 가능하며, 하이픈(-) 이나 언더바(_) 사용을 지향합니다. (Camel case는 지양)  

<span style="color:green">**yes!**</span>
```
<h1 class="article__title">기사 제목</h1>
//OOCSS 와 BEM 을 혼합해 사용한 경우(수식어를 --로 연결하지 않고 OOCSS로 표현)
<button class="article-blog__btn active">blog</button>
```
<span style="color:red">**no!**</span>
```
<h1 class="articleTitle">기사 제목</h1>
<button class="article-blog__btn--active">blog</button>
```
---- 

1. 네이밍은 알아보기 쉽게 줄여쓰지 않고 완전한 단어를 사용합니다. (사전에 특정한 단어에 대해 합의한 규칙이 있는 경우 줄여쓰기가 가능합니다.)  

<span style="color:green">**yes!**</span>
```
<h1 class="member-security__title">회원 보안</h1>
```
<span style="color:red">**no!**</span>
```
<h1 class="member-secu__tit">회원 보안</h1>
```
---- 
1. 규칙 선언부의 여는 괄호 { 이전에 띄어쓰기를 넣습니다.
2. 속성 부분에서 : 문자 뒤에 띄어쓰기를 넣습니다. 단, : 문자 앞에는 띄어쓰기를 넣지 않습니다.
3. 규칙 선언부의 닫는 괄호 } 를 새로운 줄에 넣습니다.  

<span style="color:green">**yes!**</span>
```
.show__caution {
  float: left;
  margin-top: 1em;
}
```
<span style="color:red">**no!**</span>
```
.show__caution{
  float:left;
  margin-top:1em;}
```
----

1. 주석은 새로운 줄에 적습니다. 선택자 또는 속성과 같은 줄에 주석을 작성하는 방식을 피해주세요.  
2. 자바스크립트를 바인드 해야할 때는 CSS와 겹치지 않는 별도의 클래스를 만들어 사용합니다.

<span style="color:green">**yes!**</span>
```
js-(접두어)
<button class="menu__btn js-menu__btn"></button>
```

<span style="color:red">**no!**</span>
```
<button class="menu__btn"></button>
```

구조
====

1. base
    1. _reset.scss (초기화)
    2. _fonts.scss (폰트)
2. components (모듈)
    1. _button.scss
    2. _modal.scss 
    3. _layer-popup.scss
    4. ...
3. layout
    1. _header.scss(상단 공통 레이아웃)
    2. _footer.scss(하단 공통 레이아웃)
    3. _common.scss(공통 레이아웃)
    4. ...
4. pages
    1. _index.scss
    2. _login.scss
    3. ...
5. utils
    1. _var.scss (Sass 변수)
    2. _mixin.scss (Sass Mixin)
6. vendors
    1. _bootstrap.scss(css)
    2. _semantic.scss(css)
    3. ....  

index.scss

* 위의 구조는 [이 주소]()에서 확인및 다운로드가 가능합니다.


구조 네이밍 규칙
====
1. import 파일은 파일명 앞에 언더바(_)를 사용합니다.
2. 단어와 단어사이에는 하이픈(-)을 사용합니다.
3. vendors의 경우에는 때에 따라 css파일을 import합니다.
