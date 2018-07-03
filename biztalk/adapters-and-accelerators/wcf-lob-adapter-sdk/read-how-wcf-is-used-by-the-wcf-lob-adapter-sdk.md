---
title: 读取 WCF 如何使用 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 183dd134-7273-4767-bad0-c42ae125985e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8991590d97d70fc0e2090f11f05f8882b0ca3396
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004710"
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a>读取 WCF 如何使用 WCF LOB 适配器 SDK
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构，并依赖于[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]运行时用于提供公开适配器功能和交换信息所需的基本消息传递服务。 
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个框架编写适配器，公开这些中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，并借助这些常见的适配器元素，如元数据和连接池。 它还包含支持工具，如增强的体验[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]的.NET 应用程序和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]有关[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序和[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]。  
  
 它负责[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开到广泛的使用方应用程序，管理不同的终结点之间的消息流并提供一个 SDK 和工具要自定义，服务配置和监视消息流。 例如，开发人员可以自定义的行为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过扩展其通道使用自定义消息处理程序。  
  
 之间的关系[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]以下高级体系结构图所示。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]构建的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]作为的扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型。 它提供特定于域和简化的对象模型和工具集用于为自定义构建适配器[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定。  
  
 下图显示了使用给定的适配器绑定的出站消息交换。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 下图显示了使用给定的适配器绑定的入站的消息交换。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型，请参见[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a>WCF 服务和 WCF LOB 适配器 SDK  
 当开发典型[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，第一步是创建共享与外部世界，介绍如何与服务通信的服务协定。 此协定实质上是指定的集合和访问服务提供的操作所需的消息的结构。  
  
 此协定公开为服务，一旦[服务模型 Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)可用于创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端来使用它。 约定提供了一组静态的操作和消息不得更改的信息。 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9afd-d32970f5ba0a")  
  
 适配器与此相反，使用构建[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一组动态的有关的操作和业务线系统中可用的数据集合的元数据。 业务线系统通常具有一个协定中描述的操作过多，可能有新操作添加到响应新出现的业务需求。  
  
 例如，业务线系统可能会提供帐户管理操作。 识别需要优化的新客户帐户创建后, 公司更新业务线系统，以包括新的操作。 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开它向客户端提供的元数据中此操作。  
  
 在设计时[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-基于的适配器生成协定动态以满足业务线系统的需求。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 ASDK 提供[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]供适配器使用者在设计时生成动态协定的工具。  
  
 在运行时，将消息排入编写使用适配器时[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，适配器通常必须对其执行的一系列操作接收消息。 这些操作包括：  
  
- 查找与消息相关的元数据  
  
- 打开邮件  
  
- 解释该消息  
  
- 业务线系统中调用适当的函数  
  
  情况下[!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)]服务，消息只需通过而无需通过元数据解析。  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库和 WCF LOB 适配器 SDK 的 BizTalk 适配器](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)