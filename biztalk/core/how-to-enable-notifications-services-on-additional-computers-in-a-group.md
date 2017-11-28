---
title: "如何启用在组中的其他计算机上的通知服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b65596e59820258df01a5655ea30adafe439674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a><span data-ttu-id="9d118-102">如何启用在组中的其他计算机上的通知服务</span><span class="sxs-lookup"><span data-stu-id="9d118-102">How to Enable Notifications Services on Additional Computers In A Group</span></span>
<span data-ttu-id="9d118-103">在多计算机环境中运行 BAM 时，必须在将运行 BAM 管理实用程序以便部署某一活动的每台计算机上都启用 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="9d118-103">When running BAM in a multi-computer environment, you must enable Notification Services on each computer on which you will run the BAM Management Utility to deploy an activity.</span></span>  
  
 <span data-ttu-id="9d118-104">请考虑下列方案：</span><span class="sxs-lookup"><span data-stu-id="9d118-104">Consider the following scenario:</span></span>  
  
-   <span data-ttu-id="9d118-105">组 A 由以下计算机组成：</span><span class="sxs-lookup"><span data-stu-id="9d118-105">Group A consists of the following computers:</span></span>  
  
    -   <span data-ttu-id="9d118-106">计算机 1 用作 BAM 管理计算机。</span><span class="sxs-lookup"><span data-stu-id="9d118-106">Computer 1 is used as a BAM administration computer.</span></span>  
  
    -   <span data-ttu-id="9d118-107">计算机 2 承载 BAM PIT 和星型架构数据库。</span><span class="sxs-lookup"><span data-stu-id="9d118-107">Computer 2 hosts the BAM PIT and Star Schema database.</span></span>  
  
    -   <span data-ttu-id="9d118-108">计算机 3 承载 BAM 存档和分析数据库。</span><span class="sxs-lookup"><span data-stu-id="9d118-108">Computer 3 hosts the BAM Archive and Analysis databases.</span></span>  
  
    -   <span data-ttu-id="9d118-109">计算机 4 承载 BAM 警报数据库。</span><span class="sxs-lookup"><span data-stu-id="9d118-109">Computer 4 hosts the BAM Alerts database.</span></span>  
  
    -   <span data-ttu-id="9d118-110">计算机 5 承载的其余部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="9d118-110">Computer 5 hosts the rest of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
-   <span data-ttu-id="9d118-111">组 b:</span><span class="sxs-lookup"><span data-stu-id="9d118-111">Group B:</span></span>  
  
    -   <span data-ttu-id="9d118-112">计算机 6 用作所有数据库与组 a。 在其的都共享的 BAM 管理计算机</span><span class="sxs-lookup"><span data-stu-id="9d118-112">Computer 6 is used as a BAM administration computer on which all the databases are shared with Group A.</span></span>  
  
 <span data-ttu-id="9d118-113">若要能够从组 B 中的计算机将活动部署到组 A 中的数据库，必须首先注册 Notification Services[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]承载通知服务。</span><span class="sxs-lookup"><span data-stu-id="9d118-113">To be able to deploy an activity to the databases in group A from the computer in group B, you must first register the Notification Services with the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hosting the notifications services.</span></span> <span data-ttu-id="9d118-114">如果未注册通知服务，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="9d118-114">If the Notification Services are not registered, you will receive the following error:</span></span>  
  
 <span data-ttu-id="9d118-115">正在部署警报...错误： BAM 部署失败。</span><span class="sxs-lookup"><span data-stu-id="9d118-115">Deploying Alert... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="9d118-116">未部署警报。</span><span class="sxs-lookup"><span data-stu-id="9d118-116">The alerts were not deployed.</span></span>  
  
 <span data-ttu-id="9d118-117">调用的目标发生了异常。</span><span class="sxs-lookup"><span data-stu-id="9d118-117">Exception has been thrown by the target of an invocation.</span></span>  
  
 <span data-ttu-id="9d118-118">找不到指定的 Notification Services 实例的注册表项。</span><span class="sxs-lookup"><span data-stu-id="9d118-118">The registry entries for the specified instance of Notification Services could not be found.</span></span>  
  
### <a name="to-register-notifications-services-additional-computers"></a><span data-ttu-id="9d118-119">若要注册通知服务的其他计算机</span><span class="sxs-lookup"><span data-stu-id="9d118-119">To register notifications services additional computers</span></span>  
  
1.  <span data-ttu-id="9d118-120">在其他组中的计算机，单击**启动**，指向**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**通知服务命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="9d118-120">On the computer in the additional group, click **Start**, point to **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="9d118-121">在命令提示符处，键入： **nscontrol register-名称\<选择在配置的 NS 前缀名称 >-服务器\<ns db sql 服务器 >**。</span><span class="sxs-lookup"><span data-stu-id="9d118-121">At the command prompt, type: **nscontrol register -name \<NS Prefix name chosen at config> -server \<ns db sql server>**.</span></span> <span data-ttu-id="9d118-122">这样可使 Notification Services 登录到正确的数据库（此信息由 nscontrol 在服务所在计算机的注册表中维护）。</span><span class="sxs-lookup"><span data-stu-id="9d118-122">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d118-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d118-123">See Also</span></span>  
 <span data-ttu-id="9d118-124">[更改 BAM 运行时设置](../core/changing-bam-runtime-settings.md) </span><span class="sxs-lookup"><span data-stu-id="9d118-124">[Changing BAM Runtime Settings](../core/changing-bam-runtime-settings.md) </span></span>  
 [<span data-ttu-id="9d118-125">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="9d118-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)