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

font-size: 1px; /* フォントサイズ */

line-heght: 1px; /* 行間 */




```


