# Tech Logics WEBアプリ開発者養成ドキュメント - 開発フロー/運用/保守性

ここでは運用をする際に押さえておかなければならないことをまとめたいと思います。<br>
個人開発とは違い、集団開発になると今後の運用のために予め決めておかなければならない最低限のルールなどあります。<br>
集団でスムーズに開発するためにも最低限のルールを押さえておきましょう。


##HTML,CSSのid,classの付け方、及びhtmlの構成
id名やclass名をつけるのに時間がかかったり、みんながそれぞれのclass名を付けてしまった場合<br>
CSSがバラバラになり規則性が失われてしまうので規則を統一する必要がある。<br>
あくまで下記は参考コードなどでデザインによって用途を変えなければならないが<br>
__デザインの統一性のためにも横幅、縦幅、隙間の感覚などはclassで統一するべき__である。
classは1つの.htmlファイルに複数回使えるのに対して<br>
idは1度しか使えないため基本的に__場合によって適応させるための緊急用__と考えることも有り。

弊社は要素を繋げる際に「-」（ハイフン）を利用するとする。

```html
HTML

<body>
   <div id="container">
      <!-- それぞれの分野でidをつける -->
      <header id="header" class="wrapper"><!-- デザインによって.wrapper で幅を統一 -->
         <div class="header-wrapper">
            <h2 class="logo"><img src="" alt=""></h2>
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
               </div>
            </section>
         </div>
         <!-- それぞれの分野でidをつける -->
         <div id="blog" class="wrapper">
            <section class="blog-wrapper">
               <h2></h2>
               <div class="content">
                  <p></p>
               </div>
            </section>
         </div>
      </div>
   </div><!-- #container 全体のとじタグ -->
</body>

```

まだまだ命名方法はあるので命名については下記参照サイトを参考にしてもらいたい。

####参照サイト
[ID名とクラス名のサンプル集](http://www.tagindex.com/stylesheet/basic/naming.html)

---