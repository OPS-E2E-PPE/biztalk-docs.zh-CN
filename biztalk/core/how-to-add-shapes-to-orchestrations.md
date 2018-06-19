---
title: 如何将形状添加到业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fa6634adb20ffcf927da0af6f58e9daa2800ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246949"
---
# <a name="how-to-add-shapes-to-orchestrations"></a>如何将形状添加到业务流程
本部分介绍在业务流程中添加和删除形状的过程。 有关可用的形状的详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。  
  
### <a name="to-add-a-shape-to-an-orchestration"></a>若要将形状添加到业务流程  
  
1.  在工具箱中，在**BizTalk 业务流程**选项卡上，将形状拖条连线到业务流程设计图面上。  
  
     -或者-  
  
2.  右键单击连接的线条或形状占位符想要添加该形状，指向**插入形状**，然后单击你想要添加的形状名称。  
  
    > [!NOTE]
    >  此时智能标记将出现在仍未完全配置的形状上。  
  
> [!NOTE]
>  **转换**形状和**消息分配**形状可以仅存在于**构造消息**形状。 如果你将添加这些形状之一到外部业务流程**构造消息**形状，它被自动放置到一个新**构造消息**形状。  
  
> [!NOTE]
>  **捕获异常**和**补偿**块才会存在以下**作用域**形状。  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a>从业务流程中删除形状  
  
1.  右击设计图面上的形状，然后单击**删除**。  
  
     -或者-  
  
2.  选择形状，然后按**删除**密钥。  
  
## <a name="see-also"></a>另请参阅  
 [创建业务流程](../core/creating-orchestrations.md)