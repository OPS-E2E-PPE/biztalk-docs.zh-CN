---
title: Assert | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine], .NET objects
- Assert function [Business Rules Engine], TypedXMLDocument
- Assert function [Business Rules Engine]
- Assert function [Business Rules Engine], examples
- Assert function [Business Rules Engine], TypedData table
- Assert function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e9989214-3c10-4691-9c38-f6fe64e511ed
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fcf26ae039999b4d4593f94ab4b8f375cd03a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528623"
---
# <a name="assert"></a>ActualRebinds
*断言*是添加到业务规则引擎工作内存中的对象实例的过程。 引擎处理的情况和针对的实例，使用匹配-冲突解决-操作阶段类型编写的操作根据每个实例。  
  
 下面的主题介绍使用而导致的行为**Assert**不同的事实类型的函数。  
  
## <a name="net-objects"></a>.NET 对象  
 每个对象作为单独的实例添加到工作内存中。 这意味着每个引用对象的类型的谓词分析的实例 (例如，IF Object.Property = 1)。 它还将提供到引用类型，依赖于规则条件的结果的规则操作。  
  
 请参考如下示例。  
  
 **规则 1**  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 **规则 2**  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 在规则 1 中，只有这些实例的一个值为 1 会具有其**状态**更新的属性。 在规则 2，但是，如果条件计算结果为 **，则返回 true**，为将所有实例都具有其状态已更新。 事实上，如果有多个 B 的实例，一个实例将更新条件计算结果为每次 **，则返回 true** B 实例。  
  
 若要添加.NET 对象从规则中的，可以添加内置**Assert**函数作为规则操作。 请注意，规则引擎的强大**CreateObject**函数，但它不会显示为单独的函数在业务规则编辑器。 其调用旨在通过将你想要从事实浏览器的.NET 类视图创建到操作窗格中的对象的构造函数方法。 业务规则编辑器然后会将转换构造函数方法转换成**CreateObject**在规则定义中调用。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 当**TypedXmlDocument**被声明，业务规则引擎创建子**TypedXmlDocument**实例根据规则中定义的选择器。  
  
 这两个 XPath 表达式选择器和字段。 可以选择器视为隔离 XML 文档时，将字段视为标识选择器中的特定项的节点的方法。 一个选择器中的所有字段都组合在一起作为一个对象由引擎。 当选择下的一个节点**XML 架构**在事实浏览器，业务规则编辑器的选项卡会自动填充**XPath 选择器**的所有节点的属性和**XPath 字段**不包含子节点的任何节点的属性。 或者，可以输入自己的 XPath 表达式**XPath 选择器**并**XPath 字段**如有必要。  
  
 如果选择器匹配的 XML 文档的多个部分，将其添加到或从规则引擎工作内存中取消此类型的多个对象。 假设您有下面的 XML。  
  
```  
<root>  
   <order customer="Joe">  
      <item name="router" quantity="10" cost="550" />  
      <item name="switch" quantity="3" cost="300" />  
   </order>  
   <order customer="Jane">  
      <item name="switch" quantity="1" cost="300" />  
      <item name="cable" quantity="23" cost="9.99" />  
   </order>  
</root>  
```  
  
 如果使用的选择器/顺序 (或 / / o)，两个对象添加到工作内存。  
  
 1\)  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 2\)  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 中每个选择器中，单个字段是通过 Xpath 引用的。  
  
 如果使用选择器 /root/order/item (或 (//order/item 或 //item)，四个对象添加到规则引擎工作内存中，Joe 的两个项目和 Jane 的两个项。  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 每个对象有权访问三个字段 —@name， @quantity，和@cost。 因为该对象是对原始文档的引用，您可以引用父字段 (例如，"../@customer")。  
  
 可以使用同一文档中的多个选择器。 这使您可以查看该文档的不同部分 （例如，如果一个部分为订单，另一个部分包含发货地址）。 但是，请注意，创建的对象由创建它们的 XPath 字符串定义。 使用不同的 XPath 表达式，即使它解析为同一节点中，会导致唯一**TypedXmlDocument**。  
  
 规则引擎支持基本.NET 标量类型本身，以及引用类型的对象。 XML 文档基本上是文本，但根据规则生成时指定的类型，字段值可以是任何类型。 此外，由于字段是 XPath 表达式，它们可能会返回节点集，此情况下在集中的第一项都使用作为值。  
  
 在后台，规则引擎可以将文本字段值转换为任何一种通过受支持的类型**XmlConvert**函数。 您可以将类型设置业务规则编辑器中进行指定。 如果转换不可能，将引发异常。 类型**bool**并**double**可以仅作为其各自的类型、 字符串或对象进行检索。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 当**TypedDataTable**被声明，所有**Datarow**中包含**DataTable**自动将其添加到引擎作为**TypedDataRows**. 任何时候，只要一个表或表列用作规则参数，针对单个计算表达式**TypedDataRows**，而不是根据**TypedDataTable**。  
  
 例如，假设您有针对"客户"表构建了以下规则：  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  若要生成一条规则针对数据库表，必须使用**数据表 / 行**作为数据库绑定类型。  
  
 假设您添加以下**DataTable**具有三个**Datarow**到引擎中 (作为**TypedDataTable**)。  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|提供分配器|  
|002|提供分配器|  
|003|提供分配器|  
  
 该引擎将插入三个**TypedDataRows**:001、 002 和 003。  
  
 每个**TypedDataRow**针对规则独立计算。 第一个**TypedDataRow**是否满足规则条件和两个故障。 结果将显示，如下所示。  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|采购经理|  
|002|提供分配器|  
|003|提供分配器|  
  
> [!NOTE]
>  Typeddatarow 也可以直接添加到引擎中。 如前面所述相同的方式处理。  
  
 **DataSetName.DataTableName**被视为是唯一的标识符。 因此，如果第二个**TypedDataTable**具有相同断言**数据集**名称并**DataTable**名称，它将取代第一个**TypedDataTable**. 所有**TypedDataRow**与第一个关联**TypedDataTable**将被取消，第二个**TypedDataTable**进行断言。  
  
## <a name="dataconnection"></a>DataConnection  
 如同**TypedDataTable**，将表或列拖动作为规则参数在业务规则编辑器会导致针对返回生成的规则**TypedDataRow**而不是 s **DataConnection**本身。  
  
 假设创建以下规则和一个**DataConnection** ，其中包含断言**SqlConnection**到 Northwind.Customers:  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 当引擎的计算结果中使用的规则**TypedDataTable**部分中，会动态生成一个查询如下所示：  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 因为只有一个数据库中的行满足此条件，只有一个**TypedDataRow**创建并将其添加到引擎中以便进一步处理。  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a>断言的实体和实例类型的摘要  
 下表汇总了各种类型，显示的结果中的每个断言的实体，引擎创建的实例数，以及应用于每个这些实例，以便于识别这些类型的添加行为。  
  
|实体|添加的实例数|实例类型|  
|------------|----------------------------------|-------------------|  
|.NET 对象|1 （对象本身）|完全限定的.NET 类|  
|TypedXmlDocument|1-N TypedXmlDocument(s):基于创建的选择器绑定和文档内容|DocumentType.Selector|  
|TypedDataTable|1-N TypedDataRow(s):<br /><br /> 一个用于每个 DataRow 的 DataTable 中|DataSetName.DataTableName|  
|TypedDataRow|1 (添加的 TypedDataRow)|DataSetName.DataTableName|  
|DataConnection|1-N （一个用于通过查询 DataConnection 返回每个 TypedDataRow）|DataSetName.DataTableName|  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)