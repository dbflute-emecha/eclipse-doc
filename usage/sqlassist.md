---
layout: page
title: SQLAssist
category: SQLAssist
---

* [SQLAssistとは？](#description)
* [補完機能](#assist)
  * [複数行コメントを自動的に閉じる](#multiLineComment)
  * [Sql2Entityマークの補完](#sql2entitymarkSupport)
  * [明示的なプロパティ宣言の補完](#propertySupport)
  * [プロパティオプションの補完](#optionSupport)
  * [分岐条件の補完](#conditionSupport)

## SQLAssistとは？ {#description}

Data Tools Platform (DTP) のSQLエディタで **外だしSQL** を編集する際に入力補助を行うプラグインです。
SQLの補完はDTPのSQLエディタで行われます。
SQLAssistでは、パラメータコメントやSql2Entityマークの補完を行います。

[DBFlute - 外だしSQL(OutsideSql)について]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/about.html)
{: .relatedpage}

[DBFlute - パラメータコメント]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/pmcomment.html)
{: .relatedpage}

## 補完機能 {#assist}

### 複数行コメントを自動的に閉じる {#multiLineComment}

**/\*** と入力すると **\*/** を自動で入力します。

### Sql2Entityマークの補完 {#sql2entitymarkSupport}

**\-\-** (行コメント)を入力した後に、Ctrl + Space (コンテンツ・アシスト)で利用可能なSql2Entityマークが候補として表示されます。

![Sql2Entity Mark Support]({{ site.baseurl }}/image/shot/sqlassist-sql2entity-mark.png "Sql2Entity Mark Support"){: style="border: 1px solid"}

[DBFlute - Sql2Entityタスク - Sql2Entityマーク]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/index.html#sql2entitymark)
{: .relatedpage}

### 明示的なプロパティ宣言の補完 {#propertySupport}

プロパティの型を明示的に指定する場合にはSQLの行コメント形式で記述します。

```
-- !df:pmb!
-- !![プログラム型 プロパティ名]!! // (ParameterBean)

-- #df:entity#
-- ##[プログラム型 プロパティ名]## // (CustomizeEntity)
```

このとき、 **\-\- !!** または **\-\- ##** まで入力してから、Ctrl + Space を押すと利用できる基本的な型が候補として表示されます。
表示された型の中から利用する型を選択し Enter で確定した後は、プロパティの名前(変数名)を入力してください。

![Property Type Assist]({{ site.baseurl }}/image/shot/sqlassist-property-type.png "Property Type Assist"){: width="550px" style="border: 1px solid"}

[DBFlute - ParameterBean - ParameterBeanマーク]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/parameterbean.html#parameterbeanmark)
{: .relatedpage}
[DBFlute - CustomizeEntity - CustomizeEntityマーク]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html#customizeentitymark)
{: .relatedpage}

ParameterBeanのプロパティの型として区分値やEntityを指定することも可能です。
その際は、**\-\- !!\$** と入力してから、Ctrl + Space を押すとパッケージの省略を行う変数が候補として表示されます。

![Property Package Assist]({{ site.baseurl }}/image/shot/sqlassist-property-package.png "Property Package Assist"){: width="550px" style="border: 1px solid"}

[DBFlute - ParameterBean - プログラム型のパッケージ解決]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/parameterbean.html#packageresolve)
{: .relatedpage}

### プロパティオプションの補完 {#optionSupport}

曖昧検索や日付範囲など、ParameterBeanのプロパティに付けるオプションの候補を表示します。
プロパティのオプションは、 プロパティ名の後ろに ":" (コロン) を付けて、それに続いて指定します。
オプションが複数ある場合は、"|"(パイプ)で区切ります。

":" (コロン)の後ろで、Ctrl + Space を押すとオプションの一覧が表示されます。
２つ目以降の場合は、"|"(パイプ)の後ろで、Ctrl + Space を押すとオプションの一覧が表示されます。

![Option Assist]({{ site.baseurl }}/image/shot/sqlassist-option-support.png "Option Assist"){: width="550px" style="border: 1px solid"}

[DBFlute - ParameterBeanのプロパティオプション]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/pmbpropoption.html)
{: .relatedpage}

[DBFlute - ParameterBeanの自動判別 - プロパティのコメントは？]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/pmbautodetect.html#commentoption)
{: .relatedpage}

[DBFlute - CustomizeEntity - 検索カラムのコメント]({{ site.dbflute_url }}/ja/manual/function/generator/task/sql2entity/customizeentity.html#columncomment)
{: .relatedpage}

### 分岐条件の補完 {#conditionSupport}

IFコメントやFORコメントをの入力を補完します。
**/\*(カーソル位置)\*/** で、Ctrl + Space を押すと利用可能な候補の一覧が表示されます。

* IFコメント

  [DBFlute - パラメータコメント - IFコメント]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/pmcomment.html#ifcomment)
  {: .relatedpage}

* BEGINコメント

  [DBFlute - パラメータコメント - BEGINコメント]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/pmcomment.html#begincomment)
  {: .relatedpage}

* FORコメント

  [DBFlute - パラメータコメント - FORコメント]({{ site.dbflute_url }}/ja/manual/function/ormapper/outsidesql/pmcomment.html#forcomment)
  {: .relatedpage}

![Condition Assist]({{ site.baseurl }}/image/shot/sqlassist-condition-support.png "Condition Assist"){: width="550px" style="border: 1px solid;"}

> 複数行コメントの自動入力と合わせると、「/」「\*」「Ctrl + Space」「Enter」でIFコメントが下のように入力できます。
  /\*IF pmb.(カーソル位置)\*//\*END\*/
{: .incolumn}

