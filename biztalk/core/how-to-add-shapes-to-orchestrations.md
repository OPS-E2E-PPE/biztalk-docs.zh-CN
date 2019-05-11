---
title: 如何向业务流程添加形状 |Microsoft Docs
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
ms.openlocfilehash: 0ba5e1f6484b1e7e3c268b1461aed1ea6534152b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343211"
---
# <a name="how-to-add-shapes-to-orchestrations"></a>如何向业务流程添加形状
本部分介绍用于添加和删除形状在业务流程中的过程。 有关可用形状的详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。  
  
### <a name="to-add-a-shape-to-an-orchestration"></a>若要向业务流程添加形状  
  
1.  在工具箱中，在**BizTalk 业务流程**选项卡上，在业务流程设计图面上形状拖动到连接的线条。  
  
     -或-  
  
2.  右键单击连接的线条或形状占位符，你想要添加形状，指向**插入形状**，然后单击你想要添加的形状名称。  
  
    > [!NOTE]
    >  尚未完全配置的形状中显示智能标记。  
  
> [!NOTE]
>  **转换**形状和**消息赋值**形状只能存在于**构造消息**形状。 如果您添加一个这些形状向业务流程之外**构造消息**形状，它被自动放置到一个新**构造消息**形状。  
  
> [!NOTE]
>  **捕获异常**并**补偿**块只能存在以下**范围**形状。  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a>若要从业务流程中删除形状  
  
1.  右键单击设计图面上的形状，然后单击**删除**。  
  
     -或-  
  
2.  选择形状，然后按**删除**密钥。  
  
## <a name="see-also"></a>请参阅  
 [创建业务流程](../core/creating-orchestrations.md)