---
layout: page
title: DFAssist
category: DFAssist
---

* [DFAssistとは？](#description)
* [新規DBFluteプロジェクトの作成](#newproject)
* [導出カラムのプロパティ作成](#QuickFix)
* [関係するファイルを開く](#hyperlink)
* [新規実装クラスの作成](#NewConcreteClass)

## DFAssistとは？ {#description}

DBFluteを利用したJavaプロジェクトの実装における支援を行う機能を提供します。

## 新規DBFluteプロジェクトの作成 {#newproject}

新しくDBFluteプロジェクトを作成する支援を行います。

### 新規プロジェクト作成画面を起動

「新規(New)」-「プロジェクト(Project)」から **「DBFlute」-「DBFlute Project」** で、新規DBFluteプロジェクト作成画面が起動します。

### プロジェクト作成フォルダの指定

ロケーションにはプロジェクトフォルダを作成するフォルダを指定します。
デフォルトでは、ワークスペースフォルダが指定されています。

### プロジェクト情報の設定

Mavenプロジェクトを作成する場合と同様に、作成するプロジェクトのグループID・アーティファクトID・バージョンを設定します。

### プロジェクトの作成実行

全ての情報を設定したら **「完了(Finish)」** (Enter)でプロジェクトが作成されます。
作成されるプロジェクトはMaven(m2e)形式のプロジェクトとなり、pom.xml にDBFluteを利用する為の設定が出力されます。

### プロジェクトを作成した後は

プロジェクト作成後は、pom.xmlにDBFluteのMavenによるセットアップに従い必要な情報(JDBCドライバのdependencyを定義等)の追記を行ってください。
その後、以下のコマンドを実行してDBFluteエンジンのダウンロードとクライアントの作成を行ってください。

```
[プロジェクトフォルダ] $ mvn -e dbflute:download
[プロジェクトフォルダ] $ mvn -e dbflute:create-client
```

[DBFlute - Mavenによるセットアップ]({{ site.dbflute_url }}/ja/environment/setup/maven.html)
{: .relatedpage}

## 導出カラムのプロパティ作成 {#QuickFix}

(Specify)DerivedReferrer で利用するプロパティや定数を作成する支援を行います。

[DBFlute - (Specify)DerivedReferrer]({{ site.dbflute_url }}/ja/manual/function/ormapper/conditionbean/specify/derivedreferrer.html)
{: .relatedpage}

### 実装方法

ConditionBean側の実装をして、第二引数の aliasName のところで、Member.ALIAS_latestLoginDatetime という風に、まだ存在しない定数を先に打ち込みます。

コンパイルエラーになっているところで **ctrl + 1** を押して、想定するデータ型の "DerivedProperties" を選択すると、ExEntityクラスにプロパティが自動生成されます。

![DerivedProperties QuickFix]({{ site.baseurl }}/image/shot/emecha-dfassist-derivedprop.png "DerivedProperties QuickFix"){: style="border:1px solid;" width="550px"}

## 関係するファイルを開く {#hyperlink}

DBFluteの外だしSQL(OutsideSql)を利用していると、SQLが記述されているファイルを確認したり、SQLファイルからParameterBeanやCustomizeEntityを確認したい場面に出くわします。
DFAssistを利用することで、ソースコード上の ParameterBean や CustomizeEntity から、対象となる外だしSQLをエディターで開くことができます。

**Ctrl** を押しながらクラス名にカーソル合わせると、***SQLを開く*** というメニューが出てくるので、それをクリックすると対応する外だしSQLが開きます。(HyperLink)
さらに、ParameterBeanなら ***CustomizeEntityを開く***、CustomizeEntityなら ***ParameterBeanを開く*** がメニューに出てきます。

Ctrl ではなく、**Alt** を押しながらクラス名をクリックすると選択する手間なく ***SQLを開く*** が実行されます。
同様に、**Ctrl + Alt** を押しながらクラス名をクリックすると、ParameterBeanなら ***CustomizeEntityを開く***、CustomizeEntityなら ***ParameterBeanを開く*** が実行されます。

SQLファイルからは右クリックメニューの **「EMecha」** から ***CustomizeEntityを開く*** または、***ParameterBeanを開く*** を選択すると対象のクラスを開くことが出来ます。

* BehaviorQueryPath 構成で対応するクラスが存在する場合に限る。
* SQLファイルはBehaviorのExクラスと同じパッケージか、そのサブパッケージに配置している場合に限る。

## 新規実装クラスの作成 {#NewConcreteClass}

インターフェイスや抽象クラスに対する実装クラスを作成する際のサポートを行う機能です。
DBFluteを利用しない開発の場合にも利用できる機能です。

### 操作方法

ツリー上でJavaソースファイルを選択するか、Javaソースファイルを開いているエディタ上で **「ソース(Source)」-「新規実装クラスを作成(Create New Concrete Class)」** を選択します。

クラス作成ウィザードが、インターフェイスもしくはスーパークラスに選択していたクラスが設定された状態で表示されます。

作成するクラスのパッケージには **選択していたクラスのパッケージ + .impl** が設定されているので必要に応じて適切なパッケージに変更してください。

作成するクラス名には **選択していたクラス名 + Impl** が設定されているので必要に応じて適切なクラス名に変更してください。
（このとき、選択されていたクラス名の先頭に Abstract がついていた場合は取り除かれます。）

