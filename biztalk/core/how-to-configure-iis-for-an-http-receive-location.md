---
title: 为 HTTP 接收位置配置 IIS |Microsoft Docs
description: 在 IIS 中，创建 BTS HTTP 接收应用程序和 BizTalk Server 中测试应用程序池设置
ms.custom: ''
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc616fa9834071c2ee8d2b4d63f486ff0abbeab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004817"
---
# <a name="configure-iis-for-an-http-receive-location"></a><span data-ttu-id="4586f-103">为 HTTP 接收位置配置 IIS</span><span class="sxs-lookup"><span data-stu-id="4586f-103">Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="4586f-104">HTTP 接收位置使用的应用程序在 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="4586f-104">The HTTP receive location uses an application within Internet Information Services (IIS).</span></span> <span data-ttu-id="4586f-105">本主题列出了步骤后，若要启用 HTTP 接收位置在 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="4586f-105">This topic lists the steps to enable the HTTP receive location within IIS.</span></span> 

<span data-ttu-id="4586f-106">具体取决于你的操作系统配置 IIS 应用程序的步骤可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="4586f-106">Depending on your operating system, the steps to configure the IIS application may vary.</span></span> <span data-ttu-id="4586f-107">使用与用户界面可能会不同操作系统上作为指南，这些步骤。</span><span class="sxs-lookup"><span data-stu-id="4586f-107">Use these steps as a guide, as the user interface may be different on your OS.</span></span>
  
## <a name="32-bit-vs-64-bit"></a><span data-ttu-id="4586f-108">32 位与 64 位</span><span class="sxs-lookup"><span data-stu-id="4586f-108">32-bit vs 64-bit</span></span>

<span data-ttu-id="4586f-109">HTTP 接收位置使用 BTSHTTPReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="4586f-109">An HTTP receive location uses the BTSHTTPReceive.dll.</span></span> <span data-ttu-id="4586f-110">没有 32 位和 64 位版本的 dll。</span><span class="sxs-lookup"><span data-stu-id="4586f-110">There is a 32-bit and a 64-bit version of the DLL.</span></span> <span data-ttu-id="4586f-111">选择你想要使用哪个的版本。</span><span class="sxs-lookup"><span data-stu-id="4586f-111">You choose which version you want to use.</span></span> <span data-ttu-id="4586f-112">64 位进程有更多可用内存，因此如果处理更大的消息，则可能是最佳选择 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="4586f-112">64-bit processes have more available memory, so if you process larger messages, then the 64-bit version may be best.</span></span> 

<span data-ttu-id="4586f-113">**32 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive*。</span><span class="sxs-lookup"><span data-stu-id="4586f-113">**32-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive*.</span></span>
<span data-ttu-id="4586f-114">**64 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive64*</span><span class="sxs-lookup"><span data-stu-id="4586f-114">**64-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive64*</span></span>

<span data-ttu-id="4586f-115">若要运行 64 位版本的 HTTP 接收适配器在 64 位本机模式下，打开命令提示符，并执行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="4586f-115">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode,  open a command prompt, and execute the following scripts:</span></span>  

1. <span data-ttu-id="4586f-116">类型： `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span><span class="sxs-lookup"><span data-stu-id="4586f-116">Type: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span></span>  

2. <span data-ttu-id="4586f-117">类型： `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span><span class="sxs-lookup"><span data-stu-id="4586f-117">Type: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4586f-118">任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。</span><span class="sxs-lookup"><span data-stu-id="4586f-118">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="4586f-119">对于每个进程，只能有一个独立的接收器。</span><span class="sxs-lookup"><span data-stu-id="4586f-119">You can have only one isolated receiver per process.</span></span>  
  
##  <a name="configure-the-iis-application"></a><span data-ttu-id="4586f-120">配置 IIS 应用程序</span><span class="sxs-lookup"><span data-stu-id="4586f-120">Configure the IIS application</span></span>
  
1. <span data-ttu-id="4586f-121">打开**Internet 信息服务**(打开**服务器管理器**，选择**工具**，然后选择**Internet Information Services Manager**).</span><span class="sxs-lookup"><span data-stu-id="4586f-121">Open **Internet Information Services** (open **Server Manager**, select **Tools**, and select **Internet Information Services Manager**).</span></span> 
  
2. <span data-ttu-id="4586f-122">在 IIS 中，选择你的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="4586f-122">In IIS, select your server name.</span></span> <span data-ttu-id="4586f-123">在中**功能视图**，双击**处理程序映射**。</span><span class="sxs-lookup"><span data-stu-id="4586f-123">In the **Features View**, double-click **Handler Mappings**.</span></span> <span data-ttu-id="4586f-124">在操作窗格中选择**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="4586f-124">In the Actions pane, select **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4586f-125">当在 web 服务器级别配置的脚本映射时，映射应用到所有网站。</span><span class="sxs-lookup"><span data-stu-id="4586f-125">When you configure the script mapping at the web server-level, the mapping applies to all web sites.</span></span> <span data-ttu-id="4586f-126">如果你想要将映射限制到特定网站或虚拟文件夹，选择该 web 站点或文件夹，以及如何将脚本映射。</span><span class="sxs-lookup"><span data-stu-id="4586f-126">If you want to restrict the mapping to a specific Web site or virtual folder, select that web site or folder, and then add the script map.</span></span>  
  
3. <span data-ttu-id="4586f-127">在中**添加脚本映射**，选择**请求路径**，然后键入`BtsHttpReceive.dll`。</span><span class="sxs-lookup"><span data-stu-id="4586f-127">In **Add Script Map**, select **Request path**, and type `BtsHttpReceive.dll`.</span></span>  
  
4. <span data-ttu-id="4586f-128">在中**可执行文件**，选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="4586f-128">In **Executable**, select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="4586f-129">选择**BtsHttpReceive.dll**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="4586f-129">Select **BtsHttpReceive.dll**, and then select **Open**.</span></span>  
  
5. <span data-ttu-id="4586f-130">在中**名称**，输入`BizTalk HTTP Receive`，然后选择**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="4586f-130">In **Name**, enter `BizTalk HTTP Receive`, and then select **Request Restrictions**.</span></span> <span data-ttu-id="4586f-131">在此窗口中：</span><span class="sxs-lookup"><span data-stu-id="4586f-131">In this window:</span></span>
  
   1. <span data-ttu-id="4586f-132">在中**谓词**，选择**以下谓词之一**，然后输入`POST`。</span><span class="sxs-lookup"><span data-stu-id="4586f-132">In **Verbs**, select **One of the following verbs**, and enter `POST`.</span></span>  
  
   2. <span data-ttu-id="4586f-133">在中**访问**，选择**脚本**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4586f-133">In **Access**, select **Script**, and then select **OK**.</span></span>  
  
   3. <span data-ttu-id="4586f-134">在提示是否允许 ISAPI 扩展，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="4586f-134">When prompted to allow the ISAPI extension, select **Yes**.</span></span>  
  
6. <span data-ttu-id="4586f-135">创建新的应用程序池 (右键单击**应用程序池**，选择**添加应用程序池**)。</span><span class="sxs-lookup"><span data-stu-id="4586f-135">Create a new application pool (right-click **Application Pools**, select **Add application pool**).</span></span> <span data-ttu-id="4586f-136">**名称**应用程序池 (如`BTSHTTPReceive`)，选择**NET Framework v4.0.30319**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4586f-136">**Name** your application pool (such as `BTSHTTPReceive`), select **NET Framework v4.0.30319**, and select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4586f-137">.NET 版本号可能会有所不同，具体取决于在计算机上安装.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="4586f-137">The .NET version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="4586f-138">将列出新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="4586f-138">The new application pool is listed.</span></span>  
  
7. <span data-ttu-id="4586f-139">选择新的应用程序池，并打开**高级设置**(**操作**窗格)。</span><span class="sxs-lookup"><span data-stu-id="4586f-139">Select your new application pool, and open the **Advanced Settings** (**Actions** pane).</span></span> <span data-ttu-id="4586f-140">在此窗口中：</span><span class="sxs-lookup"><span data-stu-id="4586f-140">In this window:</span></span>

    - <span data-ttu-id="4586f-141">**启用 32 位应用程序**： 设置为**True**如果选择了 32 位**BtsHttpReceive.dll**</span><span class="sxs-lookup"><span data-stu-id="4586f-141">**Enable 32-Bit Application**: Set to **True** if you chose the 32-bit **BtsHttpReceive.dll**</span></span>
    - <span data-ttu-id="4586f-142">**处理模型**部分中，**标识**： 选择省略号 (**...**)，选择**自定义帐户**，然后**设置**到该帐户是属于**BizTalk Isolated Host Users**和**IIS_WPG**组。</span><span class="sxs-lookup"><span data-stu-id="4586f-142">**Process Model** section, **Identity**: Select the ellipsis (**…**), select **Custom account**, and then **Set** it to an account that is a member of the **BizTalk Isolated Host Users** and **IIS_WPG** groups.</span></span> <span data-ttu-id="4586f-143">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="4586f-143">Select **OK**.</span></span> 
  
8. <span data-ttu-id="4586f-144">添加新的应用程序的 web 站点 (右键单击**Default Web Site**，选择**添加应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="4586f-144">Add a new application to the web site (right-click the **Default Web Site**, select **Add Application**).</span></span> <span data-ttu-id="4586f-145">在此窗口中：</span><span class="sxs-lookup"><span data-stu-id="4586f-145">In this window:</span></span>
  
   1. <span data-ttu-id="4586f-146">**别名**： 输入与应用程序关联的别名 (如`BTS HTTP Receive`，然后**选择**。</span><span class="sxs-lookup"><span data-stu-id="4586f-146">**Alias** : Enter an alias that you associate with the application (such as `BTS HTTP Receive`, and then **Select**.</span></span>  
   2. <span data-ttu-id="4586f-147">选择您刚的新应用程序池创建，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4586f-147">Select the new application pool you just created, and then select **OK**.</span></span>  
   3. <span data-ttu-id="4586f-148">**物理路径**： 选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="4586f-148">**Physical path**: Select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span>  
   4. <span data-ttu-id="4586f-149">**测试设置**以验证是否在没有错误**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="4586f-149">**Test Settings** to verify there are no errors in the **Test Connection** dialog box.</span></span> <span data-ttu-id="4586f-150">**关闭**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4586f-150">**Close**, and then select **OK**.</span></span>  
  
      > [!TIP]
      > <span data-ttu-id="4586f-151">如果测试设置返回一条警告，可能缺少应用程序池标识的对文件夹的权限或访问组。</span><span class="sxs-lookup"><span data-stu-id="4586f-151">If Test Settings returns a warning, the identity of the application pool may be missing permissions to a folder, or access to a group.</span></span> <span data-ttu-id="4586f-152">作为故障排除步骤，选择**连接身份**，输入**用户名**并**密码**是 Administrators 组的成员的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4586f-152">As a troubleshooting step, select **Connect As**, enter the **User name** and **Password** for a user account that is a member of the Administrators group.</span></span> 

9. <span data-ttu-id="4586f-153">新应用程序将显示已列入**默认网站**。</span><span class="sxs-lookup"><span data-stu-id="4586f-153">The new application appears is listed under **Default Web Sites**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4586f-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="4586f-154">See Also</span></span>  
 [<span data-ttu-id="4586f-155">如何配置 HTTP 接收位置</span><span class="sxs-lookup"><span data-stu-id="4586f-155">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)
