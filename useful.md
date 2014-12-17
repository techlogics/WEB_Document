# Tech Logics WEBアプリ開発者養成ドキュメント - よく使う実践的コード

ここではよく使う実践的コードについてまとめたいと思います。


##横並びの方法

横並びの方法は基本的に  

* float:left もしくはright（ただし*1 clearfixには気をつける）
* display: inline-block
* display: table-cell

*1 [floatを解除する手法のclearfix と 次世代のレイアウトの話](http://kojika17.com/2013/06/clearfix-2013.html)

の３通りがあります。  
用途がそれぞれ違いますので下記のデモを御覧ください。

###[デモページ](http://jsfiddle.net/icchi/c39h3ojg/)



##中央揃え

* text-align: center;
* margin: 0 auto;

の２通りがあります。  
text-align: center;は文字通りテキストを中央揃えするもので  
margin: 0 auto;は左右のmarginをautoにすることで要素ごと中央に持ってきています。


##スマホで横スクロールさせない

* overflow-x: hidden;

ただし効かない時はposition: relative;をつける。

```html

body{
    position: relative;
    overflow-x: hidden;
}

```

##水平線＜hr＞

htmlは＜hr＞のみ。

```html
<hr>
```

```css

hr{
    border:none;
    border-top:dashed 1px #CCC;
    height:1px;
    color:#FFFFFF;
    margin: 0 6 0 6;
}

```

####参照サイト
[[CSS] 水平線＜hr＞のスタイルを変更する](http://tande.jp/lab/2011/05/1384)
