---
layout: page
title: DFEditor
category: DFEditor
---

* [DFEditorとは？](#description)
* [ファイル関連付け](#contenttype)
* [エディタ機能](#function)
  * [色付け](#highlight)
  * [エラーチェック](#validate)
  * [アウトライン表示](#outline)
  * [フォールディング](#folding)
  * [自動入力](#autoedit) *@since 0.6.2*{: .freecomment}
* [設定画面](#setting) *@since 0.6.2*{: .freecomment}


## DFEditorとは？ {#description}

DBFluteプロパティ(dfprop)ファイルの設定支援を行うエディタプラグインです。
ファイルを開く際のエディタ名としては、 **DFProp Editor** と表示されます。

![DFEditor]({{ site.baseurl }}/image/shot/emecha-dfprop-outline.png "DFEditor"){: width="550px" style="border: 1px solid"}

[DBFlute - DBFluteプロパティ]({{ site.dbflute_url }}/ja/manual/reference/dfprop/index.html)
{: .relatedpage}

## ファイル関連付け {#contenttype}

拡張子が ***.dfprop .dataprop .diffmap*** のファイルに対して関連付けが行われ、ファイルを開く際のデフォルトエディタに **DFProp Editor** が設定されます。

もし、DBFluteプロパティファイルをダブルクリックで開いた際にテキストエディタで表示されてしまう場合には、ファイルのコンテキストメニューから「次で開く(Open With)」で **DFProp Editor** を選択してください。

## エディタ機能 {#function}

DFProp Editor はEclipseの標準的なテキストエディタの機能を継承して作られています。
コピー・切り取り・貼り付けといった基本的な機能や、コメントの切り替え・矩形選択などの機能は他のエディタと同様に利用することが出来ます。

### 色付け {#highlight}

DBFluteプロパティにおけるキーワードなどが色付けがされます。

配色は設定画面から変更することも可能です。 *@since 0.6.2*{: .freecomment}

[this - 設定画面](#setting)
{: .relatedword}

### エラーチェック {#validate}

ファイルを保存する時に、括弧の対応やmapにおける重複キーのチェックなど dfprop の構文チェックがされます。
*ファイル間の整合性チェックは行われません。*{: .freecomment}

### アウトライン表示 {#outline}

プロパティの構造をアウトラインビューでツリー表示します。
設定を鳥瞰するのにとても有用です。ぜひ Outline ビューを表示しましょう。

アウトラインビューの項目をクリックすることでエディタ上の該当する設定項目が選択状態になります。

**\$\$split\$\$**で分割された先の項目については、ダブルクリックすることで参照先ファイルを開いて該当する項目を選択状態にします。*@since 0.6.2*{: .freecomment}

### フォールディング {#folding}

連続するコメント行や複数行にわたる設定項目を折りたたんで表示することが出来ます。
エディタの左側にある **[-]** で折りたたみ、**[+]** で再表示します。

### 自動入力 {#autoedit}

* タブ入力時にスペース４個に自動的に置換されます。
* 括弧を入力した際に閉じ括弧を自動的に挿入します。
* 改行入力時に前の行と同じインデントとなるように補正されます。

## 設定画面 {#setting}

「ウィンドウ(Window)」-「設定(Preferences)」でワークスペースの設定画面を開き、ツリーメニューから **「EMecha」-「DFEditor」** を選択するとDFEditorの設定画面が表示されます。

設定画面では、エディタで色付けを行う際の配色を任意の色に変更することが出来ます。

![DFEditor PreferencePage]({{ site.baseurl }}/image/shot/dfeditor-preference-page.png "DFEditor PreferencePage"){: width="550px" style="border: 1px solid"}