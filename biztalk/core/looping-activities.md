---
title: 循环活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58668a901f9bb5a4aba3ae2ee25917c9227daac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330139"
---
# <a name="looping-activities"></a>循环活动
循环活动是指在业务流程内循环的操作。 就可以捕获来自业务流程内循环的操作的事件。 若要执行此操作，创建另一个活动并将映射的所有新活动里程碑和在循环内的数据。 这是必需的因为在循环中的数据处理将会发生多个计划的执行每一次。 下图显示了这种情况的示例。  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 如图所示，如果您有包含在循环中处理的多个行项的采购订单，等问题"哪些采购订单的货物价格为 $100？" 是不明确。 问题则含义明确：  
  
- 哪些采购订单的价格为 $100 的货物行？  
  
- 哪些采购订单的总计/最小/最大货物价格为 $100？  
  
  内容使用独立的从采购订单创建明确问题需要考虑的行项。 在跟踪配置文件编辑器中，根活动 （例如，采购订单） 映射到在循环外的所有操作。 子活动 （例如，行项） 映射到此循环操作。  
  
  需要一个负载项用作根活动的 ActivityID。 有一些在循环内的消息中提供此负载项。 该活动映射到关系节点下的子活动，并将其命名为根活动。  
  
## <a name="see-also"></a>请参阅  
 [与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)