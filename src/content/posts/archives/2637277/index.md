---
title: Taskerの動画再生機能で遊んでみる
published: 2017-07-10
tags: ["Archive","Tasker","Android"]
category: Diary
image: https://livedoor.blogimg.jp/harukin0731/imgs/b/c/bc7edc4b.jpg
draft: false
---


どうもみなさんこんにちは、harukinでございます。<br>
『Tasker』というAndroidアプリがありますが、<a href="http://tasker.dinglisch.net/beta.html">現在5.0β版が進行中</a>です。<br>
その5.0での追加機能の一つに動画再生機能があります。<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/b/c/bc7edc4b.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/b/c/bc7edc4b-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
<span style="font-size: xx-small;">ポインターで示してる奴</span><br>
これを活かして、動画プレーヤー(GUIでファイル選択して再生)を作ってみました。<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/0/1/01dd580a.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/0/1/01dd580a-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
<span style="font-size: xx-small;">こんな感じ</span><br>
<br>
<span style="font-size: large;">みんなで作ってみよう</span><br>
勿論Taskerですのでだれでも<span style="font-size: xx-small;">簡単に</span>作ることが出来ますよー！<br>
<b>1 必要な要素について考える</b><br>
動画プレーヤーということですが、動画を再生することだけには留まりませんよね？<br>
<font color="#ff3333">再生、停止、再生位置調整、スキップ、ファイル選択</font>などなど色々な要素が絡んできます。<br>
今のところ(beta5)で私が実現可能としたのは再生、停止、ファイル選択のみになります。後のビルドで変数が追加されたらその時には追記しようと思います。<br>
今回はシンプル(？)にこんな<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/5/4/542e6a60.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/5/4/542e6a60-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
基本的なファイル選択と再生のみを採用した物を作ろうと思います。<br>
<br>
<b>開始</b><br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/4/3/4310b487.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/4/3/4310b487-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
色々項目がありますが、ハイライトされている要素だけを考えてください。<br>
上から、<br>
　1.UI表示<br>
　2.ファイルマネージャーで使うフォルダー内リスト作成<br>
　3.移動したフォルダー数を記憶する変数作成<br>
　4.移動したフォルダーを記録する配列作成<br>
となっております。<br>
2の作業では、配列Fileに/sdcard/の中身を全部保存します。この配列内の要素がファイルマネージャーに表示されます。<br>
3の作業はフォルダーをタップしたときに1から数字が増えていきます。<br>
4の作業はフォルダーをタップしたときにタップしたフォルダーのリンクを保存します。<br>
　memo　各変数の動きの説明<br>
<br>
　　sdcard/test/test2<br>
<br>
　　　というフォルダ階層があるとき....<br>
　　File→sdcardフォルダ内のあらゆるファイルを配列で表示<br>
　　Arrayn→1<br>
　　Oldfile→'/sdcard'<br>
<br>
　testフォルダをタップすると<br>
<br>
　　File→sdcard/testフォルダ内のあらゆるファイルを配列で表示<br>
　　Arrayn→2<br>
　　Oldfile→'/sdcard','/sdcard/test'<br>
<br>
　さらにtest2をタップすると<br>
　　<br>
　　File→sdcard/test/test2フォルダ内の(ry<br>
　　Arrayn→3<br>
　　Oldfile→'/sdcard','/sdcard/test','/sdcard/test/test2'<br>
<br>
①ファイル選択<br>
今回はMenuを使います。<br>
<br>
初めのタスク実行時にFile配列にある要素が表示されます。<br>
SourceをVariable Arrayにして、Variableに%FileでOKです。<br>
ファイルタップ時のスクリプトは下です。<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/5/3/53266f3c.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/5/3/53266f3c-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
一覧にすると、<br>
　1.タップした要素がファイルかフォルダかを識別、変数Filetypeに保存<br>
　2.タップした要素名とFiletype(ファイルかフォルダか)をトーストで出力(無視しておけ)<br>
　3.もし、タップした要素がフォルダーなら...<br>
　<b>4.File配列を消す</b><br>
　5.タップした要素(フォルダー)内のあらゆるファイルをFile配列に出力<br>
　6.変数Arraynに1を足す<br>
　7.Oldfile配列にタップした要素を保存<br>
　8.又は...(2を満たさないとき、すなわちフォルダーでないとき)<br>
　9.タップした要素がファイルなら....<br>
　<b>10.もしタップした要素の文字に[指定の文字]が含まれるなら...</b><br>
　11.タップした要素をビデオとして開く<br>
　12.Playと通知表示<br>
<br>
鬼門となるのが4.と10.です。<br>
4は、たとえば現在の階層にファイルが10個ある場合に移動先が5個だとします。すると移動した場合に上5つは更新されますが下5つは継承されてしまうのです。これは、ファイルを配列として扱う上でどうしようもない点です。<br>
10は、ここに来る時点でファイルが突破した制御は<u>ファイルである</u>ということだけです。つまり、このまま動画を再生させた場合にpng画像やapkファイルなどが動画として読み込まれてしまいます。これを防ぐために、<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/7/a74e3d6e.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/7/a74e3d6e-s.jpg" alt="image" class="pict" width="480" hspace="5" height="853" border="0"></a></div><br>
<font color="#ff0000"><span style="font-size: medium;">独自に拡張子指定したったww</span></font><br>
いやぁこれどうすればいいのかわからなかったんですよね(笑)気にしなくても良いのかもしれないですけど。<br>
ところで、フォルダーを深くまで行ったはいいものの、戻りたい。<br>
そこで右下の戻るボタンの出番ですよ。<br>
奴のスクリプトはこちら↓<br>
<div align="center"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/9/d/9d926656.jpg" title="image" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/9/d/9d926656-s.jpg" alt="image" class="pict" width="480" hspace="5" height="278" border="0"></a></div><br>
上から<br>
　1.変数Arraynを-1する<br>
　2.File配列を消去する<br>
　<b>3.変数Arraynを使ってOldfile配列から要素を呼び出しその要素のあらゆるファイルをFile配列に保存</b><br>
<br>
この3が意味不明だと思います。<br>
上でのmemoを思い出して欲しいのですが、Oldfileの配列には過去にタップしたフォルダが保存されています。実は、これらは<b>全て%Oldfile(数字)でナンバー付けされており、この数字を入力することで配列の任意の値を取り出すことが出来るのです。</b><br>
そして、タップする毎にタップしたフォルダが保存され、数字を入れることにより取り出せる。つまり、この数字を扱うのがArrayn変数であり、この変数を利用して前のフォルダに戻ることが可能になります。<div style="width: 100%; height: auto; clear: both; text-align: center;" class="google-auto-placed ap_container"><ins style="display: block; margin: auto; background-color: transparent; height: 280px;" data-ad-format="auto" class="adsbygoogle adsbygoogle-noablate" data-ad-client="ca-pub-7579303910483862" data-adsbygoogle-status="done"><div id="aswift_3_host" style="border: medium none; height: 280px; width: 800px; margin: 0px; padding: 0px; position: relative; visibility: visible; background-color: transparent; display: inline-block;"></div></ins></div><br>
例　3つ目のフォルダを開いているときにArrayn変数を-1し、%Oldfile(%Arrayn)とすると一つ前のフォルダを呼び出し以下略。<br>
<br>
②再生ボタン<br>
<strike>三つありますが、現在は真ん中の再生ボタンしか動作しません...</strike><br>
ElementVideoControlのタスクのToggleを利用することで再生と一時停止を交互に切り替えることが出来ます。<br>
<br>
③動画再生<br>
ここが動画再生の本体です。ただ、この本体にはシーク機能もポーズ機能もプレイもセレクトさえもありません。<br>
なので、AutoPlayにチェックだけを入れておきましょう。<br>
<br>
以上で動画プレーヤーは完成です。<br>
是非やってみてください！<br>
<strike>酷い説明でごめんなさい.....w</strike><br>
<font color="#ff3333">わからないことがあればコメントがあればその常更新していきますのでよろしくおねがいします。</font>
