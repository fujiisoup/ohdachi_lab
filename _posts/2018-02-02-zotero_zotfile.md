---
layout: post
title: "文献情報とPDFファイルをうまく管理する(zoteroとzotfile)"
categories:
  - Researches
tags:
  - researches
  - ruby
---

### 文献情報とPDFファイルをうまく管理する(zoteroとzotfile)

研究者にとって現在の進化したIT環境は非常に有用なものです。Dropbox, Google Driveなどのファイル共有機能、Google Scholarなどの文献検索機能は、うまく活用すれば能率を大きく上げることができます。研究者の研究環境は厳しくなってきていて研究にかけることができる時間は短くなる一方なので、単純作業に費やす時間をなんとか短縮して、考えたり、計算したり、実験したりという研究者本来の業務にかけられる時間を長くすることが必要です。

文献情報管理もうまく行えば大きく省力化できる仕事の一つです。文献情報の管理は論文を書くときに特に必要です。タイトル、著者名、雑誌名などをミスなく入力し、雑誌のスタイルに合わせてリファーして参考文献リストをつくらなければなりません。入力を手動でやるとミスの可能性が上がります。データベースから自動で情報読み込むことのできる文献管理システムは大変有用です。この種の文献管理ソフトウェアはいくつかあって定番と言えるものは今現在もないと思います。商用ソフトウェアとしてはEndnote, フリーのものとしてはZoteroとMendeleyが有力と思います。それぞれの比較は以下のリンクなどを見てください。( [Washington University St Louiceのサイト](http://libguides.wustl.edu/choose),[京都大学の工学研究科のサイト](http://www.propulsion.kuaero.kyoto-u.ac.jp/%E6%96%87%E7%8C%AE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB) )

私は[Zotero](https://www.zotero.org/) のスタンダードアローン版を使っています。Google Scholar の検索ページから一気に取り込む文献を選択できる機能が素晴らしいと思っています。Zoteroは文献の名前、著者名などのメタ情報に加えて、文献そのものも管理することができます。この時情報は、Zoteroのサーバーにアップロードされます。このため複数のPCにZoteroをインストールした場合にも文献情報が同期されるので大変便利なのですが、ユーザーが無料で使えるのは100M byteまでなので、文献そのものを登録することはあまりやらないようにしていました。ところが、Zoteroの拡張機能である[Zotfile](http://zotfile.com/)をつかえば、このようなPDFファイルをDropboxとかGoogleDriveなどのクラウド的大容量のファイル共有システムに入れて管理することができることを知りました( [Managing References with Zotero and Google Drive](http://openafox.com/science/zotero) など)。ファイル自身はファイル共有機能によって同期されますので、複数の環境でPDFファイルを上手にオーガナイズすることができます。

この機能は最近になってうまく動作するようになったようで、古いWebサイトではうまくいかないと書いてあったり、情報がいろいろ錯そうしていますし、日本語の解説がほとんどなかったのでここで設定法について説明してみます。

1. Zotero のインストール。スタンドアローンシステムをインストールして、もしまだやってなければ登録する。
1. 共有ファイルシステムの中ににZotero管理のフォルダーを作る。ここで紹介している例ではGoogle Drive の中に REFSというディレクトリを作って利用した。まだ導入しなければ、[backup and sync](https://www.google.com/drive/download/backup-and-sync/)をインストールする。
1. Zotfileをインストールしてセットアップする。
1.1　インストール用のファイルをダウンロードして、ツール→アドオンから、❇印をクリックして、Install Add-on from fileでインストールする。
1.1 一度Zoteroを停止して再立ち上げ。
1.1 ツール→Zotfile Preferencesで以下の図面のようにCustum Location をPDFファイルを格納するディレクトリを指定して、Use subfolder defined by を/%w/%fにする。
![zotfile設定]({{ site.url }}/images/zotfile.png)
1.1 advanced setting からremove special characters(diacritics) from filenmeのチェックを入れる。

1. Zoteroを設定する。
1.1 編集→設定→同期タブを以下のように設定する。
![zotero設定1]({{ site.url }}/images/zotero_sync.png)
1.1 編集→設定→詳細タブの中のファイルとフォルダを以下のように設定する。
![zotero設定2]({{ site.url }}/images/zotero.png)
この時データディレクトリの場所をGoogle Driveに指定するとデータベースがこわれてしまいひどいことになるので注意（私はやらかしました）。

PDFファイルを取り込んだら、ファイルを右クリックしてManage Attachmentから Rename Attachment をすると、ファイルが共有ファイルシステムこの場合はGoogle Driveに保存されどのPCからも見られるようになる。

非常に快適です。お試しください。

この記事はZotero 5.0.34, zotfile 5.0.6の結果について2018/2に試した結果です。


