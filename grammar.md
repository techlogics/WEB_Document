# Tech Logics iOSアプリ開発者養成ドキュメント


## イントロダクション

ホームページ作成やWEBの基本といえばHTML。HTMLで枠組みを作り、
基本的な見栄えをCSS形成し、アニメーションや値の受け渡しなど特有な動作をしたい場合はJavaScriptを用いる。

WEBエンジニアにはおおまかに３種類のエンジニアに分かれており、
HTML,CSS,JavaScriptなどを扱い、見栄えの部分を形成するエンジニアを*フロントエンドエンジニア*
PHPやRuby,Javaなどサーバーサイドを扱うエンジニアのことを*バックエンドエンジニア*
Linuxサーバやセキュリティ、パフォーマンス測定に趣きを置くのを*インフラエンジニア*
と呼ばれています。

*参照サイト
[linkref]: http://qiita.com/shuntaro_tamura/items/e1a20e33c57c71679688 "フロントエンド、サーバサイド、インフラの具体例"

---

ここではHTML,CSSに関する基本的な知識を説明します。

## HTML
HTMLはウェブ上の文書を記述するためのマークアップ言語です。
[linkref]: http://ja.wikipedia.org/wiki/World_Wide_Web_Consortium "World Wide Web(通称：W3C)" で使用される各種技術の標準化を推進する為に設立された標準化団体が作ったHTMLやXHTML,CSSなどの規格があるので正しいコーディングについてはしっかり確認しましょう。

*参照サイト
[linkref]: http://webkaru.net/dev/html-w3c-markup-validation-service/ "HTML の構文チェック - W3C Markup Validation Service"


### コメント
コメントの書き方はHTML,CSS共に、// で1行コメント、/**/ で複数行コメントになります。
```html
<!-- これはコメント -->
```

```css
/* これはコメント */
```

