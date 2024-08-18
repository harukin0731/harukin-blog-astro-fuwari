---
title: 今更の新BOT稼働と一部サイト変更のお知らせ
published: 2021-05-05
tags: ["Archive","GaS","JR四国","Javascript","Server","Twitter"]
category: Diary
image: https://livedoor.blogimg.jp/harukin0731/imgs/a/9/a9f712b7-s.png
draft: false
---


おつおつです。はるきんでございます。<br>ここに書くのも久しぶりですね...最近は全然ここに書くようなネタもなかったので大人しくしてました。<br><br>「ここに書くようなネタ」が今回ちょっとできたのでざっと書いていこうと思います。<br><br>2021/5/1より、TwitterにてBOTアカウント「JR四国列車遅延情報EX」を公開しました。<br>このbotは、JR四国の提供する「JR四国列車走行位置サービス」の情報をスクレイビングして切り取りTwitterに投稿するようにしたGoogleAppsScriptです。<br><a href="https://livedoor.blogimg.jp/harukin0731/imgs/f/0/f000aba4.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/f/0/f000aba4-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="506" border="0"></a><br><br>コンソールを詳しく眺めていたら、この情報を取得できそうだなと思いたって作ってみました。<br>このGASは5分毎に定期実行するようにしており、それぞれの実行でデータ取得→データ作成→ツイートを行っております。<br><a href="https://livedoor.blogimg.jp/harukin0731/imgs/a/9/a9f712b7.png" title="Screenshot" target="_blank"><img src="https://livedoor.blogimg.jp/harukin0731/imgs/a/9/a9f712b7-s.png" alt="Screenshot" class="pict" width="480" hspace="5" height="292" border="0"></a><br>現状は5分に一度、5分以上遅れている列車を、種別or列車名+列番+遅れ時分で一纏めにして投稿しております。<br>既出のJR四国列車運行情報アプリと併せて賢くご利用くださいな！！<br><strike>逆に検索に出てきて邪魔な場合はブロックなりなんなりしてもらえたらなと....思います.....Google+の頃だったらな....適当にコレクションとかすればよかったんだけどな....</strike><br><br>そしてサイトがあることも知らない人もいるとは思いますが、harukinサイトも地味に最近強化していってます。<br>何故かPWA対応してたり、下のお知らせエリアをここのブログと共通化したり。項目もちょっとずつ増やしていってるんでよかったら見てみてほしいです。<br>因みにこのサイトはReactNative+Netlifyで公開してます。キモいです。<br>これからもね、JR四国関連のアプリは需要あるみたいだし変なことしていこうと思ってますんで。よろしくです。ほなまたー。<br><br><iframe scrolling="no" style="height: 120px; width: 580px; max-width: 100%; vertical-align:top;" src="https://richlink.blogsys.jp/embed/eca2cdc4-fd9b-3044-97b3-f928ea3c881c" frameborder="0"></iframe>
