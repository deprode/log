+++
Categories = ["log"]
Description = ""
Tags = ["css"]
Title = "トップページを雑に作り直した"
date = "2015-03-05T09:39:38+09:00"

+++
トップページを作り直しました。 [http://deprode.jp](http://deprode.jp)

## log

* Twitterの発言

昔作ったトップページは個人的に気に入ってるけど、Hugoのデザインと合わないので作り直した。その際、CSSフレームワーク（というかボイラープレートとして）Skeletonを使った。

[Skeleton](http://getskeleton.com/)は200行のCSSだが、使うときれいになる。レスポンシブも対応してる。

fontawesome含め、外部のCSSとJSはCDNを使うようにした。

削除したものは、html5shivとmetaタグのいくつか。html5shivは、IE8以下でもhtml5タグを認識できるようにするshim。アクセス解析を見て、IE8以下が1%切ってるので、削除した。（[はてなカウンター](http://counter.hatena.ne.jp/sample/report?cid=11&date=2015-02-01&mode=summary&target=browser&type=monthly)とか見ると5%近くいる。）

メタタグでなぜか`user-scalable=no`などが指定してあったので削除した。

その他、いろいろリンクを追加したり、作ったものを追加した。おでんを押すと表示するようにした。jQueryをわざわざ使うほどでもないと思ったので、Valilla.jsで書いた。（よく考えたらJSがないと見られないので不親切だったけど、知らない方がいいこともあるのでいいことにした。）

Githubにpushして終わり。