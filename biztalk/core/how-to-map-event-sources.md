---
title: "如何将事件源映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588a394fb3404872554fc786efa3fe24fdd9b47a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-event-sources"></a>如何将映射事件源
通过映射事件源可以访问 BAM 跟踪的数据项以生成警报。  
  
> [!NOTE]
>  你可以将映射从四种不同的事件源类型的数据项： 业务流程计划、 消息负载、 上下文属性或消息属性。 本主题简要介绍了从业务流程调度映射数据项的过程。  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a>将业务流程调度作为事件源进行映射  
  
1.  打开现有的跟踪配置文件，或创建一个新跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  单击**选择事件源**按钮 （位于右窗格中的跟踪配置文件中相应的编辑器上方）。  
  
3.  选择**选择业务流程计划**从级联菜单的菜单项。  
  
4.  选择要从中业务流程，通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，并依次**下一步**。  
  
     ![为事件中键入源选择父程序集](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")  
  
5.  选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。  
  
6.  在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)