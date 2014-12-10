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

## HTML
HTMLはウェブ上の文書を記述するためのマークアップ言語です。

[World Wide Web(通称：W3C)](http://ja.wikipedia.org/wiki/World_Wide_Web_Consortium)で使用される各種技術の標準化を推進する為に設立された標準化団体が作ったHTMLやXHTML,CSSなどの規格があるので正しいコーディングについてはしっかり確認しましょう。

####参照サイト
[HTML の構文チェック - W3C Markup Validation Service](http://webkaru.net/dev/html-w3c-markup-validation-service/)


### コメント
コメントの書き方はHTMLは<!-- -->、CSSは/* */といった形で1行〜複数行までがコメントになります。
```html
HTML
<!-- これはコメント -->
```

```css
CSS
/* これはコメント */
```

