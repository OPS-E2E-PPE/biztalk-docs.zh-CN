---
title: 收回 |Microsoft Docs
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
ms.openlocfilehash: 94967d573bf4293c0a2dcf6bf6c718f79d19736f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399086"
---
# <a name="retract"></a>收回
可以使用**Retract**函数以从业务规则引擎工作内存中删除对象。 以下各段介绍了与收回从规则引擎工作内存的不同类型的实体相关联的行为。  
  
## <a name="net-objects"></a>.NET 对象  
 .NET 对象在策略中可以使用收回**Retract**函数。 此函数是可在业务规则编辑器中作为**函数**词汇项： 将类 （不程序集或方法） 拖至**Retract**参数。  
  
> [!NOTE]
>  如果将方法转换成**Retract**函数，引擎将尝试取消由方法返回的对象。  
  
 取消.NET 对象从规则引擎工作内存中删除它，并会产生以下影响：  
  
-   在谓词中使用的对象的规则将其从议程中删除 （如果存在在议程上） 的操作。  
  
-   使用对象在议程的操作是从议程中删除。  
  
    > [!NOTE]
    >  议程别的其他操作可能之前已执行**Retract**调用函数。  
  
-   引擎不再评估该对象。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 也可以取消原始**TypedXmlDocument** ，添加到引擎或收回的一个子**TypedXmlDocument**从父节点的**XmlDocument**.  
  
 使用以下 XML 作为一个示例，您可以或者收回**TypedXmlDocument**与顺序或一个或两个关联**TypedXmlDocument**与订单行关联。  
  
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
  
 若要取消订单对象，将 XML 架构事实窗格中拖动架构的顶级节点。 此节点以".xsd"结尾，表示文档根节点 （不是文档元素节点）;它具有一个"/"的选择器，引用初始**TypedXmlDocument**。 当父**TypedXmlDocument**将被取消，所有**TypedXmlDocument**与关联的实例**TypedXmlDocument** (所有**TypedXmlDocument**通过调用创建的 s **Assert**函数根据策略中使用的选择器) 从工作内存中删除。  
  
 若要取消只有单个子**TypedXmlDocument** （即订单行），可以拖动到 XML 架构窗格上的此节点**Retract**函数。 务必要注意的所有**TypedXmlDocument**s 都与顶级**TypedXmlDocument**原始添加的而不是与**TypedXmlDocument**，其上方会出现在 XML 树层次结构中。 例如，产品是**TypedXmlDocument**如下订单行对象; 因此，它会与订单关联**TypedXmlDocument**，而不是与订单行**TypedXmlDocument**。 在大多数情况下，这一区别并不重要。 但是，如果取消订单对象，订单行和产品对象也将取消。 如果取消订单行对象，该对象只将被取消，而不是产品对象。  
  
 引擎仅处理和跟踪对象实例 (**TypedXmlDocument**s) 它时创建**TypedXmlDocument**最初添加。 如果创建其他节点 — 例如，通过在策略中的选择器选择的节点同级节点，这些节点不计算在规则中，除非**TypedXmlDocument**进行创建，这些断言。 添加这些新的、 较低级别**TypedXmlDocuments**会导致其进行评估规则，但顶级**TypedXmlDocument**不具备这些知识。 当顶级**TypedXmlDocument**将被取消，将新的、 独立断言**TypedXmlDocument**不会自动取消单独。 因此，如果创建新节点，则通常取消并重新添加完整的最简单**XmlDocument**。  
  
 **TypedXmlDocument**类支持多种可作为操作的一部分中的自定义.NET 成员调用的有效方法。 其中包括能够获取**XmlNode**与关联**TypedXmlDocument**或父**TypedXmlDocument**。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 可以取消两个**TypedDataRow**s 或整个**TypedDataTable**。 如果取消表，从工作内存中取消包含的所有行。  
  
 若要取消整个**TypedDataTable**需要使用一个帮助程序函数来访问**父**属性上的**TypedDataRow**，例如：  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 在前面的操作中，将拖动到表**TypedDataRow**。 在中**GetTypedDataTable**将返回的值**TypedDataRow.Parent**。  
  
 如同**TypedXmlDocument**s，如果你断言附加的新**TypedDataRow**的相同**DataTable**后断言**TypedDataTable**，它们被视为单个实体和收回**TypedDataTable**不会导致这些收回额外**TypedDataRow**s。 仅**TypedDataRow**中包含**TypedDataTable**添加时取消。  
  
## <a name="dataconnection"></a>DataConnection  
 当**DataConnection**将被取消，所有**TypedDataRow**s 从通过构造的查询数据库中检索**DataConnection**从取消工作内存中。 **DataConnection**本身也将被取消，也就是说，没有更多**TypedDataRow**s 将通过检索**DataConnection** （即，通过使用**DataConnection**中其他谓词或操作)。  
  
 使用时**DataConnection**，对单个操作的任何取消**TypedDataRow**将引擎放入不一致的状态。 因此，操作不允许对个人**TypedDataRow**与关联**DataConnection**。 如果将表 (使用**DataConnection**参数) 到**Retract**函数，则将会取消**DataConnection**。  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)