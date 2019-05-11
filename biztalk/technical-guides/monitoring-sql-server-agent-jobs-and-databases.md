---
title: 监视 SQL Server 代理作业和数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976e1d4fc3d31b10fb174a836025329c89be7171
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305481"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a><span data-ttu-id="f1234-102">监视 SQL Server 代理作业和数据库</span><span class="sxs-lookup"><span data-stu-id="f1234-102">Monitoring SQL Server Agent Jobs and Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f1234-103">包含多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]执行重要功能，以使服务器正常操作和运行的代理作业。</span><span class="sxs-lookup"><span data-stu-id="f1234-103">includes multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="f1234-104">应监视这些作业的运行状况，并确保它们无错运行。</span><span class="sxs-lookup"><span data-stu-id="f1234-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span> <span data-ttu-id="f1234-105">在 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包包含用于监视 SQL 数据库等项目的规则和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。</span><span class="sxs-lookup"><span data-stu-id="f1234-105">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack contains rules for monitoring items such as SQL databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="f1234-106">应配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]适用于所有的全面的监视管理包[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。</span><span class="sxs-lookup"><span data-stu-id="f1234-106">You should configure the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for comprehensive monitoring of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="f1234-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包包括用于监视的两个最重要的 BizTalk 运行状况的两个已禁用的规则[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业：</span><span class="sxs-lookup"><span data-stu-id="f1234-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack includes two disabled rules for monitoring the health of two of the most important BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs:</span></span>  
  
- <span data-ttu-id="f1234-108">严重错误：BizTalk SQL Server 代理作业失败-备份 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f1234-108">Critical Error: A BizTalk SQL Server Agent job failed - Backup BizTalk Server</span></span>  
  
- <span data-ttu-id="f1234-109">严重错误：BizTalk SQL Server 代理作业失败 – 跟踪消息复制</span><span class="sxs-lookup"><span data-stu-id="f1234-109">Critical Error: A BizTalk SQL Server Agent job failed – Tracked Message Copy</span></span>  
  
  <span data-ttu-id="f1234-110">若要监视所有 BizTalk Server[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，必须启用这些规则并创建为你想要使用以下过程都监视其他作业的其他规则。</span><span class="sxs-lookup"><span data-stu-id="f1234-110">To monitor all BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack, you must enable these rules and create additional rules for other jobs that you want to monitor using the following process.</span></span>  
  
- <span data-ttu-id="f1234-111">在 Operations Manager 管理员控制台中，创建两个上述规则中的任何一个的副本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]核心规则组，并相应地重命名规则。</span><span class="sxs-lookup"><span data-stu-id="f1234-111">In the Operations Manager Administrator console, create a copy of either of the two preceding rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Core Rule group, and rename the rule appropriately.</span></span>  
  
- <span data-ttu-id="f1234-112">规则在条件部分中的通配符比较参数 1 的相应更改。</span><span class="sxs-lookup"><span data-stu-id="f1234-112">In the criteria section for the rule, change the wildcard comparison for Parameter 1 appropriately.</span></span>  
  
- <span data-ttu-id="f1234-113">在某些情况下，作业名称是依赖于数据库的名称创建用户，例如，MessageBox 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f1234-113">In some cases, job names are dependent on database names that the user creates, for example, the name of the MessageBox database.</span></span>  
  
- <span data-ttu-id="f1234-114">可以针对你的规则是针对作业与单个 MessageBox 或所有 Messagebox。</span><span class="sxs-lookup"><span data-stu-id="f1234-114">Your rule can be targeted either towards a job associated with a single MessageBox or all MessageBoxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1234-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1234-115">See Also</span></span>  
 [<span data-ttu-id="f1234-116">如何启动 SQL Server 代理</span><span class="sxs-lookup"><span data-stu-id="f1234-116">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)