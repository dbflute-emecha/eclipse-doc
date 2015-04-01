---
layout: page
title: EMSql
category: EMSql
---

* [EMSqlとは？](#description)
* [設定画面](#setting)
* [操作方法](#howto)

## EMSqlとは？ {#description}

DBFluteには**外だしSQL(OutsideSql)**という**外部テキストファイルに記載されたSQL文をアプリケーションから実行**する機能があります。

DBFluteの外だしSQLでは、ある規約に則ったSQLファイルに限ってそのSQLのパス定義をBehaviorクラスに自動生成し、プログラム上でタイプセーフにどのSQLを実行するのかを指定できるようにする ***BehaviorQueryPath*** と呼ばれる機能があります。

BehaviorQueryPath を利用するための手助けを行うのが ***EMSql*** です。

EMSqlの外だしSQLファイル作成機能を利用することにより、BehaviorQueryPathに沿ったファイルの作成が行われ、SQLの雛形が出力されます。

[DBFlute - 外だしSQL(OutsideSql)について]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/about.html)
{: .relatedpage}

[DBFlute - BehaviorQueryPath]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/behaviorquerypath.html)
{: .relatedpage}

## 設定画面 {#setting}

プロジェクトのプロパティ画面を開き **「EMecha」-「EMSql」** を開くと、SQLファイルの出力先フォルダと利用するデータベースの種類(SQL型)を指定することが出来ます。

データベースの種類を設定しておくことにより、ページングを利用する外だしSQLのファイル作成時に出力される雛形がDBMSに合わせた内容になります。

[DBFlute - DBFluteのサポート情報]({{ site.dbflute_url }}/ja/environment/supported.html)
{: .relatedpage}

ファイル出力先(sqlDirectory)のデフォルトはプロジェクトの src/main/resources になっています。
DBFluteの設定に合わせて変更してください。

## 操作方法 {#howto}

Package Explorer 上で対応する Behavior クラス(Exクラスのソースファイル)を選択して右クリックし **「EMecha」-「New Outside Sql」** を選択するか、
Behavior (Exクラス) を開き、Javaエディター内で右クリックして **「EMecha」-「New Outside Sql」** を選択すると新規外だしSQLファイルの作成画面が起動します。

![New Outside SQL]({{ site.baseurl }}/image/shot/emecha-emsql-newsql.png "New Outside SQL"){: width="550px" style="border:1px solid"}

作成するSQLの種類(SELECT,INSERT,UPDATE等)を選択し、SQL名(SQL Name)に(システムでユニークな) 業務名を入力します。

作成するSQLに合わせてオプションを設定し **完了(Finish)** or **Enter** で新規ファイルが作成されエディタが開かれます。


> ExBehavior だけでなく ***ApplicationBehaviorクラス*** を選択することも出来ます。
> Package Explorer 以外にもナビゲーターやプロジェクトエクスプローラー、型階層、アウトラインなどからでも (Ex)Behavior クラスが選択されていれば同様な操作が行えます。
> また、JavaソースだけでなくScalaソースでも同様な操作で外だしSQLファイルを作成することが可能です。
{: .incolumn}

[DBFlute - EMecha - EMSql - 外だしSQLの新規作成]({{ site.dbflute_url }}/ja/manual/function/helper/emecha/emsql/index.html#newoutsidesql)
{: .relatedpage}

[DBFlute - 外だしSQLの使い方]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/howto.html)
{: .relatedpage}

[DBFlute - アプリごとのBehavior]({{ site.dbflute_url }}/ja/manual/function/genbafit/projectfit/applicationbehavior/index.html)
{: .relatedpage}

[DBFlute - ParameterBean]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/parameterbean.html)
: [Paging]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/pmbclassoption.html)
{: .relatedpage}

[DBFlute - CustomizeEntity]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html)
: [CursorHandling]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html#cursor)
: [ScalarHandling]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html#ScalarHandling)
: [DomainHandling]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html#domain)
{: .relatedpage}

[DBFlute - TypeSafeCursor]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/typesafecursor.html)
{: .relatedpage}

[DBFlute - SchemaHTML - 外だしSQL一覧]({{ site.dbflute_url }}/ja/manual/function/generator/task/doc/schemahtml.html#outsidesql)
{: .relatedpage}

[DBFlute - outsideSqlDefinitionMap]({{ site.dbflute_url }}/ja/manual/reference/dfprop/outsidesqldefinition/index.html)
: [sqlDirectory]({{ site.dbflute_url }}/ja/manual/reference/dfprop/outsidesqldefinition/index.html#sqldirectory)
: [SQLのタイトルの強制]({{ site.dbflute_url }}/ja/manual/reference/dfprop/outsidesqldefinition/index.html#isrequiredsqltitle)
: [SQLの説明の強制]({{ site.dbflute_url }}/ja/manual/reference/dfprop/outsidesqldefinition/index.html#isRequiredSqlDescription)
{: .relatedpage}



