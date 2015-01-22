# Tech Logics WEBアプリ開発者養成ドキュメント - ライブラリ

ここでは知っておくべきライブラリについてまとめたいと思います。

##スライドショー

弊社では一番導入がしやすいbxsliderを推奨しています。  

* [公式HP - bxslider](http://bxslider.com)
* [サンプル集 - bxslider](http://zxcvbnmnbvcxz.com/demonstration/slide_in_slide.html)

カルーセル（自動）の動きや向きにbxsliderでは限度があるため、  
カルーセルに長けたい場合はOwl Carouselを推奨しています。

* [レスポンシブデザインにぴったりなカルーセルスライダー「Owl Carousel」](http://sterfield.co.jp/designer/レスポンシブデザインにぴったりなカルーセルス.html)

###その他おすすめスライダー
* [ANIMATIONS FOR THUMBNAIL GRIDS](http://tympanus.net/codrops/2013/10/23/animations-for-thumbnail-grids/)
* [FULLSCREEN SLIT SLIDER WITH JQUERY AND CSS3](http://tympanus.net/codrops/2012/06/05/fullscreen-slit-slider-with-jquery-and-css3/)


####参照サイト
* [【jQuery】かっこいいスライドショーまとめ](http://matome.naver.jp/odai/2132616911530364801)


##LightBox(サムネイル画像拡大表示)

Webページ上のサムネイル画像を拡大表示できるJavaScriptのライブラリ  
画像集などによく使われる。

###おすすめLightBox
* [Simple Lightbox - Lokesh Dhakar](http://lokeshdhakar.com/projects/lightbox2/)
* [[JS]Lightboxの進化形！操作性が快適でフラットなデザインにもぴったりなレスポンシブ対応のスクリプト -Strip](http://coliss.com/articles/build-websites/operation/javascript/jquery-plugin-strip.html)

####参照サイト
* [個人的に気に入ってる10のLightbox系jQueryプラグイン及び、その特徴まとめ](http://kachibito.net/web-design/10-lightbox-jquery-plugins.html)


また、表示する要素内を細かく編集するのであれば  
jQueryのfadeIn,fadeOutを使って１から作る方が楽である。（下記のコードは複数対応）

```html
HTML

<!-- 黒透明の背景 -->
<div class="overlay></div>

<div class="list"><!-- クリックする要素 -->
~~~
</div>
<div class="pop"><!-- 表示させる要素 -->
~~~
	<div class="exit"></div><!-- 閉じるボタン -->
</div>

```

```css
CSS

.overlay{
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height:100%;
	background: rgba(0,0,0,0.6);
	display: none;
}

.pop{
	display: none;
}

```

```javascript
JavaScript

$(function(){
	$(".list").click(function(){
		$(".overlay").fadeIn();
		$(this).next(".pop").fadeIn();
	});
	$(".overlay,.exit").click(function(){
		$(".pop, .overlay").fadeOut();
	});
});

```


##カレンダー

静的ページであれば弊社の推奨ライブラリはFullCalendarです。

[多機能のカレンダーを実装するjQueryプラグインのFullCalendar](http://sterfield.co.jp/designer/多機能のカレンダーを実装するjqueryプラグインのfullcalendar.html)

###[デモページ](http://codepen.io/iw3/pen/lyhmI/)


##カスタムスクロール

スクロールをもっと充実させたい方におすすめ！  
`overflow: scroll;`にした場合でも慣性を使ったスクロールができます。

[スクロールバーのデザインをカスタマイズする超多機能jQueryプラグイン「custom scrollbar」](http://eturlt.net/blog/20130612/customscrollbar/)

###[デモページ](http://manos.malihu.gr/repository/custom-scrollbar/demo/examples/complete_examples.html)


##立体的な3Dのタブ

ロジックスでは[TECH SPACE - テクノロジー系まとめサイト](http://techspace.link)で使われております。

* [要素を立体的に回転させて動かすエフェクトTURNBOX.jsの実装方法](http://liginc.co.jp/web/js/jquery/116636)


##その他おすすめライブラリ

###・[jQueryプラグイン集 - skuare.net](http://www.skuare.net/test/jQuery_2.html)
###・[今風になった！Web制作で使える最近のjQueryプラグインまとめ](http://commte.net/blog/archives/4794)

