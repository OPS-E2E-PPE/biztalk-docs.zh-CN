---
title: "开发使用中 BizTalk 适配器的 SAP 应用程序 |Microsoft 文档"
description: "创建我的 SAP 应用程序使用 WCF、 BizTalk Server 中或 ADO.NET 与 BizTalk 适配器包 (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e8501249c460285f6f8dd429f8990d39e810e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-sap-applications"></a>开发您的 SAP 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 客户端应用程序可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]来调用上的 SAP 项目的操作。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可使用：  
  
-   通过中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   通过调用客户端代理的一个实例上的方法。  
  
-   作为承载的 WCF 服务。  
  
-   通过使用 WCF 通道模型的代码中的通道实例发送 SOAP 消息。  
  
-   通过 ADO.NET 接口。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk vs WCF 服务与 WCF 通道 vs ADO.NET
  
 下表中：  
  
-   列出可以对 SAP 系统使用执行的不同运算[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   指示哪方法 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型、 WCF 通道模型或 ADO.NET 接口) 可以用于执行操作。  
  
-   提供有关执行任务使用选的方法的详细信息的链接。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|ADO.NET 接口|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|调用中某个 SAP 系统的 Rfc|[调用中使用 BizTalk Server SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[调用中使用 WCF 服务模型的 SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统上调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[调用 Rfc 和 BAPIs 在 SAP 中使用 EXEC 命令](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|从 SAP 系统接收 RFC 的入站的调用|[接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[使用 WCF 服务模型的 SAP 中收到入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统从接收入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP 系统中调用 tRFCs|[调用 tRFCs SAP 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[调用 tRFCs SAP 使用 WCF 服务模型中](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统上调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|接收来自的入站的 tRFC 调用|[从 SAP 使用 BizTalk Server 接收入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统从接收入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP 系统上执行事务|[SAP 使用 BizTalk Server 中运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[调用 BAPIs SAP 使用 WCF 服务模型中](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统上调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|将 IDOC 发送到 SAP 系统|[将 Idoc 发送到 SAP 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[将 Idoc 发送到 SAP 使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统上调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|从 SAP 系统接收 IDOC|[从 SAP 使用 BizTalk Server 接收到的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[使用 WCF 通道模型的 SAP 系统从接收入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>后续步骤

 下一步的主题提供有关过程和示例来开发应用程序使用信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]解决方案编程。 

- [创建与 SAP 系统的连接](create-a-connection-to-the-sap-system.md)
- [获取 Visual Studio 中的 SAP 操作的元数据](get-metadata-for-sap-operations-in-visual-studio.md)
- [使用绑定属性](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [流式处理和 SAP 适配器](streaming-and-the-sap-adapter.md)
- [开发使用 SAP 适配器的 BizTalk 应用程序](develop-biztalk-applications-using-the-sap-adapter.md)
- [使用 WCF 服务模型开发应用程序](develop-sap-applications-using-the-wcf-service-model.md)
- [使用 WCF 通道模型开发应用程序](develop-sap-applications-using-the-wcf-channel-model.md)
- [以编程方式获取元数据](get-metadata-programmatically-from-sap.md)
- [.NET Framework 数据提供程序用于 mySAP](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [使用带有 SharePoint SAP 适配器](use-the-sap-adapter-with-sharepoint.md)
- [示例](samples-for-the-sap-adapter.md)
- [使用 svcutil.exe](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>另请参阅  
 [创建 SAP 系统连接 URI](create-the-sap-system-connection-uri.md)