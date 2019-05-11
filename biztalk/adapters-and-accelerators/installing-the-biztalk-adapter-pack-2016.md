---
title: 安装 BizTalk 适配器包 2016年 |Microsoft Docs
description: 在无提示模式下安装 BAP 2016，32 位与 64 位的典型或自定义安装
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ccbffa606db9f26448ee74198eeb4ec67bee94d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363953"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="a2608-103">安装 BizTalk 适配器包 2016</span><span class="sxs-lookup"><span data-stu-id="a2608-103">Install the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="a2608-104">安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="a2608-104">Install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  

-   <span data-ttu-id="a2608-105">**在交互模式下**:运行安装程序向导</span><span class="sxs-lookup"><span data-stu-id="a2608-105">**In interactive mode**: Run the setup wizard</span></span>  

-   <span data-ttu-id="a2608-106">**在静默模式下**:使用命令行</span><span class="sxs-lookup"><span data-stu-id="a2608-106">**In silent mode**: Use the command line</span></span>  

> [!IMPORTANT]
> - <span data-ttu-id="a2608-107">必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不考虑是否要安装使用向导或命令行。</span><span class="sxs-lookup"><span data-stu-id="a2608-107">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard, or the command line.</span></span>  
> - <span data-ttu-id="a2608-108">为确保 all[必备软件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-108">Be sure all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

## <a name="typical-vs-custom-installation"></a><span data-ttu-id="a2608-109">典型安装与自定义安装</span><span class="sxs-lookup"><span data-stu-id="a2608-109">Typical vs custom installation</span></span>  
<span data-ttu-id="a2608-110">列出了安装类型，以及每个选项安装的功能：</span><span class="sxs-lookup"><span data-stu-id="a2608-110">Lists the installation types, and the features that are installed with each option:</span></span>  

- <span data-ttu-id="a2608-111">**典型**并**完成**选项与关联的数据提供程序安装所有适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-111">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="a2608-112">没有选择特定的适配器的安装的选项。</span><span class="sxs-lookup"><span data-stu-id="a2608-112">You do not have the option of choosing a specific adapter to install.</span></span>  

- <span data-ttu-id="a2608-113">**自定义**选项与关联的数据提供程序将安装一个或多个适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-113">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="a2608-114">你可以选择要安装的适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-114">You can choose which adapters to install.</span></span> <span data-ttu-id="a2608-115">如果您选择安装数据提供程序，还必须安装相应的适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-115">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="a2608-116">但是，你可以无需安装相应的数据提供程序安装适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-116">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="a2608-117">执行此操作通过展开**ADO 提供程序**节点，并选择不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="a2608-117">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="a2608-118">请参阅**使用安装向导安装**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="a2608-118">See **Install using the setup wizard** (in this topic).</span></span>  

   <span data-ttu-id="a2608-119">例如，如果在安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-119">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a2608-120">但是，可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-120">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  

## <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="a2608-121">32 位和 64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="a2608-121">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="a2608-122">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="a2608-122">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="a2608-123">设计时 （时生成的操作的 LOB 应用程序的元数据）</span><span class="sxs-lookup"><span data-stu-id="a2608-123">design time (when generating metadata for operations on LOB applications)</span></span>

- <span data-ttu-id="a2608-124">BizTalk Server 管理控制台 （用于创建物理端口） 的设计时</span><span class="sxs-lookup"><span data-stu-id="a2608-124">BizTalk Server Administration console design time (for creating physical ports)</span></span>

  > [!NOTE]
  >  <span data-ttu-id="a2608-125">BizTalk Server 管理控制台作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="a2608-125">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  

- <span data-ttu-id="a2608-126">BizTalk 运行时 （发送和接收消息时的 LOB 应用程序）</span><span class="sxs-lookup"><span data-stu-id="a2608-126">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="a2608-127">可以为所有这些任务，使用一台计算机，也可以使用不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="a2608-127">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="a2608-128">因为这两[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以及 BizTalk MMC 是 32 位进程，你必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]中完成的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="a2608-128">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

### <a name="32-bit-install-scenario"></a><span data-ttu-id="a2608-129">32 位安装方案</span><span class="sxs-lookup"><span data-stu-id="a2608-129">32-bit install scenario</span></span>
<span data-ttu-id="a2608-130">每台计算机上安装以下软件。</span><span class="sxs-lookup"><span data-stu-id="a2608-130">Install the following software on each computer.</span></span> <span data-ttu-id="a2608-131">如果使用一台计算机，则必须在该计算机上安装所有软件。</span><span class="sxs-lookup"><span data-stu-id="a2608-131">If you are using a single computer, all the software must be installed on that computer.</span></span> 

1. <span data-ttu-id="a2608-132">安装 32 位 [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2608-132">Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</span></span>
2. <span data-ttu-id="a2608-133">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-133">Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>
3. <span data-ttu-id="a2608-134">安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-134">Install 32-bit LOB client and other required DLLs.</span></span>  

### <a name="64-bit-install-scenarios"></a><span data-ttu-id="a2608-135">64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="a2608-135">64-bit install scenarios</span></span>

|                                                                                                                 <span data-ttu-id="a2608-136">为 Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="a2608-136">For Visual Studio design time</span></span>                                                                                                                  |                                                                                                                  <span data-ttu-id="a2608-137">为 BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="a2608-137">For BizTalk MMC design time</span></span>                                                                                                                   |                                                                                                                                                                                                                                                                                                         <span data-ttu-id="a2608-138">Biztalk 运行时</span><span class="sxs-lookup"><span data-stu-id="a2608-138">For BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                <span data-ttu-id="a2608-139">Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="a2608-139">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a2608-140">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-140">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-141">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-141">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-142">-安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-142">- Install 32-bit LOB client and other required DLLs.</span></span> | <span data-ttu-id="a2608-143">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-143">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-144">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-144">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-145">-安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-145">- Install 32-bit LOB client and other required DLLs.</span></span> | <span data-ttu-id="a2608-146">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="a2608-146">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="a2608-147">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-147">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-148">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-148">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-149">-安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-149">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="a2608-150">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="a2608-150">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="a2608-151">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-151">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-152">安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-152">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-153">-安装 64 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-153">- Install 64-bit LOB client and other required DLLs.</span></span> | <span data-ttu-id="a2608-154">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="a2608-154">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="a2608-155">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-155">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-156">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-156">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-157">-安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-157">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="a2608-158">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="a2608-158">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="a2608-159">安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-159">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-160">安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-160">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-161">-安装 64 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-161">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="a2608-162">安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-162">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a2608-163">-安装 32 位 LOB 客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a2608-163">- Install 32-bit LOB client and other required DLLs.</span></span> |

> [!NOTE]
>  <span data-ttu-id="a2608-164">你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC 中，你必须安装 32 位或[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-164">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  

## <a name="install-using-the-setup-wizard"></a><span data-ttu-id="a2608-165">使用安装向导进行安装</span><span class="sxs-lookup"><span data-stu-id="a2608-165">Install using the setup wizard</span></span>  
<span data-ttu-id="a2608-166">安装步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式下。</span><span class="sxs-lookup"><span data-stu-id="a2608-166">Steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode.</span></span>  

1. <span data-ttu-id="a2608-167">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**。</span><span class="sxs-lookup"><span data-stu-id="a2608-167">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.</span></span>  

2. <span data-ttu-id="a2608-168">选择**安装 Microsoft BizTalk 适配器**。</span><span class="sxs-lookup"><span data-stu-id="a2608-168">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="a2608-169">在下一步的窗口中，列出了任何缺少的必备程序。</span><span class="sxs-lookup"><span data-stu-id="a2608-169">In the next window, any missing prerequisite programs are listed.</span></span> <span data-ttu-id="a2608-170">如果缺少任一元素，然后选择缺少的程序，并为您的安装程序安装它。</span><span class="sxs-lookup"><span data-stu-id="a2608-170">If any are missing, then select the missing program, and setup installs it for you.</span></span> 

   <span data-ttu-id="a2608-171">例如，选择**步骤 2:安装 Microsoft BizTalk 适配器包**或**步骤 3:安装 Microsoft BizTalk 适配器包 (x64)**。</span><span class="sxs-lookup"><span data-stu-id="a2608-171">For example, select **Step 2: Install Microsoft BizTalk Adapter Pack** or **Step 3: Install Microsoft BizTalk Adapter Pack (x64)**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a2608-172">如果您正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]虚拟机上安装向导可能会显示一条消息，它检查可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="a2608-172">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard may display a message that it's checking for available disk space.</span></span> <span data-ttu-id="a2608-173">如果挂起或只是坐在那里，会出现此消息，则我们建议您**在无提示模式下安装**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="a2608-173">If this message appears to hang or just sit there, then we recommend you **Install in silent mode** (in this topic).</span></span>  

3. <span data-ttu-id="a2608-174">在欢迎屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2608-174">On the Welcome screen, select **Next**.</span></span>  

4. <span data-ttu-id="a2608-175">接受最终用户许可协议 (EULA)，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2608-175">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  

5. <span data-ttu-id="a2608-176">在中**选择安装类型**:</span><span class="sxs-lookup"><span data-stu-id="a2608-176">In **Choose Setup Type**:</span></span>  

   -   <span data-ttu-id="a2608-177">若要安装的最常见的功能，请选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="a2608-177">To install the most common features, select **Typical**.</span></span>  

   -   <span data-ttu-id="a2608-178">若要选择你想要安装的适配器，请选择**自定义**，然后继续下一步。</span><span class="sxs-lookup"><span data-stu-id="a2608-178">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  

   -   <span data-ttu-id="a2608-179">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="a2608-179">To install all the features, select **Complete**.</span></span>  

       > [!IMPORTANT]
       >  <span data-ttu-id="a2608-180">若要安装用于与你的企业应用程序中，选择适配器**自定义**安装。</span><span class="sxs-lookup"><span data-stu-id="a2608-180">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  

6. <span data-ttu-id="a2608-181">**所需**仅在您选择自定义安装。</span><span class="sxs-lookup"><span data-stu-id="a2608-181">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="a2608-182">如果选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="a2608-182">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  

    1.  <span data-ttu-id="a2608-183">在中**自定义安装**，展开**基适配器**若要查看可用的适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-183">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  

    2.  <span data-ttu-id="a2608-184">对于不希望适配器，选择适配器旁的图标，然后选择**整个功能将不可**。</span><span class="sxs-lookup"><span data-stu-id="a2608-184">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  

    3.  <span data-ttu-id="a2608-185">展开**ADO 提供程序**，然后选择不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="a2608-185">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  

    4.  <span data-ttu-id="a2608-186">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2608-186">Select **Next**.</span></span>  

7. <span data-ttu-id="a2608-187">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="a2608-187">Select **Install**.</span></span>  

8. <span data-ttu-id="a2608-188">在中**客户体验改善计划**，可以选择进行注册。</span><span class="sxs-lookup"><span data-stu-id="a2608-188">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="a2608-189">如果你注册，可以与 Microsoft 共享的以下数据：</span><span class="sxs-lookup"><span data-stu-id="a2608-189">If you enroll, you can share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="a2608-190">与正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-190">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  

   - <span data-ttu-id="a2608-191">与将用于企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-191">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  

     <span data-ttu-id="a2608-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2608-192">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  

     <span data-ttu-id="a2608-193">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="a2608-193">Select **OK**.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="a2608-194">通过在从修复模式下运行安装程序可以随时更改此设置**程序**。</span><span class="sxs-lookup"><span data-stu-id="a2608-194">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  

9. <span data-ttu-id="a2608-195">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="a2608-195">Select **Finish**.</span></span>  

<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a><span data-ttu-id="a2608-196">在无提示模式下安装</span><span class="sxs-lookup"><span data-stu-id="a2608-196">Install in silent mode</span></span>  
 <span data-ttu-id="a2608-197">使用**msiexec**命令执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="a2608-197">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="a2608-198">作为 msiexec 命令的一部分，输入你想要安装的各个组件。</span><span class="sxs-lookup"><span data-stu-id="a2608-198">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="a2608-199">下表列出了每个组件中的值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a2608-199">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="a2608-200">使用这些值来安装 （或删除） 特定的组件。</span><span class="sxs-lookup"><span data-stu-id="a2608-200">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="a2608-201">若要安装 （或删除） 多个组件，可以使用逗号分隔这些值的组合。</span><span class="sxs-lookup"><span data-stu-id="a2608-201">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  


|                                    <span data-ttu-id="a2608-202">组件名称</span><span class="sxs-lookup"><span data-stu-id="a2608-202">Component name</span></span>                                    |                                                                <span data-ttu-id="a2608-203">命令行属性的相应值</span><span class="sxs-lookup"><span data-stu-id="a2608-203">Corresponding value for command-line properties</span></span>                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   <span data-ttu-id="a2608-204">DbFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-204">DbFeature</span></span>                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                <span data-ttu-id="a2608-205">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-205">OracleEBSFeature</span></span>                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             <span data-ttu-id="a2608-206">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-206">SapBaseAdapterFeature</span></span>                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            <span data-ttu-id="a2608-207">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-207">SiebelBaseAdapterFeature</span></span>                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   <span data-ttu-id="a2608-208">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-208">SqlFeature</span></span>                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     <span data-ttu-id="a2608-209">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-209">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="a2608-210">**请注意**:必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="a2608-210">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | <span data-ttu-id="a2608-211">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="a2608-211">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="a2608-212">**请注意**:必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="a2608-212">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span> |
|                                    <span data-ttu-id="a2608-213">所有组件</span><span class="sxs-lookup"><span data-stu-id="a2608-213">All components</span></span>                                    |                                                                                      <span data-ttu-id="a2608-214">ALL</span><span class="sxs-lookup"><span data-stu-id="a2608-214">ALL</span></span>                                                                                       |

> [!IMPORTANT]
>  <span data-ttu-id="a2608-215">功能名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a2608-215">The feature names are case-sensitive.</span></span>  

 <span data-ttu-id="a2608-216">以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。</span><span class="sxs-lookup"><span data-stu-id="a2608-216">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  

### <a name="silent-mode-steps"></a><span data-ttu-id="a2608-217">无提示模式下的步骤</span><span class="sxs-lookup"><span data-stu-id="a2608-217">Silent mode steps</span></span>

1. <span data-ttu-id="a2608-218">打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="a2608-218">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  

2. <span data-ttu-id="a2608-219">运行以下命令，根据你想要安装：</span><span class="sxs-lookup"><span data-stu-id="a2608-219">Run the following commands based on what you want to install:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a2608-220">若要执行无提示安装的基于 x64 的平台上，替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。</span><span class="sxs-lookup"><span data-stu-id="a2608-220">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  

   - <span data-ttu-id="a2608-221">若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="a2608-221">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - <span data-ttu-id="a2608-222">若要仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-222">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - <span data-ttu-id="a2608-223">若要仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-223">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - <span data-ttu-id="a2608-224">若要仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-224">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - <span data-ttu-id="a2608-225">若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-225">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - <span data-ttu-id="a2608-226">若要仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-226">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - <span data-ttu-id="a2608-227">若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-227">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - <span data-ttu-id="a2608-228">若要仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-228">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - <span data-ttu-id="a2608-229">若要安装所有基适配器，请键入：</span><span class="sxs-lookup"><span data-stu-id="a2608-229">To install all the base adapters, type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - <span data-ttu-id="a2608-230">若要安装两个.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="a2608-230">To install the two .NET Framework Data Providers, type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - <span data-ttu-id="a2608-231">任何类型的用逗号分隔的组件的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="a2608-231">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="a2608-232">例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：</span><span class="sxs-lookup"><span data-stu-id="a2608-232">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - <span data-ttu-id="a2608-233">您还可以选择无提示安装的一部分注册 CEIP。</span><span class="sxs-lookup"><span data-stu-id="a2608-233">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="a2608-234">键入：</span><span class="sxs-lookup"><span data-stu-id="a2608-234">Type:</span></span>  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      <span data-ttu-id="a2608-235">默认情况下，选项为 false。</span><span class="sxs-lookup"><span data-stu-id="a2608-235">By default the option is false.</span></span> 

     > [!IMPORTANT]
     >  <span data-ttu-id="a2608-236">安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]评估版在静默模式下，CEIP 的默认选项为 true。</span><span class="sxs-lookup"><span data-stu-id="a2608-236">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  

     <span data-ttu-id="a2608-237">有关详细信息**msiexec**命令中，键入`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="a2608-237">For more information about the **msiexec** command, type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="a2608-238">或转至[ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="a2608-238">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>

## <a name="known-install-issue"></a><span data-ttu-id="a2608-239">已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="a2608-239">Known install issue</span></span>
<span data-ttu-id="a2608-240">有关与安装相关的问题的完整列表，请参阅**故障排除**每个适配器主题。</span><span class="sxs-lookup"><span data-stu-id="a2608-240">For a comprehensive list of installation-related issues, refer to **Troubleshooting** topics for each adapter.</span></span>  

<span data-ttu-id="a2608-241">**在 64 位计算机上的运行安装程序可能会访问架构文件时引发错误**</span><span class="sxs-lookup"><span data-stu-id="a2608-241">**Running setup on a 64-bit computer may throw an error while accessing schema file**</span></span>  

<span data-ttu-id="a2608-242">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]访问 Microsoft.Adapters 时安装程序将引发错误。*\<AdapterName\>*_schema.xml 文件，但继续进行安装适配器。</span><span class="sxs-lookup"><span data-stu-id="a2608-242">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the Microsoft.Adapters.*\<AdapterName\>*_schema.xml file, but proceeds with the adapter installation.</span></span>  

<span data-ttu-id="a2608-243">**原因**</span><span class="sxs-lookup"><span data-stu-id="a2608-243">**Cause**</span></span>  

<span data-ttu-id="a2608-244">如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上同时使用的目标架构文件是相同。</span><span class="sxs-lookup"><span data-stu-id="a2608-244">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="a2608-245">因此，32 位安装的文件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在由 IIS 使用 64 位安装程序会尝试对其进行访问时。</span><span class="sxs-lookup"><span data-stu-id="a2608-245">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  

<span data-ttu-id="a2608-246">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="a2608-246">**Resolution**</span></span>  

<span data-ttu-id="a2608-247">手动复制 Microsoft.Adapters。 *\<AdapterName\>*_schema.xml 文件从*C:\Program Files\Microsoft BizTalk 适配器包 (x64) \IIS 架构*到*C:\Windows\System32\inetsrv\config\schema*。</span><span class="sxs-lookup"><span data-stu-id="a2608-247">Manually copy the Microsoft.Adapters.*\<AdapterName\>*_schema.xml file from *C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas* to *C:\Windows\System32\inetsrv\config\schema*.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a2608-248">下一步</span><span class="sxs-lookup"><span data-stu-id="a2608-248">Next step</span></span>
[<span data-ttu-id="a2608-249">安装后步骤</span><span class="sxs-lookup"><span data-stu-id="a2608-249">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)