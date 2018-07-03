---
title: 升级 BizTalk Server 中的 RosettaNet 加速器 (BTARN) |Microsoft Docs"
description: 请按照升级步骤更新到 BizTalk Server 中的当前版本的 BTARN
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 80e813ced767cdd56910027b655060e1db9f91fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011294"
---
# <a name="upgrade-the-rosettanet-accelerator"></a><span data-ttu-id="e8406-103">升级 RosettaNet 加速器</span><span class="sxs-lookup"><span data-stu-id="e8406-103">Upgrade the RosettaNet accelerator</span></span>

## <a name="upgrade-overview"></a><span data-ttu-id="e8406-104">升级概述</span><span class="sxs-lookup"><span data-stu-id="e8406-104">Upgrade overview</span></span>
<span data-ttu-id="e8406-105">你可以升级到最新版本的以前版本的 BizTalk Accelerator for RosettaNet (BTARN) 安装。</span><span class="sxs-lookup"><span data-stu-id="e8406-105">You can upgrade the previous version of the BizTalk Accelerator for RosettaNet (BTARN) installation to the current version.</span></span> <span data-ttu-id="e8406-106">升级过程包括升级 BizTalk Server 以及然后升级 BTARN。</span><span class="sxs-lookup"><span data-stu-id="e8406-106">The upgrade process involves upgrading BizTalk Server, and then upgrading BTARN.</span></span>  
  
 <span data-ttu-id="e8406-107">可以升级从以前版本的 BTARN 到通过运行 BTARN 安装程序。</span><span class="sxs-lookup"><span data-stu-id="e8406-107">You can upgrade from the previous version of BTARN to a by running the BTARN installation program.</span></span> <span data-ttu-id="e8406-108">安装程序会将 BTRAN 配置信息迁移到最新版本。</span><span class="sxs-lookup"><span data-stu-id="e8406-108">The setup migrates the BTRAN configuration information to the current version.</span></span>  
  
 <span data-ttu-id="e8406-109">在多服务器 BTARN 环境中，应升级所有 BizTalk Server，然后再到 BTARN。</span><span class="sxs-lookup"><span data-stu-id="e8406-109">In a multi-server BTARN environment, you should upgrade all BizTalk Servers first, and then to BTARN.</span></span> <span data-ttu-id="e8406-110">请按以下顺序迁移服务器：</span><span class="sxs-lookup"><span data-stu-id="e8406-110">Migrate your servers in the following order:</span></span>  
  
- <span data-ttu-id="e8406-111">承载 BizTalk 组的服务器</span><span class="sxs-lookup"><span data-stu-id="e8406-111">The server hosting the BizTalk Group</span></span>  
  
- <span data-ttu-id="e8406-112">各个处理节点</span><span class="sxs-lookup"><span data-stu-id="e8406-112">Each processing node</span></span>  
  
- <span data-ttu-id="e8406-113">BAM 门户服务器</span><span class="sxs-lookup"><span data-stu-id="e8406-113">The BAM portal server</span></span>  
  
  <span data-ttu-id="e8406-114">BTARN 中升级过程，请确保您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8406-114">In the BTARN upgrade process, ensure you do the following:</span></span>  
  
- <span data-ttu-id="e8406-115">检查 SQL Server (MSSQLSERVER) 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="e8406-115">Check if the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="e8406-116">切勿运行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="e8406-116">Do not run a silent installation.</span></span>  
  
## <a name="upgrade-steps"></a><span data-ttu-id="e8406-117">升级步骤</span><span class="sxs-lookup"><span data-stu-id="e8406-117">Upgrade steps</span></span>  
  
1.  <span data-ttu-id="e8406-118">升级 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="e8406-118">Upgrade BizTalk Server.</span></span> <span data-ttu-id="e8406-119">请参阅[BizTalk Server 最新内容、 安装、 配置和升级](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="e8406-119">See [BizTalk Server What's New, Installation, Configuration, and Upgrade](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
2.  <span data-ttu-id="e8406-120">备份 BTARN 数据库和 BTARN 消息架构。</span><span class="sxs-lookup"><span data-stu-id="e8406-120">Back up the BTARN database and BTARN message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8406-121">您应备份出于安全考虑在 BTARN 数据库。</span><span class="sxs-lookup"><span data-stu-id="e8406-121">You should back up the BTARN database for safety reasons.</span></span> <span data-ttu-id="e8406-122">安装程序会将 BTRAN 数据库迁移到较新版本。</span><span class="sxs-lookup"><span data-stu-id="e8406-122">The installation program migrates the BTRAN database to the newer version.</span></span>  
  
3.  <span data-ttu-id="e8406-123">备份下的任何文件 *< 驱动器\>*: \Program Files\\Microsoft BizTalk Accelerator RosettaNet 文件夹所做的更改，例如，SDK 中的文件。</span><span class="sxs-lookup"><span data-stu-id="e8406-123">Back up any files under the *<drive\>*:\Program Files\\Microsoft BizTalk Accelerator for RosettaNet folder that you have made changes to, for example, files in the SDK.</span></span>  
  
4.  <span data-ttu-id="e8406-124">取消部署引用一个或多个早期版本 BTARN 程序集的项目或程序集。</span><span class="sxs-lookup"><span data-stu-id="e8406-124">Undeploy any projects or assemblies that have references to one or more of the previous versions of BTARN assemblies.</span></span>  
  
5.  <span data-ttu-id="e8406-125">在 Visual Studio 中，手动取消部署所有 BTARN 程序集，按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="e8406-125">In Visual Studio, manually undeploy all BTARN assemblies, in the following order:</span></span>  
  
    -   <span data-ttu-id="e8406-126">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="e8406-126">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="e8406-127">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="e8406-127">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="e8406-128">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="e8406-128">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="e8406-129">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="e8406-129">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="e8406-130">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="e8406-130">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="e8406-131">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="e8406-131">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="e8406-132">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="e8406-132">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="e8406-133">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="e8406-133">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="e8406-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="e8406-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="e8406-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="e8406-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="e8406-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="e8406-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
6.  <span data-ttu-id="e8406-137">运行 BTARN 安装。</span><span class="sxs-lookup"><span data-stu-id="e8406-137">Run the BTARN installation.</span></span> <span data-ttu-id="e8406-138">请参阅[安装和配置 RosettaNet 加速器](install-configure-biztalk-accelerator-for-rosettanet.md)。</span><span class="sxs-lookup"><span data-stu-id="e8406-138">See [Install and configure the RosettaNet accelerator](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
7.  <span data-ttu-id="e8406-139">使用**BTSTask.exe** (\Program Files\Microsoft BizTalk Server) 来手动重新部署 BTARN 程序集按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="e8406-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) to manually redeploy the BTARN assemblies in the following order:</span></span>  
  
    -   <span data-ttu-id="e8406-140">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="e8406-140">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="e8406-141">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="e8406-141">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="e8406-142">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="e8406-142">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="e8406-143">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="e8406-143">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="e8406-144">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="e8406-144">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="e8406-145">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="e8406-145">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="e8406-146">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="e8406-146">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="e8406-147">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="e8406-147">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="e8406-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="e8406-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="e8406-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="e8406-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="e8406-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span><span class="sxs-lookup"><span data-stu-id="e8406-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8406-151">有关详细信息**BTSTask.exe**，请参阅 BizTalk Server 帮助中的"BTSTask 命令行参考"主题。</span><span class="sxs-lookup"><span data-stu-id="e8406-151">For more information about **BTSTask.exe**, see the "BTSTask Command-line Reference" topic in BizTalk Server Help.</span></span>  
  
8.  <span data-ttu-id="e8406-152">重新生成任何项目或程序集引用了一个或多个 [BTARN 程序集。</span><span class="sxs-lookup"><span data-stu-id="e8406-152">Rebuild any projects or assemblies that have a reference to one or more of the [BTARN assemblies.</span></span> <span data-ttu-id="e8406-153">使用**BTSTask.exe**手动重新部署这些项目。</span><span class="sxs-lookup"><span data-stu-id="e8406-153">Use **BTSTask.exe** to manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="e8406-154">对于以下各项，请将 IIS 中的虚拟文件夹从 ASP.NET 2.0 升级到 ASP.NET 4.0：</span><span class="sxs-lookup"><span data-stu-id="e8406-154">Upgrade the virtual folders in IIS from ASP.NET 2.0 to ASP.NET 4.0 for the following:</span></span>  
  
    -   <span data-ttu-id="e8406-155">BTARNApp</span><span class="sxs-lookup"><span data-stu-id="e8406-155">BTARNApp</span></span>  
  
    -   <span data-ttu-id="e8406-156">BTARNHttpReceive</span><span class="sxs-lookup"><span data-stu-id="e8406-156">BTARNHttpReceive</span></span>  
  
10. <span data-ttu-id="e8406-157">重新启动计算机以应用所作的任何修改。</span><span class="sxs-lookup"><span data-stu-id="e8406-157">Restart the computer to apply any modifications done.</span></span>  
  
