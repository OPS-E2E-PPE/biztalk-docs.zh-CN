---
title: "开发在 BizTalk Server 应用程序 Siebel |Microsoft 文档"
description: "创建 Siebel 应用程序使用 WCF，或在 BizTalk Server 中使用 BizTalk 适配器包 (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bc04906-6d64-433c-b357-797ec5883279
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1535a3aa7861effdad998d4d997fbcdfced02c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-siebel-applications"></a>开发 Siebel 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 客户端应用程序可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]来调用 Siebel 项目上的操作。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可使用：  
  
-   通过 BizTalk Server 解决方案中的物理端口绑定。  
  
-   通过调用客户端代理的一个实例上的方法。  
  
-   作为承载的 WCF 服务。  
  
-   通过使用 WCF 通道模型的代码中的通道实例发送 SOAP 消息。  
  
-   通过 ADO.NET 接口。  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk vs WCF 服务与 WCF 通道 vs ADO.NET
 下表中：  
  
-   列出可以对 Siebel 系统使用执行的不同运算[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
-   指示哪方法 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型、 WCF 通道模型或 ADO.NET 接口) 可以用于执行操作。  
  
-   提供有关执行任务使用选的方法的详细信息的链接。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|ADO.NET 接口|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|在业务组件的基本插入、 更新、 删除和查询操作|[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)|[使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)|[使用 Siebel 适配器使用 WCF 通道模型运行业务组件上的操作](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)|[在带有 Siebel 业务组件上运行 SELECT 查询](run-a-select-query-on-business-components-with-siebel.md)**注意：**只能执行选择操作使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。|  
|对具有 MVG 字段的业务组件的操作|[使用 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)|[在上运行操作的业务组件与 MVG 字段与使用 WCF 服务模型和 Siebel 适配器](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)|||  
|对与选择列表字段的业务组件的操作|[使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)||||  
|调用业务服务|[调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)|||[使用 Siebel 运行业务服务上的执行操作](run-an-execute-operation-on-business-services-with-siebel.md)|  
|调用具有集成对象的业务服务|[调用具有集成对象使用 Siebel 适配器的业务服务方法](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)||||  

## <a name="next-steps"></a>后续步骤  
 本部分中的主题提供信息、 过程和示例来帮助你开发的应用程序使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]解决方案编程。 

- [创建与 Siebel 系统的连接](create-a-connection-to-the-siebel-system.md)
- [获取 Visual Studio 中的 Siebel 操作的元数据](get-metadata-for-siebel-operations-in-visual-studio.md)
- [元数据节点 Id](metadata-node-ids1.md)
- [使用绑定属性](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [开发使用 Siebel 适配器的 BizTalk 应用程序](develop-biztalk-applications-using-the-siebel-adapter.md)
- [使用 WCF 服务模型开发应用程序](develop-siebel-applications-using-the-wcf-service-model.md)
- [使用 WCF 通道模型开发应用程序](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [.NET Framework 数据提供程序用于 Siebel eBusiness Applications](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [使用带有 SharePoint Siebel 适配器](use-the-siebel-adapter-with-sharepoint.md)
- [示例](samples-for-the-siebel-adapter.md)
- [使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)