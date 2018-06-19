---
title: 清单： 监视操作的准备情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913ed00da2bda4126ba298bbb9bce2980efa4366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300013"
---
# <a name="checklist-monitoring-operational-readiness"></a><span data-ttu-id="0a6ca-102">清单： 监视操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="0a6ca-102">Checklist: Monitoring Operational Readiness</span></span>
<span data-ttu-id="0a6ca-103">本主题列出了监视生产时应遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-103">This topic lists the steps that you should follow when monitoring a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="0a6ca-104">步骤</span><span class="sxs-lookup"><span data-stu-id="0a6ca-104">Steps</span></span>|<span data-ttu-id="0a6ca-105">参考</span><span class="sxs-lookup"><span data-stu-id="0a6ca-105">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="0a6ca-106">选择并实施你的 BizTalk 应用程序和基础结构的监视策略。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-106">Select and implement a monitoring strategy for your BizTalk applications and infrastructure.</span></span>|[<span data-ttu-id="0a6ca-107">监视 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="0a6ca-107">Monitoring the BizTalk Server Environment</span></span>](../technical-guides/monitoring-the-biztalk-server-environment.md)|  
|<span data-ttu-id="0a6ca-108">监视磁盘空间使用情况。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-108">Monitor disk space usage.</span></span>|[<span data-ttu-id="0a6ca-109">监视磁盘空间使用情况</span><span class="sxs-lookup"><span data-stu-id="0a6ca-109">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)|  
|<span data-ttu-id="0a6ca-110">监视 SQL 服务器：</span><span class="sxs-lookup"><span data-stu-id="0a6ca-110">Monitor SQL Server:</span></span><br /><br /> <span data-ttu-id="0a6ca-111">-验证运行 SQL Server 住房该计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在被监视的数据库。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-111">-   Verify that computers running SQL Server housing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are being monitored.</span></span><br /><span data-ttu-id="0a6ca-112">-验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在监视作业。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-112">-   Verify that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] jobs are being monitored.</span></span>|<span data-ttu-id="0a6ca-113">-   [监视 SQL Server](../technical-guides/monitoring-sql-servers.md)</span><span class="sxs-lookup"><span data-stu-id="0a6ca-113">-   [Monitoring SQL Servers](../technical-guides/monitoring-sql-servers.md)</span></span><br /><span data-ttu-id="0a6ca-114">-   [监视 BizTalk Server 数据库](../technical-guides/monitoring-biztalk-server-databases.md)</span><span class="sxs-lookup"><span data-stu-id="0a6ca-114">-   [Monitoring BizTalk Server Databases](../technical-guides/monitoring-biztalk-server-databases.md)</span></span>|  
|<span data-ttu-id="0a6ca-115">监视 BizTalk 应用程序：</span><span class="sxs-lookup"><span data-stu-id="0a6ca-115">Monitor BizTalk applications:</span></span><br /><br /> <span data-ttu-id="0a6ca-116">-修改现有规则和/或复制到自定义管理包以监视自定义的 BizTalk 应用程序的规则。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-116">-   Modify existing rules and/or copy rules to a custom management pack to monitor a custom BizTalk application.</span></span><br /><span data-ttu-id="0a6ca-117">-创建每个定义的规则的操作。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-117">-   Create actions for each defined rule.</span></span><br /><span data-ttu-id="0a6ca-118">-创建迭代进程来自动执行手动任务。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-118">-   Create iterative processes to automate manual tasks.</span></span><br /><span data-ttu-id="0a6ca-119">-使用阈值规则来自动执行手动任务。</span><span class="sxs-lookup"><span data-stu-id="0a6ca-119">-   Use threshold rules to automate manual tasks.</span></span>|<span data-ttu-id="0a6ca-120">-   [监视应用程序和主机实例](../technical-guides/monitoring-applications-and-host-instances.md)</span><span class="sxs-lookup"><span data-stu-id="0a6ca-120">-   [Monitoring Applications and Host Instances](../technical-guides/monitoring-applications-and-host-instances.md)</span></span><br /><span data-ttu-id="0a6ca-121">-   [监视 BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)</span><span class="sxs-lookup"><span data-stu-id="0a6ca-121">-   [Monitoring BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="0a6ca-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="0a6ca-122">In This Section</span></span>  
  
-   [<span data-ttu-id="0a6ca-123">监视磁盘空间使用情况</span><span class="sxs-lookup"><span data-stu-id="0a6ca-123">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)