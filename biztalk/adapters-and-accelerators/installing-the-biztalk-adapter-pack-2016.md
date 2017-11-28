---
title: "安装 BizTalk 适配器包 2016年 |Microsoft 文档"
description: "在无提示模式下安装的 BAP 2016，32 位与 64 位的典型或自定义安装"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0939ddaa11e409ec42989062e28314c14277549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="4c694-103">安装 BizTalk 适配器包 2016</span><span class="sxs-lookup"><span data-stu-id="4c694-103">Install the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="4c694-104">安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="4c694-104">Install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="4c694-105">**在交互模式中**： 运行安装程序向导</span><span class="sxs-lookup"><span data-stu-id="4c694-105">**In interactive mode**: Run the setup wizard</span></span>  
  
-   <span data-ttu-id="4c694-106">**在静默模式下**： 使用命令行</span><span class="sxs-lookup"><span data-stu-id="4c694-106">**In silent mode**: Use the command line</span></span>  
  
> [!IMPORTANT]
> - <span data-ttu-id="4c694-107">必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不管是否使用安装向导或命令行。</span><span class="sxs-lookup"><span data-stu-id="4c694-107">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard, or the command line.</span></span>  
> - <span data-ttu-id="4c694-108">为确保 all[软件必备项](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)在安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-108">Be sure all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

## <a name="typical-vs-custom-installation"></a><span data-ttu-id="4c694-109">典型安装与自定义安装</span><span class="sxs-lookup"><span data-stu-id="4c694-109">Typical vs custom installation</span></span>  
<span data-ttu-id="4c694-110">列出的安装类型，以及每个选项安装的功能：</span><span class="sxs-lookup"><span data-stu-id="4c694-110">Lists the installation types, and the features that are installed with each option:</span></span>  
  
-   <span data-ttu-id="4c694-111">**典型**和**完成**选项安装所有的适配器，请与关联的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="4c694-111">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="4c694-112">你没有选择特定的适配器的安装的选项。</span><span class="sxs-lookup"><span data-stu-id="4c694-112">You do not have the option of choosing a specific adapter to install.</span></span>  
  
-   <span data-ttu-id="4c694-113">**自定义**选项与关联的数据提供程序安装一个或多个适配器。</span><span class="sxs-lookup"><span data-stu-id="4c694-113">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="4c694-114">你可以选择要安装哪些适配器。</span><span class="sxs-lookup"><span data-stu-id="4c694-114">You can choose which adapters to install.</span></span> <span data-ttu-id="4c694-115">如果你选择安装数据提供程序，你还必须安装相应的适配器。</span><span class="sxs-lookup"><span data-stu-id="4c694-115">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="4c694-116">但是，你可以安装适配器，而无需安装相应的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="4c694-116">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="4c694-117">执行此操作通过展开**ADO 提供程序**节点，，然后选择你不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="4c694-117">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="4c694-118">请参阅**使用安装向导安装**（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="4c694-118">See **Install using the setup wizard** (in this topic).</span></span>  
  
     <span data-ttu-id="4c694-119">例如，如果你安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-119">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="4c694-120">但是，你可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-120">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
## <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="4c694-121">32 位和 64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="4c694-121">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="4c694-122">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="4c694-122">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="4c694-123">设计时 （在生成 LOB 应用程序上的操作的元数据）</span><span class="sxs-lookup"><span data-stu-id="4c694-123"> design time (when generating metadata for operations on LOB applications)</span></span>
  
-   <span data-ttu-id="4c694-124">BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时</span><span class="sxs-lookup"><span data-stu-id="4c694-124">BizTalk Server Administration console design time (for creating physical ports)</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="4c694-125">BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="4c694-125">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="4c694-126">BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）</span><span class="sxs-lookup"><span data-stu-id="4c694-126">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="4c694-127">你可以为所有这些大小，使用一台计算机，或使用不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="4c694-127">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="4c694-128">因为同时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]你在其中完成的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="4c694-128">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

### <a name="32-bit-install-scenario"></a><span data-ttu-id="4c694-129">32 位安装方案</span><span class="sxs-lookup"><span data-stu-id="4c694-129">32-bit install scenario</span></span>
<span data-ttu-id="4c694-130">每台计算机上安装以下软件。</span><span class="sxs-lookup"><span data-stu-id="4c694-130">Install the following software on each computer.</span></span> <span data-ttu-id="4c694-131">如果你使用的一台计算机，则必须在该计算机上安装所有软件。</span><span class="sxs-lookup"><span data-stu-id="4c694-131">If you are using a single computer, all the software must be installed on that computer.</span></span> 
 
1. <span data-ttu-id="4c694-132">安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c694-132">Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span></span>
2. <span data-ttu-id="4c694-133">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-133">Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>
3. <span data-ttu-id="4c694-134">安装 32 位 LOB 客户端和其他所需 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-134">Install 32-bit LOB client and other required DLLs.</span></span>  
  
### <a name="64-bit-install-scenarios"></a><span data-ttu-id="4c694-135">64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="4c694-135">64-bit install scenarios</span></span>
  
|<span data-ttu-id="4c694-136">为 Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="4c694-136">For Visual Studio design time</span></span>|<span data-ttu-id="4c694-137">为 BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="4c694-137">For BizTalk MMC design time</span></span>|<span data-ttu-id="4c694-138">有关 BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="4c694-138">For BizTalk run time</span></span>|<span data-ttu-id="4c694-139">Visual Studio 设计时间和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="4c694-139">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="4c694-140">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-140">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-141">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-141">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-142">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-142">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="4c694-143">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-143">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-144">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-144">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-145">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-145">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="4c694-146">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="4c694-146">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="4c694-147">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-147">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-148">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-148">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-149">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-149">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="4c694-150">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="4c694-150">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="4c694-151">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-151">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-152">-安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-152">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-153">-安装 64 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-153">- Install 64-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="4c694-154">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="4c694-154">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="4c694-155">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-155">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-156">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-156">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-157">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-157">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="4c694-158">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="4c694-158">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="4c694-159">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-159">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-160">-安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-160">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-161">-安装 64 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-161">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="4c694-162">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-162">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4c694-163">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4c694-163">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4c694-164">在你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-164">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="install-using-the-setup-wizard"></a><span data-ttu-id="4c694-165">使用安装向导进行安装</span><span class="sxs-lookup"><span data-stu-id="4c694-165">Install using the setup wizard</span></span>  
<span data-ttu-id="4c694-166">安装步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式中。</span><span class="sxs-lookup"><span data-stu-id="4c694-166">Steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode.</span></span>  
  
1.  <span data-ttu-id="4c694-167">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**。</span><span class="sxs-lookup"><span data-stu-id="4c694-167">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.</span></span>  
  
2.  <span data-ttu-id="4c694-168">选择**安装 Microsoft BizTalk 适配器**。</span><span class="sxs-lookup"><span data-stu-id="4c694-168">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="4c694-169">在下一步的窗口中，列出了任何缺少的必备程序。</span><span class="sxs-lookup"><span data-stu-id="4c694-169">In the next window, any missing prerequisite programs are listed.</span></span> <span data-ttu-id="4c694-170">如果缺少任一元素，然后选择缺少的程序，并为您的安装程序安装它。</span><span class="sxs-lookup"><span data-stu-id="4c694-170">If any are missing, then select the missing program, and setup installs it for you.</span></span> 

    <span data-ttu-id="4c694-171">例如，选择**步骤 2： 安装 Microsoft BizTalk 适配器包**或**步骤 3： 安装 Microsoft BizTalk 适配器包 (x64)**。</span><span class="sxs-lookup"><span data-stu-id="4c694-171">For example, select **Step 2: Install Microsoft BizTalk Adapter Pack** or **Step 3: Install Microsoft BizTalk Adapter Pack (x64)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c694-172">如果你正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上虚拟机，安装向导可能会显示一条消息，它正在检查可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="4c694-172">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard may display a message that it's checking for available disk space.</span></span> <span data-ttu-id="4c694-173">如果挂起或只需在这里，会出现此消息，则我们建议你**在无提示模式下安装**（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="4c694-173">If this message appears to hang or just sit there, then we recommend you **Install in silent mode** (in this topic).</span></span>  
  
3.  <span data-ttu-id="4c694-174">在欢迎屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4c694-174">On the Welcome screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="4c694-175">接受最终用户许可协议 (EULA)，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4c694-175">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="4c694-176">在**选择安装类型**:</span><span class="sxs-lookup"><span data-stu-id="4c694-176">In **Choose Setup Type**:</span></span>  
  
    -   <span data-ttu-id="4c694-177">若要安装的最常见的功能，请选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="4c694-177">To install the most common features, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="4c694-178">若要选择你想要安装的适配器，选择**自定义**，然后继续下一步。</span><span class="sxs-lookup"><span data-stu-id="4c694-178">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  
  
    -   <span data-ttu-id="4c694-179">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="4c694-179">To install all the features, select **Complete**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="4c694-180">若要安装使用要与企业应用程序之间的接口，请选择适配器**自定义**安装。</span><span class="sxs-lookup"><span data-stu-id="4c694-180">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  
  
6. <span data-ttu-id="4c694-181">**所需**仅在您选择自定义安装。</span><span class="sxs-lookup"><span data-stu-id="4c694-181">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="4c694-182">如果你选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="4c694-182">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  
  
    1.  <span data-ttu-id="4c694-183">在**自定义安装**，展开**基适配器**若要查看可用的适配器。</span><span class="sxs-lookup"><span data-stu-id="4c694-183">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  
  
    2.  <span data-ttu-id="4c694-184">对于你不希望的适配器，选择该适配器旁边的图标，然后选择**整个功能将不可**。</span><span class="sxs-lookup"><span data-stu-id="4c694-184">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  
  
    3.  <span data-ttu-id="4c694-185">展开**ADO 提供程序**，然后选择你不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="4c694-185">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  
  
    4.  <span data-ttu-id="4c694-186">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="4c694-186">Select **Next**.</span></span>  
  
7.  <span data-ttu-id="4c694-187">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="4c694-187">Select **Install**.</span></span>  
  
8.  <span data-ttu-id="4c694-188">在**客户体验改善计划**，你可以选择注册。</span><span class="sxs-lookup"><span data-stu-id="4c694-188">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="4c694-189">如果注册后，你可以与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="4c694-189">If you enroll, you can share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="4c694-190">与你正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-190">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="4c694-191">与你使用的企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-191">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
     <span data-ttu-id="4c694-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c694-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  
     
     <span data-ttu-id="4c694-193">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="4c694-193">Select **OK**.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="4c694-194">你始终可以通过在从修复模式下运行安装程序来更改此设置**程序**。</span><span class="sxs-lookup"><span data-stu-id="4c694-194">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  
  
9. <span data-ttu-id="4c694-195">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="4c694-195">Select **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a><span data-ttu-id="4c694-196">在无提示模式下安装</span><span class="sxs-lookup"><span data-stu-id="4c694-196">Install in silent mode</span></span>  
 <span data-ttu-id="4c694-197">使用**msiexec**命令以执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="4c694-197">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="4c694-198">作为 msiexec 命令的一部分，输入你想要安装的各个组件。</span><span class="sxs-lookup"><span data-stu-id="4c694-198">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="4c694-199">下表列出了每个组件值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c694-199">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="4c694-200">使用这些值来安装 （或删除） 特定的组件。</span><span class="sxs-lookup"><span data-stu-id="4c694-200">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="4c694-201">若要安装 （或删除） 多个组件，可以使用由逗号分隔这些值的组合。</span><span class="sxs-lookup"><span data-stu-id="4c694-201">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  
  
|<span data-ttu-id="4c694-202">组件名称</span><span class="sxs-lookup"><span data-stu-id="4c694-202">Component name</span></span>|<span data-ttu-id="4c694-203">对应的命令行属性值</span><span class="sxs-lookup"><span data-stu-id="4c694-203">Corresponding value for command-line properties</span></span>|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="4c694-204">DbFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-204">DbFeature</span></span>|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="4c694-205">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-205">OracleEBSFeature</span></span>|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="4c694-206">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-206">SapBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="4c694-207">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-207">SiebelBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="4c694-208">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-208">SqlFeature</span></span>|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="4c694-209">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-209">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="4c694-210">**请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="4c694-210">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="4c694-211">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="4c694-211">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="4c694-212">**请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="4c694-212">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span>|  
|<span data-ttu-id="4c694-213">所有组件</span><span class="sxs-lookup"><span data-stu-id="4c694-213">All components</span></span>|<span data-ttu-id="4c694-214">ALL</span><span class="sxs-lookup"><span data-stu-id="4c694-214">ALL</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c694-215">功能名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4c694-215">The feature names are case-sensitive.</span></span>  
  
 <span data-ttu-id="4c694-216">以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。</span><span class="sxs-lookup"><span data-stu-id="4c694-216">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  
  
### <a name="silent-mode-steps"></a><span data-ttu-id="4c694-217">静默模式下的步骤</span><span class="sxs-lookup"><span data-stu-id="4c694-217">Silent mode steps</span></span>
  
1.  <span data-ttu-id="4c694-218">打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="4c694-218">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
2.  <span data-ttu-id="4c694-219">运行基于你想要安装的以下命令：</span><span class="sxs-lookup"><span data-stu-id="4c694-219">Run the following commands based on what you want to install:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c694-220">若要执行无提示安装在基于 x64 的平台上，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。</span><span class="sxs-lookup"><span data-stu-id="4c694-220">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  
  
    -   <span data-ttu-id="4c694-221">若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="4c694-221">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   <span data-ttu-id="4c694-222">仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-222">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   <span data-ttu-id="4c694-223">仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-223">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   <span data-ttu-id="4c694-224">仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-224">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="4c694-225">若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-225">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   <span data-ttu-id="4c694-226">仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-226">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="4c694-227">若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-227">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="4c694-228">仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-228">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   <span data-ttu-id="4c694-229">若要安装的所有基适配器，请键入：</span><span class="sxs-lookup"><span data-stu-id="4c694-229">To install all the base adapters, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   <span data-ttu-id="4c694-230">若要安装两个.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="4c694-230">To install the two .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="4c694-231">任何类型的以逗号分隔各个组件的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="4c694-231">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="4c694-232">例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-232">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="4c694-233">你还可以选择注册 CEIP 的无提示安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c694-233">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="4c694-234">类型：</span><span class="sxs-lookup"><span data-stu-id="4c694-234">Type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         <span data-ttu-id="4c694-235">默认情况下该选项为 false。</span><span class="sxs-lookup"><span data-stu-id="4c694-235">By default the option is false.</span></span> 
  
        > [!IMPORTANT]
        >  <span data-ttu-id="4c694-236">安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的评估版，CEIP 的默认选项为 true。</span><span class="sxs-lookup"><span data-stu-id="4c694-236">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  
  
     <span data-ttu-id="4c694-237">有关详细信息**msiexec**命令中，键入`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="4c694-237">For more information about the **msiexec** command, type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="4c694-238">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="4c694-238">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
     
## <a name="known-install-issue"></a><span data-ttu-id="4c694-239">已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="4c694-239">Known install issue</span></span>
<span data-ttu-id="4c694-240">有关安装相关的问题的完整列表，请参阅**故障排除**为每个适配器的主题。</span><span class="sxs-lookup"><span data-stu-id="4c694-240">For a comprehensive list of installation-related issues, refer to **Troubleshooting** topics for each adapter.</span></span>  
  
<span data-ttu-id="4c694-241">**在 64 位计算机上的运行安装程序可能会访问架构文件时引发错误**</span><span class="sxs-lookup"><span data-stu-id="4c694-241">**Running setup on a 64-bit computer may throw an error while accessing schema file**</span></span>  
  
<span data-ttu-id="4c694-242">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序在访问 Microsoft.Adapters 时引发错误。*\<AdapterName >*_schema.xml 文件，但与适配器安装继续进行。</span><span class="sxs-lookup"><span data-stu-id="4c694-242">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the Microsoft.Adapters.*\<AdapterName>*_schema.xml file, but proceeds with the adapter installation.</span></span>  
  
<span data-ttu-id="4c694-243">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="4c694-243">**Cause**</span></span>  
  
<span data-ttu-id="4c694-244">如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上使用两个目标架构文件是相同。</span><span class="sxs-lookup"><span data-stu-id="4c694-244">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="4c694-245">因此，该文件安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在使用 IIS 时 64 位安装程序会尝试访问它。</span><span class="sxs-lookup"><span data-stu-id="4c694-245">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  
  
<span data-ttu-id="4c694-246">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="4c694-246">**Resolution**</span></span>  
  
<span data-ttu-id="4c694-247">手动复制 Microsoft.Adapters。 *\<AdapterName >*_schema.xml 文件从*C:\Program Files\Microsoft BizTalk 适配器包 (x64) \IIS 架构*到*C:\Windows\System32\inetsrv\config\schema*.</span><span class="sxs-lookup"><span data-stu-id="4c694-247">Manually copy the Microsoft.Adapters.*\<AdapterName>*_schema.xml file from *C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas* to *C:\Windows\System32\inetsrv\config\schema*.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="4c694-248">下一步</span><span class="sxs-lookup"><span data-stu-id="4c694-248">Next step</span></span>
[<span data-ttu-id="4c694-249">安装后步骤</span><span class="sxs-lookup"><span data-stu-id="4c694-249">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)