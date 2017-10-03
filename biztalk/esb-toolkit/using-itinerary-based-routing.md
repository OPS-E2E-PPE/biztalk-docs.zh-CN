---
title: "使用基于路线的路由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc0a0eb3a212efccd4ddbe4e275042ecb850095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-itinerary-based-routing"></a>使用基于路线的路由
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供基于路线的邮件路由通过实现要启用方案时的处理序列步骤的某个特定消息的路由滑动模式不知道在设计时和每个消息都可能不同。 此模式的实现使用路由滑动来表示这些步骤以 XML 格式的集合，并确定需要在运行时期间可能出现哪些步骤。 路由滑动，通常称为"ESB 日程表"，状态是一组有序的定义必须执行的消息，因为它正在处理的步骤的声明性说明[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件和 BizTalk Server 运行时。 在 ESB 路线中指定特定的处理指令与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件，也称为"ESB 路线本服务。" ESB 路线服务的目的是滑动的要执行的处理说明进行操作并更新路由，以指示挂起指令下的一步的状态。  
  
 本部分介绍的基于路线的处理功能[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 本节包含以下主题：  
  
-   [ESB 路线管理](../esb-toolkit/esb-itinerary-management.md)  
  
-   [上渐变和关闭渐变](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [选择消息传送和业务流程路线服务](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [使用管道组件来选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [使用管道组件读取一条路线](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [使用管道组件来缓存请求作出响应一条路线](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [创建路线订阅服务器](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [执行路线服务](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   超链接"http://msdn.microsoft.com/en-us/library/ee236752 (BTS.10).aspx"[路线基于路由的项目](../esb-toolkit/itinerary-based-routing-artifacts.md)