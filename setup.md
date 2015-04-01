---
layout: page
title: EMechaのセットアップ (インストール)
category: setup
---

* [古い EMecha と ResourceSynchronizer を削除](#migration)
* [セットアップの種類](#types)
* [dropins に配備](#dropins)
* [更新サイトを利用](#update-site)

## 古い EMecha と ResourceSynchronizer を削除 {#migration}

すでに Java6,7 用の EMecha(0.5.x 以前) が Eclipse にインストールされている場合は、そちらを削除します。
念のため、eclipseをまるごとバックアップしておくとよいでしょう。

(0.5.x 以前と0.6.x以降でプラグインIDが異なるため手動での削除が必要となります。)
{: .freecomment}

Help - Install New Software... の What is already installed? から、EMecha と ResourceSynchronizer を Uninstall します。

ResourceSynchronizerも削除するのは、新しい EMecha に同等の機能 (EMSynchronizer) が搭載されており機能が競合してしまうからです。

(ResourceSynchronizerを参考にさせて頂いています。素晴らしい機能が公開されていることに感謝、ありがとうございます)
{: .freecomment}

## セットアップの種類 {#types}

新たに Eclipse のプラグインを利用する場合のインストール方法は dropins への配備(3.4以降)と更新サイトを利用する方法の２種類が存在します。

(厳密には３つ目の方法として plugins フォルダに直接配備する方法もありますが、リスクが大きいためお勧めしません。)
{: .freecomment}

## dropins に配備 {#dropins}

### １. EMecha をダウンロード

EMechaのリリースページから、最新版の DBFlute-EMecha.zip をダウンロードします。

[ダウンロードサイト - EMecha - Releases]({{ site.github.owner_url }}/dbflute-emecha-eclipse/releases/latest)
{: .relatedpage}

### ２. EMecha をdropinsに配置

Eclipse の dropins ディレクトリに解凍します。

<pre><code>
eclipse <span class="freecomment">// Eclipse本体のディレクトリ</span>
 |-configuration
 |-dropins
 |  |-DBFlute-EMecha <span class="point">// ☆ここに解凍</span>
 |  |   |-eclipse
 |  |      |-features
 |  |      |  |-org.dbflute.emecha.feature_0.6.1...jar
 |  |      |-plugins
 |  |         |-org.dbflute.emecha_0.6.1...jar
 |  |         |-org.dbflute.emecha...._0.6.1...jar
 |  |         |-...
 |  |
 |  |-...
 |-features
 |-plugins
 |-Eclipse.app
 |-...
</code></pre>


### ３. Eclipse を起動

新規インストールの場合はそのまま Eclipse を起動します。
アップグレードの場合は Eclipse に起動オプションとして -clean を付与して起動します。

## 更新サイトを利用 {#update-site}

準備中
{: .freecomment}

{::comment}
更新サイト
  : {{ site.github.owner_url }}{{ site.eclipse_update_url }}
{:/comment}
