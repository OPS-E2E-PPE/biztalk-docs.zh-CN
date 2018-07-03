---
title: WCF LOB 适配器 SDK 适配器通道和服务之间的差异 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8583b615e6a6e8fcd999e5120bca531d3c74090d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010030"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 适配器通道和服务之间的差异
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]每个提供了一组可用于将应用程序功能提供给使用方应用程序在同一计算机上或在网络上的 Api。 若要选择最合适的框架，您必须考虑将公开提供的功能的业务需求以及目标系统应用程序的属性。 本主题提供了可用于选择合适的框架的准则。  
  
## <a name="when-to-write-an-adapter"></a>何时编写一个适配器  
 请考虑编写适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]时：  
  
- 在目标系统是现有的、 非*Web 服务启用*系统  
  
- 在目标系统是动态的可以使用新的操作增强  
  
- 目标系统具有大量的元数据  
  
- 大型、 不同的目标系统的数据的用户数  
  
- 消费应用程序需要丰富的应用程序元数据发现功能  
  
  例如，如果目标系统包含数百个用于管理卫生保健声明的操作和操作都是动态 （这意味着用户可以添加执行其他任务的新操作），则最好公开此功能使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. 这将确保新的操作是使用适配器的应用程序可发现。 使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，必须修改服务协定，因为它是静态的。  
  
## <a name="when-to-write-a-service"></a>何时编写的服务  
 使用*WCF 服务模型*创建服务时：  
  
- 在目标系统是静态的且具有一组固定的操作  
  
- 目标系统具有很少或没有元数据  
  
- 服务开发人员都有详细的应用程序公开的了解  
  
- 公开的全新应用程序  
  
- 要创建泛型传输适配器  
  
  例如，如果目标系统包含用于管理的体育团队 20 操作，您可以公开操作作为静态协定使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。 通过此操作，避免实现不必要的元数据功能并有可能可以最大程度减少开发时间。  
  
## <a name="when-to-write-a-channel"></a>当编写一个通道  
 使用*WCF 通道模型*创建通道时：  
  
-   创建网络协议。 网络协议的示例包括 WS-ReliableMessaging 协议。  
  
-   发送/接收 WCF 消息而不是 WCF （TCP、 HTTP、 命名管道、 MSMQ 和对等通道） 中包含的传输。 例如，可以编写 UDP 传输、 TIBCO 或 Java 消息服务 (JMS) 传输。  
  
-   与不作为 Web 服务公开的系统集成。  在这种情况下你传输充当调整现有系统的消息格式或 API 允许 WCF 客户端的 WCF 消息以直接与现有系统进行通信的适配器。 此示例是 Web 服务增强 (WSE) 3.0 TCP 传输。  
  
## <a name="see-also"></a>请参阅  
 [规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [了解 LOB 系统与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)