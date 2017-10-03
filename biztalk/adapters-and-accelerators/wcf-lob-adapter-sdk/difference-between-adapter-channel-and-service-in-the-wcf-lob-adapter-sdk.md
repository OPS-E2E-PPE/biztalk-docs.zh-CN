---
title: "在 WCF LOB 适配器 SDK 适配器通道和服务之间的差异 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e377568887d3d626e288fc47f82714b189d44b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a>在 WCF LOB 适配器 SDK 适配器通道和服务之间的差异
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]每提供一组可用于公开到消费应用程序在同一台计算机或网络中的应用程序功能的 Api。 若要选择最合适的框架，你必须考虑的目标系统应用程序公开的功能的业务要求以及要公开的属性。 本主题提供了可用于选择合适的框架的准则。  
  
## <a name="when-to-write-an-adapter"></a>何时编写一个适配器  
 请考虑编写适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]时：  
  
-   目标系统是现有的、 非*Web 服务启用*系统  
  
-   目标系统是动态的并且可以使用新操作增强  
  
-   目标系统具有大量的元数据  
  
-   没有大规模、 多样化的目标系统的数据的用户数  
  
-   消费应用程序需要丰富的应用程序元数据发现功能  
  
 例如，如果目标系统包含数百个用于管理卫生保健声明的操作和操作是动态 （这意味着用户可以添加执行其他任务的新操作），其意义公开此功能使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. 这将确保新的操作可使用该适配器的应用程序发现。 与[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，必须修改服务协定，因为它是静态。  
  
## <a name="when-to-write-a-service"></a>何时开始编写服务  
 使用*WCF 服务模型*创建服务时：  
  
-   目标系统是静态的具有一组固定的操作  
  
-   目标系统具有很少或没有元数据  
  
-   服务开发人员的详细知识要公开的应用程序  
  
-   公开一个全新的应用程序  
  
-   要创建泛型传输适配器  
  
 例如，如果目标系统包含用于管理运动队 20 操作，你可以公开为静态协定使用的操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。 通过这样做，避免实现不必要的元数据功能，并可能可以最大程度减少开发时间。  
  
## <a name="when-to-write-a-channel"></a>当编写一个通道  
 使用*WCF 通道模型*创建的通道时：  
  
-   创建一个网络协议。 网络协议的示例包括 Ws-reliablemessaging 协议。  
  
-   发送/接收 WCF 消息传输而不是包含在 WCF （TCP、 HTTP、 命名管道、 MSMQ 和对等通道）。 例如，你可以编写 UDP 传输、 TIBCO 或 Java 消息服务 (JMS) 传输。  
  
-   与不作为 Web 服务公开的系统的集成。  在这种情况下，您的传输充当调整到现有系统的消息格式或 API 允许 WCF 客户端的 WCF 消息进行对话直接对现有系统的适配器。 此示例是 Web 服务增强功能 (WSE) 3.0 TCP 传输。  
  
## <a name="see-also"></a>另请参阅  
 [规划和设计使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [了解 LOB 系统与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)