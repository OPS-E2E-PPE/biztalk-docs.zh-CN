---
title: 使用基于路线的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b09610d1c8952ae077fc872e7cd0c073a33eef4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396436"
---
# <a name="using-itinerary-based-routing"></a>使用基于路线的路由
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供基于路线的消息路由通过实现以启用方案时的一系列处理步骤的特定消息的传送名单模式不知道在设计时和每个消息都可能不同。 此模式的实现使用传送名单来表示这些步骤以 XML 格式的集合，并确定需要在运行时期间执行的步骤。 传送名单，通常称为"ESB 路线"，状态是一个有序的声明性定义在通过处理，则在一条消息时必须执行的步骤的说明[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件和 BizTalk Server 运行时。 ESB 路线中指定的特定处理指令与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件，也称为"ESB 路线服务。" ESB 路线服务的目的是要执行的处理指令并更新以指示下一个挂起的指令的传送名单的状态。  

 本部分介绍的基于路线的处理功能[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 本节包含以下主题：  

- [ESB 路线管理](../esb-toolkit/esb-itinerary-management.md)  

- [接入点和接出点](../esb-toolkit/on-ramps-and-off-ramps.md)  

- [在消息传递和业务流程路线服务之间进行选择](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  

- [使用管道组件选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  

- [使用管道组件读取路线](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  

- [使用管道组件缓存“要求-响应”路线](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  

- [创建路线订阅方](../esb-toolkit/creating-itinerary-subscribers.md)  

- [执行路线服务](../esb-toolkit/executing-an-itinerary-service.md)  

- 超链接"<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>"[基于路线的路由项目](../esb-toolkit/itinerary-based-routing-artifacts.md)
