---
title: 如何设置节点属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c79eac-d9ba-45e2-a6e9-770b2bcb2067
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e70a1c6797379c81c22d1fc38a503974d8ac795
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022539"
---
# <a name="how-to-set-node-properties"></a>如何设置节点属性
在将节点插入 BizTalk 架构后，通常需要对该节点属性的默认值进行更改。 每种类型的节点都具有不同的属性集，在这些属性集中，对一种属性的设置将会影响其他属性的可用性。 例如，在设置前**默认的环绕符**的属性**架构**节点，则必须设置**默认环绕符类型**属性设置为任一**字符**或**十六进制**，从而建立要在其中表示前一属性的格式。 此外，这些属性不可用，既不是整个**分析**的属性类别到其所属，除非**平面文件扩展**通过启用**架构编辑器扩展**属性。  

 与其支持的 XML 架构定义 (XSD) 语言一样，节点属性数量较多而且可能十分复杂。 本主题只对检查和设置节点属性所涉及的通用步骤进行了简要说明。 有关这些属性的详细信息，包括，例如，其默认值有关的信息和允许的值，请参阅**Schema Property Reference**。 有关更多详细信息与 XSD 概念和这些节点属性的大多数为基础的元素，请直接参阅信息有关[在 Web 上找到 XSD](../core/xsd-resources-on-the-web.md)。  

这些属性和架构属性引用的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

  
## <a name="examine-a-node-property-value"></a>检查节点属性值  
  
1. 在 BizTalk 编辑器中，打开包含要检查的属性的架构，然后选择包含该属性的节点。  
  
2. 如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。  
  
3. 如有必要，可滚动“属性”窗口以查找目标属性，并记下其值。  
  
    您可以使用位于“属性”窗口顶部的按钮更改属性的排序方式，可以在其类别内按字母顺序排列，或按字母顺序排列但不考虑（或不显示）其类别。  
  
## <a name="set-a-node-property-value"></a>设置节点属性值  
  
1. 在 BizTalk 编辑器中，打开包含要设置的属性的架构，然后选择包含该属性的节点。  
  
2. 如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。  
  
3. 如有必要，可滚动“属性”窗口以查找目标属性。  
  
    您可以使用位于“属性”窗口顶部的按钮更改属性的排序方式，可以在其类别内按字母顺序排列，或按字母顺序排列但不考虑（或不显示）其类别。  
  
4. 在值字段中设置属性的值，该字段将位于属性名称的右侧。 根据属性的类型，可以键入值或从下拉列表中选择值，而此下拉列表会在选择值字段时显示。 对于某些属性，这两种操作均可用。 某些属性显示一个省略号 (**...**) 按钮，可以设置在其中一个对话框更为复杂的值，例如集合、 被单击的打开。  
  
5. 如果已为该属性键入新值，请按 Enter 结束。  
  
##  <a name="clear-a-node-property-value"></a>清除节点属性值  
  
1.  选择包含目标属性的节点。  
  
2.  在属性窗口中，双击你想要清除的属性值，用鼠标右键单击，再单击属性值**删除**。  
  
## <a name="restore-a-node-property-to-its-default-value"></a>节点属性还原为其默认值  
  
1.  选择包含目标属性的节点。  
  
2.  在属性窗口中，右键单击你想要重置为其默认值，然后单击属性名称**重置**。  
  
## <a name="see-also"></a>请参阅  
 [使用现有节点](../core/working-with-existing-nodes.md)