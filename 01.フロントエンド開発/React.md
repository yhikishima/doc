
react
======================

参考サイト
------
[ReactのTutorialをArdaで写経してみる(Babel版)](http://qiita.com/akiramei/items/d6ef17784afdd7f838c3 "")

[Reactとbrowserifyとbabelifyによるブラウザ上でのNode.js資産の活用](http://blog.knjcode.com/react-browserify-babelify-string-codec/ "")

[Hello React.js](http://qiita.com/koba04/items/ecebd86eaee6cb1ad0eb "")


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
