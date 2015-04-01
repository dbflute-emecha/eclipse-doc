---
layout: page
title: EMSynchronizer
category: EMSynchronizer
---

* [EMSynchronizerとは？](#description)
* [待ち受けポートの指定](#setting)

## EMSynchronizerとは？ {#description} 

Eclipseの外部でファイルが変更された場合、Eclipse上でリフレッシュ操作を行う必要があります。
DBFluteで自動生成タスクを実行した際のファイル変更はEclipseの外側で行われるためEclipse側の表示は即時反映されません。

EMSynchronizerはHTTPのリクエストを受け取ることでEclipse側のリフレッシュを実行します。

DBFluteでは自動生成タスクの最後にEclipse側のリフレッシュを行うリクエストが発行されるようになっています。

[DBFlute - refreshDefinitionMap]({{ site.dbflute_url }}/ja/manual/reference/dfprop/refreshdefinition/index.html)
{: .relatedpage}

> ResourceSynchronizer の機能を参考にしています。
{: .incolumn}


## 待ち受けポートの指定 {#setting}

「ウィンドウ(Window)」-「設定(Preferences)」でワークスペースの設定画面を開き、ツリーメニューから「EMecha」-「EMSynchronizer」を選択するとEMSynchronizerの設定画面が表示されます。

ポート番号に任意のポートを指定するとデフォルト待ち受けポートが変更されます。
refreshDefinitionMapに合わせて設定を行ってください。

デフォルトの待ち受けポートは 8386 番ポートです。

デフォルトの設定のままEclipseを複数起動したときなどで既に 8386 番ポートが利用されている場合には 8386 -> 8387 -> 8388 の順に空いているポートで起動します。 
