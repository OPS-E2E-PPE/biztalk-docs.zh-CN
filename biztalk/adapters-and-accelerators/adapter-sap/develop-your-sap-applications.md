---
title: 开发 SAP 应用程序在 BizTalk 中使用的适配器 |Microsoft Docs
description: 创建 SAP 应用程序使用 WCF、 BizTalk Server 或 ADO.NET 与 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 855f794e7fa0cbffaf7a99a2b113aac5a0bbda31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373498"
---
# <a name="develop-your-sap-applications"></a>开发 SAP 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 客户端应用程序可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用 SAP 项目上的操作。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可使用：  
  
- 通过中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 通过调用客户端代理的实例上的方法。  
  
- 为托管 WCF 服务。  
  
- 通过在使用 WCF 通道模型的代码中某个通道实例发送 SOAP 消息。  
  
- 通过 ADO.NET 接口。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk 与 WCF 服务与 WCF 通道 vs ADO.NET
  
 下表中：  
  
- 列出了可以对 SAP 系统使用的不同操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 指示该方法 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型、 WCF 通道模型或 ADO.NET 接口) 可用于执行操作。  
  
- 提供指向有关执行该任务使用所选的方法的详细信息。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|ADO.NET 接口|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|SAP 系统中调用 Rfc|[调用中使用 BizTalk Server 的 SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[调用中使用 WCF 服务模型的 SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[调用上使用 WCF 通道模型的 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[调用 Rfc 和 Bapi 在 SAP 中使用 EXEC 命令](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|接收来自 SAP 系统的入站的 RFC 调用|[接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[在使用 WCF 服务模型的 SAP 中收到的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统从接收的入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP 系统中调用 Trfc|[调用 Trfc SAP 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[调用 Trfc 在 SAP 中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[调用上使用 WCF 通道模型的 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|接收来自入站的 tRFC 调用|[接收来自 SAP 使用 BizTalk Server 的入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[在使用 WCF 服务模型的 SAP 中收到入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 SAP 系统从接收的入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP 系统上执行事务|[在 SAP 中使用 BizTalk Server 运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[调用中使用 WCF 服务模型的 SAP Bapi](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[调用上使用 WCF 通道模型的 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|将 IDOC 发送到 SAP 系统|[向使用 BizTalk Server 的 SAP 发送 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[向使用 WCF 服务模型的 SAP 发送 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[调用上使用 WCF 通道模型的 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|从 SAP 系统接收 IDOC|[接收来自使用 BizTalk Server 的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[使用 WCF 通道模型的 SAP 系统从接收的入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>后续步骤

 下一步的主题提供有关过程和示例，以开发应用程序使用的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在这种[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]编程解决方案。 

- [创建指向 SAP 系统的连接](create-a-connection-to-the-sap-system.md)
- [在 Visual Studio 中获取 SAP 操作的元数据](get-metadata-for-sap-operations-in-visual-studio.md)
- [使用绑定属性](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [流式处理和 SAP 适配器](streaming-and-the-sap-adapter.md)
- [使用 SAP 适配器开发 BizTalk 应用程序](develop-biztalk-applications-using-the-sap-adapter.md)
- [使用 WCF 服务模型开发应用程序](develop-sap-applications-using-the-wcf-service-model.md)
- [使用 WCF 通道模型开发应用程序](develop-sap-applications-using-the-wcf-channel-model.md)
- [以编程方式获取元数据](get-metadata-programmatically-from-sap.md)
- [使用用于 mySAP.NET Framework 数据提供程序](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [使用包含 SharePoint 的 SAP 适配器](use-the-sap-adapter-with-sharepoint.md)
- [示例](samples-for-the-sap-adapter.md)
- [使用 svcutil.exe](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>请参阅  
 [创建 SAP 系统连接 URI](create-the-sap-system-connection-uri.md)