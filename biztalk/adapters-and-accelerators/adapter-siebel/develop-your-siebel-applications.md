---
title: 开发 Siebel 应用程序在 BizTalk Server |Microsoft Docs
description: 创建使用 WCF 的 Siebel 应用程序或 BizTalk Server 使用 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bc04906-6d64-433c-b357-797ec5883279
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d65dd25f3b2bbcc90acda9fcdc5cb0eb3b2f5c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002422"
---
# <a name="develop-your-siebel-applications"></a>开发 Siebel 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 客户端应用程序可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]调用 Siebel 项目上的操作。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可使用：  
  
-   通过 BizTalk Server 解决方案中的一个物理端口绑定。  
  
-   通过调用客户端代理的实例上的方法。  
  
-   为托管 WCF 服务。  
  
-   通过在使用 WCF 通道模型的代码中某个通道实例发送 SOAP 消息。  
  
-   通过 ADO.NET 接口。  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk 与 WCF 服务与 WCF 通道 vs ADO.NET
 下表中：  
  
- 列出了可以执行在 Siebel 系统使用的不同操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
- 指示该方法 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型、 WCF 通道模型或 ADO.NET 接口) 可用于执行操作。  
  
- 提供指向有关执行该任务使用所选的方法的详细信息。  
  
|                                   任务                                    |                                                                                       BizTalk Server                                                                                        |                                                                                    WCF 服务模型                                                                                    |                                                                              WCF 通道模型                                                                               |                                                                                                                        ADO.NET 接口                                                                                                                        |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 在业务组件上的基本的 Insert、 Update、 Delete 和查询操作 |              [运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)              |     [使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)     | [使用 Siebel 适配器使用 WCF 通道模型运行业务组件上的操作](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md) | [使用 Siebel 业务组件上运行 SELECT 查询](run-a-select-query-on-business-components-with-siebel.md)**注意：** 只能执行选择操作使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。 |
|             在包含 MVG 字段与在业务组件上的操作             |   [在包含 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)    | [使用 Siebel 适配器使用 WCF 服务模型运行在包含 MVG 字段的业务组件上的操作](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md) |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |
|          与选择列表字段的业务组件上的操作           | [使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md) |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |
|                        调用业务服务                         |                [调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)                |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                    [运行与 Siebel 业务服务上的执行操作](run-an-execute-operation-on-business-services-with-siebel.md)                                                                    |
|            通过集成对象调用业务服务            |           [调用业务服务方法，通过集成对象使用 Siebel 适配器](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)            |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |

## <a name="next-steps"></a>后续步骤  
 在本部分中的主题提供信息、 步骤和示例，以帮助您开发使用的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在这种[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]编程解决方案。 

- [创建与 Siebel 系统的连接](create-a-connection-to-the-siebel-system.md)
- [在 Visual Studio 中获取 Siebel 操作的元数据](get-metadata-for-siebel-operations-in-visual-studio.md)
- [元数据节点 ID](metadata-node-ids1.md)
- [使用绑定属性](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [使用 Siebel 适配器开发 BizTalk 应用程序](develop-biztalk-applications-using-the-siebel-adapter.md)
- [使用 WCF 服务模型开发应用程序](develop-siebel-applications-using-the-wcf-service-model.md)
- [使用 WCF 通道模型开发应用程序](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [使用 Siebel 适配器和 SharePoint](use-the-siebel-adapter-with-sharepoint.md)
- [示例](samples-for-the-siebel-adapter.md)
- [使用 ServiceModel 元数据实用工具和用于 Siebel eBusiness 应用程序的 BizTalk 适配器](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)