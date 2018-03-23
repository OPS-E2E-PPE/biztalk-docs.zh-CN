---
title: 为 mySAP Business Suite 的 BizTalk 适配器的体系结构概述 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d571cdd3beea2bc9a57ec7ad15f865e7ef51e53a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite"></a>为 mySAP Business Suite 的 BizTalk 适配器的体系结构概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]实现[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定，其中包含单个自定义传输绑定元素，可实现与 SAP 系统的通信。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时，向应用程序可以通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与通过 SAP Unicode RFC SDK (librfc32u.dll) 的 64 位或 32 位版本的 SAP 系统进行通信。 

下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 ![SAP 结束&#45;到&#45;结束体系结构](../../adapters-and-accelerators/adapter-sap/media/9ba0c31f-90df-444d-8192-42743c893d51.gif "9ba0c31f-90df-444d-8192-42743c893d51")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开与 SAP 系统[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 客户端应用程序交换使用 SOAP 消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道执行操作并访问 SAP 系统上的数据。 上图显示四种方式在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可使用。  
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道使用执行 SAP 系统的操作的应用程序[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型交换 SOAP 消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关开发解决方案的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型编程，请参见[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。  
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务调用方法的模型应用程序[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端在 SAP 系统上执行操作。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的运算[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为.NET 方法。 你可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 svcutil.exe 工具来创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]从公开元数据的客户端类[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型编程和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
-   通过配置为使用带有 SAP 绑定配置的绑定中的 WCF 自定义传输类型为 BizTalk WCF 自定义适配器某一 BizTalk 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。 BizTalk WCF 自定义适配器启用之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务。 BizTalk WCF 自定义适配器支持自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通过其 WCF 自定义绑定传输类型，该对话框可以配置任何[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]作为 BizTalk WCF 自定义适配器使用的绑定公开给配置系统的绑定。 有关如何使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)。 可以通过在 SAP 绑定上设置绑定属性加载 BizTalk 分层通道绑定元素支持 BizTalk 事务。  
  
-   通过 IIS 托管的 Web 服务。 在此方案中，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务代理，承载于 IIS 中使用的标准之一[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP 绑定。  
  
-   通过[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]上运行[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并提供一个 ADO.NET 接口到 SAP 系统。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和 SAP RFC 库始终托管进程的应用程序或服务使用适配器。  
  
## <a name="sap-adapter-and-wcf"></a>SAP 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供一个基于 SOAP 消息的交换对客户端和服务之间的通道的编程模型。 这些消息将由通信的客户端和服务公开的终结点之间发送。  
  
 终结点组成*终结点地址*指定的位置从该处接收消息，*绑定*它指定用于交换消息，以及通信协议*协定*指定终结点公开的操作和数据类型。 绑定由一个或多个堆叠在一起以定义如何与终结点交换消息的绑定元素组成。  
  
 至少，绑定必须指定的传输和编码用于与终结点交换消息。 会通过组成一个或多个通道的通道堆栈终结点之间的消息交换。 每个通道是一个终结点配置的绑定中的绑定元素的具体实现。  
  
[WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，SAP 绑定 (**Microsoft.Adapters.SAP.SAPBinding**)。 默认情况下，此绑定包含单个自定义传输绑定元素，SAP 适配器绑定元素 (**Microsoft.Adapters.SAP.SAPAdapter**)，从而使 SAP 系统的操作。 使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以设置**EnableBizTalkCompatibilityMode**绑定属性加载自定义绑定元素，BizTalk 分层通道绑定元素，之上 SAP 适配器绑定元素。 BizTalk 分层通道绑定元素实现内部[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并且不公开的外部 SAP 绑定。  
  
 **Microsoft.Adapters.SAP.SAPBinding** （SAP 绑定） 和**Microsoft.Adapters.SAP.SAPAdapter** （SAP 适配器绑定元素） 为公共类，并还公开给配置系统。 由于 SAP 适配器绑定元素公开时公开，你可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定支持的扩展的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 例如，可以实现一个自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型编程解决方案，用于聚合数据库操作到单个多功能操作，或执行架构由自定义应用程序实现的操作和 SAP 系统上的操作之间进行转换。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和上运行[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供的软件框架和工具可供基础结构，它[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]利用为了给用户和适配器客户端提供一组丰富的功能。  

## <a name="sap-adapter-and-the-wcf-lob-adapter-sdk"></a>SAP 适配器和 WCF LOB 适配器 SDK
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]实现利用提供的功能的核心组件的一组[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和提供连接到 SAP 系统通过 SAP Unicode RFC SDK 库 (librfc32u.dll)。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]用作通过其软件层[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接口与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]，和 RFC SDK 用作通过其层[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 SAP 系统的接口。 下图显示的内部组件之间的关系[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以及这些组件和 RFC SDK 之间。  
  
 ![内部适配器组件的关系](../../adapters-and-accelerators/adapter-sap/media/10f97b95-4e82-4592-ba07-0f58478305c2.gif "10f97b95-4e82-4592-ba07-0f58478305c2")  
  
## <a name="connection-to-the-sap-system"></a>连接到 SAP 系统  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 SAP 系统通过 SAP Unicode RFC SDK 库 (librfc32u.dll) 连接。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 32 位和 64 位版本的 SAP RFC SDK。 SAP RFC SDK 启用外部程序来调用 ABAP 函数上的 SAP 系统。  
  
 通过提供一个连接 URI 建立到 SAP 系统连接到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下类型的到 SAP 系统的连接：  
  
-   应用程序基于主机的连接 (A)，在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]直接连接到 SAP 应用程序服务器。  
  
-   负载平衡连接 (B)，在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP 消息服务器。  
  
-   基于目标的连接 (D) 到 SAP 系统的连接由 saprfc.ini 配置文件中的目标。 A、 B 和 R 支持类型连接。  
  
-   在其中适配器接收 Rfc、 tRFC 和通过 SAP 系统指定的侦听器主机、 侦听器网关服务和侦听器程序 ID，在连接 URI 中直接或通过基于 R 的上一个 RFC 目标的 Idoc 侦听器连接 (R)saprfc.ini 配置文件中的目标。  
  
 Saprfc.ini 文件有关的详细信息，请参阅"SAPRFC。INI 文件"中的[SAP 文档](https://help.sap.com/doc/PRODUCTION/saphelp_nwpi711/7.1.1/en-US/48/c4168eca64581de10000000a42189c/frameset.htm)。  
  
 有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP 系统，请参阅[创建与 SAP 系统的连接](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)