# Tech Logics WEBアプリ開発者養成ドキュメント - 文法

## イントロダクション

ホームページ作成やWEBの基本といえばHTML。HTMLで枠組みを作り、
基本的な見栄えをCSS形成し、アニメーションや値の受け渡しなど特有な動作をしたい場合はJavaScriptを用いる。

WEBエンジニアにはおおまかに３種類のエンジニアに分かれており、

HTML,CSS,JavaScriptなどを扱い、見栄えの部分を形成するエンジニアを__フロントエンドエンジニア__  
PHPやRuby,Javaなどサーバーサイドを扱うエンジニアのことを__バックエンドエンジニア__  
Linuxサーバやセキュリティ、パフォーマンス測定に趣きを置くのを__インフラエンジニア__

と呼ばれています。

####参照サイト
[フロントエンド、サーバサイド、インフラの具体例](http://qiita.com/shuntaro_tamura/items/e1a20e33c57c71679688)

---

ここではHTML,CSSに関する基本的な知識を説明します。
また、既存のチュートリアルサイトで良いものがたくさんあるので
先に下記で紹介するそちらをおすすめ致します。

##おすすめ参考サイト
* [W3Schools Online Web Tutorials](http://www.w3schools.com)
海外の入門サイト。
HTML,HTML5,CSS,CSS3,JavaScript,jQuery,SQL,PHPまで全てあり
デモ環境も揃っているのでだいたいのチュートリアルは理解できるはず。


##HTML
HTMLはウェブ上の文書を記述するためのマークアップ言語です。
####参照サイト
[Wikipedia - HTML](http://ja.wikipedia.org/wiki/HyperText_Markup_Language)


-

###HTMLタグを把握しよう

####参照サイト
* [HTML 要素リファレンス - MDN](https://developer.mozilla.org/ja/docs/Web/HTML/Element)
* [HTMLタグリファレンス（目的別）](http://www.htmq.com/html/indexm.shtml)


-
###正しい構文を身につけよう
[World Wide Web(通称：W3C)](http://ja.wikipedia.org/wiki/World_Wide_Web_Consortium)で使用される各種技術の標準化を推進する為に設立された標準化団体が作ったHTMLやXHTML,CSSなどの規格があるので正しいコーディングについてはしっかり確認しましょう。

####参照サイト
* [HTML の構文チェック - W3C Markup Validation Service](http://webkaru.net/dev/html-w3c-markup-validation-service/)



##CSS
CSSは、HTMLやXMLの要素をどのように修飾（表示）するかを指示する、W3Cによる仕様の一つで、文書の構造と体裁を分離させるという理念を実現する為に提唱されたスタイルシートの具体的な仕様の一つ。
####参照サイト
[Wikipedia - CSS](http://ja.wikipedia.org/wiki/Cascading_Style_Sheets)



-

##HTMLの要素一覧

```html
HTML

<!-- コメントアウト -->

<div></div> <!-- 基本的なブロック要素 -->

<section></section> <!-- 意味や機能のひとまとまりのこと -->

<article></article> <!-- 独立した記事のセクション -->

```

##CSSの要素一覧

```css
CSS

/* コメントアウト */
/*font-size ・・・ フォントサイズ */
font-size: 1px; /* フォントサイズ */

/*font-style ・・・ フォントスタイル */
font-style: normal; /* 初期値。標準 */
font-style: italic; /* イタリック体 */
font-style: oblique; /* 斜体 */

/* font-variant ･･･ フォントをスモールキャップにする */
font-variant: normal; /* 初期値。標準 */
font-variant: small-caps; /* スモールキャップのフォントで表示 */

/* font-weight ･･･ フォントの太さを指定 */

font-weight: normal; /* 標準(400) */
font-weight: bold; /* 太字(700) */
font-weight: lighter; /*相対的に補足する */
font-weght: bolder; /* 相対的に太くする */
font-weght: 100; /*100,200,300,400,500,600,700,800,900で指定 */

/* font-family ･･･ フォントの種類を指定 */
/* フォント名で指定 シングルコーテーション(')またはダブルコーテーション(")で囲む*/
font-family: "ＭＳ ゴシック"; /* MSゴシック */
font-family: "ＭＳ 明朝"; /* MS明朝 */
/* キーワードで指定 */
font-family: sans-serif; /* ゴシック系のフォント */
font-family: serif; /* 明朝系のフォント */
font-family: cursive; /* 筆記体・草書体のフォント */
font-family: fantasy; /* 装飾的なフォント */
font-family: monospace; /* 等幅フォント */
/* 複数指定で環境で利用可能なものが選択され、イメージに近いフォントを表示させることが出来る */
font-family: "ＭＳ ゴシック",sans-serif;
font-family: "ＭＳ 明朝",serif;

/* font-size-adjust ･･･ フォントのサイズを調整 */
font-size-adjust: none; /* 初期値 */
font-size-adjust: 0.5; /* ( 小文字xの高さ / フォントの高さ )の数値で指定 */



line-heght: 1px; /* 行間 */


/*width ・・・ 幅を指定*/
width: auto; /*初期値。自動設定*/
width: 1px; /*値で指定*/
width: 1%;/*%で指定*/

/*max-width ・・・ 幅の最大値を指定*/
max-width: none; /*初期値。最大値を制限しない*/
max-width: 1px; /*値で指定*/
max-width: 1%; /*%で指定*/

/*min-width ・・・ 幅の最小値を指定*/
min-width: 1px; /*値で指定*/
min-width: 1%; /*%で指定*/


/*height ・・・ 高さを指定*/
height: auto; /*初期値。自動設定*/
height: 1px; /*値で指定*/
height: 1%;/*%で指定*/

/*max-height ・・・ 高さの最大値を指定*/
max-height: none; /*初期値。最大値を制限しない*/
max-height: 1px; /*値で指定*/
max-height: 1%; /*%で指定*/

/*min-height ・・・ 高さの最小値を指定*/
min-height: 1px; /*値で指定*/
min-height: 1%; /*%で指定*/


/*margin ・・・ 外側の余白を指定*/
margin: auto; /*自動*/
margin: 1px; /*数値で指定*/
margin: 1%; /*%で指定*/
/*２つの値で上、下の外側の余白を指定*/
margin: 1px 2px;/*上1px 下2px;*/
/*3つの値で上、左右、下の外側の余白を指定*/
margin: 1px 2px 3px;/*上1px 左右2px; 下3px*/
/*4つの値で上、右、下、左の外側の余白を指定*/
margin: 1px 2px 3px 4px; /*上1px、右2px、下3px、左4px*/

/*margin-top ・・・ 上の外側の余白を指定*/
/*margin-left ・・・ 右の外側の余白を指定*/
/*margin-rigth ・・・ 左の外側の余白を指定*/
/*margin-bottom ・・・ 下の外側の余白を指定*/


/*padding ・・・ 内側の余白を指定*/
padding: auto; /*自動*/
padding: 1px; /*数値で指定*/
padding: 1%; /*%で指定*/
/*２つの値で上、下の内側の余白を指定*/
padding: 1px 2px;/*上1px 下2px;*/
/*3つの値で上、左右、下の内側の余白を指定*/
padding: 1px 2px 3px;/*上1px 左右2px; 下3px*/
/*4つの値で上、右、下、左の内側の余白を指定*/
padding: 1px 2px 3px 4px; /*上1px、右2px、下3px、左4px*/

/*padding-top ・・・ 上の内側の余白を指定*/
/*padding-left ・・・ 右の内側の余白を指定*/
/*padding-rigth ・・・ 左の内側の余白を指定*/
/*padding-bottom ・・・ 下の内側の余白を指定*/


/*color ・・・ 文字色、色を指定*/
color: #000000; /* 黒 */
color: #f00; /* 赤 */
color: rgb(0,255,0); /* 緑 */
color: rgba(0,0,0,0.5);/* 半透明の黒 */
color: blue; /* 青,カラーネームで指定,red,green,black,orangeなど */


/*background ・・・ 背景に関する指定*/
background: #000000; /* 背景色を黒にする */
background: url("../image/bg.jpg"); /* 背景をbg.jpgにする */
background: rgb(0,0,0) url("../image/bg.jpg"); /* 背景色を黒,bg.jpgにする */

/*background-color ・・・ 背景色を指定 */
background-color: transparent; /* 背景透明。初期値 */
background-color: #ffffff; /* 背景色を白にする */
background-color: rgba(255,0,0,0.5); /* 背景色を半透明の赤にする */

/*background-image ・・・ 背景画像を指定 */
background-image: none; /* 何もない 初期値 */
background-image: url(URI); /* 背景をURIで指定した画像にする */
background-image: url("../image/bg.jpg"); /* 背景をbg.jpgにする */

/*background-attachment ・・・ 背景画像の固定・移動を指定 */
background-attachment: fixed; /* 背景画像を固定、スクロールしても動かない */
background-attachment: scroll; /* スクロールで背景画像が移動 */

/*background-position ・・・ 背景画像の表示位置を指定 */
background-position: right; /* 右側に表示 top,right,left,bottom,centerで指定できる*/
background-position: left bottom; /*左下に表示 */
background-position: 30% 50%; /*左から30%、上から50%のところに表示 */
background-position: 100px 200px; /*左から100px、上から200pxのところに表示 */

/*background-repeat ・・・ 背景画像のリピートを指定 */
background-repeat: repeat; /* 初期値。繰り返して表示 */
background-repeat: repeat-x; /* 横方向のみ繰り返して表示 */
background-repeat: repeat-y; /* 縦方向のみ繰り返して表示 */
background-repeat: no-repeat; /*画像を一回だけ表示させて繰り返さない */





```


