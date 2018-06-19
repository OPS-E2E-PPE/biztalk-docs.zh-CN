---
title: 如何将数据复制到与消息的上下文可分辨字段 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248965"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a>如何将数据复制到可分辨的字段的消息上下文
本主题提供有关将提升为属性的分步说明**可分辨字段**。  
  
 你可以选择**可分辨字段**通过升级**属性字段**出于以下原因升级：  
  
-   **属性字段**值限于 255 个字符的长度。  
  
-   **属性字段**值存储在数据库中，并因此具有多个开销低于**可分辨字段**。 **可分辨字段**不需要任何其他存储; 它们是实质上是别名**XPath**，从而允许业务流程更轻松地访问直接从消息的相关值。  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a>将属性升级为可分辨字段  
  
1.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**可分辨字段**。  
  
    > [!NOTE]
    >  记录节点永远不会被提升为**可分辨字段**，不管它们包含的内容类型。  
  
2.  右键单击所选的节点，单击**Promote**，然后单击**显示提升**。  
  
     **升级属性**对话框随即打开与所选的节点显示的所选对话框左侧的架构树中。  
  
3.  在**升级属性**对话框中，选择**可分辨字段**选项卡。  
  
4.  与节点可升级的左侧的架构树中仍选定**升级属性**对话框中，单击**添加**。  
  
     如果允许，所选的节点添加到列表上**可分辨字段**选项卡。如果不允许，消息框将提供说明。  
  
5.  你可以在对话框中，单击左侧架构树中选择更多节点升级**添加**后每个所选内容。  
  
6.  完成后，单击**确定**。  
  
     选择进行升级的节点现**可分辨字段**。  
  
## <a name="see-also"></a>另请参阅  
 [提升属性](../core/promoting-properties.md)   
 [如何创建属性架构](../core/how-to-create-property-schemas.md)   
 [使用与控件消息处理的消息内容的方法](../core/ways-to-use-message-content-to-control-message-processing.md)