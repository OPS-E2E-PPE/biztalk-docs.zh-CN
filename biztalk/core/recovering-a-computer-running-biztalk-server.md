---
title: 恢复运行 BizTalk Server 的计算机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a55af6d6-f11a-46e4-9b8e-0a1ca35998c4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f417197e833e314a632351ee309d96ac87556e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398020"
---
# <a name="recovering-a-computer-running-biztalk-server"></a><span data-ttu-id="ee4c5-102">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="ee4c5-102">Recovering a Computer Running BizTalk Server</span></span>
<span data-ttu-id="ee4c5-103">为了恢复运行 BizTalk Server 的计算机，您必须能够访问 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-103">In order to recover a computer running BizTalk Server, you must be able to access the BizTalk Server databases.</span></span> <span data-ttu-id="ee4c5-104">必要时还需还原 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-104">If necessary, restore the BizTalk Server databases.</span></span> <span data-ttu-id="ee4c5-105">另外，在恢复运行 BizTalk Server 的计算机之前，还必须重新安装 BizTalk Server 以及所有的必备软件。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-105">In addition, before you can recover the computer running BizTalk Server, you must reinstall BizTalk Server and all of the prerequisites.</span></span>  
  
 <span data-ttu-id="ee4c5-106">完成这些步骤后，可以使用本部分中说明的过程恢复您的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-106">When these steps are complete, you can use the procedures in this section to recover your BizTalk server.</span></span> <span data-ttu-id="ee4c5-107">恢复 BizTalk Server 所必须遵循的过程取决于您使用的版本。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-107">The procedures you must follow to recover BizTalk Server depend on the edition you are using.</span></span> <span data-ttu-id="ee4c5-108">下表列出了每一个版本所必需的过程。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-108">The following table lists the required procedures for each edition.</span></span>  
  
|<span data-ttu-id="ee4c5-109">任务</span><span class="sxs-lookup"><span data-stu-id="ee4c5-109">Task</span></span>|<span data-ttu-id="ee4c5-110">标准</span><span class="sxs-lookup"><span data-stu-id="ee4c5-110">Standard</span></span>|<span data-ttu-id="ee4c5-111">开发人员</span><span class="sxs-lookup"><span data-stu-id="ee4c5-111">Developer</span></span>|<span data-ttu-id="ee4c5-112">Enterprise</span><span class="sxs-lookup"><span data-stu-id="ee4c5-112">Enterprise</span></span>|  
|----------|--------------|---------------|----------------|  
|<span data-ttu-id="ee4c5-113">**如何还原证书存储区**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-113">**How to Restore the Certificate Store**</span></span>|<span data-ttu-id="ee4c5-114">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-114">**X**</span></span>|||  
|<span data-ttu-id="ee4c5-115">**如何恢复企业单一登录 (SSO)**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-115">**How to Recover Enterprise Single Sign-On (SSO)**</span></span>|<span data-ttu-id="ee4c5-116">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-116">**X**</span></span>|<span data-ttu-id="ee4c5-117">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-117">**X**</span></span>|<span data-ttu-id="ee4c5-118">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-118">**X**</span></span>|  
|<span data-ttu-id="ee4c5-119">**如何恢复 BizTalk 组**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-119">**How to Recover the BizTalk Group**</span></span>|<span data-ttu-id="ee4c5-120">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-120">**X**</span></span>|<span data-ttu-id="ee4c5-121">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-121">**X**</span></span>|<span data-ttu-id="ee4c5-122">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-122">**X**</span></span>|  
|<span data-ttu-id="ee4c5-123">**如何恢复 BizTalk Server 配置**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-123">**How to Recover the BizTalk Server Configuration**</span></span>|<span data-ttu-id="ee4c5-124">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-124">**X**</span></span>|<span data-ttu-id="ee4c5-125">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-125">**X**</span></span>|<span data-ttu-id="ee4c5-126">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-126">**X**</span></span>|  
|<span data-ttu-id="ee4c5-127">**如何恢复 BAM 警报**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-127">**How to Recover BAM Alerts**</span></span><br /><br /> <span data-ttu-id="ee4c5-128">除非正在使用 BAM，否则无需此过程。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-128">Not required unless you're using BAM.</span></span>|<span data-ttu-id="ee4c5-129">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-129">**X**</span></span>|<span data-ttu-id="ee4c5-130">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-130">**X**</span></span>|<span data-ttu-id="ee4c5-131">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-131">**X**</span></span>|  
|<span data-ttu-id="ee4c5-132">**如何恢复 BAM 门户**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-132">**How to Recover the BAM Portal**</span></span><br /><br /> <span data-ttu-id="ee4c5-133">除非正在使用 BAM，否则无需此过程。</span><span class="sxs-lookup"><span data-stu-id="ee4c5-133">Not required unless you're using BAM.</span></span>|<span data-ttu-id="ee4c5-134">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-134">**X**</span></span>|<span data-ttu-id="ee4c5-135">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-135">**X**</span></span>|<span data-ttu-id="ee4c5-136">**X**</span><span class="sxs-lookup"><span data-stu-id="ee4c5-136">**X**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="ee4c5-137">本节内容</span><span class="sxs-lookup"><span data-stu-id="ee4c5-137">In This Section</span></span>  
  
-   [<span data-ttu-id="ee4c5-138">如何还原证书存储区</span><span class="sxs-lookup"><span data-stu-id="ee4c5-138">How to Restore the Certificate Store</span></span>](../core/how-to-restore-the-certificate-store.md)  
  
-   [<span data-ttu-id="ee4c5-139">如何恢复企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ee4c5-139">How to Recover Enterprise Single Sign-On</span></span>](../core/how-to-recover-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="ee4c5-140">如何恢复 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="ee4c5-140">How to Recover the BizTalk Group</span></span>](../core/how-to-recover-the-biztalk-group.md)  
  
-   [<span data-ttu-id="ee4c5-141">如何恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="ee4c5-141">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="ee4c5-142">如何恢复 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="ee4c5-142">How to Recover BAM Alerts</span></span>](../core/how-to-recover-bam-alerts.md)  
  
-   [<span data-ttu-id="ee4c5-143">如何恢复 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="ee4c5-143">How to Recover the BAM Portal</span></span>](../core/how-to-recover-the-bam-portal.md)