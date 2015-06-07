react
======================

参考サイト
------
[ReactのTutorialをArdaで写経してみる(Babel版)](http://qiita.com/akiramei/items/d6ef17784afdd7f838c3 "")

[Reactとbrowserifyとbabelifyによるブラウザ上でのNode.js資産の活用](http://blog.knjcode.com/react-browserify-babelify-string-codec/ "")

[Hello React.js](http://qiita.com/koba04/items/ecebd86eaee6cb1ad0eb "")

[React.js を試す – ツリービュー](http://akabeko.me/blog/2014/12/reactjs-treeview/ "")

[いま最も注目のライブラリ「React.js」でシングルページアプリケーションを作ってみよう！ 【前編】](http://codezine.jp/article/detail/8491 "")

[React.js + Webpack + ContainerJSでTODOリストを作ってみた](http://unageanu.hatenablog.com/entry/2015/03/18/072511 "")

[Reactでちょっとしたサービスを作りました](http://lealog.hateblo.jp/entry/2015/05/06/002643 "")


はまりポイント
-----

>react@0.13.1 では Uncaught TypeError: Cannot read property '__reactAutoBindMap' ofundefined が発生しました。以下のようにするとエラー回避できるみたいです。

>diff --git a/src/main.js b/src/main.js
index 83ec83a..4eb2e95 100644
--- a/src/main.js
+++ b/src/main.js
@@ -1,7 +1,7 @@
 var React = require('react');
 var view = require('./view.jsx');

>-React.renderComponent(
-  view(),
+React.render(
+  React.createElement(view),
   document.getElementById('content')
 );
