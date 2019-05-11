---
title: 如何将数据复制到消息上下文作为可分辨字段 |Microsoft Docs
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
ms.openlocfilehash: 3fd5708fb972c21c84ae70f258c46e2d4cbcced9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340123"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a>如何将数据复制到消息上下文作为可分辨字段
本主题提供有关将属性升级为的分步说明**可分辨字段**。  
  
 您可以选择**可分辨字段**通过升级**属性字段**出于以下原因升级：  
  
-   **属性字段**值被限制为 255 个字符的长度。  
  
-   **属性字段**值存储在数据库中，并因此具有更多的开销比**可分辨字段**。 **可分辨字段**不需要任何其他存储时，它们是实质上是别名**XPath**，从而允许业务流程更轻松地访问相关的值直接从消息。  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a>若要将属性升级为可分辨字段  
  
1.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**可分辨字段**。  
  
    > [!NOTE]
    >  记录节点永远无法升级为**可分辨字段**，无论它们包含的内容类型。  
  
2.  右键单击所选的节点，单击**Promote**，然后单击**显示升级**。  
  
     **升级属性**对话框将打开与所选的节点显示为对话框的左侧的架构树中已选中。  
  
3.  在中**升级属性**对话框中，选择**可分辨字段**选项卡。  
  
4.  与要升级在左侧和右侧的架构树中仍然处于选中状态的节点**升级属性**对话框中，单击**添加**。  
  
     如果允许，选定的节点添加到列表上**可分辨字段**选项卡。如果不允许，消息框提供了说明。  
  
5.  您可以选择升级的其他节点在架构树中的对话框中，单击左侧**添加**后每个所选内容。  
  
6.  完成后，单击**确定**。  
  
     现已选定要升级的节点**可分辨字段**。  
  
## <a name="see-also"></a>请参阅  
 [升级属性](../core/promoting-properties.md)   
 [如何创建属性架构](../core/how-to-create-property-schemas.md)   
 [使用消息内容控制消息处理的方法](../core/ways-to-use-message-content-to-control-message-processing.md)