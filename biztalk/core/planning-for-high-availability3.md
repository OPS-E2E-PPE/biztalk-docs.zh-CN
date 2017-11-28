---
title: "规划高 Availability3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- high availability
- planning, high availability
- high availability, architecture
ms.assetid: 16feada0-b0b1-4e58-9477-fbd1aae2f51e
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6a8a69af5fd1ff59a4e69e02a52124d89db1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability"></a><span data-ttu-id="59850-102">规划高可用性</span><span class="sxs-lookup"><span data-stu-id="59850-102">Planning for High Availability</span></span>
<span data-ttu-id="59850-103">许多公司都使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来处理其业务所依赖的数据。</span><span class="sxs-lookup"><span data-stu-id="59850-103">Many companies use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process data that their business depends on.</span></span> <span data-ttu-id="59850-104">对于这些公司，由硬件停用所导致的延长故障时间将意味着工作效率和盈利率的降低。</span><span class="sxs-lookup"><span data-stu-id="59850-104">For these companies, the consequences of a prolonged downtime because of a hardware outage can mean diminished productivity and profitability.</span></span> <span data-ttu-id="59850-105">本节提供有关提高 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的可用性以最大程度地延长 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案运行时间的指南。</span><span class="sxs-lookup"><span data-stu-id="59850-105">This section provides guidance for increasing availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment in order to maximize uptime of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59850-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="59850-106">In This Section</span></span>  
-   [<span data-ttu-id="59850-107">使用 SQL Server Alwayson 可用性组的高可用性</span><span class="sxs-lookup"><span data-stu-id="59850-107">High Availability using SQL Server Always On Availability Groups</span></span>](../core/high-availability-using-sql-server-always-on-availability-groups.md)
  
-   [<span data-ttu-id="59850-108">规划你的平台容错</span><span class="sxs-lookup"><span data-stu-id="59850-108">Planning Your Platform for Fault Tolerance</span></span>](../core/planning-your-platform-for-fault-tolerance.md)  
  
-   [<span data-ttu-id="59850-109">创建高度可用的 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="59850-109">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="59850-110">示例 BizTalk Server 高可用性方案</span><span class="sxs-lookup"><span data-stu-id="59850-110">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)  
  
-   [<span data-ttu-id="59850-111">为企业单一登录的高可用性</span><span class="sxs-lookup"><span data-stu-id="59850-111">High Availability for Enterprise Single Sign-On</span></span>](../core/high-availability-for-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="59850-112">高可用性和 Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="59850-112">High Availability and the Microsoft Operations Framework</span></span>](../core/high-availability-and-the-microsoft-operations-framework.md)  
  
## <a name="reference"></a><span data-ttu-id="59850-113">参考</span><span class="sxs-lookup"><span data-stu-id="59850-113">Reference</span></span>  
  
-   <span data-ttu-id="59850-114">[Getting Started with SQL Server 2008 故障转移群集](http://go.microsoft.com/fwlink/?LinkId=130375)(http://go.microsoft.com/fwlink/?LinkId=130375)</span><span class="sxs-lookup"><span data-stu-id="59850-114">[Getting Started with SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span></span>  
  
-   <span data-ttu-id="59850-115">[白皮书： SQL Server 2008 故障转移群集](http://go.microsoft.com/fwlink/?LinkId=189522)(http://go.microsoft.com/fwlink/?LinkId=189522)</span><span class="sxs-lookup"><span data-stu-id="59850-115">[White Paper: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span></span>  
  
-   <span data-ttu-id="59850-116">[Windows Server 2008 分步指南](http://go.microsoft.com/fwlink/?LinkId=189545)(http://go.microsoft.com/fwlink/?LinkId=189545)</span><span class="sxs-lookup"><span data-stu-id="59850-116">[Windows Server 2008 Step-by-Step Guides](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span></span>