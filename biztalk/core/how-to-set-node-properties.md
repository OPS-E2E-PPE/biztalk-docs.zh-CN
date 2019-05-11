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
ms.openlocfilehash: f3bd08285230f48c44e75b7eca47a4c6038df413
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383907"
---
# <a name="how-to-set-node-properties"></a>如何设置节点属性
在将节点插入 BizTalk 架构，您通常需要更改该节点的属性从其默认值。 每种节点类型具有一组不同的属性，并在这些集之一中的一个属性的设置可能会影响其他属性的可用性。 例如，在设置前**默认的环绕符**的属性**架构**节点，则必须设置**默认环绕符类型**属性设置为任一**字符**或**十六进制**，从而建立要在其中表示前一属性的格式。 此外，这些属性不可用，既不是整个**分析**的属性类别到其所属，除非**平面文件扩展**通过启用**架构编辑器扩展**属性。  

 节点属性数量较多而且可能很复杂，因为它们支持的 XML 架构定义 (XSD) 语言。 本主题仅简要介绍所涉及检查和设置节点属性的常规步骤。 有关这些属性的详细信息，包括，例如，其默认值有关的信息和允许的值，请参阅**Schema Property Reference**。 有关更多详细信息与 XSD 概念和这些节点属性的大多数为基础的元素，请直接参阅信息有关[在 Web 上找到 XSD](../core/xsd-resources-on-the-web.md)。  

这些属性和架构属性引用的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

  
## <a name="examine-a-node-property-value"></a>检查节点属性值  
  
1. 在 BizTalk 编辑器中，打开包含你想要检查，的属性的架构，然后选择包含该属性的节点。  
  
2. 如有必要，请按 F4 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。  
  
3. 如有必要，向下滚动属性窗口以查找感兴趣的属性，并记下其值。  
  
    可以使用属性窗口顶部的按钮更改属性的排序，其类别中按字母顺序或不考虑 （或不显示） 的情况下按字母顺序的方式及其类别。  
  
## <a name="set-a-node-property-value"></a>设置节点属性值  
  
1. 在 BizTalk 编辑器中，打开包含你想要设置，的属性的架构，然后选择包含该属性的节点。  
  
2. 如有必要，请按 F4 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。  
  
3. 如有必要，向下滚动属性窗口以查找感兴趣的属性。  
  
    可以使用属性窗口顶部的按钮更改属性的排序，其类别中按字母顺序或不考虑 （或不显示） 的情况下按字母顺序的方式及其类别。  
  
4. 是属性名称右侧的值字段中设置属性的值。 根据该属性的类型，可能会键入一个值，或从选择的值字段时显示的下拉列表中选择值。 对于某些属性，这两种操作。 某些属性显示一个省略号 (**...**) 按钮，可以设置在其中一个对话框更为复杂的值，例如集合、 被单击的打开。  
  
5. 如果键入属性的新值之后，按 ENTER 结束。  
  
##  <a name="clear-a-node-property-value"></a>清除节点属性值  
  
1.  选择包含目标属性的节点。  
  
2.  在属性窗口中，双击你想要清除的属性值，用鼠标右键单击，再单击属性值**删除**。  
  
## <a name="restore-a-node-property-to-its-default-value"></a>节点属性还原为其默认值  
  
1.  选择包含目标属性的节点。  
  
2.  在属性窗口中，右键单击你想要重置为其默认值，然后单击属性名称**重置**。  
  
## <a name="see-also"></a>请参阅  
 [使用现有节点](../core/working-with-existing-nodes.md)