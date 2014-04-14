% title: Famo.us is now open source
% subtitle: UIE LT 2014/04/14
% author: Kazumasa Kohtaka
% contact: <span>e-mail</span> <a href="mailto:kkohtaka@uievolution.com">kkohtaka@uievolution.com</a>
% favicon: http://uievolution.co.jp/favicon.ico

---
title: Famo.us って?

* Web app (HTML5 app) を Native app のパフォーマンスで実行させるためのエンジン
* これまで Private Beta で利用されていたが, 誰でも見られるようになった
	* [Famo.us Launch Event](https://www.youtube.com/watch?v=YmQMVjCVZBo)

---
title: Demo - Rise

* [http://demo.famo.us/rise/](http://demo.famo.us/rise/)

<img src="http://api.qrserver.com/v1/create-qr-code/?color=000000&amp;bgcolor=FFFFFF&amp;data=http%3A%2F%2Fdemo.famo.us%2Frise%2F&amp;qzone=1&amp;margin=0&amp;size=200x200&amp;ecc=L" />

---
title: Demo - Twitter

* [http://demo.famo.us/tweetus/](http://demo.famo.us/tweetus/)

<img src="http://api.qrserver.com/v1/create-qr-code/?color=000000&amp;bgcolor=FFFFFF&amp;data=http%3A%2F%2Fdemo.famo.us%2Ftweetus%2F&amp;qzone=1&amp;margin=0&amp;size=200x200&amp;ecc=L" />

---
title: Demo - Game

* [http://famous-bird.herokuapp.com/](http://famous-bird.herokuapp.com/)

<img src="http://api.qrserver.com/v1/create-qr-code/?color=000000&amp;bgcolor=FFFFFF&amp;data=http%3A%2F%2Ffamous-bird.herokuapp.com%2F&amp;qzone=1&amp;margin=0&amp;size=200x200&amp;ecc=L" />

---
title: Demo - Others

* [http://www.codepen.io/befamous/](http://www.codepen.io/befamous/)

<img src="http://api.qrserver.com/v1/create-qr-code/?color=000000&amp;bgcolor=FFFFFF&amp;data=http%3A%2F%2Fwww.codepen.io%2Fbefamous%2F&amp;qzone=1&amp;margin=0&amp;size=200x200&amp;ecc=L" />

---
title:  どうやって使うの?

* [Famo.us](https://github.com/Famous/famous) on Github

* [Node.js](http://nodejs.org/) & [Yeoman](http://yeoman.io/) (Scaffolding) & [Grunt](http://gruntjs.com/) (Build)

<pre class="prettyprint" data-lang="bash">
$ npm install -g generator-famous
$ mkdir newProject
$ cd newProject
$ yo famous
$ grunt serve
</pre>

---
title:  どうやって実現しているの?

* DOM を使わずに独自のレンダリングエンジンを持つことで実現
	* 最終的にブラウザで表示される際にはもちろん DOM になるが, JavaScript から DOM へアクセスしないという意味

* いくつかの CSS プロパティに対して使われる H/W アクセラレーションを利用している
	* [matrix3d()](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function)
	* [window.requestAnimationFrame()](https://developer.mozilla.org/en-US/docs/Web/API/window.requestAnimationFrame)
	* 60FPS を実現している

---
title:  Dev Tools で見てみる

* [The Future of Javascript Animation with Famo.us](http://blog.percolatestudio.com/engineering/the-future-of-javascript-animation-with-famous/)

* [Web Page Design with the GPU in Mind](https://developers.google.com/events/io/sessions/325091862)


---
title:  他のライブラリと併用できる?

* どうやっているのか分からないが, Launch Event では [Angularjs](http://angularjs.org/) と併用できると言っていた

---
title:  まとめ

* Famo.us は CSS 経由で H/W を利用して描画を行っている
* Famo.us は高性能だが, 利用するには Famo.us の流儀に従わなければならない (DOM を捨てなければならない)
* 他のライブラリとの併用の仕方は今のところ不明
