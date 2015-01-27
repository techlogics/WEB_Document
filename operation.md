# Tech Logics WEBアプリ開発者養成ドキュメント - 開発フロー/運用/保守

ここでは運用をする際に押さえておかなければならないことをまとめたいと思います。  
個人開発とは違い、集団開発になると今後の運用のために予め決めておかなければならない最低限のルールなどあります。  
集団でスムーズに開発するためにも最低限のルールを押さえておきましょう。


##フォルダの構成

フォルダの構成は以下のとおりとする。

* フォルダ
	* index.html
	* blog（ページごとのフォルダ）
		* index.html
	* css（フォルダ）
		* reset.css
		* style.css（もしくはcommon.css）
		* blog.css
		* ~~~
	* js（フォルダ）
		* common.js
		* blog.js
		* ~~~
	* images（フォルダ）
		* common（フォルダ）
			* main-bg.png
			* common-banner01.png
		* blog（フォルダ）
			* blog-img01.png
			* blog-img02.png


##HTML,CSSのid,classの付け方、及びHTMLの構成
id名やclass名をつけるのに時間がかかったり、みんながそれぞれのclass名を付けてしまった場合  
CSSがバラバラになり規則性が失われてしまうので規則を統一する必要がある。  
あくまで下記は参考コードなのでデザインによって用途を変えなければならないが  
__デザインの統一性のためにも横幅、縦幅、隙間の感覚などはclassで統一するべき__である。  
classは1つの.htmlファイルに__複数回使える__のに対して  
idは__1度しか使えない__ため基本的にidは__場合によって適応させるための緊急用__と考えることも有り。  

命名方法として一般的に

* __チェインケース__（例： class="top-box" top-img01.png）

* __スネークケース__（例： class="top_box" top_img01.png）

* __キャメルケース__（例： class="topBox" topImg01.png）

の３種類に分かれている。

弊社は要素を繋げる際に「-」（ハイフン・チェインケース）を利用するとする。


###【※参照１】HTMLの構造（例）
```html
HTML5コード例）

<!DOCTYPE HTML> 
<html>
<head>
<meta charset="UTF-8" />
<meta name="keywords" content="Github,ドキュメント,プログラミングコミュニティTECH LOGICS,株式会社Far Connection" />
<meta name="description" content="プログラミングTECH LOGICSは〜" />

<title>WEBアプリ開発者養成ドキュメント - TECH LOGICS</title> 

<!-- ページ数が少ない場合（style.cssに書き込みページごとにcssを分けない）
<link rel=”stylesheet” href="css/reset.css" />
<link rel=”stylesheet” href="css/style.css" />
-->

<!-- 複数ページ（ページ数が多い場合）
<link rel=”stylesheet” href="reset.css" />
<link rel=”stylesheet” href="common.css" />
<link rel=”stylesheet” href="top.css" />
-->

<!-- バージョン毎のデフォルトjsはhead内 -->
<!--[if IE]>
<script type="text/javascript" src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->

</head>
<body>

   <div id="container">
      <!-- それぞれの分野でidをつける -->
      <header id="header" class="wrapper"><!-- デザインによって.wrapper で幅を統一 -->
         <div class="header-wrapper">
            <h2 class="logo"><img src="images/common/logo.png" alt=""></h2>
            <aside id="nav"> <!-- idを上手く使うことでCSSを #nav ul, #nav liの#nav配下で管理できる -->
               <ul>
                  <li></li>
                  <li></li>
                  <li></li>
                  <li></li>
               </ul>
            </aside>
         </div>
      </header>
      <div class="main-wrapper">
         <!-- それぞれの分野でidをつける -->
         <div id="top" class="wrapper">
            <!-- そうすることによって分野ごとで同じ横幅（.wrapper）のレイアウトだけどそれぞれで細かい違いがある場合でも #top h2, #top p などidと要素だけで管理できる  -->
            <section class="top-wrapper"><!-- 次にh2などh要素がくるためsection -->
               <h2></h2>
               <div class="content">
                  <p></p>
                  <img src="images/top/top-img01.png" alt="">
               </div>
            </section>
         </div>
         <!-- それぞれの分野でidをつける -->
         <div id="blog" class="wrapper">
            <section class="blog-wrapper">
               <h2></h2>
               <div class="content">
                  <h3></h3>
                  <div class="box-wrapper clearfix">
                     <div class="common-box">
                        <img src="images/blog/blog-img01.png" alt="">
                     </div>
                     <div class="common-box">
                        <img src="images/blog/blog-img01.png" alt="">
                     </div>
                  </div>
               </div>
            </section>
         </div>
      </div>
   </div><!-- #container 全体のとじタグ -->
   
   <!-- 通常js部分は最後 -->
	<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
	<script src="//code.jquery.com/jquery-migrate-1.2.1.min.js"></script>
	<script type="text/javascript" src="js/common.js"></script>
	<script type="text/javascript" src="js/top.js"></script>
	
</body>

```

まだまだ命名方法はあるので命名については下記参照サイトを参考にしてもらいたい。

####参照サイト
[ID名とクラス名のサンプル集](http://www.tagindex.com/stylesheet/basic/naming.html)



##CSSの構成・規約

弊社のコーディング規約は
[Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#ID_and_Class_Name_Delimiters) に則ります。 
また、html,css規約にてリファクタリングする際、 
HTMLは[Dirty Markup](http://www.dirtymarkup.com) 
CSSは[ProCSSor - Advanced CSS Prettifier](http://tools.maxcdn.com/process) 
の2spacesを推奨します。


```css

クラス名のあとに半角スペース

/* 推奨しない */
.class1{
	position: relative;
}

/* 推奨 */
.class1 {
	position: relative;
}

------------------------------------

bold（値）の前を空ける

/* 推奨しない */
h3 {
  font-weight:bold;
}

/* 推奨 */
h3 {
  font-weight: bold;
}

------------------------------------

font-size（プロパテイ）の前をインデントをつける

/* 推奨しない */
h3 {
font-size: 12px;
}

/* 推奨 */
h3 {
	font-size: 12px;
}

------------------------------------

複数指定する場合は改行

/* 推奨しない */
a:focus, a:active {
	position: relative; top: 1px;
}

/* 推奨 */
h1,
h2,
h3 {
	font-weight: normal;
	line-height: 1.2;
}

------------------------------------

html要素名は簡略化する

/* 推奨しない */
ul#example {}
div.error {}

/* 推奨 */
#example {}
.error {}

------------------------------------

プロパティ名・値はできるだけ簡略化する

/* 推奨しない */
border-top-style: none;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;

/* 推奨 */
border-top: 0;
padding: 0 1em 2em;

------------------------------------

色コードを簡略化出来るならする

/* 推奨しない */
color: #eebbcc;

/* 推奨 */
color: #ebc;

------------------------------------

最後の要素には;（セミコロン）をつける

/* 推奨しない */
.test {
  display: block;
  height: 100px
}

/* 推奨 */
.test {
  display: block;
  height: 100px;
}

------------------------------------


```

###- ページ数が少ない場合

* css
 * reset.css(全ページ必ず共通)
 * style.css(全ページ必ず共通、idでcssを振り分ける)

__詳しくは上部【参照１】のコードへ__


###- 複数ページの場合（ページ数が多い場合）

* css
 * reset.css(全ページ必ず共通)
 * common.css(全ページ必ず共通)
 * top.css(各ページに対応)
 * blog.css(各ページに対応)

 __詳しくは上部【参照１】のコードへ__

 
##デフォルトで便利なCSS

```css

common.cssの例）

/*---- 間隔（margin,padding）----*/
.mg0 {
	margin: 0px;
}
.pd0 {
	padding: 0px;
}
.mg5 {
	margin: 5px;
}
.pd5 {
	padding: 5px;
}
.mg10 {
	margin: 10px;
}
.pd10 {
	padding: 10px;
}
～
.mg50 {
	margin: 50px;
}
.pd50 {
	padding: 50px;
}

/*---- フォント---- */
.fs10 {
	font-size: 10px;
}
.fs11 {
	font-size: 11px;
}
.fs12 {
	font-size: 12px;
}
～
.fs20 {
	font-size: 20px;
}


```

##!importantはなるべく使わない

!importantは優先度を変えてしまうため、ここでつけて問題はないか確認し、  
優先度をしっかり考慮して適切につける。


##画像はPNG

弊社では出来る限り、ファイル容量が軽く透過できる.pngを利用する。
ただしIE6以前で透過PNGが利用できないため、必要に応じてGIFを使い分けます。



##JavaScript（JS）の読み込み場所
弊社では

* if分内のjsはhead内
* 通常のjsはbodyの閉じタグ前

と2通りにjsの読み込み場所を変えております。（ __詳しくは上部【参照１】のコードへ__ ）  
高速化するためや、jqueryやcanvasになると最後に読み込まないと動かない場合がある（htmlが読み込まれてからでないと動かない場合がある）といった理由があります。


####参照サイト
* [JavaScriptの読み込み位置をページ最後にしたほうがよい理由](http://memocarilog.info/jquery/5842)
