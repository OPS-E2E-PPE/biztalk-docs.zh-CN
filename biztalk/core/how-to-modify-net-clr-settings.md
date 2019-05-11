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
ms.openlocfilehash: 512907afe143b92af3eafea2156efd42d97f4f75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384606"
---
# <a name="how-to-modify-net-clr-settings"></a><span data-ttu-id="c0021-102">如何修改.NET CLR 设置</span><span class="sxs-lookup"><span data-stu-id="c0021-102">How to Modify .NET CLR Settings</span></span>
<span data-ttu-id="c0021-103">若要更新的 Windows 中的 BizTalk 主机实例相关联的.NET 线程池可用线程数，可以修改相应的公共运行时语言 (CLR) Hosting 值使用 BizTalk 设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="c0021-103">To update the number of Windows threads available in the .NET thread pool associated with an instance of a BizTalk host, you can modify the appropriate Common Runtime Language (CLR) Hosting values using the BizTalk Settings Dashboard.</span></span> <span data-ttu-id="c0021-104">本主题提供了修改这些设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="c0021-104">This topic provides the step-by-step procedure to modify these settings.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c0021-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="c0021-105">Prerequisites</span></span>  
 <span data-ttu-id="c0021-106">若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c0021-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a><span data-ttu-id="c0021-107">若要修改的主机实例的.NET CLR 设置</span><span class="sxs-lookup"><span data-stu-id="c0021-107">To modify the .NET CLR settings of a host instance</span></span>  

1. <span data-ttu-id="c0021-108">在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="c0021-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  

2. <span data-ttu-id="c0021-109">在中**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，单击 **.NET CLR**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c0021-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instance** tab, click the **.NET CLR** tab.</span></span>  

3. <span data-ttu-id="c0021-110">执行以下操作，单击**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="c0021-110">Do the following and click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  


   |     <span data-ttu-id="c0021-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c0021-111">Use this</span></span>      |                                                                                <span data-ttu-id="c0021-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c0021-112">To do this</span></span>                                                                                | <span data-ttu-id="c0021-113">边界值</span><span class="sxs-lookup"><span data-stu-id="c0021-113">Boundary values</span></span> | <span data-ttu-id="c0021-114">默认值</span><span class="sxs-lookup"><span data-stu-id="c0021-114">Default value</span></span> | <span data-ttu-id="c0021-115">升级逻辑</span><span class="sxs-lookup"><span data-stu-id="c0021-115">Upgrade logic</span></span> |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | <span data-ttu-id="c0021-116">**主机实例**</span><span class="sxs-lookup"><span data-stu-id="c0021-116">**Host Instance**</span></span> | <span data-ttu-id="c0021-117">从下拉列表框中，选择正在运行的主机实例上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机。</span><span class="sxs-lookup"><span data-stu-id="c0021-117">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span> |        -        |       -       |       -       |

    <span data-ttu-id="c0021-118">**线程设置**</span><span class="sxs-lookup"><span data-stu-id="c0021-118">**Threading Settings**</span></span>  

   |<span data-ttu-id="c0021-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c0021-119">Use this</span></span>|<span data-ttu-id="c0021-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c0021-120">To do this</span></span>|<span data-ttu-id="c0021-121">边界值</span><span class="sxs-lookup"><span data-stu-id="c0021-121">Boundary values</span></span>|<span data-ttu-id="c0021-122">默认值</span><span class="sxs-lookup"><span data-stu-id="c0021-122">Default value</span></span>|<span data-ttu-id="c0021-123">升级逻辑</span><span class="sxs-lookup"><span data-stu-id="c0021-123">Upgrade logic</span></span>|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |<span data-ttu-id="c0021-124">**最大值。工作线程数**</span><span class="sxs-lookup"><span data-stu-id="c0021-124">**Max. worker threads**</span></span>|<span data-ttu-id="c0021-125">指定的最大.NET CLR 工作线程数。</span><span class="sxs-lookup"><span data-stu-id="c0021-125">Specify the maximum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="c0021-126">[最小工作线程，500]</span><span class="sxs-lookup"><span data-stu-id="c0021-126">[Min worker threads, 500]</span></span>|<span data-ttu-id="c0021-127">25</span><span class="sxs-lookup"><span data-stu-id="c0021-127">25</span></span>|<span data-ttu-id="c0021-128">迁移主机实例注册表设置以主机实例设置，忽略 Version、 Flavor、 标志和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="c0021-128">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="c0021-129">**最小工作线程**</span><span class="sxs-lookup"><span data-stu-id="c0021-129">**Min. worker threads**</span></span>|<span data-ttu-id="c0021-130">指定的最小.NET CLR 工作线程数。</span><span class="sxs-lookup"><span data-stu-id="c0021-130">Specify the minimum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="c0021-131">[0, 500]</span><span class="sxs-lookup"><span data-stu-id="c0021-131">[0, 500]</span></span>|<span data-ttu-id="c0021-132">5</span><span class="sxs-lookup"><span data-stu-id="c0021-132">5</span></span>|<span data-ttu-id="c0021-133">迁移主机实例注册表设置以主机实例设置，忽略 Version、 Flavor、 标志和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="c0021-133">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="c0021-134">**最大值。IO 线程数**</span><span class="sxs-lookup"><span data-stu-id="c0021-134">**Max. IO threads**</span></span>|<span data-ttu-id="c0021-135">指定的最大 IO 线程数。</span><span class="sxs-lookup"><span data-stu-id="c0021-135">Specify the maximum number of IO threads.</span></span>|<span data-ttu-id="c0021-136">[最小 IO 线程，1000年]</span><span class="sxs-lookup"><span data-stu-id="c0021-136">[Min IO threads, 1000]</span></span>|<span data-ttu-id="c0021-137">250</span><span class="sxs-lookup"><span data-stu-id="c0021-137">250</span></span>|<span data-ttu-id="c0021-138">迁移主机实例注册表设置以主机实例设置，忽略 Version、 Flavor、 标志和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="c0021-138">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="c0021-139">**最小值。IO 线程数**</span><span class="sxs-lookup"><span data-stu-id="c0021-139">**Min. IO threads**</span></span>|<span data-ttu-id="c0021-140">指定的最小 IO 线程数。</span><span class="sxs-lookup"><span data-stu-id="c0021-140">Specify the minimum number of IO threads.</span></span>|<span data-ttu-id="c0021-141">[0, 1000]</span><span class="sxs-lookup"><span data-stu-id="c0021-141">[0, 1000]</span></span>|<span data-ttu-id="c0021-142">25</span><span class="sxs-lookup"><span data-stu-id="c0021-142">25</span></span>|<span data-ttu-id="c0021-143">迁移主机实例注册表设置以主机实例设置，忽略 Version、 Flavor、 标志和 MinCompletionPortThreads。</span><span class="sxs-lookup"><span data-stu-id="c0021-143">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  

    <span data-ttu-id="c0021-144">.NET CLR 设置因每个核 CPU。</span><span class="sxs-lookup"><span data-stu-id="c0021-144">.NET CLR Settings are per-core CPU.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c0021-145">若要还原默认设置，请单击**还原为默认值**。</span><span class="sxs-lookup"><span data-stu-id="c0021-145">To restore the default settings, click **Restore Defaults**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c0021-146">**工作线程**用于处理排队的工作项并**I/O 线程**是与 I/O 完成端口来处理已完成的异步 I/O 请求相关联的回调线程。</span><span class="sxs-lookup"><span data-stu-id="c0021-146">**Worker threads** are used to handle queued work items and **I/O threads** are dedicated callback threads associated with an I/O completion port to handle a completed asynchronous I/O request.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c0021-147">如果 BizTalk 从以前的版本，在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$ 值升级*主机名*\CLR Hosting 注册表项将会在设置仪表板中。</span><span class="sxs-lookup"><span data-stu-id="c0021-147">If BizTalk is upgraded from a previous version, the values in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$*hostname*\CLR Hosting registry key will be set in Settings Dashboard.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c0021-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0021-148">See Also</span></span>  
 [<span data-ttu-id="c0021-149">如何修改主机实例设置</span><span class="sxs-lookup"><span data-stu-id="c0021-149">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)