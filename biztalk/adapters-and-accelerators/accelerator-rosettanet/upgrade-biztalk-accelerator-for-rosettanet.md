---
title: "升级在 BizTalk Server 中的 RosettaNet 快捷键 (BTARN) |Microsoft 文档\""
description: "请按照更新 BTARN 到 BizTalk Server 中的当前版本的升级步骤"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 16e6083f3e5fb1778d77536cd602ee2208c0005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-the-rosettanet-accelerator"></a><span data-ttu-id="307b4-103">升级 RosettaNet 快捷键</span><span class="sxs-lookup"><span data-stu-id="307b4-103">Upgrade the RosettaNet accelerator</span></span>

## <a name="upgrade-overview"></a><span data-ttu-id="307b4-104">升级概述</span><span class="sxs-lookup"><span data-stu-id="307b4-104">Upgrade overview</span></span>
<span data-ttu-id="307b4-105">可以将 BizTalk Accelerator for RosettaNet (BTARN) 安装以前版本升级到最新版本。</span><span class="sxs-lookup"><span data-stu-id="307b4-105">You can upgrade the previous version of the BizTalk Accelerator for RosettaNet (BTARN) installation to the current version.</span></span> <span data-ttu-id="307b4-106">升级过程包括升级 BizTalk Server 中，然后升级 BTARN。</span><span class="sxs-lookup"><span data-stu-id="307b4-106">The upgrade process involves upgrading BizTalk Server, and then upgrading BTARN.</span></span>  
  
 <span data-ttu-id="307b4-107">你可以升级到 BTARN 的先前版本中通过运行 BTARN 安装程序。</span><span class="sxs-lookup"><span data-stu-id="307b4-107">You can upgrade from the previous version of BTARN to a by running the BTARN installation program.</span></span> <span data-ttu-id="307b4-108">安装程序将 BTRAN 配置信息迁移到最新版本。</span><span class="sxs-lookup"><span data-stu-id="307b4-108">The setup migrates the BTRAN configuration information to the current version.</span></span>  
  
 <span data-ttu-id="307b4-109">在多服务器 BTARN 环境中，应升级所有 BizTalk 服务器，然后再到 BTARN。</span><span class="sxs-lookup"><span data-stu-id="307b4-109">In a multi-server BTARN environment, you should upgrade all BizTalk Servers first, and then to BTARN.</span></span> <span data-ttu-id="307b4-110">请按以下顺序迁移服务器：</span><span class="sxs-lookup"><span data-stu-id="307b4-110">Migrate your servers in the following order:</span></span>  
  
-   <span data-ttu-id="307b4-111">承载 BizTalk 组的服务器</span><span class="sxs-lookup"><span data-stu-id="307b4-111">The server hosting the BizTalk Group</span></span>  
  
-   <span data-ttu-id="307b4-112">各个处理节点</span><span class="sxs-lookup"><span data-stu-id="307b4-112">Each processing node</span></span>  
  
-   <span data-ttu-id="307b4-113">BAM 门户服务器</span><span class="sxs-lookup"><span data-stu-id="307b4-113">The BAM portal server</span></span>  
  
 <span data-ttu-id="307b4-114">BTARN 在升级过程，请确保你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="307b4-114">In the BTARN upgrade process, ensure you do the following:</span></span>  
  
-   <span data-ttu-id="307b4-115">检查 SQL Server (MSSQLSERVER) 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="307b4-115">Check if the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="307b4-116">切勿运行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="307b4-116">Do not run a silent installation.</span></span>  
  
## <a name="upgrade-steps"></a><span data-ttu-id="307b4-117">升级步骤</span><span class="sxs-lookup"><span data-stu-id="307b4-117">Upgrade steps</span></span>  
  
1.  <span data-ttu-id="307b4-118">升级 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="307b4-118">Upgrade BizTalk Server.</span></span> <span data-ttu-id="307b4-119">请参阅[BizTalk Server 最新内容、 安装、 配置和升级](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="307b4-119">See [BizTalk Server What's New, Installation, Configuration, and Upgrade](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
2.  <span data-ttu-id="307b4-120">备份 BTARN 数据库和 BTARN 消息架构。</span><span class="sxs-lookup"><span data-stu-id="307b4-120">Back up the BTARN database and BTARN message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="307b4-121">你应备份出于安全原因 BTARN 数据库。</span><span class="sxs-lookup"><span data-stu-id="307b4-121">You should back up the BTARN database for safety reasons.</span></span> <span data-ttu-id="307b4-122">安装程序将 BTRAN 数据库迁移到较新版本。</span><span class="sxs-lookup"><span data-stu-id="307b4-122">The installation program migrates the BTRAN database to the newer version.</span></span>  
  
3.  <span data-ttu-id="307b4-123">备份下的任何文件*< 驱动器\>*: \Program Files\\Microsoft BizTalk Accelerator RosettaNet 文件夹所做更改，例如，文件 SDK 中。</span><span class="sxs-lookup"><span data-stu-id="307b4-123">Back up any files under the *<drive\>*:\Program Files\\Microsoft BizTalk Accelerator for RosettaNet folder that you have made changes to, for example, files in the SDK.</span></span>  
  
4.  <span data-ttu-id="307b4-124">取消部署引用一个或多个早期版本 BTARN 程序集的项目或程序集。</span><span class="sxs-lookup"><span data-stu-id="307b4-124">Undeploy any projects or assemblies that have references to one or more of the previous versions of BTARN assemblies.</span></span>  
  
5.  <span data-ttu-id="307b4-125">在 Visual Studio 中，手动取消部署所有 BTARN 程序集，按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="307b4-125">In Visual Studio, manually undeploy all BTARN assemblies, in the following order:</span></span>  
  
    -   <span data-ttu-id="307b4-126">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="307b4-126">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="307b4-127">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="307b4-127">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="307b4-128">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="307b4-128">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="307b4-129">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="307b4-129">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="307b4-130">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="307b4-130">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="307b4-131">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="307b4-131">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="307b4-132">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="307b4-132">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="307b4-133">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="307b4-133">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="307b4-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="307b4-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="307b4-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="307b4-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="307b4-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="307b4-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
6.  <span data-ttu-id="307b4-137">运行 BTARN 安装。</span><span class="sxs-lookup"><span data-stu-id="307b4-137">Run the BTARN installation.</span></span> <span data-ttu-id="307b4-138">请参阅[安装和配置 RosettaNet 快捷键](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="307b4-138">See [Install and configure the RosettaNet accelerator](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
7.  <span data-ttu-id="307b4-139">使用**BTSTask.exe** (files\microsoft BizTalk Server) 手动重新部署 BTARN 程序集按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="307b4-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) to manually redeploy the BTARN assemblies in the following order:</span></span>  
  
    -   <span data-ttu-id="307b4-140">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="307b4-140">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="307b4-141">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="307b4-141">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="307b4-142">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="307b4-142">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="307b4-143">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="307b4-143">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="307b4-144">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="307b4-144">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="307b4-145">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="307b4-145">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="307b4-146">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="307b4-146">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="307b4-147">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="307b4-147">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="307b4-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="307b4-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="307b4-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="307b4-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="307b4-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="307b4-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="307b4-151">有关详细信息**BTSTask.exe**，请参阅 BizTalk Server 帮助中的"BTSTask 命令行参考"主题。</span><span class="sxs-lookup"><span data-stu-id="307b4-151">For more information about **BTSTask.exe**, see the "BTSTask Command-line Reference" topic in BizTalk Server Help.</span></span>  
  
8.  <span data-ttu-id="307b4-152">重新生成的任何项目或程序集引用了一个或多个 [BTARN 程序集。</span><span class="sxs-lookup"><span data-stu-id="307b4-152">Rebuild any projects or assemblies that have a reference to one or more of the [BTARN assemblies.</span></span> <span data-ttu-id="307b4-153">使用**BTSTask.exe**手动重新部署这些项目。</span><span class="sxs-lookup"><span data-stu-id="307b4-153">Use **BTSTask.exe** to manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="307b4-154">对于以下各项，请将 IIS 中的虚拟文件夹从 ASP.NET 2.0 升级到 ASP.NET 4.0：</span><span class="sxs-lookup"><span data-stu-id="307b4-154">Upgrade the virtual folders in IIS from ASP.NET 2.0 to ASP.NET 4.0 for the following:</span></span>  
  
    -   <span data-ttu-id="307b4-155">BTARNApp</span><span class="sxs-lookup"><span data-stu-id="307b4-155">BTARNApp</span></span>  
  
    -   <span data-ttu-id="307b4-156">BTARNHttpReceive</span><span class="sxs-lookup"><span data-stu-id="307b4-156">BTARNHttpReceive</span></span>  
  
10. <span data-ttu-id="307b4-157">重新启动计算机以应用所作的任何修改。</span><span class="sxs-lookup"><span data-stu-id="307b4-157">Restart the computer to apply any modifications done.</span></span>  
  
