---
title: 如何配置终止形状 |Microsoft 文档
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
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247925"
---
# <a name="how-to-configure-the-terminate-shape"></a>如何配置终止形状
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
终止形状  
  
 终止形状用于结束某一业务流程实例。 可以指定一个消息字符串，以便在“组中心”页的输出中查看时随该形状一起显示。  
  
> [!CAUTION]
>  如果你将放置**终止**形状内**并行操作**形状和使用分支**终止**上运行，在实例完成立即，而不考虑是否其他分支已完成运行。 根据您的设计，在此情况下结果可能不可预测。  
  
> [!CAUTION]
>  如果**终止**形状遇到业务流程中同步调用 (与**调用**形状) 通过另一个业务流程、 嵌套的实例和所有封闭的业务流程将终止实例。  
  
### <a name="to-configure-a-terminate-shape"></a>配置终止形状  
  
-   你可以使用**错误消息**属性来指定你想要将形状在组中心页面上将查询输出中查看时与关联的文本。 此文本可能是文字字符串或表达式计算结果为**System.String**。  
  
    > [!CAUTION]
    >  如果输入字符串，则必须将其括在引号中。