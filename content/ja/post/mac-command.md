---
title: "macOS固有のコマンドについて調べる。"
summary: "macOS固有の便利コマンドを紹介"
date: 2019-07-30T16:28:32+09:00
tags: ["macOS"]
draft: true
---



macOSはUNIXライクのOSとして有名ですが、固有のコマンドが存在します。 <br>
覚えておくと後々便利そうなコマンドを備忘録として残す。

 

## 1.pbcopy

ターミナルの標準入力をペーストボード(クリップボード)に保存するコマンド。
よくsshで使用する公開鍵をコピーする際に使用しています。

e.g)

```
 $ pbcopy < ~/.ssh/id_rsa.pub
```

出力をリダイレクトでpbcopyに入力することによってファイルの中身をクリップボードにコピーできます。<br>
ちなみに直接打ち込んでクリップボードに保存することも可能です。
```
$ pbcopy　(終了はCtrl + D)
hogehoge
```

<figure class="figure-image figure-image-fotolife" title="pbcopy_clipboard">[f:id:ryo8ma:20190730152816p:plain]<figcaption>pbcopy_clipboard</figcaption></figure>

クリップボードに保存されていることが確認できます。

## 2.pbpaste

クリップボードに保存されている内容を標準出力へ渡すコマンド。

```
$ echo 'hogehoge' | pbcopy
```
```
$ pbpaste > test.txt
$ cat test.txt
hogehoge
```
pbcopyと併用すれば作業を効率化できそうです。

## 3.screencapture

通常macでスクリーンショットを撮る場合は「Cmd + Shift + 4(3)」のショートカットキーを使用することが
多いと思います。ターミナル上でも同様の操作を行うことが可能です。

・選択範囲を指定のディレクトリに保存
```
$ screencapture -i ~/Desktop/hogehoge.png
```

-c オプションでクリップボードに保存することも可能。
```
$ screencapture -ic ~/Desktop/hogehoge.png
```

## 4.open

ターミナルからファイル、ファルダ、URLをopenコマンドを使用することによって開くことが可能です。
(アプリケーションを指定して開くこともできます。)

・WEBページを開く
```
$ open https://ryo8md-ls.hatenablog.com/
```


## まとめ

まだまだmac固有のコマンドは存在するので、便利そうなのを発見したら追記します。

##### 参考情報


[https://do-zan.com/mac-terminal-screencapture/]

[https://macwiki.osdn.jp/wiki/index.php/OSX%E3%81%AE%E5%9B%BA%E6%9C%89%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89]


