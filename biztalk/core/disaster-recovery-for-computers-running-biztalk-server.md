---
title: 运行 BizTalk Server 的计算机的灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7469c97409ce53a995db95b263f5874e737a9905
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350996"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a><span data-ttu-id="b40ea-102">运行 BizTalk Server 的计算机的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="b40ea-102">Disaster Recovery for Computers Running BizTalk Server</span></span>
<span data-ttu-id="b40ea-103">如果你的组织中运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，您应将其替换相同设置的计算机。</span><span class="sxs-lookup"><span data-stu-id="b40ea-103">If the computer running BizTalk Server in your organization suffers an unrecoverable hardware failure, you should replace it with an identical computer.</span></span> <span data-ttu-id="b40ea-104">这假定 BizTalk Server 数据库将保持不变，并故障是其中的任何一种运行 BizTalk Server 的计算机。</span><span class="sxs-lookup"><span data-stu-id="b40ea-104">This assumes that the BizTalk Server databases are intact, and that the failure is in any one of the computers running BizTalk Server.</span></span>  
  
 <span data-ttu-id="b40ea-105">一种可行方法是保持运行 BizTalk Server 安装中的每台计算机的已更新的映像。</span><span class="sxs-lookup"><span data-stu-id="b40ea-105">One possible approach is to maintain an updated image of every computer running BizTalk Server in your installation.</span></span> <span data-ttu-id="b40ea-106">在计算机出现硬件故障，恢复操作只需部署一台新计算机上存储的映像。</span><span class="sxs-lookup"><span data-stu-id="b40ea-106">When a computer suffers a hardware failure, the recovery action is as simple as deploying the stored image on a new computer.</span></span> <span data-ttu-id="b40ea-107">灾难恢复主题讨论其中存储此类映像是不可行的情况。</span><span class="sxs-lookup"><span data-stu-id="b40ea-107">The disaster recovery topics address the case where storing such images is not feasible.</span></span>  
## <a name="recovering-different-editions-of-biztalk-server"></a><span data-ttu-id="b40ea-108">恢复不同版本的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b40ea-108">Recovering Different Editions of BizTalk Server</span></span>  
 <span data-ttu-id="b40ea-109">恢复方法是在计算机上运行的 BizTalk Server 的版本而异。</span><span class="sxs-lookup"><span data-stu-id="b40ea-109">The recovery approach is different depending on the edition of BizTalk Server running on the computer.</span></span>  
  
 <span data-ttu-id="b40ea-110">对于 BizTalk Server 开发人员版和 BizTalk Server Enterprise Edition，多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许。</span><span class="sxs-lookup"><span data-stu-id="b40ea-110">For BizTalk Server Developer Edition and BizTalk Server Enterprise Edition, multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are permitted.</span></span> <span data-ttu-id="b40ea-111">当运行 BizTalk Server 的计算机出现故障时，可以准备一台替代计算机并将其加入到现有的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="b40ea-111">When one of the computers running BizTalk Server fails, you can prepare a replacement computer and join it to the existing BizTalk group.</span></span> <span data-ttu-id="b40ea-112">在这种情况下，可以使用相同的名称或不同的名称的计算机加入到 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="b40ea-112">In this case, you can join a computer with either the same name or a different name to the BizTalk group.</span></span>  
  
 <span data-ttu-id="b40ea-113">对于 BizTalk Server Standard Edition，您不能将计算机加入到 BizTalk 组，所以上述方法不适用。</span><span class="sxs-lookup"><span data-stu-id="b40ea-113">For BizTalk Server Standard Edition, you cannot join the computer to a BizTalk group, so the above approach is not suitable.</span></span> <span data-ttu-id="b40ea-114">相反，我们概述了设置一台新计算机并还原所需的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置设置，从而替代其功能。</span><span class="sxs-lookup"><span data-stu-id="b40ea-114">Instead, we outline the steps needed to set up a new computer and restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration settings so that it can function as a replacement.</span></span> <span data-ttu-id="b40ea-115">有关详细信息，请参阅[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b40ea-115">For more information, see [How to Recover the BizTalk Group](../core/how-to-recover-the-biztalk-group.md).</span></span>  
  
## <a name="recovery-phases"></a><span data-ttu-id="b40ea-116">恢复阶段</span><span class="sxs-lookup"><span data-stu-id="b40ea-116">Recovery Phases</span></span>  
 <span data-ttu-id="b40ea-117">运行 BizTalk Server 的计算机的恢复可分为以下三个阶段：</span><span class="sxs-lookup"><span data-stu-id="b40ea-117">The recovery of a computer running BizTalk Server can be classified into the following three phases:</span></span>  
  
1.  <span data-ttu-id="b40ea-118">**准备基础平台**</span><span class="sxs-lookup"><span data-stu-id="b40ea-118">**Preparing the Base Platform**</span></span>  
  
     <span data-ttu-id="b40ea-119">本阶段包括基本平台包括操作系统、 必备软件和适当的 BizTalk Server 组件的计算机的准备。</span><span class="sxs-lookup"><span data-stu-id="b40ea-119">This phase includes the preparation of a computer with the base platform including the operating system, software prerequisites and appropriate BizTalk Server components.</span></span> <span data-ttu-id="b40ea-120">本指南假定，在尝试还原 BizTalk Server 配置前，必须具有基础平台、 先决条件和安装 BizTalk Server 组件的计算机。</span><span class="sxs-lookup"><span data-stu-id="b40ea-120">This guide assumes that before you attempt to restore the BizTalk Server configuration, you have a computer with the base platform, prerequisites, and BizTalk Server components installed.</span></span> <span data-ttu-id="b40ea-121">本指南不涉及基础平台的还原。</span><span class="sxs-lookup"><span data-stu-id="b40ea-121">This guide does not cover base platform restoration.</span></span>  
  
2.  <span data-ttu-id="b40ea-122">**还原 BizTalk Server 配置**</span><span class="sxs-lookup"><span data-stu-id="b40ea-122">**Restoring the BizTalk Server Configuration**</span></span>  
  
     <span data-ttu-id="b40ea-123">此阶段假定出现故障的计算机，包括该计算机的 BizTalk Server 配置文件的副本上配置的功能的记录。</span><span class="sxs-lookup"><span data-stu-id="b40ea-123">This phase assumes that you have a record of the features configured on the failed computer, including a copy of the BizTalk Server configuration file for that computer.</span></span> <span data-ttu-id="b40ea-124">本指南提供有关还原 BizTalk Server 配置的指导。</span><span class="sxs-lookup"><span data-stu-id="b40ea-124">This guide provides guidance for restoring the BizTalk Server configuration.</span></span>  
  
3.  <span data-ttu-id="b40ea-125">**还原 BizTalk 应用程序**</span><span class="sxs-lookup"><span data-stu-id="b40ea-125">**Restoring BizTalk Applications**</span></span>  
  
     <span data-ttu-id="b40ea-126">此阶段涉及到还原与由替代计算机上的 BizTalk Server 进程承载的应用程序相关联的.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="b40ea-126">This phase involves restoring the .NET assemblies connected with the applications that are hosted by the BizTalk Server processes on the replacement computer.</span></span> <span data-ttu-id="b40ea-127">应在其各自的位置或在计算机上的全局程序集缓存 (GAC) 中安装需要如 BizTalk 程序集之外的用户程序集的任何项目。</span><span class="sxs-lookup"><span data-stu-id="b40ea-127">Any artifacts that are needed, such as user assemblies apart from BizTalk assemblies, should be installed in their respective locations or the global assembly cache (GAC) on the computer.</span></span> <span data-ttu-id="b40ea-128">在此阶段，本指南提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="b40ea-128">This guide provides some guidance on this phase.</span></span> <span data-ttu-id="b40ea-129">但是，没有单独的脚本或工具，用于还原 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b40ea-129">However, there are no separate scripts or tools for restoring BizTalk applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40ea-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b40ea-130">See Also</span></span>  
 [<span data-ttu-id="b40ea-131">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b40ea-131">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)