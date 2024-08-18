---
title: Fedoraがemergencymodeに突入してしまったお話
published: 2017-07-20
tags: ["Archive","Linux","Fedora"]
category: Diary
image: https://livedoor.blogimg.jp/harukin0731/imgs/8/c/8c82c0b4.jpg
draft: false
---

どうも皆様こんにちは、harukinでございます。<br>
すっかり忘れかける所でしたが、FedoraがEmergency modeが発動してしまったので後学もついでに書いておきます。<br>
<br>
まあとりあえず画像見てもらいましょう。<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/8/c/8c82c0b4.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/8/c/8c82c0b4-s.jpg" alt="image" class="pict" width="480" hspace="5" height="360" border="0"></a></div><br>
<span style="font-size: x-small;">Emergencymodeとは→何らかの原因でLinuxが正常に起動しない場合に発動する所謂Windowsでのセーフモードのようなものらしいです。</span><br>
<span style="font-size: medium;"><font color="#ff0000">やっちゃいました＼(^o^)／</font></span><br>
なんでだろう、とりあえず何かテキスト保存されてるっぽいから<br>
cd /run/initramfs/<br>
./rdsosreport.txt<br>
あれ？実行ファイルでないって怒られた(´･ω･`)<br>
そりゃそうか、<span style="font-size: large;">実行ファイルじゃなくてテキストファイルだもんなw</span><br>
気を取り直して<br>
vi ./rdsosreport.txt<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/1/d/1d996179.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/1/d/1d996179-s.jpg" alt="image" class="pict" width="480" hspace="5" height="360" border="0"></a></div><br>
お、出てきた。<br>
これは...起動ログみたいやな。<br>
下にガンガン行くとなんかerror見つけた。<br>
/dev/mapper/fedora-rootがおかしいらしい。fsckしろと。<br>
ほいほい了解で～す、<br>
fsck /dev/mapper/fedora-root<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/7/1/71968a09.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/7/1/71968a09-s.jpg" alt="image" class="pict" width="480" hspace="5" height="360" border="0"></a></div><br>
あー、やっぱり壊れちゃってたのね。<br>
ほい、y、yっと。<br>
よし、完了。<br>
最後に<br>
~/shutdown<br>
これで再起動するから、さてどうなるかな？？<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/5/d/5d40043e.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/5/d/5d40043e-s.jpg" alt="image" class="pict" width="480" hspace="5" height="360" border="0"></a></div><br>
よし、復活！！<br>
<br>
でもこれ、壊れたのを無理矢理直したに過ぎないからデスクトップ開いたら一部おかしくなってた。<br>
恐らく壊れてたのはカーネルだろうから更新したら直るかなぁとupdate見てみるとあった。<br>
そこで先日の記事に引き継がれるのです......<br>
無事にアプデ掛けたら完全復活したので満足満足。<br>
<br>
で、何故壊れちゃったのかと考察したら、その事件の前日Windowsを起動してシャットダウンしたところいつまでたってもシャットダウンしない(多分Win側の問題)ので電源ボタンブチ切っちゃったんですけど多分そのときにやらかしたんじゃないかなぁと(笑)<br>
というのも、とあるソフトでWindowsからLinuxの各種パーティションにアクセスできるようにしていたので改変されてしまったのだと思われます....<br>
いやはや、怖いねぇ！(笑)<br>
もし同じ現象に会った方に役に立つかもしれないと思いながらここに置いておきます。
