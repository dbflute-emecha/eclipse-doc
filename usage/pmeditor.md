---
layout: page
title: PMEditor
category: PMEditor
---

* [PMEditorとは？](#description)
* [ファイル関連付け](#contenttype)
* [エディタ機能](#function)
  * [色付け](#highlight)
  * [分岐条件の補完](#conditionSupport)
* [設定画面](#setting)

## PMEditorとは？ {#description}

[MailFlute](https://github.com/dbflute-session/mailflute)で利用するテンプレートファイルの作成支援を行うエディタプラグインです。
ファイルを開く際のエディタ名としては、 **PMEditor** と表示されます。

## ファイル関連付け {#contenttype}

拡張子が ***.dfmail .dfpm*** のファイルに対して関連付けが行われ、ファイルを開く際のデフォルトエディタに **PMEditor** が設定されます。

## エディタ機能 {#function}

PMEditorはEclipseの標準的なテキストエディタの機能を継承して作られています。
コピー・切り取り・貼り付けといった基本的な機能や、コメントの切り替え・矩形選択などの機能は他のエディタと同様に利用することが出来ます。

### 色付け {#highlight}

ヘッダ部とパラメータコメント部が色分けされます。

### 分岐条件の補完 {#conditionSupport}

IFコメントやFORコメントをの入力を補完します。
**/\*(カーソル位置)\*/** で、Ctrl + Space を押すと利用可能な候補の一覧が表示されます。

## 設定画面 {#setting}

設定画面では、エディタで色付けを行う際の配色を任意の色に変更することが出来ます。
