---
title: "运行 BizTalk Server 的计算机的灾难恢复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac655c10aaa443f9971fc40f7301a9e608e0e7eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a><span data-ttu-id="c9b03-102">运行 BizTalk Server 的计算机的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="c9b03-102">Disaster Recovery for Computers Running BizTalk Server</span></span>
<span data-ttu-id="c9b03-103">如果您的组织中运行 BizTalk Server 的计算机出现了无法恢复的硬件故障，则应该用相同设置的计算机代替它。</span><span class="sxs-lookup"><span data-stu-id="c9b03-103">If the computer running BizTalk Server in your organization suffers an unrecoverable hardware failure, you should replace it with an identical computer.</span></span> <span data-ttu-id="c9b03-104">其假定条件是，BizTalk Server 数据库保存完整，并且故障发生在运行 BizTalk Server 的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="c9b03-104">This assumes that the BizTalk Server databases are intact, and that the failure is in any one of the computers running BizTalk Server.</span></span>  
  
 <span data-ttu-id="c9b03-105">一种可能的方法是为安装环境中运行 BizTalk Server 的每台计算机都保留一个最新的映像。</span><span class="sxs-lookup"><span data-stu-id="c9b03-105">One possible approach is to maintain an updated image of every computer running BizTalk Server in your installation.</span></span> <span data-ttu-id="c9b03-106">在计算机出现硬件故障时，恢复操作只不过是在新计算机上部署存储的映像。</span><span class="sxs-lookup"><span data-stu-id="c9b03-106">When a computer suffers a hardware failure, the recovery action is as simple as deploying the stored image on a new computer.</span></span> <span data-ttu-id="c9b03-107">本灾难恢复主题讨论不适于存储这种映像的情况。</span><span class="sxs-lookup"><span data-stu-id="c9b03-107">The disaster recovery topics address the case where storing such images is not feasible.</span></span>  
## <a name="recovering-different-editions-of-biztalk-server"></a><span data-ttu-id="c9b03-108">恢复不同版本的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c9b03-108">Recovering Different Editions of BizTalk Server</span></span>  
 <span data-ttu-id="c9b03-109">恢复方法因计算机上运行的 BizTalk Server 的版本不同而异。</span><span class="sxs-lookup"><span data-stu-id="c9b03-109">The recovery approach is different depending on the edition of BizTalk Server running on the computer.</span></span>  
  
 <span data-ttu-id="c9b03-110">对于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 开发人员版和 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 企业版，允许多台计算机运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c9b03-110">For [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Developer Edition and [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Enterprise Edition, multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are permitted.</span></span> <span data-ttu-id="c9b03-111">当其中一台运行 BizTalk Server 的计算机发生故障时，可以准备一台替代计算机并将其加入现有 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="c9b03-111">When one of the computers running BizTalk Server fails, you can prepare a replacement computer and join it to the existing BizTalk group.</span></span> <span data-ttu-id="c9b03-112">在这种情况下，可以向 BizTalk 组中加入同名或不同名的计算机。</span><span class="sxs-lookup"><span data-stu-id="c9b03-112">In this case, you can join a computer with either the same name or a different name to the BizTalk group.</span></span>  
  
 <span data-ttu-id="c9b03-113">对于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 标准版，则不能向 BizTalk 组中加入计算机，所以上述方法不适用。</span><span class="sxs-lookup"><span data-stu-id="c9b03-113">For [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Standard Edition, you cannot join the computer to a BizTalk group, so the above approach is not suitable.</span></span> <span data-ttu-id="c9b03-114">我们概述以下必要步骤，以设置一台新计算机并还原 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置设置，从而使其具备替代功能。</span><span class="sxs-lookup"><span data-stu-id="c9b03-114">Instead, we outline the steps needed to set up a new computer and restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration settings so that it can function as a replacement.</span></span> <span data-ttu-id="c9b03-115">有关详细信息，请参阅[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="c9b03-115">For more information, see [How to Recover the BizTalk Group](../core/how-to-recover-the-biztalk-group.md).</span></span>  
  
## <a name="recovery-phases"></a><span data-ttu-id="c9b03-116">恢复阶段</span><span class="sxs-lookup"><span data-stu-id="c9b03-116">Recovery Phases</span></span>  
 <span data-ttu-id="c9b03-117">运行 BizTalk Server 的计算机的恢复过程可分为以下三个阶段：</span><span class="sxs-lookup"><span data-stu-id="c9b03-117">The recovery of a computer running BizTalk Server can be classified into the following three phases:</span></span>  
  
1.  <span data-ttu-id="c9b03-118">**准备基础平台**</span><span class="sxs-lookup"><span data-stu-id="c9b03-118">**Preparing the Base Platform**</span></span>  
  
     <span data-ttu-id="c9b03-119">此阶段需要准备一个具有基础平台的计算机，该平台需包含操作系统、必备软件和适当的 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="c9b03-119">This phase includes the preparation of a computer with the base platform including the operating system, software prerequisites and appropriate BizTalk Server components.</span></span> <span data-ttu-id="c9b03-120">本指南假定，在尝试还原 BizTalk Server 配置前，计算机已安装了基础平台、必备软件和 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="c9b03-120">This guide assumes that before you attempt to restore the BizTalk Server configuration, you have a computer with the base platform, prerequisites, and BizTalk Server components installed.</span></span> <span data-ttu-id="c9b03-121">本指南不涉及基础平台的还原。</span><span class="sxs-lookup"><span data-stu-id="c9b03-121">This guide does not cover base platform restoration.</span></span>  
  
2.  <span data-ttu-id="c9b03-122">**还原 BizTalk Server 配置**</span><span class="sxs-lookup"><span data-stu-id="c9b03-122">**Restoring the BizTalk Server Configuration**</span></span>  
  
     <span data-ttu-id="c9b03-123">此阶段假定您已记录了发生故障计算机上的功能，这包括该计算机的 BizTalk Server 配置文件的副本。</span><span class="sxs-lookup"><span data-stu-id="c9b03-123">This phase assumes that you have a record of the features configured on the failed computer, including a copy of the BizTalk Server configuration file for that computer.</span></span> <span data-ttu-id="c9b03-124">本指南将指导您还原 BizTalk Server 配置。</span><span class="sxs-lookup"><span data-stu-id="c9b03-124">This guide provides guidance for restoring the BizTalk Server configuration.</span></span>  
  
3.  <span data-ttu-id="c9b03-125">**还原 BizTalk 应用程序**</span><span class="sxs-lookup"><span data-stu-id="c9b03-125">**Restoring BizTalk Applications**</span></span>  
  
     <span data-ttu-id="c9b03-126">此阶段将在替代计算机上还原与在 BizTalk Server 进程上运行的应用程序连接的 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="c9b03-126">This phase involves restoring the .NET assemblies connected with the applications that are hosted by the BizTalk Server processes on the replacement computer.</span></span> <span data-ttu-id="c9b03-127">所需的所有项目，如 BizTalk 程序集之外的用户程序集，都应该安装到计算机上其各自的位置或全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="c9b03-127">Any artifacts that are needed, such as user assemblies apart from BizTalk assemblies, should be installed in their respective locations or the global assembly cache (GAC) on the computer.</span></span> <span data-ttu-id="c9b03-128">本指南为此阶段提供了一些指导。</span><span class="sxs-lookup"><span data-stu-id="c9b03-128">This guide provides some guidance on this phase.</span></span> <span data-ttu-id="c9b03-129">但是，并不涉及用于还原 BizTalk 应用程序的单独脚本或工具。</span><span class="sxs-lookup"><span data-stu-id="c9b03-129">However, there are no separate scripts or tools for restoring BizTalk applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b03-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b03-130">See Also</span></span>  
 [<span data-ttu-id="c9b03-131">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c9b03-131">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)