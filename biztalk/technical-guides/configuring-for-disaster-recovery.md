---
title: "为灾难恢复配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3899b27324fa00e0b5c630c7be4433f65a917a1b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="71e80-102">为灾难恢复配置</span><span class="sxs-lookup"><span data-stu-id="71e80-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="71e80-103">BizTalk Server 日志传送功能扩展现有的备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。</span><span class="sxs-lookup"><span data-stu-id="71e80-103">The BizTalk Server Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> <span data-ttu-id="71e80-104">BizTalk Server 日志传送无需手动还原的备份作业，生成的备份集的一系列，并发生系统故障时减少停机时间。</span><span class="sxs-lookup"><span data-stu-id="71e80-104">BizTalk Server Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> <span data-ttu-id="71e80-105">BizTalk Server 日志传送是 BizTalk 灾难恢复过程的关键组件。</span><span class="sxs-lookup"><span data-stu-id="71e80-105">BizTalk Server Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71e80-106">每个应用程序团队必须有案可稽的备份和还原进行了补充本主题中提供的概念的灾难恢复计划。</span><span class="sxs-lookup"><span data-stu-id="71e80-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="71e80-107">整体计划应该解决整个系统，包括应用程序和操作系统的组件。</span><span class="sxs-lookup"><span data-stu-id="71e80-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="71e80-108">执行灾难恢复操作是非常类似于手动还原到一组新的 BizTalk 组[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。</span><span class="sxs-lookup"><span data-stu-id="71e80-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="71e80-109">主要差别在于该 BizTalk Server 日志传送将持续在灾难恢复站点，保存许多手动步骤的日志应用。</span><span class="sxs-lookup"><span data-stu-id="71e80-109">The primary difference is that BizTalk Server log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="71e80-110">因此，仅最后一组日志必须手动恢复时实现日志传送的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="71e80-110">Therefore, only the last set of logs must be restored manually when BizTalk Server log shipping is implemented.</span></span> <span data-ttu-id="71e80-111">否则，上次的完整备份自上次完整备份后跟的所有日志备份将必须手动还原。</span><span class="sxs-lookup"><span data-stu-id="71e80-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> <span data-ttu-id="71e80-112">BizTalk Server 日志传送减少了工作，此手动过程，加快了还原的灾难恢复站点。</span><span class="sxs-lookup"><span data-stu-id="71e80-112">BizTalk Server log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="71e80-113">本部分介绍在生产配置的建议，以便于灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="71e80-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71e80-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="71e80-114">In This Section</span></span>  
  
-   [<span data-ttu-id="71e80-115">准备灾难恢复站点</span><span class="sxs-lookup"><span data-stu-id="71e80-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="71e80-116">日志传送用户帐户和角色</span><span class="sxs-lookup"><span data-stu-id="71e80-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="71e80-117">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="71e80-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="71e80-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71e80-118">See Also</span></span>  
 [<span data-ttu-id="71e80-119">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="71e80-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)