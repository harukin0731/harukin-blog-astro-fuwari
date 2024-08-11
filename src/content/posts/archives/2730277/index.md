---
title: アップデートのトランザクションについて
published: 2017-07-18
tags: ["Archive","Linux","Fedora"]
category: Diary
image: https://livedoor.blogimg.jp/harukin0731/imgs/1/4/1417b1a2.png
draft: false
---


どうも皆様こんにちは、harukinでございます。<br>Fedora26が最近公開されたようで、早速更新をしてみました。<br>が、方法は<a target="_blank" href="https://fedorajp.jimdo.com/%E6%9B%B4%E6%96%B0/">こちら</a>のサイトがとてもわかり易く紹介してあるので見てください()<br>今回はその過程で発生したトランザクションエラーに関して説明をしていきたいと思います。<br><a target="_blank" title="Mate Terminal_327" href="https://livedoor.blogimg.jp/harukin0731/imgs/1/4/1417b1a2.png"><img class="pict" alt="Mate Terminal_327" src="https://livedoor.blogimg.jp/harukin0731/imgs/1/4/1417b1a2-s.png" width="480" hspace="5" height="250" border="0"></a><br>Fedoraを使用していると遭遇する最大の悩み、トランザクション。<br>ややこしいったらありゃしない。<br>意味わからん・・・・<br>結論から行くと、少しめんどくさいですが手動でアプデをしてあげることでトランザクションを突破することができるようになります。<br>このスクショの場合は <br><blockquote>sudo dnf update 表示されているパッケージ名<br></blockquote>と試していくといつかできるようになります()<br>私の場合はこのbaseの方だけを手動でupdateさせた後にまとめてアプデをすることで突破できました。<br>以前はそれぞれ競合ということできちんと理解せずに競合対象をアンインストールさせていましたが残念ながらどちらもアンインストールさせるわけにはいかない重要なソフトに依存されていたので調べてみた所存です。<br>初めて気がついたので参考程度に。
