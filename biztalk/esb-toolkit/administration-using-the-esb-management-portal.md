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
ms.openlocfilehash: 9b0687b57ed18cd657a70ce50f1d1efc284d6392
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379492"
---
# <a name="administration-using-the-esb-management-portal"></a><span data-ttu-id="85120-102">使用 ESB 管理门户管理</span><span class="sxs-lookup"><span data-stu-id="85120-102">Administration Using the ESB Management Portal</span></span>
<span data-ttu-id="85120-103">ESB 管理门户中，作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，是演示如何使用指标和存在的可能性用于扩展 BizTalk ESB 工具包的示例站点。</span><span class="sxs-lookup"><span data-stu-id="85120-103">The ESB Management Portal, included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], is a sample site that demonstrates the use of metrics and the possibilities that exist for extending the BizTalk ESB Toolkit.</span></span> <span data-ttu-id="85120-104">该门户提供了可以从其生成自己的自定义的门户的起始点。</span><span class="sxs-lookup"><span data-stu-id="85120-104">The portal provides a starting point from which you can build your own customized portal.</span></span>  
  
 <span data-ttu-id="85120-105">ESB 管理门户也是一个高性能且有用的工具，可帮助最大程度地使用和效率的 ESB 异常管理系统。</span><span class="sxs-lookup"><span data-stu-id="85120-105">The ESB Management Portal is also a highly capable and useful tool that can help to maximize the use and efficiency of the ESB exception management system.</span></span> <span data-ttu-id="85120-106">此外，该门户提供了一个用户界面为基础的通用描述、 发现和集成 (UDDI) 注册表服务器和审核等功能的图形配置功能查看历史记录信息，配置警报和通知，并允许用户以订阅警报，可指示 ESB 应用程序中发生的错误。</span><span class="sxs-lookup"><span data-stu-id="85120-106">In addition, the portal provides a user interface for an underlying Universal Description, Discovery, and Integration (UDDI) registry server and graphical configuration capabilities for features such as auditing, viewing history information, configuring alerts and notifications, and allowing users to subscribe to alerts that indicate faults occurring in ESB applications.</span></span>  
  
 <span data-ttu-id="85120-107">本部分介绍可以使用 ESB 管理门户中，其中包括完成操作的常见任务：</span><span class="sxs-lookup"><span data-stu-id="85120-107">This section describes the common tasks you can accomplish using the ESB Management Portal, including the following:</span></span>  
  
-   [<span data-ttu-id="85120-108">使用异常和故障消息</span><span class="sxs-lookup"><span data-stu-id="85120-108">Working with Exceptions and Fault Messages</span></span>](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [<span data-ttu-id="85120-109">配置警报、通知和订阅</span><span class="sxs-lookup"><span data-stu-id="85120-109">Configuring Alerts, Notifications, and Subscriptions</span></span>](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [<span data-ttu-id="85120-110">查看和管理审核和历史记录</span><span class="sxs-lookup"><span data-stu-id="85120-110">Viewing and Managing Auditing and History</span></span>](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [<span data-ttu-id="85120-111">使用图表和报表分析故障趋势</span><span class="sxs-lookup"><span data-stu-id="85120-111">Analyzing Fault Trends Using Charts and Reports</span></span>](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [<span data-ttu-id="85120-112">查看和发布 UDDI 注册</span><span class="sxs-lookup"><span data-stu-id="85120-112">Viewing and Publishing UDDI Registrations</span></span>](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  <span data-ttu-id="85120-113">ESB 管理门户的各个功能的详细说明，请参阅[ESB 管理门户功能参考](../esb-toolkit/esb-management-portal-feature-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="85120-113">For a detailed description of the individual features of the ESB Management Portal, see [ESB Management Portal Feature Reference](../esb-toolkit/esb-management-portal-feature-reference.md).</span></span>  
  
## <a name="esb-portal-technologies"></a><span data-ttu-id="85120-114">ESB 门户技术</span><span class="sxs-lookup"><span data-stu-id="85120-114">ESB Portal Technologies</span></span>  
 <span data-ttu-id="85120-115">ESB 管理门户利用以下技术：</span><span class="sxs-lookup"><span data-stu-id="85120-115">The ESB Management Portal takes advantage of the following technologies:</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
- <span data-ttu-id="85120-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="85120-116">ASP.NET</span></span>
  
- <span data-ttu-id="85120-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。</span><span class="sxs-lookup"><span data-stu-id="85120-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span></span> <span data-ttu-id="85120-118">ESB 管理门户使用以下 Enterprise Library 程序集：</span><span class="sxs-lookup"><span data-stu-id="85120-118">The ESB Management Portal uses the following Enterprise Library assemblies:</span></span>  
  
  -   <span data-ttu-id="85120-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span><span class="sxs-lookup"><span data-stu-id="85120-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span></span>  
  
  -   <span data-ttu-id="85120-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span><span class="sxs-lookup"><span data-stu-id="85120-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span></span>  
  
  -   <span data-ttu-id="85120-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span><span class="sxs-lookup"><span data-stu-id="85120-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span></span>  
  
  -   <span data-ttu-id="85120-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="85120-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span></span>  
  
  -   <span data-ttu-id="85120-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span><span class="sxs-lookup"><span data-stu-id="85120-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span></span>  
  
  -   <span data-ttu-id="85120-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span><span class="sxs-lookup"><span data-stu-id="85120-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span></span>  
  
  -   <span data-ttu-id="85120-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span><span class="sxs-lookup"><span data-stu-id="85120-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span></span>  
  
  -   <span data-ttu-id="85120-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span><span class="sxs-lookup"><span data-stu-id="85120-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span></span>  
  
  -   <span data-ttu-id="85120-127">Microsoft.Practices.Unity</span><span class="sxs-lookup"><span data-stu-id="85120-127">Microsoft.Practices.Unity</span></span>  
  
- <span data-ttu-id="85120-128">[Microsoft 图表控件](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) Microsoft.NET framework 4</span><span class="sxs-lookup"><span data-stu-id="85120-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span></span>  
  
<span data-ttu-id="85120-129">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]指标跟踪仅扩展到异常管理系统的错误跟踪。</span><span class="sxs-lookup"><span data-stu-id="85120-129">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] metric tracking extends only to fault tracking for the exception management system.</span></span>