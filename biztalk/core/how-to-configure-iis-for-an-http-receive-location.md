---
title: "如何配置 IIS，用于 HTTP 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a><span data-ttu-id="96c03-102">如何配置 IIS，用于 HTTP 接收位置</span><span class="sxs-lookup"><span data-stu-id="96c03-102">How to Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="96c03-103">你必须根据所用的 Microsoft Windows 版本来以相应的方式配置 Microsoft Internet 信息服务 (IIS)，以便使用 HTTP 适配器接收位置。</span><span class="sxs-lookup"><span data-stu-id="96c03-103">Depending on which version of Microsoft Windows you are using, you will have to configure Microsoft Internet Information Services (IIS) differently to work with the HTTP adapter receive location.</span></span>  
  
 <span data-ttu-id="96c03-104">如果操作系统为 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，则 IIS 7.0 提供两种不同的应用程序隔离模式来保护 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="96c03-104">If your operating system is [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], IIS 7.0 provides two different application isolation modes to protect Web applications.</span></span> <span data-ttu-id="96c03-105">工作进程隔离模式为默认模式。</span><span class="sxs-lookup"><span data-stu-id="96c03-105">Worker process isolation mode is the default mode.</span></span> <span data-ttu-id="96c03-106">你可以将 HTTP 适配器接收位置配置为使用上述两种模式之一，但由于工作进程隔离模式的安全性已提高，因此建议使用该模式。</span><span class="sxs-lookup"><span data-stu-id="96c03-106">You can configure the HTTP adapter receive location to work with either mode, but worker process isolation mode is recommended for its improved security functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96c03-107">如果你的操作系统是 x64 版本的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，64 位版本的 HTTP 接收适配器安装到*\<驱动器 >***\Program Files (x86) \Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64**目录你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认情况下。</span><span class="sxs-lookup"><span data-stu-id="96c03-107">If your operating system is the x64 edition of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], the 64-bit version of the HTTP receive adapter is installed to the *\<drive>***\Program Files (x86)\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\HttpReceive64** directory of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by default.</span></span> <span data-ttu-id="96c03-108">若要以 64 位本机模式运行 64 位版本的 HTTP 接收适配器，则必须从命令行执行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="96c03-108">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode you must execute the following script from a command line:</span></span>  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  <span data-ttu-id="96c03-109">任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。</span><span class="sxs-lookup"><span data-stu-id="96c03-109">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="96c03-110">对于每个进程，只能有一个独立的接收器。</span><span class="sxs-lookup"><span data-stu-id="96c03-110">You can have only one isolated receiver per process.</span></span>  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a><span data-ttu-id="96c03-111">若要配置 IIS 7.0 工作进程隔离模式使用 HTTP 适配器接收位置</span><span class="sxs-lookup"><span data-stu-id="96c03-111">To configure the IIS 7.0 worker process isolation mode to work with the HTTP adapter receive location</span></span>  
  
1.  <span data-ttu-id="96c03-112">单击**启动**，指向**设置**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="96c03-112">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="96c03-113">在 Control Panel 中，双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="96c03-113">In Control Panel, double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="96c03-114">在管理工具中，双击**Internet Information Services**。</span><span class="sxs-lookup"><span data-stu-id="96c03-114">In Administrative Tools, double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="96c03-115">在 Internet 信息服务中，选择根 Web 服务器条目。</span><span class="sxs-lookup"><span data-stu-id="96c03-115">In Internet Information Services, select the root Web server entry.</span></span> <span data-ttu-id="96c03-116">在**功能视图**，双击**处理程序映射**，然后在操作窗格中，单击**添加脚本映射**。</span><span class="sxs-lookup"><span data-stu-id="96c03-116">In the **Features View**, double-click **Handler Mappings**, and then in the Actions pane, click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c03-117">在 Web 服务器级别配置脚本映射会导致此映射应用于所有子网站。</span><span class="sxs-lookup"><span data-stu-id="96c03-117">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="96c03-118">如果要将映射限制为特定网站或虚拟文件夹，请选择目标站点或文件夹（而不是 Web 服务器）。</span><span class="sxs-lookup"><span data-stu-id="96c03-118">If you want to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
5.  <span data-ttu-id="96c03-119">在**添加脚本映射**对话框中，在**请求路径**字段中，键入`BtsHttpReceive.dll`。</span><span class="sxs-lookup"><span data-stu-id="96c03-119">In the **Add Script Map** dialog box, in the **Request path** field, type `BtsHttpReceive.dll`.</span></span>  
  
6.  <span data-ttu-id="96c03-120">在**可执行文件**字段中，单击省略号 (**...**) 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。</span><span class="sxs-lookup"><span data-stu-id="96c03-120">In the **Executable** field, click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="96c03-121">选择**BtsHttpReceive.dll** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="96c03-121">Select **BtsHttpReceive.dll** and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="96c03-122">在**名称**字段中，键入`BizTalk HTTP Receive`，然后单击**请求限制**。</span><span class="sxs-lookup"><span data-stu-id="96c03-122">In the **Name** field, type `BizTalk HTTP Receive`, and then click **Request Restrictions**.</span></span>  
  
8.  <span data-ttu-id="96c03-123">在**请求限制**对话框中，单击**谓词**选项卡上，然后选择**的以下谓词之一**。</span><span class="sxs-lookup"><span data-stu-id="96c03-123">In the **Request Restrictions** dialog box, click the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="96c03-124">输入`POST`作为谓词。</span><span class="sxs-lookup"><span data-stu-id="96c03-124">Enter `POST` as the verb.</span></span>  
  
9. <span data-ttu-id="96c03-125">上**访问**选项卡上，选择**脚本**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="96c03-125">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="96c03-126">在提示是否允许 ISAPI 扩展插件时，单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="96c03-126">When prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
11. <span data-ttu-id="96c03-127">右键单击**应用程序池**，指向**新建**，然后单击**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="96c03-127">Right-click **Application Pools**, point to **New**, and then click **Application pool**.</span></span>  
  
12. <span data-ttu-id="96c03-128">在**添加应用程序池**对话框中，在**名称**框中，键入应用程序池的名称。</span><span class="sxs-lookup"><span data-stu-id="96c03-128">In the **Add Application Pool** dialog box, in the **Name** box, type a name for the application pool.</span></span> <span data-ttu-id="96c03-129">选择**NET Framework v4.0.30319** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="96c03-129">Select **NET Framework v4.0.30319** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c03-130">版本号可能会因计算机上安装的 .NET Framework 版本而异。</span><span class="sxs-lookup"><span data-stu-id="96c03-130">The version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="96c03-131">新的应用程序池出现在列表中**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="96c03-131">The new application pool appears in the list of **Application Pools**.</span></span>  
  
13. <span data-ttu-id="96c03-132">在**应用程序池**中**功能视图**，选择新的应用程序池，，然后单击**高级设置**在操作窗格中。</span><span class="sxs-lookup"><span data-stu-id="96c03-132">In **Application Pools**, in the **Features View**, select the new application pool, and then click **Advanced Settings** in the Actions pane.</span></span>  
  
14. <span data-ttu-id="96c03-133">在**高级设置**对话框中，在**进程模型**部分中，在**标识**字段中，单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="96c03-133">In the **Advanced Settings** dialog box, in the **Process Model** section, in the **Identity** field, click the ellipsis (**…**) button.</span></span>  
  
15. <span data-ttu-id="96c03-134">在**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="96c03-134">In the **Application Pool Identity** dialog box, select **Custom account**, and then click **Set**.</span></span> <span data-ttu-id="96c03-135">单击“确定”  关闭“高级设置”  对话框。</span><span class="sxs-lookup"><span data-stu-id="96c03-135">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
16. <span data-ttu-id="96c03-136">在 IIS 管理器中，打开**站点**文件夹。</span><span class="sxs-lookup"><span data-stu-id="96c03-136">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="96c03-137">右键单击**Default Web Site** ，然后单击**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="96c03-137">Right-click the **Default Web Site** and then click **Add Application**.</span></span>  
  
17. <span data-ttu-id="96c03-138">在**添加应用程序**对话框中，在**别名**，输入别名以将应用程序后，相关联，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="96c03-138">In the **Add Application** dialog box, in **Alias**, enter an alias to associate with the application, and then click **Select**.</span></span>  
  
18. <span data-ttu-id="96c03-139">在**选择应用程序池**对话框中，选择更早版本，创建新应用程序池，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="96c03-139">In the **Select Application Pool** dialog box, select the new application pool you created earlier, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="96c03-140">单击省略号 (**...**) 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]为 HttpReceive**物理路径**。</span><span class="sxs-lookup"><span data-stu-id="96c03-140">Click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
20. <span data-ttu-id="96c03-141">单击**连接身份**并输入**用户名**和**密码**的用户帐户的是管理员组的成员，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="96c03-141">Click **Connect As** and enter the **User name** and **Password** for a user account that is a member of the Administrators group, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="96c03-142">单击**测试设置**并验证没有错误都显示在**测试连接**对话框。</span><span class="sxs-lookup"><span data-stu-id="96c03-142">Click **Test Settings** and verify that no errors are displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="96c03-143">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="96c03-143">Click **Close**, and then click **OK**.</span></span>  
  
22. <span data-ttu-id="96c03-144">新的应用程序将出现在列表**默认网站**Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="96c03-144">The new application appears in the list of **Default Web Sites** in Internet Information Services (IIS) Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c03-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96c03-145">See Also</span></span>  
 [<span data-ttu-id="96c03-146">如何配置 HTTP 接收位置</span><span class="sxs-lookup"><span data-stu-id="96c03-146">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)