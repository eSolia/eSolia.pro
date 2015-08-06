---
authorkey: rickcogley
author: Rick Cogley
date: 2015-07-14T14:46:15+09:00
publishdate: 2015-07-14T08:46:15+09:00
description: イソリアから、eSolia.proのブログポスト、イソリアが何故Hugoと言うサイトジェネレーターを選択したのか。
draft: true
slug: why-did-esolia-choose-hugo
title: 何故Hugoを選択したのか?
subtitle: パフォーマンスを重視した静的サイトジェネレータ
postsummary: 社歴を渡って、イソリアが様々なシステムを利用してウェブサイトの作製と公開を使ってきたが、最近に全サイト再構築プロジェクトを静的サイトゲネレーターHugoで、行うことに決定した。ヒューゴは使いやすく、早いでけでなく、Mac、Windows、Linuxに簡単にインストールと管理が可能。
alternatelocales:
  - en-US
tags:
  - Hugo
  - 静的サイトジェネレータ
  - パーフォマンス
  - クロスプラットホーム
  - セキュリティ
  - SSG
  - Golang
topics:
  - サイト
authors:
  - Rick Cogley
images:
  - /img/eSolia-Post-Hugo-Flow-ja.png
  - /img/hugo-logo.png
  - /img/eSolia-Chicklet-Color-1024px.png  
---

## 歴史・バックグランド

イソリアは様々なシステムを利用して、当社ウェビサイトを作製して出版してきました。例えば、Microsoftフォロントページ、IBMホームページビルダー、マクロメディア ドリームウィーバーやRealMacラピッドウィーバーなど、PCやマックのローカルハードディスクにインストールする幾つかの「ビルダー」タイプのアプリで。又、WordPress、Drupal、Typo3などサーバ側にインストールするCMSタイプのシステムも利用したことある。

しかし、データベースを元にしなくて良いサイトがあれば、「静的」サイトゲネレーターで十分なはず。静的ウェブサイトは、HTML、CSS、Javascript ファイルで構成される物です。サイト開発する人はよく静的サイトを手動で作製して、FTPやSSHでウェブサーバにアップして公開する物です。

## 静的サイトジェネレータのベネフィット

イソリアはいろんなウェブページを管理してますが、弊社の場合、特にCMSを必要としていません。データベースの書き込み・読み込みからサイトのページを自動的に発行する必要が特になければ、CMSを利用するオーバーヘッド勿体無い。我々は、セキュリティとパーフォマンスが充実した静的サイトに決定しました。

簡単ですが、動的CMSでホストされているものと静的Webサイトに関して考慮されるべき事項を次の表に示します。

_項目_  |静的    | 動的CMS
----------|----------|------
_パフォーマンス_    |最高       |中〜高
_セキュリティ_       |最高    |中〜低
_インフラストラクチャ_       |単純    |より複雑
_バックアップ_     |容易     |より難しい
_データ駆動化_  |いいえ     |はい
_コンテンツ更新_  |ファイル単位    |ダッシュボード
_視覚スタイル_   | どの様なものも   |テーマによる
_アップグレード_    |任意   |継続的かつ脆弱

## 一般静的サイトジェネレータの難しいところ

近頃オーペンソース流行の「静的サイトゲネレーター」(SSG)の何らかのアプリをマックやPCにインストールして、HTMLテンプレート、CSS、Javascript、メディア ファイルと、マークダウン形式コンテンツを合体させて、サイトを構成するだけです。SSGの難しいところは、使うのにPerl、RubyやPythonのようなプログラミング言語の環境が必要となります。

従ってSSGは、必要な開発環境とその環境に必要なサポートプログラムを管理し続けるオーバーヘッドも負担しなければならない。面倒なことにOSをパッチするだけで環境が壊れる可能性も、多いにある。つまり、OSも開発環境のアプグレードを万膳に完了させないといけなければ、サイトのコンテンツ更新が不可能。

もう一つの問題は、サイトの構成時間です。SSGは一つ一つファイルを見て、再構成しなければならないため、時間が必要です。

## そしてHugoの登場

<figure class="image-container">
<img class="materialboxed right responsive-img" width="300" data-caption="Hugo Logo" alt="Hugo Logo" src="/img/hugo-logo.png" >
</figure>

イソリアはとにかく、「簡単に使える」、「面倒な開発環境不要」、「サイトビルドが早い」と言う条件を満たすSSGをじっくり探しました。その条件にぴったり合う、モダンなGo言語で開発された[Hugo](http://gohugo.io)と言う優れた静的サイトジェネレーターを発見し、選定しました。

インストールが簡単なWindows、Mac、Linux向けのアプリになっているだけでなく、Hugoクリエーターの[スティーブ フランキア 氏](http://spf13.com) ([@spf13](https://github.com/spf13)) とヒューゴの作成に携わり沢山の苦労の形にしてくれた[関係者の皆様](https://github.com/spf13/hugo/graphs/contributors)が、極力早くサイト作製を可能にしたのである。

結果的に、Hugoサイトはミリセカンド単位でファイルから作製される。ファイル作製の時間よりも、出来上がったファイルをウェブサーバーにアップロードする時間がとても長い！

それに、Hugoは一つだけのファイルで配布されていますので、アップグレードは問題ありません。その一つのファイルに、必要な物全てが含まれている。

## Hugoを使うには

Hugoを使うにはウェブデザイナーが、cssとjavascriptやHugoが特別に理解できるコード(ページのタイトル、キーワードなど)を参照するhtmlの「テンプレート」ファイルを作製する。
コンテンツは、[マークダウン](http://daringfireball.net/projects/markdown/)形式のテキストファイルで作る。サイトをゲネレーションするには、Hugoを実行することによって数ミリセカンド後、Hugoがコンテンツとテンプレートをマージさせて、ファイルがサイトフォルダーに出力されて、出来上がり。最後にそのフォルダーをウェブサーバに転送させて、完了。

<figure class="image-container">
<img class="materialboxed responsive-img" width="500" data-caption="Hugoフロー図" alt="Hugoと言う静的コンテンツゲネレーションの、ワークフロー図。" src="/img/eSolia-Post-Hugo-Flow-ja.png" >
<figcaption><em>Hugoのフロー図</em></figcaption>
</figure>

## イソリアはどこでHugoを使っているか

SSGをテストをした時、Hugoの簡単さとパーフォーマンスに驚き、弊社の全サイトに再構築に決定した。現在まで、[英語](http://esolia.com) と [日本語](http://esolia.co.jp) のサイトと、当サイト[eSolia.pro](http://esolia.pro) ブログも含む。

2015年現在、Hugoのオーペンソース [コミュニティー](http://discuss.gohugo.io/latest) がとても良い感じで、[開発](https://github.com/spf13/hugo) もアクティブに進んでいる。是非ご参考ください。