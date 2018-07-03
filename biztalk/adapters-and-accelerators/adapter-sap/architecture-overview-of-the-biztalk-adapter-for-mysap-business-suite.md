---
title: 用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture of SAP adapter
- adapters, architecture
ms.assetid: 1b45edb0-2476-427b-b6cd-41e38ed815e0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6e05cde05819edf1bbe1525d87797bf1131f1d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006046"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite"></a>用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]实现[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定，其中包含用于实现与 SAP 系统的通信的单个自定义传输绑定元素。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时和公开给应用程序可以通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 64 位或 32 位版本的 SAP Unicode RFC SDK (librfc32u.dll) 通过 SAP 系统进行通信。 

下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 ![SAP 端&#45;到&#45;结束体系结构](../../adapters-and-accelerators/adapter-sap/media/9ba0c31f-90df-444d-8192-42743c893d51.gif "9ba0c31f-90df-444d-8192-42743c893d51")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开 SAP 系统作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 客户端应用程序交换的 SOAP 消息具有[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道来执行操作并访问 SAP 系统上的数据。 上图中显示四种方法在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以使用。  
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道使用执行 SAP 系统的操作的应用程序[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型来交换 SOAP 消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关开发解决方案的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型编程，请参见[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。  
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务调用方法的模型应用程序[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端 SAP 系统上执行操作。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为.NET 方法。 可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 svcutil.exe 工具来创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开的元数据中的客户端类[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型编程并[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
- 通过配置为使用包含 SAP 绑定配置的绑定中的 WCF 自定义传输类型为 BizTalk WCF 自定义适配器的 BizTalk 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。 BizTalk WCF 自定义适配器实现之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序和一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务。 BizTalk WCF 自定义适配器支持自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通过 WCF 自定义绑定传输类型，这样就可以配置任何[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]向配置系统公开为使用 BizTalk WCF 自定义适配器的绑定的绑定。 有关如何使用详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)。 可以通过在 SAP 绑定上设置绑定属性加载 BizTalk 分层通道绑定元素支持 BizTalk 事务。  
  
- 通过 IIS 托管的 Web 服务。 在此方案中，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]承载于 IIS 中使用的一个标准的服务代理[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP 绑定。  
  
- 通过[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]上运行[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，并提供到 SAP 系统的 ADO.NET 接口。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和 SAP RFC 库始终托管进程的应用程序或使用适配器服务。  
  
## <a name="sap-adapter-and-wcf"></a>SAP 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 显示基于客户端和服务之间的通道的 SOAP 消息交换的编程模型。 终结点公开的通信的客户端和服务之间发送这些消息。  
  
 终结点组成*终结点地址*用于指定从该处接收消息，该位置*绑定*它指定用于交换消息，以及的通信协议*协定*指定终结点公开的操作和数据类型。 一个绑定包含一个或多个绑定元素堆叠在一起以定义如何与终结点交换消息。  
  
 至少，绑定必须指定的传输和编码用于与终结点交换消息。 终结点之间的消息交换的分组成一个或多个通道的通道堆栈。 每个通道是绑定的终结点配置中的绑定元素之一的具体实现。  
  
[WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，SAP 绑定 (**Microsoft.Adapters.SAP.SAPBinding**)。 默认情况下，此绑定包含一个单一的自定义传输绑定元素，SAP 适配器的绑定元素 (**Microsoft.Adapters.SAP.SAPAdapter**)，使 SAP 系统的操作。 使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以设置**EnableBizTalkCompatibilityMode**绑定要加载自定义绑定元素，BizTalk 分层通道绑定元素，基于 SAP 适配器绑定属性元素。 BizTalk 分层通道绑定元素在内部实现[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并不外部 SAP 绑定公开。  
  
 **Microsoft.Adapters.SAP.SAPBinding** （SAP 绑定） 和**Microsoft.Adapters.SAP.SAPAdapter** （SAP 适配器绑定元素） 为公共类，并向配置系统还公开。 因为 SAP 适配器绑定元素公开时公开，您可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定的扩展功能的支持[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 例如，可以实现自定义绑定以支持企业单一登录 (SSO) 中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型编程解决方案，用于聚合数据库操作到单个多功能操作，或执行架构由自定义应用程序实现的操作和 SAP 系统的操作之间的转换。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]构建的[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上运行和[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个软件框架和工具基础结构的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]利用为了给用户和适配器客户端提供一套丰富的功能。  

## <a name="sap-adapter-and-the-wcf-lob-adapter-sdk"></a>SAP 适配器和 WCF LOB 适配器 SDK
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]实现了一组利用提供的功能的核心组件[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和提供连接到 SAP 系统中通过 SAP Unicode RFC SDK 库 (librfc32u.dll)。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]充当通过它的软件层[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]，并通过其层作为 RFC SDK[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 SAP 系统的接口。 下图显示了的内部组件之间的关系[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]之间以及这些组件和 RFC SDK。  
  
 ![内部适配器组件的关系](../../adapters-and-accelerators/adapter-sap/media/10f97b95-4e82-4592-ba07-0f58478305c2.gif "10f97b95-4e82-4592-ba07-0f58478305c2")  
  
## <a name="connection-to-the-sap-system"></a>连接到 SAP 系统  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 SAP 系统中通过 SAP Unicode RFC SDK 库 (librfc32u.dll) 连接。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 32 位和 64 位版本的 SAP RFC SDK。 SAP RFC SDK，外部程序可以调用 ABAP 函数上的 SAP 系统。  
  
 通过提供一个连接 URI 建立到 SAP 系统连接到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下类型的连接到 SAP 系统：  
  
- 应用程序 – 基于主机的连接 (A)，在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]直接连接到 SAP 应用程序服务器。  
  
- 负载平衡连接 (B)，在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP 消息服务器。  
  
- 基于目标的连接 (D) 与 SAP 系统的连接由 saprfc.ini 配置文件中的目标。 A、 B 和 R 支持类型连接。  
  
- 在其中适配器接收 Rfc、 tRFC 和通过指定的侦听器主机、 侦听器网关服务和侦听器程序 ID，直接在连接 URI 或基于 R 的 SAP 系统上的 RFC 目标的 Idoc 侦听器连接 (R)saprfc.ini 配置文件中的目标。  
  
  Saprfc.ini 文件有关的详细信息，请参阅"SAPRFC。INI 文件"中的[SAP 文档](https://help.sap.com/doc/PRODUCTION/saphelp_nwpi711/7.1.1/en-US/48/c4168eca64581de10000000a42189c/frameset.htm)。  
  
  详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP 系统，请参阅[创建连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。  
  
## <a name="see-also"></a>请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)