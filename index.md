---
layout: page
title: EMecha for Eclipse
---

* [EMecha for Eclipse とは？](#description)
* [EMecha for Eclipse が必要とする環境](#environment)
* [EMecha for Eclipse のセットアップ](#setup)
  * [インストール](#install)
  * [アップグレード](#upgrade)

## EMecha for Eclipse とは？ {#description}

EMecha for Eclipse (いーめか ふぉー いくりぷす)とは、DBFluteを支援するツールの中でもEclipseプラグインとして提供するツールのことを示します。

Eclipseを利用する際の 環境面の支援・実装面の支援 などDBFluteに特化した機能が充実しており、開発中はアーキテクトもディベロッパーもこのプラグインを多いに活用 して、より良いDBFluteライフを楽しんで頂ければと。

## EMecha for Eclipse が必要とする環境 {#environment}

Eclipse 4.x (Eclipse IDE for Java EE Developers is better) JRE 7 or later

必須プラグイン

: * Eclipse Java Development Tools (JDT)
  * Data Tools Platform (DTP)

## EMecha for Eclipse のセットアップ {#setup}

> EMecha 0.5.x 以前を利用している場合は事前に Uninstall しておいてください。
> 
> ResourceSynchronizer と同等の機能(EMSynchronizer)が搭載されているため、競合を防ぐために ResourceSynchronizer も Uninstall しておいてください。
> *(ResourceSynchronizerを参考にさせて頂いています。)*{: .freecomment}
{: .incolumn}

### インストール {#install}

ダウンロードページよりDBFlute-EMecha.zipを取得し、Eclipseのdropinsフォルダに解凍してください。

[ダウンロードページ - EMecha - Releases]({{ site.github.owner_url }}/dbflute-emecha-eclipse/releases/latest)
{: .detailpage}

{::comment}
更新サイト
: 更新サイトからインストールする場合は、以下のURLを利用することが出来ます。
  : {{site.github.url}}/updates
{:/comment}


[インストール手順]({{ site.baseurl }}/setup.html)
{: .detailpage}

### アップグレード {#upgrade}

インストール時に利用した手順によりアップグレードを実施します。

常に最新版を利用することをお奨めします。
