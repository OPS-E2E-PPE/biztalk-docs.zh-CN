---
title: 监视 SQL Server 代理作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fb4026b95a5f368c265b49425ab1d3e1ec776cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015388"
---
# <a name="monitoring-sql-server-agent-jobs"></a><span data-ttu-id="7f465-102">监视 SQL Server 代理作业</span><span class="sxs-lookup"><span data-stu-id="7f465-102">Monitoring SQL Server Agent Jobs</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7f465-103"> 包括执行重要功能，以使服务器正常操作和运行的多个 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="7f465-103"> includes multiple SQL Server Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="7f465-104">您应该监视这些作业的运行状况，确保它们无错运行。</span><span class="sxs-lookup"><span data-stu-id="7f465-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span>  

## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a><span data-ttu-id="7f465-105">用于监视 SQL Server 代理作业的指导原则</span><span class="sxs-lookup"><span data-stu-id="7f465-105">Guidelines for Monitoring the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="7f465-106">下面是用于监视作业的指导原则：</span><span class="sxs-lookup"><span data-stu-id="7f465-106">Following are guidelines for monitoring the jobs:</span></span>  

- <span data-ttu-id="7f465-107">**验证 SQL Server 代理服务正在运行**</span><span class="sxs-lookup"><span data-stu-id="7f465-107">**Verify that the SQL Server Agent service is running**</span></span>  

- <span data-ttu-id="7f465-108">**验证 BizTalk server 安装的 SQL Server 代理作业已启用并正在运行成功**</span><span class="sxs-lookup"><span data-stu-id="7f465-108">**Verify that the SQL Server Agent jobs installed by BizTalk Server are enabled and running successfully**</span></span>  

   <span data-ttu-id="7f465-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server 代理作业至关重要： 如果未运行，随着时间的推移会降低系统性能。</span><span class="sxs-lookup"><span data-stu-id="7f465-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server Agent jobs are crucial: if they are not running, system performance will degrade over time.</span></span>  

- <span data-ttu-id="7f465-110">**验证 BizTalk Server SQL Server 代理作业及时完成**</span><span class="sxs-lookup"><span data-stu-id="7f465-110">**Verify that the BizTalk Server SQL Server Agent jobs are completing in a timely manner**</span></span>  

   <span data-ttu-id="7f465-111">设置 Microsoft System Center Operations Manager 以监视作业。</span><span class="sxs-lookup"><span data-stu-id="7f465-111">Set up Microsoft System Center Operations Manager to monitor the jobs.</span></span>  

   <span data-ttu-id="7f465-112">应注意的特定于某些作业的计划：</span><span class="sxs-lookup"><span data-stu-id="7f465-112">You should be aware of schedules that are particular to certain jobs:</span></span>  

  -   <span data-ttu-id="7f465-113">默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业会连续运行。</span><span class="sxs-lookup"><span data-stu-id="7f465-113">The MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job runs continuously by default.</span></span> <span data-ttu-id="7f465-114">监视软件，应考虑此计划，并生成警告。</span><span class="sxs-lookup"><span data-stu-id="7f465-114">Monitoring software should take this schedule into account and not produce warnings.</span></span>  

  -   <span data-ttu-id="7f465-115">MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或未计划，但它由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动每隔 10 秒。</span><span class="sxs-lookup"><span data-stu-id="7f465-115">The MessageBox_Message_Cleanup_BizTalkMsgBoxDb job is not enabled or scheduled, but it is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job every 10 seconds.</span></span> <span data-ttu-id="7f465-116">因此，此作业不应启用、 计划，或手动启动。</span><span class="sxs-lookup"><span data-stu-id="7f465-116">Therefore, this job should not be enabled, scheduled, or manually started.</span></span>  

- <span data-ttu-id="7f465-117">**验证已正确配置 SQL Server 代理服务的启动类型**</span><span class="sxs-lookup"><span data-stu-id="7f465-117">**Verify that the Startup type of the SQL Server Agent service is configured correctly**</span></span>  

   <span data-ttu-id="7f465-118">验证 SQL Server 代理服务是否与配置**Startuptype**的**自动**除非 SQL Server 代理服务配置为在 Windows Server 群集上群集资源。</span><span class="sxs-lookup"><span data-stu-id="7f465-118">Verify that the SQL Server Agent service is configured with a **Startuptype** of **Automatic** unless the SQL Server Agent service is configured as a cluster resource on a Windows Server cluster.</span></span> <span data-ttu-id="7f465-119">如果 SQL Server 代理服务配置为群集资源，则应配置**Startuptype**作为**手动**由于该服务将由群集服务。</span><span class="sxs-lookup"><span data-stu-id="7f465-119">If the SQL Server Agent service is configured as a cluster resource, then you should configure the **Startuptype** as **Manual** since the service will be managed by the Cluster service.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="7f465-120">其他资源</span><span class="sxs-lookup"><span data-stu-id="7f465-120">Additional Resources</span></span>  

- <span data-ttu-id="7f465-121">有关监视的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业，请参阅[监视 SQL Server 代理作业和数据库](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="7f465-121">For more information about monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Agent jobs, see [Monitoring SQL Server Agent Jobs and Databases](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).</span></span>  

- <span data-ttu-id="7f465-122">详细了解附带的 SQL Server 代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请参阅["数据库结构和作业"](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>)。</span><span class="sxs-lookup"><span data-stu-id="7f465-122">For more information about the SQL Server Agent jobs that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] see ["Database Structure and Jobs"](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>).</span></span>
