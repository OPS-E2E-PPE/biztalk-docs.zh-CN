---
title: "类型化事实 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6041a64fcc4b3496c319a25a2ce758ed7f52a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="typed-facts"></a>类型化的事实
*类型化事实*是实现的类**ITypedFact**接口： **TypedXmlDocument**，**该组**， **TypedDataTable**，和**TypedDataRow**。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 **TypedXmlDocument**类表示业务规则框架中的 XML 文档类型。 在规则中使用 XML 文档的节点作为参数时，将创建两个 XPath 表达式：选择器绑定和字段绑定。  
  
 如果该节点不具有任何子节点，*选择器绑定*（也称为 XmlDocument 绑定） 创建到节点的父节点和*字段绑定*创建 （也称为 XmlDocumentMember 绑定）节点自身。 此字段绑定是相对于选择器绑定的。 如果该节点具有子节点，则将为该节点创建选择器绑定，而不创建任何字段绑定。  
  
 假设您具有以下架构：  
  
 ![事实数据资源管理器中显示的示例架构](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")  
Case.xsd  
  
 如果选择“Income”节点，则只创建选择器绑定，因为该节点具有子节点。 中的默认 XPath 表达式**XPath 选择器**的属性窗格中的属性包含：  
  
```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  
  
 但是，如果选择“Name”节点，则将创建选择器绑定和字段绑定。 绑定信息与下面所列相似：  
  
|属性|值|  
|--------------|-----------|  
|**XPath 的字段**|*[local-name()='Name' and namespace-uri()='']|  
|**XPath 选择器**|/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']|  
  
 在将节点拖动到规则参数中，将新的绑定信息放入策略之前，您可以更改 XML 节点的默认 XPath 表达式。 但是请注意，对 XPath 表达式所做的任何编辑内容都必须在重新加载架构时重新输入到业务规则编辑器中。  
  
 如果为 XML 节点创建了词汇定义，则根据之前描述的规则，这些绑定的 XPath 表达式具有相似的默认值，但可在词汇定义向导中进行编辑。 对表达式所做的更改放在词汇定义中，并反映在使用这些定义生成的所有规则参数中。  
  
## <a name="dataconnection"></a>DataConnection  
 **数据连接**中提供一个.NET 类**RuleEngine**库。 它包含一种.NET **SqlConnection**实例和一个**数据集**名称。 **数据集**名称可用于创建的唯一标识符**SqlConnection**并可用于定义生成的类型。  
  
 **该组**类提供了一种性能优化到业务规则引擎。 而不是断言到引擎非常大的数据库表 (**TypedDataTable**类) 可以包含许多数据库行 (**TypedDataRow**类) 不相关的策略，你可以断言轻量**该组**。 当引擎评估策略时，它动态生成基于规则谓词/操作和查询的 SELECT 查询**该组**在执行。 例如，假设您具有以下规则：  
  
```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  
  
 以下 SQL 查询生成于该规则：  
  
```  
Select * From [Product] Where [UnitPrice] >= 0  
```  
  
 查询的结果被作为数据行添加回引擎中。  
  
> [!NOTE]
>  使用**OleDbConnection**中**该组**当前不支持。  
  
 当你选择要在规则条件或操作中使用的数据库表/列时，你可以选择将绑定到使用对象**该组**或**TypedDataTable**通过选择"数据连接"或"数据库表/行"从**数据库绑定类型**性的属性窗口中的下拉列表框**数据库**事实浏览器选项卡。  
  
> [!NOTE]
>  默认情况下，将使用 DataConnection 绑定。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 你可以断言 ADO.NET **DataTable**对象插入引擎，但它将被视为任何其他.NET 对象。 在大多数情况下你将改为想要断言的规则引擎类**TypedDataTable**。  
  
 **TypedDataTable**是一个包装类，包含 ADO.NET **DataTable**。 该构造函数只需使用**DataTable**。 任何时候，只要一个表或表的列用作规则参数，针对单个计算该表达式**TypedDataRow**包装器，而不是针对**TypedDataTable**。  
  
## <a name="typeddatarow"></a>TypedDataRow  
 这是 ADO 的类型化的事实包装**DataRow**对象。 将表或列拖动到业务规则编辑器中的规则参数会导致规则生成针对返回**TypedDataRow**包装器。  
  
## <a name="see-also"></a>另请参阅  
 [事实](../core/facts.md)