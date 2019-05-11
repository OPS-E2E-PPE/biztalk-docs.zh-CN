---
title: 如何配置侦听形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55a717c45e5c40b4022c38d2b668cae4c615f248
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386054"
---
# <a name="how-to-configure-the-listen-shape"></a>如何配置侦听形状
侦听操作使应用程序要等待的时间的一个或多个端口上的若干消息之一，或指定的超时间隔，并根据结果的分支后停止等待。  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
侦听形状  
  
 您可以添加任意数量的分支。 可以将放置其他任何形状下方初始**接收**或**延迟**形状。  
  
 可以使用激活接收**侦听**形状。 如果的一个分支**侦听**形状包含激活接收，则所有分支都必须都包含激活接收，而且可以使用无超时。 激活接收必须是每个分支中的第一个操作。  
  
 可以使用**侦听**分支业务流程流的形状基于发生的一个或多个事件。 每个分支中的第一个形状必须是**延迟**或**接收**形状。 满足其条件的第一个分支 — 的超时值的匹配项**延迟**形状或接收的消息**接收**形状，将执行。 如果需要可以添加其他分支。  
  
### <a name="to-configure-a-listen-shape"></a>若要配置侦听形状  
  
1.  选择分支。  
  
2.  在属性窗口中，指定**分支类型**属性。  
  
     -或-  
  
     拖动**延迟**或**接收**形状拖到该分支。  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a>若要向侦听形状添加分支  
  
-   右键单击**侦听**形状，然后单击**新建侦听分支**。  
  
    > [!NOTE]
    >  若要删除分支起源**侦听**形状中，右键单击你想要删除，然后单击的分支**删除**。