---
title: 使用 ESB 管理门户管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c44951b4284e0d17b2d8e69011cedfa213c219
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967758"
---
# <a name="administration-using-the-esb-management-portal"></a>使用 ESB 管理门户管理
ESB 管理门户中，作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，是演示如何使用指标和存在的可能性用于扩展 BizTalk ESB 工具包的示例站点。 该门户提供了可以从其生成自己的自定义的门户的起始点。  
  
 ESB 管理门户也是一个高性能且有用的工具，可帮助最大程度地使用和效率的 ESB 异常管理系统。 此外，该门户提供了一个用户界面为基础的通用描述、 发现和集成 (UDDI) 注册表服务器和审核等功能的图形配置功能查看历史记录信息，配置警报和通知，并允许用户以订阅警报，可指示 ESB 应用程序中发生的错误。  
  
 本部分介绍可以使用 ESB 管理门户中，其中包括完成操作的常见任务：  
  
-   [使用异常和故障消息](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [配置警报、通知和订阅](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [查看和管理审核和历史记录](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [使用图表和报表分析故障趋势](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [查看和发布 UDDI 注册](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  ESB 管理门户的各个功能的详细说明，请参阅[ESB 管理门户功能参考](../esb-toolkit/esb-management-portal-feature-reference.md)。  
  
## <a name="esb-portal-technologies"></a>ESB 门户技术  
 ESB 管理门户利用以下技术：  
  
- [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
- ASP.NET
  
- [Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。 ESB 管理门户使用以下 Enterprise Library 程序集：  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
  -   Microsoft.Practices.Unity  
  
- [Microsoft 图表控件](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) Microsoft.NET framework 4  
  
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]指标跟踪仅扩展到异常管理系统的错误跟踪。