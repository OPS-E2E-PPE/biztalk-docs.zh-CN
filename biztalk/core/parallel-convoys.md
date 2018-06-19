---
title: 并行保护 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c6993aa3c5dd47cb5b554dd8ab2080020ebb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264837"
---
# <a name="parallel-convoys"></a>并行的保护
一个并行的队列允许多个单个消息联接在一起以获得所需的结果。 一组相关消息可以按任何顺序到达，但 BizTalk Server 必须在启动进程之前收到所有这些。  
  
 例如，当医院承认新患者，医院需要几个部分从 patient，包括过去的医疗历史记录和联系信息的保险信息的信息。 多个不同的人收集此信息，包括保险专家、 护士和接线员。 有几个不同系统处理此信息。 此提交的集合中的顺序信息发生不能保证。 例如，信息收集器可能忙于处理其他患者、 医疗记录部门在其计划，可能会在后面或保险系统可能不正常。 组织的方式组装患者此信息必须贯穿整个患者在医院所花费的时间。 这可确保将患者接收适当的小心和准确的计费。  
  
 前面的方案是需要并行的队列消息处理的业务方案的示例。 企业要求规定之前接收到医院患者收到的三个不同类型的消息。 这些三个消息是保险、 历史记录和患者的消息。 任一这些消息可以是第一条消息到达个 patient，并且这将创建的争用条件。 若要解决此问题，请三个**接收**形状放入**并行操作**形状和每个接收标记为激活 = True。 这样，要启动业务流程的三个消息的任何一个。 业务流程实例等待，直到在继续之前到达进一步处理到其他两条消息。  
  
## <a name="implementing-parallel-convoys"></a>实现并行保护  
 您可以使用 BizTalk Server 中的“并行关联接收”消息传送设计模式来实现并行保护。 并行关联接收相关的两个或多个分支中接收语句**并行操作**形状。 如果在多个并行任务中初始化一个相关性，每个关联的接收必须初始化完全相同的关联集。 这种任务接收到关联的消息会首先执行的实际初始化，以及在中的其他任务上执行验证**并行操作**业务流程中的形状。  
  
 并行的队列实现的示例，请参阅"并行保护"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>另请参阅  
 [使用队列方案](../core/working-with-convoy-scenarios.md)   
 [顺序保护](../core/sequential-convoys.md)