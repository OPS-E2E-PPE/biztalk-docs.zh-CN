---
title: "监视 SQL Server 代理作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489e9e8e8b5bf5b00125036d71ff5fa0f37f3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-agent-jobs"></a><span data-ttu-id="06e91-102">监视 SQL Server 代理作业</span><span class="sxs-lookup"><span data-stu-id="06e91-102">Monitoring SQL Server Agent Jobs</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="06e91-103">包括执行重要的功能使你的服务器操作和正常运行的多个 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="06e91-103"> includes multiple SQL Server Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="06e91-104">您应该监视这些作业的运行状况，确保它们无错运行。</span><span class="sxs-lookup"><span data-stu-id="06e91-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span>  
  
## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a><span data-ttu-id="06e91-105">用于监视 SQL Server 代理作业的准则</span><span class="sxs-lookup"><span data-stu-id="06e91-105">Guidelines for Monitoring the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="06e91-106">下面是用于监视作业的指导原则：</span><span class="sxs-lookup"><span data-stu-id="06e91-106">Following are guidelines for monitoring the jobs:</span></span>  
  
-   <span data-ttu-id="06e91-107">**验证 SQL Server 代理服务正在运行**</span><span class="sxs-lookup"><span data-stu-id="06e91-107">**Verify that the SQL Server Agent service is running**</span></span>  
  
-   <span data-ttu-id="06e91-108">**验证由 BizTalk 服务器安装的 SQL Server 代理作业已启用并运行成功**</span><span class="sxs-lookup"><span data-stu-id="06e91-108">**Verify that the SQL Server Agent jobs installed by BizTalk Server are enabled and running successfully**</span></span>  
  
     <span data-ttu-id="06e91-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server 代理作业至关重要： 如果它们未运行，随着时间的推移将降低系统性能。</span><span class="sxs-lookup"><span data-stu-id="06e91-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server Agent jobs are crucial: if they are not running, system performance will degrade over time.</span></span>  
  
-   <span data-ttu-id="06e91-110">**验证，及时完成 BizTalk Server SQL Server 代理作业**</span><span class="sxs-lookup"><span data-stu-id="06e91-110">**Verify that the BizTalk Server SQL Server Agent jobs are completing in a timely manner**</span></span>  
  
     <span data-ttu-id="06e91-111">设置 Microsoft System Center Operations Manager 以监视作业。</span><span class="sxs-lookup"><span data-stu-id="06e91-111">Set up Microsoft System Center Operations Manager to monitor the jobs.</span></span>  
  
     <span data-ttu-id="06e91-112">你应注意的特定于某些作业的计划：</span><span class="sxs-lookup"><span data-stu-id="06e91-112">You should be aware of schedules that are particular to certain jobs:</span></span>  
  
    -   <span data-ttu-id="06e91-113">默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业是连续运行。</span><span class="sxs-lookup"><span data-stu-id="06e91-113">The MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job runs continuously by default.</span></span> <span data-ttu-id="06e91-114">监视软件应考虑此计划，并且不生成警告。</span><span class="sxs-lookup"><span data-stu-id="06e91-114">Monitoring software should take this schedule into account and not produce warnings.</span></span>  
  
    -   <span data-ttu-id="06e91-115">MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或计划，但它会启动 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业每隔 10 秒。</span><span class="sxs-lookup"><span data-stu-id="06e91-115">The MessageBox_Message_Cleanup_BizTalkMsgBoxDb job is not enabled or scheduled, but it is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job every 10 seconds.</span></span> <span data-ttu-id="06e91-116">因此，此作业不应启用、 计划，或手动启动。</span><span class="sxs-lookup"><span data-stu-id="06e91-116">Therefore, this job should not be enabled, scheduled, or manually started.</span></span>  
  
-   <span data-ttu-id="06e91-117">**验证已正确配置 SQL Server 代理服务的启动类型**</span><span class="sxs-lookup"><span data-stu-id="06e91-117">**Verify that the Startup type of the SQL Server Agent service is configured correctly**</span></span>  
  
     <span data-ttu-id="06e91-118">验证 SQL Server 代理服务使用配置**Startuptype**的**自动**除非的 SQL Server 代理服务配置为在 Windows Server 群集上的群集资源。</span><span class="sxs-lookup"><span data-stu-id="06e91-118">Verify that the SQL Server Agent service is configured with a **Startuptype** of **Automatic** unless the SQL Server Agent service is configured as a cluster resource on a Windows Server cluster.</span></span> <span data-ttu-id="06e91-119">如果 SQL Server 代理服务配置为群集资源，则应配置**Startuptype**作为**手动**由于服务将由群集服务。</span><span class="sxs-lookup"><span data-stu-id="06e91-119">If the SQL Server Agent service is configured as a cluster resource, then you should configure the **Startuptype** as **Manual** since the service will be managed by the Cluster service.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="06e91-120">其他资源</span><span class="sxs-lookup"><span data-stu-id="06e91-120">Additional Resources</span></span>  
  
-   <span data-ttu-id="06e91-121">有关监视的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业，请参阅[监视 SQL Server 代理作业和数据库](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="06e91-121">For more information about monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Agent jobs, see [Monitoring SQL Server Agent Jobs and Databases](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).</span></span>  
  
-   <span data-ttu-id="06e91-122">有关附带的 SQL Server 代理作业的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请参阅["数据库结构和作业"](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451)。</span><span class="sxs-lookup"><span data-stu-id="06e91-122">For more information about the SQL Server Agent jobs that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] see ["Database Structure and Jobs"](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451).</span></span>