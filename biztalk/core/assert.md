---
title: 断言 |Microsoft 文档
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
ms.openlocfilehash: a2de66aab5cde0a9515f41713d3390632180fbff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234045"
---
# <a name="assert"></a>ActualRebinds
*断言*是添加到业务规则引擎的工作内存的对象实例的过程。 引擎根据针对实例类型编写的条件和操作，使用匹配-冲突解决-操作阶段来处理每个实例。  
  
 以下主题介绍使用而导致的行为**断言**不同的事实类型的函数。  
  
## <a name="net-objects"></a>.NET 对象  
 每个对象作为单独的实例添加到工作内存中。 这意味着实例由每个引用对象类型的谓词进行分析（例如，IF Object.Property = 1）。 它还可用于引用类型的规则操作（取决于规则条件的结果）。  
  
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
  
 仅这些具有的实例的值为 1 将具有在规则 1 中，其**状态**更新的属性。 在规则 2，但是，如果条件计算结果为**true**，将的所有实例都具有更新其状态。 事实上，如果有 B 的多个实例，一个实例将更新条件计算结果为每次**true** B 实例。  
  
 若要断言中规则中的.NET 对象，你可以添加内置**断言**充当规则操作。 请注意，为规则引擎**CreateObject**函数，但它不会显示为单独的函数中业务规则编辑器。 通过将要创建的对象的构造函数方法从事实浏览器的 .NET 类视图拖动到操作窗格，可以生成对该函数的调用。 业务规则编辑器会将转换到的构造函数方法**CreateObject**调用中的规则定义的。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 当**TypedXmlDocument**被声明，业务规则引擎创建子**TypedXmlDocument**实例基于规则中定义的选择器。  
  
 选择器和字段都是 XPath 表达式。 您可以将选择器视为隔离 XML 文档的节点的方法，将字段视为标识选择器中的特定项的方法。 一个选择器中的所有字段按引擎分组为一个对象。 当选择一个节点下的**XML 架构**选项卡上的事实数据资源管理器，业务规则编辑器自动填写**XPath 选择器**属性的所有节点，和**XPath 字段**的任何不包含子节点的节点的属性。 或者，也可以输入自己的 XPath 表达式**XPath 选择器**和**XPath 字段**如有必要。  
  
 如果选择器与 XML 文档的多个部分相匹配，则将向规则引擎工作内存中添加或从中取消多个此类型的对象。 假定存在以下 XML：  
  
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
  
 如果使用选择器 /root/order（或 //order），则将向工作内存添加两个对象。  
  
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
  
 在每个选择器中，各个字段通过 XPaths 进行引用。  
  
 如果您使用选择器 /root/order/item（或 //order/item 或 //item），则将向规则引擎工作内存添加四个对象，Joe 两个项目，Jane 两个项目。  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 每个对象有权访问三个字段 —@name， @quantity，和@cost。 因为对象是为原始文档的引用，你可以引用的父字段 (例如，"../@customer")。  
  
 您可以在同一文档中使用多个选择器。 这样您就可以查看文档的不同部分（例如，如果一个部分为订单，而另一个部分包含发货地址）。 但请记住，所创建的对象是由创建它们的 XPath 字符串定义的。 使用不同的 XPath 表达式中，即使它解析为同一节点，导致唯一**TypedXmlDocument**。  
  
 规则引擎本身支持基本 .NET 标量类型以及引用类型的对象。 XML 文档基本上都是文本，但根据在构造规则时指定的类型，字段值可以是任何类型。 同时，由于字段是 XPath 表达式，因此它们可能会返回节点集。在这种情况下，将使用集合中的第一项作为值。  
  
 在后台，规则引擎可以将文本字段值转换为任何一种通过受支持的类型**XmlConvert**函数。 可以通过在业务规则编辑器中设置类型来指定该功能。 如果无法进行转换，则将会引发异常。 类型**bool**和**double**可以检索仅作为其各自的类型、 字符串或对象。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 当**TypedDataTable**被声明，所有**Datarow**中包含**DataTable**自动断言作为引擎**TypedDataRows**. 任何时候，只要一个表或表的列用作规则参数，针对单个计算该表达式**TypedDataRows**，而不是针对**TypedDataTable**。  
  
 例如，假设您针对“Customers”表构建了以下规则：  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  若要生成针对数据库表的规则，你必须使用**数据表 / 行**作为数据库绑定类型。  
  
 假设你断言以下**DataTable**有三个**Datarow**引擎 (作为**TypedDataTable**)。  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|Supply Clerk|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
 引擎插入三个**TypedDataRows**: 001、 002 以及 003。  
  
 每个**TypedDataRow**根据规则单独计算。 第一个**TypedDataRow**满足规则条件和两个失败。 结果如下所示：  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|采购经理|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
> [!NOTE]
>  TypedDataRow 也可以直接添加引擎中。 其处理方式与前面所述的方式相同。  
  
 **DataSetName.DataTableName**被视为唯一标识符。 因此，如果第二个**TypedDataTable**声明具有相同**数据集**名称和**DataTable**名称，第一个与它所取代**TypedDataTable**. 所有**TypedDataRow**与第一个关联**TypedDataTable**收回，第二个**TypedDataTable**断言。  
  
## <a name="dataconnection"></a>DataConnection  
 与**TypedDataTable**，拖动表或列作为业务规则编辑器中规则参数会导致规则生成针对返回**TypedDataRow**相对于 s **数据连接**本身。  
  
 假设创建以下规则和**该组**断言，该字符串包含**SqlConnection** Northwind.Customers 到：  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 当引擎的计算结果中使用规则**TypedDataTable**部分中，它动态生成如下所示的查询：  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 因为数据库中的只有一个行满足此条件，只有一个**TypedDataRow**被创建并进行进一步处理引擎断言。  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a>添加的实体和实例类型摘要  
 下表概括列出了各种类型的添加行为，显示了在引擎中为添加的每个实体创建的结果实例数，以及应用于这些实例以便对其进行标识的类型。  
  
|实体|添加的实例数|实例类型|  
|------------|----------------------------------|-------------------|  
|.NET 对象|1 个（对象本身）|完全限定的 .NET 类|  
|TypedXmlDocument|1-N 个 TypedXmlDocument：基于所创建的选择器绑定和文档内容|DocumentType.Selector|  
|TypedDataTable|1-N 个 TypedDataRow：<br /><br /> DataTable 中的每个 DataRow 各一个|DataSetName.DataTableName|  
|TypedDataRow|1 个（添加的 TypedDataRow）|DataSetName.DataTableName|  
|DataConnection|1-N 个（通过查询 DataConnection 返回的每个 TypedDataRow 各一个）|DataSetName.DataTableName|  
  
## <a name="see-also"></a>另请参阅  
 [引擎控制功能](../core/engine-control-functions.md)