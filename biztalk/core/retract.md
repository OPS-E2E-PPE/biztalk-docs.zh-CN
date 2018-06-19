---
title: 收回 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb4739412d310d2a69b53c8470abc7461ce3ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270109"
---
# <a name="retract"></a>收回
你可以使用**收回**函数从业务规则引擎使用内存中移除对象。 以下各段落介绍了与从规则引擎的工作内存中取消不同类型的实体的操作相关联的行为。  
  
## <a name="net-objects"></a>.NET 对象  
 .NET 对象是否被收回是在策略中使用**收回**函数。 此函数可用于业务规则编辑器作为**函数**词汇项： 将类 （不的程序集或方法） 拖到**收回**参数。  
  
> [!NOTE]
>  如果拖动到方法**收回**函数，该引擎尝试收回由方法返回的对象。  
  
 取消 .NET 对象将会从规则引擎的工作内存中删除该对象，并且此操作具有以下影响：  
  
-   在谓词中使用该对象的规则将会从议程中删除其操作（如果在议程中存在任何操作）。  
  
-   从议程中删除使用这些对象的操作。  
  
    > [!NOTE]
    >  较高安排上其他操作可能已执行之前**收回**调用函数。  
  
-   引擎不再评估该对象。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 您既可以收回原始**TypedXmlDocument** ，引擎所断言或收回一个子**TypedXmlDocument**从父节点创建的 s **XmlDocument**.  
  
 使用下面的 XML 作为示例，你可以既收回**TypedXmlDocument**与顺序或一个或两个关联**TypedXmlDocument**与 orderline 关联。  
  
```  
<order>  
   <orderline customer="Joe" linenumber="001">  
      <product name="router" quantity="10" cost="550" />  
   </orderline>  
   <orderline customer="Jane" linenumber="002">  
      <product name="switch" quantity="1" cost="300" />  
   </orderline>  
</order>  
```  
  
 若要取消订单对象，应在 XML 架构事实窗格中拖动架构的顶部节点。 此节点以".xsd"结尾，表示文档根节点 （不是文档元素节点）;它具有一个"/"的选择器，指的是初始**TypedXmlDocument**。 当父**TypedXmlDocument**是否被收回，所有**TypedXmlDocument**与关联的实例**TypedXmlDocument** (所有**TypedXmlDocument**通过调用创建的 s**断言**函数根据策略中使用的选择器) 从使用内存中删除。  
  
 收回仅各个子**TypedXmlDocument** (即 orderline)，可以将此节点拖到 XML 架构窗格中从**收回**函数。 务必请注意，所有**TypedXmlDocument**s 了与顶级**TypedXmlDocument**最初声明的而不是与**TypedXmlDocument**上面它出现在 XML 树层次结构。 例如，产品是**TypedXmlDocument**下面 orderline 对象中; 因此，它可能与订单关联**TypedXmlDocument**，而不是与 orderline **TypedXmlDocument**。 在大多情况下，此差别并不重要。 但是，如果取消订单对象，则也将取消订单行和产品对象。 如果取消订单行对象，则仅取消该对象，而不会取消产品对象。  
  
 引擎仅适用于和跟踪对象实例 (**TypedXmlDocument**s) 它时创建**TypedXmlDocument**最初断言。 如果你创建的其他节点-例如，通过在策略中选择器选择的节点同级节点-除非这些节点不会评估规则中**TypedXmlDocument**进行创建，这些断言。 新的、 较低级别的这些断言**TypedXmlDocuments**使它们在规则，但顶级评估**TypedXmlDocument**没有了解它们。 当顶级**TypedXmlDocument**是否被收回，将新的、 独立断言**TypedXmlDocument**s 交换机间链路不自动收回。 因此，如果创建新节点，它将通常最简单收回并重新声明完整**XmlDocument**。  
  
 **TypedXmlDocument**类支持大量的有用可作为操作的一部分中自定义.NET 成员调用的方法。 这些包括能够获取**XmlNode**与关联**TypedXmlDocument**或父**TypedXmlDocument**。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 您可以收回任一单个**TypedDataRow**s 或整个**TypedDataTable**。 如果取消表，则将从工作内存中取消所包含的所有行。  
  
 收回整个**TypedDataTable**你需要使用 helper 函数访问**父**属性**TypedDataRow**，例如：  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 在前面的操作，将拖动到表**TypedDataRow**。 在**GetTypedDataTable**将返回的值**TypedDataRow.Parent**。  
  
 与**TypedXmlDocument**s，如果你断言附加的新**TypedDataRow**s 针对相同**DataTable**后断言**TypedDataTable**，它们被视为单个实体和收回**TypedDataTable**不会导致这些收回额外**TypedDataRow**s。 仅**TypedDataRow**s 中包含**TypedDataTable**时它所断言收回。  
  
## <a name="dataconnection"></a>DataConnection  
 当**该组**是否被收回，所有**TypedDataRow**s 从通过由构造的查询数据库中检索**该组**从收回工作内存。 **该组**本身是否也被收回，也就是说，没有更**TypedDataRow**将通过检索 s**该组**（即，通过使用**数据连接**其他谓词或操作中)。  
  
 使用时**该组**，任何收回操作对单个**TypedDataRow**引擎将置于不一致状态。 因此，操作不允许对各个**TypedDataRow**与关联**该组**。 如果拖动表 (使用**该组**参数) 到**收回**函数，你将会收回**该组**。  
  
## <a name="see-also"></a>另请参阅  
 [引擎控制功能](../core/engine-control-functions.md)