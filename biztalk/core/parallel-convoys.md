---
title: 并行保护 |Microsoft Docs
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
ms.openlocfilehash: edc797c59332d9a2453f38afd5daffabfbcdac9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393412"
---
# <a name="parallel-convoys"></a>并行保护
并行保护可以使多个单独的消息以实现所需的效果。 组相关消息可以按任意顺序到达，但 BizTalk Server 必须在启动进程之前收到所有项。  
  
 例如，当医院承认这一点新患者，医院需要一些相关的信息从患者，包括保险信息、 过去的医疗历史记录和联系信息。 多个人员收集此信息，包括保险专家、 护士和接线员。 多个不同的系统处理此信息。 在哪个集合中，此提交订单信息发生不能保证。 例如，信息收集器可能还忙于其他患者、 医疗记录部门可能在其计划中，在后面或保险系统可能不正常。 以有序的方式组装病人的此信息必须贯穿整个在医院患者所花费的时间。 这可确保将患者接收相应管理和精确的计费。  
  
 前面的方案是需要并行保护消息处理的商业应用场景的示例。 业务要求规定病人入院到医院之前的三个不同类型的消息的接收。 这些三个消息是保险、 历史记录和患者的消息。 这些消息的任何一个可以是第一条消息到达患者，并且这将创建一个争用条件。 若要解决此问题，三个**接收**形状放入**并行操作**形状并且每个接收标记为 Activate = True。 这样，三条消息以启动业务流程的任何一个。 业务流程实例等待，直到其他两条消息到达到继续进行处理后，再继续下一步。  
  
## <a name="implementing-parallel-convoys"></a>实现并行保护  
 您可以通过使用实现并行保护"并行关联接收"消息传送在 BizTalk Server 中的设计模式。 并行关联接收相关的两个或多个分支中接收语句**并行操作**形状。 如果在多个并行任务中初始化该相关时，每个相关的接收必须初始化一组完全相同的相关性。 接收相关的消息的此类任务首先执行实际的初始化，并对中的其他任务执行的验证**并行操作**形状在业务流程中。  
  
 有关并行保护实现的示例，请参阅 SDK 示例"并行保护"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>请参阅  
 [使用保护方案](../core/working-with-convoy-scenarios.md)   
 [顺序保护](../core/sequential-convoys.md)