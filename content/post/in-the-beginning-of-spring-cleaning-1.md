+++
date = "2015-01-03T05:23:31+09:00"
draft = true
title = "in the beginning of spring cleaning No.1"
tags = ["tmux"]
categories = ["environment"]

+++

年始最初のMac大掃除。  
No.1としておこう。

まずはターミナルの基礎になっている、tmuxの設定を。  

## Powerline
powerline/powerlineが最近更新されているようなので、再び調べて使ってみることにした。  
以前はpowerline-daemonの取り扱いがよくわからず断念した悔しい思い出があったが、今回は[マニュアル](https://powerline.readthedocs.org/en/latest/index.html)通りにpipインストールでやってみて、ステータスラインのテーマも用意されているものを使ってみたところ、ちゃんと動いた。

![](/images/ss/Screenshot-2015-01-03-06.37.57.png)

しかし、pyenvからのpipインストールなので、レポジトリのコピーが

```
~/.pyenv/versions/2.7.8/lib/python2.7/site-packages/
```

に置かれる。
テーマの場所もその階層内なので、dotfiles管理としてhomesickを使っているのにも関わらず管理できないのは困る。  
エイリアスを貼るのもなんかおかしいし、本当はdotfiles階層内に置きたいところ。  
ただ、そうするとテーマファイルが見つからないとなり、ステータスラインが表示されなくなってしまう。
たぶんpowerline-configコマンドあたりで設定を変更する感じがするのだが、保留。  
また今度やりたいな。  
というかスクラッチで書きたくなってしまう。  
無理だけど。

## Status line
とりあえず随分ディレクトリを掘って配置されたステータスライン設定用のjsonファイルを編集。  
jsonでかけるのは良いかも。

```json
{
  "segments": {
    "right": [
    {
      "function": "powerline.segments.shell.jobnum"
    },
    {
      "function": "powerline.segments.common.net.external_ip"
    },
    {
      "function": "powerline.segments.common.bat.battery",
      "empty_heart": "u'O'",
      "full_heart": "u'O'",
      "gamify": "False",
      "steps": "5",
      "format": "u'{capacity:3.0%}')"
    },
    {
      "function": "powerline.segments.common.time.date"
    }
    ]
  }
}
```

すでに用意されているfunctionを使って、ステータスラインを装飾していく。  
functionについてはマニュアルを参考のこと。

ペイン仕切り線の色を変えることによって現在のペインを目立たせることができるのだが、デフォルトだとgreenになるのかどこかで指定されているのか、とにかくステータスラインとあっていなかったので
```
setw -g pane-active-border-fg blue
```
として色を変更。  

今考えると、去年はpowerlineステータスライン使っていなかったのか。  
見栄えよくなり、新鮮味があっていい。

## Time
ただ、これらの設定をするのに1日かかってしまった。  
ソースコードを見て、なぜ動かないかを探るクセがついた・見れば少し分かるようになったのは良いことだけど、まだまだ時間が掛かりすぎる。

## Rails and etc
Railsを覚えようと思いたち、早半年以上。  
JavaScriptも適当にやりながら、途中SublimeTextのパッケージを書くために少しPython、IntelliJのテーマを変えたくてほんの少しJava。  
SASSはとりあえずかけるけど、ネストできるだけでmixinあたりはまだまだ把握していない。  
gulpはそこそこ分かったので、逆にgruntを知らない文拒否反応が出る。遅い。  
bower、Yeoman、そのあたりもなんとなく分かりつつある。内部処理ではなく、表面的な使い方だけね。

VagrantでのRails用boxは4つスターがついたので、少しやる気出してしっかり組んでみた。

## Editor
エディタはSublimeText。これはそろそろ1年になる？Dreamweaver使ってたころが懐かしい。  

次にIntelliJでIDEデビュー。RubyMineが良いとのことで触ってみたけど、いろいろYakが多い。  

SublimeTextが少し遅いのと、日本語入力でラグがあるので文章は打ちづらい。  
Atom.ioをはじめたけど、当たり前にできることが少なくてパッケージ導入前提なのでハマるとハマる。  
とりあえずは動くようになったけど、うーんという感じ。  
本当に速く、カスタマイズ性はIntlliJよりあり、統合環境をすべて整備してくれるエディタないのかな。  
それがVimなんかな・・・

## look back
一番最初はなんだっけ？Windowsの時はEmEditorとか使ってたな。  
いつかのエントリで昔を振り返ってみたいな。  
あさどうやMacky、EmEditorやWindows2000、go163、懐かしい。

あのころはほぼすべてのことを調べて、効率化は考えずにあげることだけ考えてた。  
あのころのモチベーションはどこに？

## Misc
いろいろやり過ぎなんだろうか。  
いや、いろいろやることが多すぎるんだろう。今の時代。
