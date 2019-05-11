---
title: 如何启用在组中的其他计算机上的通知服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97319d9bef68aa29be1c8de04b1f876a1bb778d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337986"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a><span data-ttu-id="24d1f-102">如何启用在组中的其他计算机上的通知服务</span><span class="sxs-lookup"><span data-stu-id="24d1f-102">How to Enable Notifications Services on Additional Computers In A Group</span></span>
<span data-ttu-id="24d1f-103">当在多计算机环境中运行 BAM，必须在其将运行 BAM 管理实用程序来部署某一活动每台计算机上启用 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="24d1f-103">When running BAM in a multi-computer environment, you must enable Notification Services on each computer on which you will run the BAM Management Utility to deploy an activity.</span></span>  
  
 <span data-ttu-id="24d1f-104">请考虑下列方案：</span><span class="sxs-lookup"><span data-stu-id="24d1f-104">Consider the following scenario:</span></span>  
  
- <span data-ttu-id="24d1f-105">组 A 包含以下计算机：</span><span class="sxs-lookup"><span data-stu-id="24d1f-105">Group A consists of the following computers:</span></span>  
  
  - <span data-ttu-id="24d1f-106">计算机 1 用作 BAM 管理计算机。</span><span class="sxs-lookup"><span data-stu-id="24d1f-106">Computer 1 is used as a BAM administration computer.</span></span>  
  
  - <span data-ttu-id="24d1f-107">计算机 2 承载 BAM PIT 和星型架构数据库。</span><span class="sxs-lookup"><span data-stu-id="24d1f-107">Computer 2 hosts the BAM PIT and Star Schema database.</span></span>  
  
  - <span data-ttu-id="24d1f-108">计算机 3 承载 BAM 存档和分析数据库。</span><span class="sxs-lookup"><span data-stu-id="24d1f-108">Computer 3 hosts the BAM Archive and Analysis databases.</span></span>  
  
  - <span data-ttu-id="24d1f-109">计算机 4 承载 BAM 警报数据库。</span><span class="sxs-lookup"><span data-stu-id="24d1f-109">Computer 4 hosts the BAM Alerts database.</span></span>  
  
  - <span data-ttu-id="24d1f-110">计算机 5 承载的其余部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="24d1f-110">Computer 5 hosts the rest of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
- <span data-ttu-id="24d1f-111">组 b:</span><span class="sxs-lookup"><span data-stu-id="24d1f-111">Group B:</span></span>  
  
  -   <span data-ttu-id="24d1f-112">为 BAM 管理计算机的所有数据库都共享与组 a。 使用计算机 6</span><span class="sxs-lookup"><span data-stu-id="24d1f-112">Computer 6 is used as a BAM administration computer on which all the databases are shared with Group A.</span></span>  
  
  <span data-ttu-id="24d1f-113">若要能够从组 B 中的计算机组 A 中的数据库部署某一活动，必须先注册 Notification Services[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]托管通知服务。</span><span class="sxs-lookup"><span data-stu-id="24d1f-113">To be able to deploy an activity to the databases in group A from the computer in group B, you must first register the Notification Services with the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hosting the notifications services.</span></span> <span data-ttu-id="24d1f-114">如果未注册 Notification Services，您将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="24d1f-114">If the Notification Services are not registered, you will receive the following error:</span></span>  
  
  <span data-ttu-id="24d1f-115">部署警报...错误：BAM 部署失败。</span><span class="sxs-lookup"><span data-stu-id="24d1f-115">Deploying Alert... ERROR: The BAM deployment failed.</span></span>  
  
  <span data-ttu-id="24d1f-116">未部署警报。</span><span class="sxs-lookup"><span data-stu-id="24d1f-116">The alerts were not deployed.</span></span>  
  
  <span data-ttu-id="24d1f-117">调用的目标已引发异常。</span><span class="sxs-lookup"><span data-stu-id="24d1f-117">Exception has been thrown by the target of an invocation.</span></span>  
  
  <span data-ttu-id="24d1f-118">找不到指定的 Notification Services 实例的注册表项。</span><span class="sxs-lookup"><span data-stu-id="24d1f-118">The registry entries for the specified instance of Notification Services could not be found.</span></span>  
  
### <a name="to-register-notifications-services-additional-computers"></a><span data-ttu-id="24d1f-119">若要注册通知服务的其他计算机</span><span class="sxs-lookup"><span data-stu-id="24d1f-119">To register notifications services additional computers</span></span>  
  
1.  <span data-ttu-id="24d1f-120">在其他组中计算机上，单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**Notification Services 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="24d1f-120">On the computer in the additional group, click **Start**, point to **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="24d1f-121">在命令提示符处，键入： **nscontrol register-名称\<NS 前缀名称在配置选择\>-服务器\<ns db sql server\>**。</span><span class="sxs-lookup"><span data-stu-id="24d1f-121">At the command prompt, type: **nscontrol register -name \<NS Prefix name chosen at config\> -server \<ns db sql server\>**.</span></span> <span data-ttu-id="24d1f-122">这可使 Notification Services 登录到正确的数据库 （此信息保留在服务计算机的注册表中由 nscontrol）。</span><span class="sxs-lookup"><span data-stu-id="24d1f-122">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d1f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="24d1f-123">See Also</span></span>  
 <span data-ttu-id="24d1f-124">[更改 BAM 运行时设置](../core/changing-bam-runtime-settings.md) </span><span class="sxs-lookup"><span data-stu-id="24d1f-124">[Changing BAM Runtime Settings](../core/changing-bam-runtime-settings.md) </span></span>  
 [<span data-ttu-id="24d1f-125">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="24d1f-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)