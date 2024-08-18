---
title: hubzilla鯖移行メモ
published: 2018-12-15
tags: ["Archive","Linux","Server","mysql","Hubzilla"]
category: Diary
draft: false
---



<!-- wp:paragraph -->
<p>鯖を移行したので備忘録にメモ。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>移行データ</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>DB本体→mysqldumpにて</li><li>/storeディレクトリを丸ごとコピー(画像その他のデータ)</li><li>/.htconfig.phpを丸ごとコピー(hubzilla本体の設定データ)</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>基本的に必要なデータはこれだけ。移行先鯖でこれらを転送しておけばいい。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>個人的には容量も大きく暗号化もしっかりしており、なおかつCUIツールが普及しているMEGAを転送に使用。楽。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>移行先では普通にhubzillaを建ててからディレクトリに放り込むだけ。それと権限設定。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
