---
title: "什么是源事件视图？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, Source Event view
- Source Event view [Tracking Profile Editor]
- message schemas, Tracking Profile Editor
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, message schemas
- Tracking Profile Editor, orchestrations
ms.assetid: 72e74780-8590-484b-899d-cdc3d2a908be
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2437d2effe2fa03078e7f92fdb06f378c9e7cac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-source-event-view"></a>什么是源事件视图？
“事件源”视图是跟踪配置文件编辑器 (TPE) 显示从程序集中选择的业务流程或消息架构或者映射到活动定义的上下文属性的地方。  
  
 “事件源”视图显示在用户界面的右窗格中。 该窗格的内容随所选数据源而变化。  
  
## <a name="event-source-options"></a>事件源选项  
 你可以为事件源的四个选项： 业务流程计划、 消息传递负载、 上下文属性和消息传递的属性。  
  
 业务流程和消息传送负载要求选择要从中映射数据项的程序集。 然后从该程序集中选择特定的业务流程或目标消息负载架构。 对于业务流程调度，系统为您提供了程序集中的业务流程的列表。 使用消息传送负载，可以在消息传送架构列表中进行选择，上下文属性显示程序集和系统架构中可公用的架构的列表。  
  
 选择上下文属性时，系统首先为您提供一个上下文属性名称列表。 当您选择某个上下文属性时，该上下文属性的相关架构会显示在右窗格中。 然后，通过将该上下文属性拖放到某个活动节点上，可以将该属性映射到相应活动中。  
  
 选择消息传送属性时，系统会为您提供能映射到活动的已知消息传送属性的列表。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [业务流程计划视图](../core/orchestration-schedule-view.md)  
  
-   [消息传递负载视图](../core/messaging-payload-view.md)  
  
-   [上下文属性视图](../core/context-property-view.md)  
  
-   [消息属性视图](../core/messaging-property-view.md)