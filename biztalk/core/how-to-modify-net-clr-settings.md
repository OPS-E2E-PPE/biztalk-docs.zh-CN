---
title: 如何修改.NET CLR 设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe3d54aa508d45211277377c2f2d8880c37044d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015150"
---
# <a name="how-to-modify-net-clr-settings"></a><span data-ttu-id="b3a03-102">如何修改 .NET CLR 设置</span><span class="sxs-lookup"><span data-stu-id="b3a03-102">How to Modify .NET CLR Settings</span></span>
<span data-ttu-id="b3a03-103">若要更新与 BizTalk 主机的实例相关联的 .NET 线程池中可用的 Windows 线程数，可以使用“BizTalk 设置仪表板”修改相应的公共语言运行时 (CLR) Hosting 值。</span><span class="sxs-lookup"><span data-stu-id="b3a03-103">To update the number of Windows threads available in the .NET thread pool associated with an instance of a BizTalk host, you can modify the appropriate Common Runtime Language (CLR) Hosting values using the BizTalk Settings Dashboard.</span></span> <span data-ttu-id="b3a03-104">本主题提供了修改这些设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="b3a03-104">This topic provides the step-by-step procedure to modify these settings.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="b3a03-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="b3a03-105">Prerequisites</span></span>  
 <span data-ttu-id="b3a03-106">若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="b3a03-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a><span data-ttu-id="b3a03-107">修改主机实例的 .NET CLR 设置</span><span class="sxs-lookup"><span data-stu-id="b3a03-107">To modify the .NET CLR settings of a host instance</span></span>  

1. <span data-ttu-id="b3a03-108">在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="b3a03-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  

2. <span data-ttu-id="b3a03-109">在中**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，单击 **.NET CLR**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b3a03-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instance** tab, click the **.NET CLR** tab.</span></span>  

3. <span data-ttu-id="b3a03-110">执行以下操作，单击**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="b3a03-110">Do the following and click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  


   |     <span data-ttu-id="b3a03-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b3a03-111">Use this</span></span>      |                                                                                <span data-ttu-id="b3a03-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b3a03-112">To do this</span></span>                                                                                | <span data-ttu-id="b3a03-113">边界值</span><span class="sxs-lookup"><span data-stu-id="b3a03-113">Boundary values</span></span> | <span data-ttu-id="b3a03-114">默认值</span><span class="sxs-lookup"><span data-stu-id="b3a03-114">Default value</span></span> | <span data-ttu-id="b3a03-115">升级逻辑</span><span class="sxs-lookup"><span data-stu-id="b3a03-115">Upgrade logic</span></span> |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | <span data-ttu-id="b3a03-116">**主机实例**</span><span class="sxs-lookup"><span data-stu-id="b3a03-116">**Host Instance**</span></span> | <span data-ttu-id="b3a03-117">从下拉框中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机上选择正在运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="b3a03-117">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span> |        -        |       -       |       -       |

    <span data-ttu-id="b3a03-118">**线程设置**</span><span class="sxs-lookup"><span data-stu-id="b3a03-118">**Threading Settings**</span></span>  

   |<span data-ttu-id="b3a03-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b3a03-119">Use this</span></span>|<span data-ttu-id="b3a03-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b3a03-120">To do this</span></span>|<span data-ttu-id="b3a03-121">边界值</span><span class="sxs-lookup"><span data-stu-id="b3a03-121">Boundary values</span></span>|<span data-ttu-id="b3a03-122">默认值</span><span class="sxs-lookup"><span data-stu-id="b3a03-122">Default value</span></span>|<span data-ttu-id="b3a03-123">升级逻辑</span><span class="sxs-lookup"><span data-stu-id="b3a03-123">Upgrade logic</span></span>|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |<span data-ttu-id="b3a03-124">**最大值。工作线程数**</span><span class="sxs-lookup"><span data-stu-id="b3a03-124">**Max. worker threads**</span></span>|<span data-ttu-id="b3a03-125">指定 .NET CLR 工作线程的最大数量。</span><span class="sxs-lookup"><span data-stu-id="b3a03-125">Specify the maximum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="b3a03-126">[最小工作线程，500]</span><span class="sxs-lookup"><span data-stu-id="b3a03-126">[Min worker threads, 500]</span></span>|<span data-ttu-id="b3a03-127">25</span><span class="sxs-lookup"><span data-stu-id="b3a03-127">25</span></span>|<span data-ttu-id="b3a03-128">将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="b3a03-128">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="b3a03-129">**最小工作线程**</span><span class="sxs-lookup"><span data-stu-id="b3a03-129">**Min. worker threads**</span></span>|<span data-ttu-id="b3a03-130">指定 .NET CLR 工作线程的最小数量。</span><span class="sxs-lookup"><span data-stu-id="b3a03-130">Specify the minimum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="b3a03-131">[0, 500]</span><span class="sxs-lookup"><span data-stu-id="b3a03-131">[0, 500]</span></span>|<span data-ttu-id="b3a03-132">5</span><span class="sxs-lookup"><span data-stu-id="b3a03-132">5</span></span>|<span data-ttu-id="b3a03-133">将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="b3a03-133">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="b3a03-134">**最大值。IO 线程数**</span><span class="sxs-lookup"><span data-stu-id="b3a03-134">**Max. IO threads**</span></span>|<span data-ttu-id="b3a03-135">指定 IO 线程的最大数量。</span><span class="sxs-lookup"><span data-stu-id="b3a03-135">Specify the maximum number of IO threads.</span></span>|<span data-ttu-id="b3a03-136">[最小 IO 线程，1000]</span><span class="sxs-lookup"><span data-stu-id="b3a03-136">[Min IO threads, 1000]</span></span>|<span data-ttu-id="b3a03-137">250</span><span class="sxs-lookup"><span data-stu-id="b3a03-137">250</span></span>|<span data-ttu-id="b3a03-138">将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="b3a03-138">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="b3a03-139">**最小值。IO 线程数**</span><span class="sxs-lookup"><span data-stu-id="b3a03-139">**Min. IO threads**</span></span>|<span data-ttu-id="b3a03-140">指定 IO 线程的最小数量。</span><span class="sxs-lookup"><span data-stu-id="b3a03-140">Specify the minimum number of IO threads.</span></span>|<span data-ttu-id="b3a03-141">[0, 1000]</span><span class="sxs-lookup"><span data-stu-id="b3a03-141">[0, 1000]</span></span>|<span data-ttu-id="b3a03-142">25</span><span class="sxs-lookup"><span data-stu-id="b3a03-142">25</span></span>|<span data-ttu-id="b3a03-143">将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="b3a03-143">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  

    <span data-ttu-id="b3a03-144">.NET CLR 设置因 CPU 核心而异。</span><span class="sxs-lookup"><span data-stu-id="b3a03-144">.NET CLR Settings are per-core CPU.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b3a03-145">若要还原默认设置，请单击**还原为默认值**。</span><span class="sxs-lookup"><span data-stu-id="b3a03-145">To restore the default settings, click **Restore Defaults**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b3a03-146">**工作线程**用于处理排队的工作项并**I/O 线程**是与 I/O 完成端口来处理已完成的异步 I/O 请求相关联的回调线程。</span><span class="sxs-lookup"><span data-stu-id="b3a03-146">**Worker threads** are used to handle queued work items and **I/O threads** are dedicated callback threads associated with an I/O completion port to handle a completed asynchronous I/O request.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b3a03-147">如果 BizTalk 从以前的版本，在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$ 值升级*主机名*\CLR Hosting 注册表项将会在设置仪表板中。</span><span class="sxs-lookup"><span data-stu-id="b3a03-147">If BizTalk is upgraded from a previous version, the values in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$*hostname*\CLR Hosting registry key will be set in Settings Dashboard.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b3a03-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3a03-148">See Also</span></span>  
 [<span data-ttu-id="b3a03-149">如何修改主机实例设置</span><span class="sxs-lookup"><span data-stu-id="b3a03-149">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)