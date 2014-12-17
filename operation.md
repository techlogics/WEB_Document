# Tech Logics WEBアプリ開発者養成ドキュメント - 開発フロー/運用/保守性

ここでは運用をする際に押さえておかなければならないことをまとめたいと思います。  
個人開発とは違い、集団開発になると今後の運用のために予め決めておかなければならない最低限のルールなどあります。  
集団でスムーズに開発するためにも最低限のルールを押さえておきましょう。


##HTML,CSSのid,classの付け方、及びhtmlの構成
id名やclass名をつけるのに時間がかかったり、みんながそれぞれのclass名を付けてしまった場合  
CSSがバラバラになり規則性が失われてしまうので規則を統一する必要がある。  
あくまで下記は参考コードなのでデザインによって用途を変えなければならないが  
__デザインの統一性のためにも横幅、縦幅、隙間の感覚などはclassで統一するべき__である。  
classは1つの.htmlファイルに__複数回使える__のに対して  
idは__1度しか使えない__ため基本的にidは__場合によって適応させるための緊急用__と考えることも有り。  

一般的には

* チェインケース（例： class="top-box" top-img01.png）

* スネークケース（例： class="top_box" top_img01.png）

* キャメルケース（例： class="topBox" topImg01.png）

の３種類に分かれている。

弊社は要素を繋げる際に「_」（アンダーバー・スネークケース）を利用するとする。


###【参照１】HTMLの構造（例）
```html
HTMLコード例）

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

<!-- バージョン毎のデフォルトjs -->
<!--[if IE]>
<script type="text/javascript" src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->

</head>
<body>

   <div id="container">
      <!-- それぞれの分野でidをつける -->
      <header id="header" class="wrapper"><!-- デザインによって.wrapper で幅を統一 -->
         <div class="header_wrapper">
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
      <div class="main_wrapper">
         <!-- それぞれの分野でidをつける -->
         <div id="top" class="wrapper">
            <!-- そうすることによって分野ごとで同じ横幅（.wrapper）のレイアウトだけどそれぞれで細かい違いがある場合でも #top h2, #top p などidと要素だけで管理できる  -->
            <section class="top_wrapper"><!-- 次にh2などh要素がくるためsection -->
               <h2></h2>
               <div class="content">
                  <p></p>
                  <img src="images/top/top_img01.png" alt="">
               </div>
            </section>
         </div>
         <!-- それぞれの分野でidをつける -->
         <div id="blog" class="wrapper">
            <section class="blog_wrapper">
               <h2></h2>
               <div class="content">
                  <h3></h3>
                  <div class="box_wrapper clearfix">
                     <div class="common_box">
                        <img src="images/blog/blog_img01.png" alt="">
                     </div>
                     <div class="common_box">
                        <img src="images/blog/blog_img01.png" alt="">
                     </div>
                  </div>
               </div>
            </section>
         </div>
      </div>
   </div><!-- #container 全体のとじタグ -->
   
   <!-- 通常js部分 -->
	<script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
	<script src="//code.jquery.com/jquery-migrate-1.2.1.min.js"></script>
	<script type="text/javascript" src="js/common.js"></script>
	<script type="text/javascript" src="js/top.js"></script>
	
</body>

```

まだまだ命名方法はあるので命名については下記参照サイトを参考にしてもらいたい。

####参照サイト
[ID名とクラス名のサンプル集](http://www.tagindex.com/stylesheet/basic/naming.html)

--

###JavaScript（JS）の読み込み場所
弊社では

* if分内のjsはhead内
* 通常のjsはbodyの閉じタグ前

と2通りにjsの読み込み場所を変えております。（詳しくは上部【参照１】のコードへ）  
jqueryやcanvasになると最後に読み込まないと動かない場合がある（htmlが読み込まれてからでないと動かない場合がある）といった理由で


####参照サイト
* [JavaScriptの読み込み位置をページ最後にしたほうがよい理由](http://memocarilog.info/jquery/5842)



##CSSの構成・規約

```css

/*--- スペースいれる ---*/
.class1 {
 
}

/*--- 複数の場合は改行 ---*/
.class1,
.class2,
.class3{
 
}

```

###ページ数が少ない場合

* css
 * reset.css(全ページ必ず共通)
 * style.css(全ページ必ず共通、idでcssを振り分ける)

詳しくは上部【参照１】のコードへ


###複数ページの場合（ページ数が多い場合）

* css
 * reset.css(全ページ必ず共通)
 * common.css(全ページ必ず共通)
 * top.css(各ページに対応)
 * blog.css(各ページに対応)

 

```css

common.cssの例）

/*---- 間隔（margin,padding）----*/
.mg0 {
	margin:0px;
}
.pd0 {
	padding:0px;
}
.mg5 {
	margin:5px;
}
.pd5 {
	padding:5px;
}
.mg10 {
	margin:10px;
}
.pd10 {
	padding:10px;
}
～
.mg50 {
	margin:50px;
}
.pd50 {
	padding:50px;
}

/*---- フォント---- */
.fs10 {
	font-size:10px;
}
.fs11 {
	font-size:11px;
}
.fs12 {
	font-size:12px;
}
～
.fs20 {
	font-size:20px;
}


```


##画像



