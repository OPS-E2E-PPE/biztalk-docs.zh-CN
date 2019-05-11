---
title: 配置灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0bce395a5873947d006aa84b620b921a4a8e943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253552"
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="167eb-102">配置灾难恢复</span><span class="sxs-lookup"><span data-stu-id="167eb-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="167eb-103">BizTalk Server 日志传送功能扩展了现有备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。</span><span class="sxs-lookup"><span data-stu-id="167eb-103">The BizTalk Server Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> <span data-ttu-id="167eb-104">BizTalk Server 日志传送无需手动还原一系列的备份作业，生成的备份集，并可以缩短出现系统故障时的停机时间。</span><span class="sxs-lookup"><span data-stu-id="167eb-104">BizTalk Server Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> <span data-ttu-id="167eb-105">BizTalk Server 日志传送是 BizTalk 灾难恢复过程的关键组件。</span><span class="sxs-lookup"><span data-stu-id="167eb-105">BizTalk Server Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="167eb-106">每个应用程序团队必须有案可稽的备份和还原提供补充了本主题中提供的概念的灾难恢复计划。</span><span class="sxs-lookup"><span data-stu-id="167eb-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="167eb-107">总体计划应该处理整个系统，包括应用程序和操作系统的组件。</span><span class="sxs-lookup"><span data-stu-id="167eb-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="167eb-108">执行灾难恢复操作是非常类似于手动执行到一组新的 BizTalk 组的还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。</span><span class="sxs-lookup"><span data-stu-id="167eb-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="167eb-109">主要区别在于该 BizTalk Server 日志传送适用持续在灾难恢复站点上，保存多的手动步骤的日志。</span><span class="sxs-lookup"><span data-stu-id="167eb-109">The primary difference is that BizTalk Server log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="167eb-110">因此，仅日志的最后一组必须手动还原时 BizTalk Server 实现日志传送。</span><span class="sxs-lookup"><span data-stu-id="167eb-110">Therefore, only the last set of logs must be restored manually when BizTalk Server log shipping is implemented.</span></span> <span data-ttu-id="167eb-111">否则，自上次完整备份之后进行所有日志备份的最后一个完整备份将需要手动还原。</span><span class="sxs-lookup"><span data-stu-id="167eb-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> <span data-ttu-id="167eb-112">BizTalk Server 日志传送可减少此手动过程，从而加快的灾难恢复站点还原的工作。</span><span class="sxs-lookup"><span data-stu-id="167eb-112">BizTalk Server log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="167eb-113">本部分介绍了生产配置的建议来简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="167eb-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="167eb-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="167eb-114">In This Section</span></span>  
  
-   [<span data-ttu-id="167eb-115">准备灾难恢复站点</span><span class="sxs-lookup"><span data-stu-id="167eb-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="167eb-116">日志传送用户帐户和角色</span><span class="sxs-lookup"><span data-stu-id="167eb-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="167eb-117">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="167eb-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="167eb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="167eb-118">See Also</span></span>  
 [<span data-ttu-id="167eb-119">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="167eb-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)