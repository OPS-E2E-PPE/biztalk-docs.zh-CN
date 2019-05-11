---
title: 如何将映射事件源 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, alerts
- orchestrations, schedules
- events, mapping sources
- orchestrations, tracking profiles
- events, orchestration schedules
- tracking profiles, orchestrations
- tracking profiles, alerts
- alerts, tracking profiles
- alerts, BAM
- tracking profiles, mapping event sources
- events, tracking profiles
ms.assetid: 507f1624-2cd8-4960-8c63-7797ab22519e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56f9d85d0ac3509eb954f6c2d50496ce5979769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336636"
---
# <a name="how-to-map-event-sources"></a>如何将映射事件源
映射事件源可以访问 BAM 跟踪以生成警报的数据项。  
  
> [!NOTE]
>  可以将映射数据项从四种不同的事件源类型： 业务流程调度、 消息负载、 上下文属性或消息传送属性。 本主题中的过程概述了从业务流程调度映射数据项。  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a>若要将业务流程调度映射为事件源  
  
1.  打开现有的跟踪配置文件或创建新的跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  单击**选择事件源**按钮 （位于跟踪配置文件编辑器中的右窗格上方）。  
  
3.  选择**选择业务流程计划**级联菜单中的菜单项。  
  
4.  选择要从中提取业务流程通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，，然后单击**下一步**。  
  
     ![父程序集选作 TPE 中的事件源](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")  
  
5.  选择业务流程中的数据项的源**业务流程名称**列表框中，，然后单击**确定**。  
  
6.  在右窗格中选择的数据项目，并将其拖到左窗格中的活动中的相应节点。  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)