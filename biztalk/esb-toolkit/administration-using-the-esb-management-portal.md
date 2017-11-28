---
title: "使用 ESB 管理门户管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="administration-using-the-esb-management-portal"></a><span data-ttu-id="86755-102">使用 ESB 管理门户管理</span><span class="sxs-lookup"><span data-stu-id="86755-102">Administration Using the ESB Management Portal</span></span>
<span data-ttu-id="86755-103">ESB 管理门户中，作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，是演示如何使用度量值和存在可能的匹配项用于扩展 BizTalk ESB 工具包的示例站点。</span><span class="sxs-lookup"><span data-stu-id="86755-103">The ESB Management Portal, included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], is a sample site that demonstrates the use of metrics and the possibilities that exist for extending the BizTalk ESB Toolkit.</span></span> <span data-ttu-id="86755-104">门户提供了可以从中生成自定义门户网站的起点。</span><span class="sxs-lookup"><span data-stu-id="86755-104">The portal provides a starting point from which you can build your own customized portal.</span></span>  
  
 <span data-ttu-id="86755-105">ESB 管理门户也是一个高度支持且有用的工具，可以有助于最大程度地使用和 ESB 异常管理系统的效率。</span><span class="sxs-lookup"><span data-stu-id="86755-105">The ESB Management Portal is also a highly capable and useful tool that can help to maximize the use and efficiency of the ESB exception management system.</span></span> <span data-ttu-id="86755-106">此外，该门户提供的用户界面实现的基础的通用、 描述、 发现和集成 (UDDI) 注册表服务器和审核，等功能的图形配置功能查看历史记录信息，配置警报和通知，并允许用户订阅指明 ESB 应用程序中发生的错误的警报。</span><span class="sxs-lookup"><span data-stu-id="86755-106">In addition, the portal provides a user interface for an underlying Universal Description, Discovery, and Integration (UDDI) registry server and graphical configuration capabilities for features such as auditing, viewing history information, configuring alerts and notifications, and allowing users to subscribe to alerts that indicate faults occurring in ESB applications.</span></span>  
  
 <span data-ttu-id="86755-107">本部分介绍你可以使用 ESB 管理门户中，其中包括达到目的的常见任务：</span><span class="sxs-lookup"><span data-stu-id="86755-107">This section describes the common tasks you can accomplish using the ESB Management Portal, including the following:</span></span>  
  
-   [<span data-ttu-id="86755-108">使用异常和错误消息</span><span class="sxs-lookup"><span data-stu-id="86755-108">Working with Exceptions and Fault Messages</span></span>](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [<span data-ttu-id="86755-109">配置警报、 通知和订阅</span><span class="sxs-lookup"><span data-stu-id="86755-109">Configuring Alerts, Notifications, and Subscriptions</span></span>](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [<span data-ttu-id="86755-110">查看和管理审核和历史记录</span><span class="sxs-lookup"><span data-stu-id="86755-110">Viewing and Managing Auditing and History</span></span>](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [<span data-ttu-id="86755-111">使用图表和报表的分析错误趋势</span><span class="sxs-lookup"><span data-stu-id="86755-111">Analyzing Fault Trends Using Charts and Reports</span></span>](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [<span data-ttu-id="86755-112">查看和发布 UDDI 注册</span><span class="sxs-lookup"><span data-stu-id="86755-112">Viewing and Publishing UDDI Registrations</span></span>](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  <span data-ttu-id="86755-113">ESB 管理门户的各个功能的详细说明，请参阅[ESB 管理门户功能参考](../esb-toolkit/esb-management-portal-feature-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="86755-113">For a detailed description of the individual features of the ESB Management Portal, see [ESB Management Portal Feature Reference](../esb-toolkit/esb-management-portal-feature-reference.md).</span></span>  
  
## <a name="esb-portal-technologies"></a><span data-ttu-id="86755-114">ESB 门户技术</span><span class="sxs-lookup"><span data-stu-id="86755-114">ESB Portal Technologies</span></span>  
 <span data-ttu-id="86755-115">ESB 管理门户利用以下技术：</span><span class="sxs-lookup"><span data-stu-id="86755-115">The ESB Management Portal takes advantage of the following technologies:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   <span data-ttu-id="86755-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="86755-116">ASP.NET</span></span>
  
-   <span data-ttu-id="86755-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。</span><span class="sxs-lookup"><span data-stu-id="86755-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span></span> <span data-ttu-id="86755-118">ESB 管理门户使用以下企业库程序集：</span><span class="sxs-lookup"><span data-stu-id="86755-118">The ESB Management Portal uses the following Enterprise Library assemblies:</span></span>  
  
    -   <span data-ttu-id="86755-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span><span class="sxs-lookup"><span data-stu-id="86755-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span></span>  
  
    -   <span data-ttu-id="86755-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span><span class="sxs-lookup"><span data-stu-id="86755-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span></span>  
  
    -   <span data-ttu-id="86755-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span><span class="sxs-lookup"><span data-stu-id="86755-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span></span>  
  
    -   <span data-ttu-id="86755-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="86755-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span></span>  
  
    -   <span data-ttu-id="86755-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span><span class="sxs-lookup"><span data-stu-id="86755-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span></span>  
  
    -   <span data-ttu-id="86755-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span><span class="sxs-lookup"><span data-stu-id="86755-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span></span>  
  
    -   <span data-ttu-id="86755-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span><span class="sxs-lookup"><span data-stu-id="86755-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span></span>  
  
    -   <span data-ttu-id="86755-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span><span class="sxs-lookup"><span data-stu-id="86755-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span></span>  
  
    -   <span data-ttu-id="86755-127">Microsoft.Practices.Unity</span><span class="sxs-lookup"><span data-stu-id="86755-127">Microsoft.Practices.Unity</span></span>  
  
-   <span data-ttu-id="86755-128">[Microsoft 图表控制](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) 的 Microsoft.NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="86755-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span></span>  
  
<span data-ttu-id="86755-129">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]指标跟踪仅扩展到异常管理系统的错误跟踪。</span><span class="sxs-lookup"><span data-stu-id="86755-129">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] metric tracking extends only to fault tracking for the exception management system.</span></span>