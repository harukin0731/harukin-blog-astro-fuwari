---
title: davinciをArchにインストールして動作確認してみる
published: 2019-03-03
tags: ["Archive","Linux","Davinci","ArchLinux"]
category: Diary
image: https://livedoor.blogimg.jp/harukin0731/imgs/2/2/225c64c1.png
draft: false
---

<div>なんなんだおまえは....</div><br><div><a href="https://www.blackmagicdesign.com/jp/products/davinciresolve/" target="_blank"></a><a target="_blank" title="Screenshot" href="https://livedoor.blogimg.jp/harukin0731/imgs/2/2/225c64c1.png"><img class="pict" alt="Screenshot" src="https://livedoor.blogimg.jp/harukin0731/imgs/2/2/225c64c1-s.png" width="480" hspace="5" height="300" border="0"></a><br>https://www.blackmagicdesign.com/jp/products/davinciresolve/</div><br><div>フォロワーさんの伝でdavinciという動画編集ソフトを知ることになったのだけれど、サイト見て驚いたのは<b>Linux対応</b>だということ。</div><div>この類のソフトはWindowsのみだったりするから有難い.....</div><div>一応Archにあるんかなって見てみると<a href="https://livedoor.blogimg.jp/harukin0731/imgs/8/9/8975bf0d.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/8/9/8975bf0d-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="322" border="0"></a><br>おお、あるじゃんあるじゃん。早速導n.......</div><div><a href="https://livedoor.blogimg.jp/harukin0731/imgs/4/1/418500cf.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/4/1/418500cf-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="322" border="0"></a><br><span style="font-size: 150%;">いや無理なんかーいw</span></div><div><span style="font-size: 150%;"><span style="font-size: 100%;">ちょっと考えたけど、重要なのはこの上の文字みたいね。</span></span></div><blockquote><div><span style="font-size: 100%;">The package can be downloaded here: https://www.blackmagicdesign.com/products/davinciresolve/<br>&nbsp; -&gt; Please remember to put a downloaded package DaVinci_Resolve_15.2.4_Linux.zip into the build directory /tmp/trizen-harukin/davinci-resolve or /home/haruk</span></div></blockquote><div><span style="font-size: 100%;">なるほど？パッケージ自体は自分で落してこいと。</span></div><div>なんじゃこの面倒くささは。</div><div><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/5/a53e9a49.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/5/a53e9a49-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="300" border="0"></a><br>ということでダウンロードしにいってきた。</div><div>これあれだな、<i>ダウンロード時にユーザー登録必須だからそっから落としてこい</i>ってことなのね。</div><div>まぁ利権とかあるんでしょう、仕方無い。</div><div>本体が800MB以上あるのでそれなりに覚悟して臨もう。<a href="https://livedoor.blogimg.jp/harukin0731/imgs/1/e/1e0fac26.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/1/e/1e0fac26-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="211" border="0"></a><br></div><div>831.7MB。なかなかありますな....</div><div>これをさっきの記述通りに</div><div><span style="font-size: 100%;">/tmp/trizen-harukin/davinci-resolve</span></div><div><span style="font-size: 100%;">に入れて、と。</span></div><div><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/d/8/d8b41c0a.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/d/8/d8b41c0a-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="340" border="0"></a><br>これでいいのかな、そんじゃ再実行と。<a href="https://livedoor.blogimg.jp/harukin0731/imgs/9/6/961b4b45.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/9/6/961b4b45-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="322" border="0"></a><br>ログイン名....???</span></div><div><span style="font-size: 100%;"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/d/7/d7badb04.png" alt="Screenshot" class="pict" width="321" hspace="5" height="146" border="0"><br></span></div><div><span style="font-size: 100%;">pkgbuild見てみたら$(logname)とやら。</span></div><div><span style="font-size: 100%;">なんだろこれ。</span></div><div><span style="font-size: 100%;">GGって...</span></div><div><span style="font-size: 100%;"><a href="https://www.atmarkit.co.jp/ait/articles/1807/27/news020.html" target="_blank">https://www.atmarkit.co.jp/ait/articles/1807/27/news020.html</a><br></span></div><div><span style="font-size: 100%;">ほう、lognameってコマンドがあるのね。</span></div><div><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/d/8/d8ba4daf.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/d/8/d8ba4daf-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="322" border="0"></a><br>はい、ビンゴ〜wどういうこっちゃw</span></div><div><span style="font-size: 100%;"><br></span></div><div><span style="font-size: 100%;"><br></span></div><div><span style="font-size: 100%;">色々調べたけどよくわかんなかったのでpkgbuildの$(logname)を</span><span style="font-size: 100%;"><span style="font-size: 100%;">$(whoami)にしてやったらビルド通過。</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/c/4/c4a28b98.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/c/4/c4a28b98-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="300" border="0"></a><br>1683.63 MiB。。。。。。。尋常じゃねぇ....</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;">起動するけれど、<br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/d/ad3dfe4c.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/d/ad3dfe4c-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="300" border="0"></a><br><br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/4/a4fc55a6.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/4/a4fc55a6-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="217" border="0"></a><br><br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;">起動しない。</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/2/a2227ef2.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/2/a2227ef2-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="505" border="0"></a><br>GPUの設定の書き換え。</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a href="https://livedoor.blogimg.jp/harukin0731/imgs/f/d/fdd213c6.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/f/d/fdd213c6-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="326" border="0"></a><br>クラッシュ.....</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;">ここで、aurにグラボ指定の設定があった気がしたので、nvidiaを指定してインストールしてみた。</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><a target="_blank" title="Screenshot" href="https://livedoor.blogimg.jp/harukin0731/imgs/f/e/fe4e59b7.png"><img class="pict" alt="Screenshot" src="https://livedoor.blogimg.jp/harukin0731/imgs/f/e/fe4e59b7-s.png" width="480" hspace="5" height="300" border="0"></a><br>おし。GJ。</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><img class="pict" alt="Screenshot" src="https://livedoor.blogimg.jp/harukin0731/imgs/e/e/eed93979.png" width="108" hspace="5" height="76" border="0"><br>おっかしいなぁ、mp4が音声ファイルとして取り込まれてまう....</span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;">とりあえずプログラム自体の動作は確認したので今回はここまで。<br></span></span></div><div><span style="font-size: 100%;"><span style="font-size: 100%;"><br></span></span></div>