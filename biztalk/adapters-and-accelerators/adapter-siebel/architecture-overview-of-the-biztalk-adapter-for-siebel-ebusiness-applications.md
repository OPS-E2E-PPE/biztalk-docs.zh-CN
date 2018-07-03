---
title: 用于 Siebel eBusiness 应用程序的 BizTalk 适配器的体系结构概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture of Siebel adapter
- Siebel COM Data Control
- adapters, architecture
ms.assetid: b048937f-207b-4c64-8837-7bfeecedfa03
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b77d1da9261ae4a532e8b56be0f4172350f800e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981438"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>用于 Siebel eBusiness 应用程序的 BizTalk 适配器的体系结构概述
描述使用的端到端解决方案的体系结构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]若要在 Siebel 系统，以及的内部体系结构上运行[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
 了解[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]体系结构可帮助你：  
  
- 了解之间的关系[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。  
  
- 了解安全边界，以便可以在解决方案中来提高数据安全性。  
  
- 了解[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定属性。  
  
- 解决安装问题。  

## <a name="adapter-architecture-overview"></a>适配器体系结构概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]构建的[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上运行和[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时间。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个软件框架和工具基础结构的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]采用为了给用户和适配器客户端提供一套丰富的功能。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。 此绑定包含可实现与 Siebel 系统的通信的单个自定义传输绑定元素。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]由包装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时和公开给应用程序可以通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。  
  
## <a name="siebel-com-data-control"></a>Siebel COM 数据控件  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与通过 Siebel COM 数据控件库 (sstchca.dll) 和 Microsoft.Adapters.Siebel.SiebelBusinessObjectInterface.dll 库 Siebel 系统连接。 Siebel COM 数据控件是 Siebel Web 客户端的组件。 
  
 Siebel COM 数据控件接口启用外部客户端，如[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接并与 Siebel 应用程序对象管理器通信 Siebel Enterprise Server 上。 Siebel 对象管理器和 Siebel Enterprise Server，以及其他连接参数中指定[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接 URI。 有关连接 URI 的详细信息，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  
  
 下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
 ![Siebel 端&#45;到&#45;结束体系结构](../../adapters-and-accelerators/adapter-siebel/media/1ae1955e-b7d7-44a0-80c1-1e835edab356.gif "1ae1955e-b7d7-44a0-80c1-1e835edab356")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开为 Siebel 系统[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行的操作和访问 Siebel 系统上的数据，客户端应用程序交换的 SOAP 消息具有[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图中显示四种方法在其中[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以使用。  
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序使用执行 Siebel 系统的操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型来交换 SOAP 消息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 有关开发解决方案的详细信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型，请参见[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端执行 Siebel 系统的操作。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]作为.NET 方法。 可以使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 来创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开的元数据中的客户端类[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。  
  
- 通过 BizTalk 接收位置或发送端口配置为使用 Microsoft BizTalk Wcf-custom 适配器。 WCF 自定义适配器，使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]可扩展性功能。 通过使用 WCF 自定义适配器可以选择并配置 Siebel 绑定和行为的接收位置或发送端口。 BizTalk 分层通道绑定元素，它可以通过在 Siebel 绑定上设置绑定属性加载支持 BizTalk 事务。 有关如何使用详细信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)。
  
- 通过 IIS 托管的 Web 服务。 在此方案中，使用标准的 WCF Http 绑定的 IIS 中承载 WCF 服务代理使用该适配器生成的。 这会为 Web 服务向外部用户公开的服务协定。 IIS 自动承载在运行时，这反过来与 Siebel 系统进行通信的适配器。  
  
  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和 Siebel COM 数据控件库始终是在进程内承载的应用程序或使用适配器服务。  
  
## <a name="siebel-adapter-and-wcf"></a>Siebel 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 显示基于客户端和服务之间的通道的 SOAP 消息交换的编程模型。 终结点公开的通信的客户端和服务之间发送这些消息。 终结点包括：  
  
- *终结点地址*，它指定接收消息的位置。  
  
- 一个*绑定*，它指定用于交换消息的通信协议。  
  
- 一个*协定*，它指定终结点公开的操作和数据类型。  
  
  一个绑定包含一个或多个绑定元素堆叠在一起以定义如何与终结点交换消息。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 终结点之间的消息交换的分组成一个或多个通道的通道堆栈。 每个通道是一个终结点配置的绑定中的绑定元素的具体实现。 [WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
  [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]Siebel 绑定的自定义绑定 (**Microsoft.Adapters.Siebel.SiebelBinding**)。 默认情况下，此绑定包含一个单一的自定义传输绑定元素，Siebel 适配器的绑定元素 (**Microsoft.Adapters.Siebel.SiebelAdapter**)，这样 Siebel 系统的操作。 使用时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以设置**EnableBizTalkCompatibilityMode**绑定要加载自定义绑定元素属性，BizTalk 分层通道绑定元素 — 在 Siebel 适配器之上绑定元素。 BizTalk 分层通道绑定元素在内部实现[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，并且不公开外部 Siebel 绑定。  
  
  **Microsoft.Adapters.Siebel.SiebelBinding** （Siebel 绑定） 和**Microsoft.Adapters.Siebel.SiebelAdapter** （Siebel 适配器绑定元素） 为公共类，并还公开到配置系统。 Siebel 适配器绑定元素公开时公开，因为您可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定的扩展功能的支持[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 例如，可以实现自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型编程。 执行此操作的原因是为：  
  
- 聚合到单个多功能操作的数据库操作。  
  
- 执行架构由自定义应用程序实现的操作和 Siebel 系统的操作之间的转换。  

## <a name="siebel-adapter-and-wcf-lob-adapter-sdk"></a>Siebel 适配器和 WCF LOB 适配器 SDK

[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]实现了一组核心组件的：  
  
- 利用提供的功能[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。  
  
- 可以连接到 Siebel 系统通过 Siebel COM 数据控件库 (sstchca.dll)。  
  
  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]属于软件层，通过该[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 WCF; 接口Siebel COM 数据控件是通过其层[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Siebel 系统的接口。 下图显示了的内部组件之间的关系[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]之间以及这些组件和 Siebel COM 数据控件。  
  
  ![Siebel 适配器内部体系结构](../../adapters-and-accelerators/adapter-siebel/media/e4accea7-86b2-4f2a-937a-edff7e1100ec.gif "e4accea7-86b2-4f2a-937a-edff7e1100ec")
   
## <a name="see-also"></a>请参阅  
 [保护 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
 [了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)