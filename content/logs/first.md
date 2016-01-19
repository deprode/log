+++
date = "2015-02-28T18:29:55+09:00"
title = "Hugoで試行錯誤する"
tags = ["hugo", "css"]
+++

とりあえず、HugoでPublishできるまで作ってみるかと思っている。
Tumblr2Hugoとかは自分で作らないとダメだと思うので、あきらめるか気が向いたらあれしよう。

Hugoでテーマ作ってると、他の人のやつも参考になるんだけど、最初にやるなら公式ドキュメントが役に立つ。よくわからないところはチュートリアルになってるので、見た方がいい。

[Automated deployments with Wercker](http://gohugo.io/tutorials/automated-deployments/)  
[Creating a New Theme](http://gohugo.io/tutorials/creating-a-new-theme/)  
[Hosting on GitHub Pages](http://gohugo.io/tutorials/github-pages-blog/)  

ドット.がついてなくて、ないよ！って言われまくったけど最初わからなかった（集中してなかった＆目が悪い）ので、厳しさがある。エラーが出ないのにheader.htmlにあるTitleと.Site.Titleが出力されないというのも、partialのファイル名の他にドットを書く必要があったからだった。

関係ないけど、Markdownの改行ってスペース2つでできるんだけど、なぜか間違って\<br\>タグを書かないとダメって覚えてて、ダメだと思った。あと、普通にjavascriptをそのまま出す（Markdownだから当たり前だけど）ので、心配と言えば心配。

コードのハイライト。クライアントサイドで行う際は、highlight.jsなどでやってくれ、らしい。  
[Syntax Highlighting](http://gohugo.io/extras/highlighting/)


```
    var a = "hello hugo";
    alert(a);
```

他の人のブログ見ると、archivesとかlogsとかにしてて、どうやって作るのかと思っていろいろ調べた結果、content/postの名前を置き換えるとできるっぽいことに気づいたけど、これが正しいのかはわからん。

Tagsとかは、一応自動生成してくれるっぽい。他のthemeを見ると、taxonomiesをつかって、tags.htmlに誘導してたりするけど、categoryもsectionも、とかじゃなきゃとりあえずlist.htmlでいいでしょ。

で、いろいろあってwerkerを使ってdeployするところまで来て、やった。（Githubのリポジトリ作り直したらWerckerでエラー出てなくても作り直した方がいいことに気がついた。）Applicationのチェックはデフォルトでいいみたい。repoとrepo public,userにチェックした。

CNAMEでdeprode.jpをトップにしてるので、サブドメインだと表示がうまくいかない。手作業で、各ページへのリンクを張り直したり、RSSのリンクを作り直したりした。その後、git rebase -i --rootとか使って、失敗をなかったことにした。

終わり。

これらの記事を見て使おうと思った：

- [OctopressからHugoへ移行した | SOTA](http://deeeet.com/writing/2014/12/25/hugo/)  
- [Jekyllが許されるのは小学生までだよね - MOL](http://t32k.me/mol/log/hugo/)  
- [WordPress から Hugo に乗り換えました - rakuishi.com](http://rakuishi.com/archives/wordpress-to-hugo/)  
