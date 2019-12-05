<!-- TOC -->

- [1. はじめに](#1-はじめに)
- [2. エディタ関係](#2-エディタ関係)
    - [2.1. TeXStudioでplatexを使うために](#21-texstudioでplatexを使うために)
- [3. pLaTeX全般](#3-platex全般)
        - [3.0.1. 自前マクロv.s 分割ファイル](#301-自前マクロvs-分割ファイル)
        - [3.0.2. amsbookを用いたときに章ごとに謎の空白ページが現れる](#302-amsbookを用いたときに章ごとに謎の空白ページが現れる)
        - [3.0.3. その他もろもろ](#303-その他もろもろ)
        - [3.0.4. ハイパーリンクを挿入する際に便利なChromeの拡張機能](#304-ハイパーリンクを挿入する際に便利なchromeの拡張機能)
    - [3.1. Tikzpictureに関すること](#31-tikzpictureに関すること)
        - [3.1.1. 特定のフォントのみ使いたいが、他のパッケージと競合する](#311-特定のフォントのみ使いたいが他のパッケージと競合する)
    - [3.2. Beamer](#32-beamer)
        - [3.2.1. スライドの色付けの問題](#321-スライドの色付けの問題)
    - [3.3. Beamerポスター](#33-beamerポスター)
    - [3.4. BibTeX](#34-bibtex)
        - [3.4.1. Bibtexが出力できない](#341-bibtexが出力できない)
        - [3.4.2. 参考文献を自前で書かないといけない場合](#342-参考文献を自前で書かないといけない場合)
        - [3.4.3. A0サイズでフォントが汚くなる現象](#343-a0サイズでフォントが汚くなる現象)
        - [3.4.4. BibTeXの行間の調整](#344-bibtexの行間の調整)

<!-- /TOC -->

# 1. はじめに

ここでは自分が気になっていることやまとまっていない話を
書き溜めていく。基本的に今まであったトラブルとか自分が知ったTips
それに対する現在の状況などを書き留めていく。
ある程度長い文章になった場合に別記事にしていく。
(この記事は日々更新していく)

# 2. エディタ関係

## 2.1. TeXStudioでplatexを使うために

TeXLiveで標準装備
pLaTeXを使えるようにするには設定を調整する必要があるが、
TeXWorksと少し勝手が違うため自分は最初混乱したが
下のリンクを見ることで解決した。

[QA: TexStudio，TeXmakerの利用](https://oku.edu.mie-u.ac.jp/tex/mod/forum/discuss.php?d=1623)

# 3. pLaTeX全般

### 3.0.1. 自前マクロv.s 分割ファイル

\newcommand等の設定を各ファイルに書かないで済む方法の一つとして
自前のパッケージ(styファイル)を書いておき利用するという方法がある。

今までは自分はその方法を主に用いてきたが、分割ファイルを用いる方法も
ありうるということを知った。しかし今のところどう使い分けるべきか
よくわからない。

**自前マクロのメリット・デメリット**

**分割ファイルのメリット・デメリット**

### 3.0.2. amsbookを用いたときに章ごとに謎の空白ページが現れる
\chapter{name}を用いたときになぞの空白が
謎の空白ページが現れるために必要以上にページが多くなってしまっている。

**原因** \chapterのデフォルトの設定で空白ページが出るようになっている。これはオプションで変更できる。

**解決方法** documentclassのoptionにopenanyを加える。

### 3.0.3. その他もろもろ

円マークニ個と角括弧を並べて入力するとエラーを吐き出した。

**原因** 謎

ピリオドを\operatorname{}内に入れて、エラーが出た。

**原因** 謎

### 3.0.4. ハイパーリンクを挿入する際に便利なChromeの拡張機能
hyperref.styを用いるとハイパーリンクを文中に挿入することができる。

``
\href{url}{name}
``

入力はいたってシンプルであるが、いろんなものを検索してそれらを一気に
ノートとして書き留めたい場合は各urlごとにいちいち書く必要があり面倒である。
そんなときに役に立つのが次のChromeの拡張機能である。

[https://chrome.google.com/webstore/detail/copy-url-to-clipboard/miancenhdlkbmjmhlginhaaepbdnlllc?hl=ja:embed:cite]

これを用いれば、簡単にurlをlatex形式に変換してくれる。
実際にはLaTeX以外の様々な形式に対応している。

## 3.1. Tikzpictureに関すること

Tikzには三次元座標をデフォルトで利用することができる。
しかしこのままだとx-y軸が直交したものしか描画できない。
一方でパッケージを追加することでより三次元の図を書けるように
なっている。

使用例はたとえばこちらにある

[https://tex.stackexchange.com/questions/414403/drawing-vectors-on-3-d-coordinate-system:embed:cite]

### 3.1.1. 特定のフォントのみ使いたいが、他のパッケージと競合する

あるパッケージの特定のフォントのみ使いたいというときがある。
自分の場合はMnSymbolにある特定のフォントを用いたかったが
amsの標準的なフォントと競合するパッケージであった。

そのときの対処法は例えばこちらにある。

[https://tex.stackexchange.com/questions/36006/importing-single-symbol-from-mnsymbol?fbclid=IwAR04lsgO5MKJ6Wv90XvZ86PB1dNQcCNKJU5EJBMPXy4cbNJ3OP_lmP3cH6A:embed:cite]

[https://zrbabbler.hatenablog.com/entry/20160607/1465260507:embed:cite]



## 3.2. Beamer

### 3.2.1. スライドの色付けの問題

これはBeamerに限った話ではなくスライド全体の話である。
スライドの色づけは基本的にスライドを見やすくするために
用いられるが、色覚異常の人にも見えるような配色をするべきである。
健常者には見えやすい配色であっても色覚異常の人には
判別不能な色などはいろいろと存在する。
具体的にはこちらに簡単な説明がある。
[https://www.nig.ac.jp/color/gen/:embed:cite]

しかしこれをきちんと調べるのはそれなりに慣れないといけない。
そんな時に便利なのが次のChromeの拡張機能である。

[https://chrome.google.com/webstore/detail/spectrum/ofclemegkcmilinpcimpjkfhjfgmhieb?hl=ja:embed:cite]

これを用いると色覚異常の様々なケースでスクリーンを眺めることができる。
これを利用することで色に強く依存したスライドかどうか
一目でわかるようになるので便利である。

## 3.3. Beamerポスター

## 3.4. BibTeX

### 3.4.1. Bibtexが出力できない
mathscinetから文献情報をBibtexで出力して入力したが、エラーを吐き出した。

**原因** 数理解析考究録において\bとなるべきところが\Bとなっていた

### 3.4.2. 参考文献を自前で書かないといけない場合

次のサイトが便利である。それぞれの記事の種類に対して
書くべき項目が自動で教えてくれる。

[BibTeX Online Editor](https://truben.no/latex/bibtex/)

ただし、TeXStudioがあればそれでもすぐわかる。

### 3.4.3. A0サイズでフォントが汚くなる現象

BeamerにはBeamerで用いたスライドをそのままposterに援用することができる。

それの説明は「Beamer ポスター」で検索できる。
基本的には次のパッケージを用いることで
扱うことができる。

``
\usepackage[orientation=portrait,size=a3,scale=1.5]{beamerposter}
``

しかし、A0サイズを扱おうとしたらフォントが汚くなった。

具体的には欧文文字が細くなりすぎてしまうことと

数式中の括弧が小さいままになってしまった。

逆にA3サイズを用いている分には問題はなかった。

**原因**  \usepackage[T1]{fontenc} と \usepackage{mathabx}の影響

前者はフォントのエンコーディングを変換するもので
後者は大型演算子を補強するものである。

それぞれが上に挙げた問題を引き起こしていた。

### 3.4.4. BibTeXの行間の調整

参考文献の文字を小さくするのは簡単だが
参考文献の行間の調整は少し手間がかかる。
解決するには次のようにすればよい。

[Adjusting the space between references in the bibliography.](http://www.math.cmu.edu/~gautam/sj/blog/20140712-bibtex-spacing.html)

[bibspacing.sty](http://www.math.cmu.edu/~gautam/sj/blog/20140712-bibtex-spacing/bibspacing.sty)

**`bibspacing.sty`**

``` 
\newlength{\bibitemsep}\setlength{\bibitemsep}{.2\baselineskip plus .05\baselineskip minus .05\baselineskip}
\newlength{\bibparskip}\setlength{\bibparskip}{0pt}
\let\oldthebibliography\thebibliography
\renewcommand\thebibliography[1]{%
  \oldthebibliography{#1}%
  \setlength{\parskip}{\bibitemsep}%
  \setlength{\itemsep}{\bibparskip}%
}
```