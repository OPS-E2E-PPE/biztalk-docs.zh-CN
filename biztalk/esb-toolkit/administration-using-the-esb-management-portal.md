---
title: 使用 ESB 管理门户管理 |Microsoft 文档
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
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290269"
---
# <a name="administration-using-the-esb-management-portal"></a>使用 ESB 管理门户管理
ESB 管理门户中，作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，是演示如何使用度量值和存在可能的匹配项用于扩展 BizTalk ESB 工具包的示例站点。 门户提供了可以从中生成自定义门户网站的起点。  
  
 ESB 管理门户也是一个高度支持且有用的工具，可以有助于最大程度地使用和 ESB 异常管理系统的效率。 此外，该门户提供的用户界面实现的基础的通用、 描述、 发现和集成 (UDDI) 注册表服务器和审核，等功能的图形配置功能查看历史记录信息，配置警报和通知，并允许用户订阅指明 ESB 应用程序中发生的错误的警报。  
  
 本部分介绍你可以使用 ESB 管理门户中，其中包括达到目的的常见任务：  
  
-   [使用异常和错误消息](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [配置警报、 通知和订阅](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [查看和管理审核和历史记录](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [使用图表和报表的分析错误趋势](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [查看和发布 UDDI 注册](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  ESB 管理门户的各个功能的详细说明，请参阅[ESB 管理门户功能参考](../esb-toolkit/esb-management-portal-feature-reference.md)。  
  
## <a name="esb-portal-technologies"></a>ESB 门户技术  
 ESB 管理门户利用以下技术：  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   ASP.NET
  
-   [Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。 ESB 管理门户使用以下企业库程序集：  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
    -   Microsoft.Practices.Unity  
  
-   [Microsoft 图表控制](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) 的 Microsoft.NET Framework 4  
  
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]指标跟踪仅扩展到异常管理系统的错误跟踪。