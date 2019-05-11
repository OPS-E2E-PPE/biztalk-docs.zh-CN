---
title: 规划高 Availability3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- high availability
- planning, high availability
- high availability, architecture
ms.assetid: 16feada0-b0b1-4e58-9477-fbd1aae2f51e
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b4993522725d1a42fd8777fbfd21f91edc0940
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395702"
---
# <a name="planning-for-high-availability"></a><span data-ttu-id="20425-102">规划高可用性</span><span class="sxs-lookup"><span data-stu-id="20425-102">Planning for High Availability</span></span>
<span data-ttu-id="20425-103">许多公司都使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理其业务所依赖的数据。</span><span class="sxs-lookup"><span data-stu-id="20425-103">Many companies use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process data that their business depends on.</span></span> <span data-ttu-id="20425-104">对于这些公司，由硬件停用较长时间的停机时间的结果可能会降低工作效率和盈利能力。</span><span class="sxs-lookup"><span data-stu-id="20425-104">For these companies, the consequences of a prolonged downtime because of a hardware outage can mean diminished productivity and profitability.</span></span> <span data-ttu-id="20425-105">本部分提供用于提高可用性的指导你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，以便最大化运行时间的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="20425-105">This section provides guidance for increasing availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment in order to maximize uptime of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20425-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="20425-106">In This Section</span></span>  
-   [<span data-ttu-id="20425-107">使用 SQL Server AlwaysOn 可用性组实现高可用性</span><span class="sxs-lookup"><span data-stu-id="20425-107">High Availability using SQL Server Always On Availability Groups</span></span>](../core/high-availability-using-sql-server-always-on-availability-groups.md)
  
-   [<span data-ttu-id="20425-108">规划你的平台容错功能</span><span class="sxs-lookup"><span data-stu-id="20425-108">Planning Your Platform for Fault Tolerance</span></span>](../core/planning-your-platform-for-fault-tolerance.md)  
  
-   [<span data-ttu-id="20425-109">创建高度可用的 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="20425-109">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="20425-110">BizTalk Server 高可用性示例方案</span><span class="sxs-lookup"><span data-stu-id="20425-110">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)  
  
-   [<span data-ttu-id="20425-111">企业单一登录的高可用性</span><span class="sxs-lookup"><span data-stu-id="20425-111">High Availability for Enterprise Single Sign-On</span></span>](../core/high-availability-for-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="20425-112">高可用性和 Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="20425-112">High Availability and the Microsoft Operations Framework</span></span>](../core/high-availability-and-the-microsoft-operations-framework.md)  
  
## <a name="reference"></a><span data-ttu-id="20425-113">参考</span><span class="sxs-lookup"><span data-stu-id="20425-113">Reference</span></span>  
  
-   <span data-ttu-id="20425-114">[开始使用 SQL Server 2008 故障转移群集](http://go.microsoft.com/fwlink/?LinkId=130375)(http://go.microsoft.com/fwlink/?LinkId=130375)</span><span class="sxs-lookup"><span data-stu-id="20425-114">[Getting Started with SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span></span>  
  
-   <span data-ttu-id="20425-115">[白皮书：SQL Server 2008 故障转移群集](http://go.microsoft.com/fwlink/?LinkId=189522)(http://go.microsoft.com/fwlink/?LinkId=189522)</span><span class="sxs-lookup"><span data-stu-id="20425-115">[White Paper: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span></span>  
  
-   <span data-ttu-id="20425-116">[Windows Server 2008 分步指南](http://go.microsoft.com/fwlink/?LinkId=189545)(http://go.microsoft.com/fwlink/?LinkId=189545)</span><span class="sxs-lookup"><span data-stu-id="20425-116">[Windows Server 2008 Step-by-Step Guides](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span></span>