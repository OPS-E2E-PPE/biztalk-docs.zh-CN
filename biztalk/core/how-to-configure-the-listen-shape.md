---
title: "如何配置侦听形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-listen-shape"></a>如何配置侦听形状
侦听操作使应用程序可以等待一个或多个端口上的若干消息之一，或者在指定的超时间隔后停止等待，以及基于结果进行分支。  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
侦听形状  
  
 可以添加任意数量的分支。 你可以将初始下面的任何其他形状**接收**或**延迟**形状。  
  
 可以使用激活中接收**侦听**形状。 如果的一个分支**侦听**形状包含激活接收，则所有分支都必须都包含激活接收，而且可以使用无超时。 激活接收必须是每个分支中的第一个操作。  
  
 你可以使用**侦听**形状上的分支业务流程流与基于一个或多个事件的匹配项。 每个分支中的第一个形状必须是**延迟**或**接收**形状。 满足其条件的第一个分支-对使用超时的匹配项**延迟**形状或收到的消息**接收**形状-将执行。 可以根据需要添加更多的分支。  
  
### <a name="to-configure-a-listen-shape"></a>配置侦听形状  
  
1.  选择某一分支。  
  
2.  在属性窗口中，指定**分支类型**属性。  
  
     -或者-  
  
     拖动**延迟**或**接收**形状拖到该分支。  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a>向侦听形状添加分支  
  
-   右键单击**侦听**形状，然后单击**新侦听分支**。  
  
    > [!NOTE]
    >  若要删除分支起源**侦听**形状，右键单击你想要删除，，然后单击的分支**删除**。