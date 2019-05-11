---
title: 如何配置终止形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177666efceb34d78b492c93b7f365fc36c3855bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340293"
---
# <a name="how-to-configure-the-terminate-shape"></a>如何配置终止形状
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
终止形状  
  
 终止形状用于结束业务流程实例。 可以指定来显示形状时从组中心页的输出中查看的消息字符串。  
  
> [!CAUTION]
>  如果将置于**Terminate**形状内**并行操作**形状，并使用分支**终止**上运行它时，该实例将立即完成，而不考虑是否其他分支完成运行。 根据你的设计，结果可能不可预测在这种情况下。  
  
> [!CAUTION]
>  如果**Terminate**形状遇到同步调用业务流程中 (如同**调用**形状) 通过另一个业务流程，则嵌套的实例和所有封闭的业务流程将终止实例。  
  
### <a name="to-configure-a-terminate-shape"></a>若要配置终止形状  
  
-   可以使用**错误消息**属性来指定你想要与形状时在组中心页上的查询输出中查看相关联的文本。 文本字符串或表达式的计算结果为此文本可能太**System.String**。  
  
    > [!CAUTION]
    >  如果输入的文本字符串，必须将其括在引号中。