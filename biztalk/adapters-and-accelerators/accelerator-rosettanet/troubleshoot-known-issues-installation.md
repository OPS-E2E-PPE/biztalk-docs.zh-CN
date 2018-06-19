---
title: 排除故障并在 BizTalk Server 上安装的已知的问题与 BizTalk RosettaNet 快捷键 (BTARN) |Microsoft 文档"
description: 安装与 BTARN 安装 BizTalk Server 中的 SQL，主机实例和已知的错误的服务帐户的建议
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdca89c1a7a4ed3834103776f9f28c8631c5de0a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22210837"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a><span data-ttu-id="fc131-103">解决安装问题和发现的已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="fc131-103">Troubleshoot the installation and see the known install issues</span></span>

  
## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a><span data-ttu-id="fc131-104">不要在域控制器计算机上安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc131-104">Do not install SQL Server on the domain controller computer</span></span>  
 <span data-ttu-id="fc131-105">如果在同一台计算机作为域控制器计算机上安装 SQL Server，它在尝试创建 SQL 发送端口时将返回以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="fc131-105">If you install SQL Server on the same computer as your domain controller computer, it returns the following error message when it is trying to create the SQL send ports:</span></span>  
  
```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  

```
  
> [!IMPORTANT]
>  <span data-ttu-id="fc131-106">不要在域控制器计算机上安装 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="fc131-106">Do not install SQL Server on the domain controller computer.</span></span>  
  
## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a><span data-ttu-id="fc131-107">应用程序池的服务帐户必须与独立主机和主机实例的服务帐户相同</span><span class="sxs-lookup"><span data-stu-id="fc131-107">Service account for the application pools must be the same as the service account for the Isolated Host and Host instances</span></span>  
 <span data-ttu-id="fc131-108">如果为 BTARN 应用程序池设置的服务帐户从独立主机帐户不同，BTARN 不正确处理传入消息。</span><span class="sxs-lookup"><span data-stu-id="fc131-108">If the service account set for the BTARN application pools is different from the Isolated Host account, BTARN does not process incoming messages correctly.</span></span> <span data-ttu-id="fc131-109">当接收.aspx 页调用管道时，管道没有合适的证书的访问。</span><span class="sxs-lookup"><span data-stu-id="fc131-109">When the receive .aspx page calls the pipeline, the pipeline does not have access to the appropriate certificates.</span></span> <span data-ttu-id="fc131-110">因此，它不会对传入消息进行解密或验证的签名。</span><span class="sxs-lookup"><span data-stu-id="fc131-110">Therefore, it does not decrypt the incoming message or validate the signature.</span></span> <span data-ttu-id="fc131-111">此外，它将无法访问 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="fc131-111">Also, it won't be able to access the MessageBox database.</span></span>  
  

## <a name="known-install-issues"></a><span data-ttu-id="fc131-112">已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="fc131-112">Known install issues</span></span>

  
### <a name="btarn-http-front-end-feature-configuration-fails"></a><span data-ttu-id="fc131-113">BTARN HTTP 前结束功能配置失败</span><span class="sxs-lookup"><span data-stu-id="fc131-113">BTARN HTTP Front End Feature configuration fails</span></span>  
 <span data-ttu-id="fc131-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="fc131-114">**Problem**</span></span>  
  
 <span data-ttu-id="fc131-115">如果通过执行自定义安装来仅安装 BTARN HTTP 前端功能，安装完成后，BTARN 配置可能会因以下错误而失败：</span><span class="sxs-lookup"><span data-stu-id="fc131-115">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail with the following error after setup has completed:</span></span> 

`Failed to create object for feature: WebApp`  
  
 <span data-ttu-id="fc131-116">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fc131-116">**Resolution**</span></span>  
  
<span data-ttu-id="fc131-117">手动将文件复制和重新配置：</span><span class="sxs-lookup"><span data-stu-id="fc131-117">Manually copy files and reconfigure:</span></span> 
  
1.  <span data-ttu-id="fc131-118">从 BizTalk Server 计算机的以下两个文件复制到计算机在其安装了 BTARN HTTP 前端功能：</span><span class="sxs-lookup"><span data-stu-id="fc131-118">Copy the following two files from an BizTalk Server computer to the computer on which you installed the BTARN HTTP Front End feature:</span></span>
  
    -   <span data-ttu-id="fc131-119">Microsoft.VC80.ATL.manifest</span><span class="sxs-lookup"><span data-stu-id="fc131-119">Microsoft.VC80.ATL.manifest</span></span>  
  
    -   <span data-ttu-id="fc131-120">atl80.dll</span><span class="sxs-lookup"><span data-stu-id="fc131-120">atl80.dll</span></span>  
  
     <span data-ttu-id="fc131-121">如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 <*驱动器*>: files\microsoft Visual Studio < 版本\>\VC\redist\x86\Microsoft.VC100.ATL.</span><span class="sxs-lookup"><span data-stu-id="fc131-121">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is <*drive*>:\Program Files\Microsoft Visual Studio <version\>\VC\redist\x86\Microsoft.VC100.ATL.</span></span>  
  
     <span data-ttu-id="fc131-122">如果相同的 BizTalk Server 计算机上未安装 Visual Studio，两个文件的源文件夹是在 <*驱动器*>: \WINDOWS\WinSxS。</span><span class="sxs-lookup"><span data-stu-id="fc131-122">If Visual Studio is not installed on the same BizTalk Server computer, the source folder for the two files is under <*drive*>:\WINDOWS\WinSxS.</span></span>  
  
2.  <span data-ttu-id="fc131-123">将复制的文件添加到安装了 BTARN HTTP 前端功能的计算机。</span><span class="sxs-lookup"><span data-stu-id="fc131-123">Add the copied files to the computer on which you installed BTARN HTTP Front End feature.</span></span> <span data-ttu-id="fc131-124">默认情况下，将文件复制到 <*驱动器*>: files\microsoft BizTalk Accelerator for RosettaNet。</span><span class="sxs-lookup"><span data-stu-id="fc131-124">By default, copy the files to <*drive*>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet.</span></span>  
  
3.  <span data-ttu-id="fc131-125">将文件复制到 HTTP 前端计算机后，运行**Configuration.exe**试。</span><span class="sxs-lookup"><span data-stu-id="fc131-125">After you have copied the files to the HTTP Front End computer, run **Configuration.exe** again.</span></span>  
  
### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a><span data-ttu-id="fc131-126">某些 BTARN 程序集在 GAC 中保持卸载后</span><span class="sxs-lookup"><span data-stu-id="fc131-126">Some BTARN Assemblies stay in GAC after uninstalling</span></span>  
 <span data-ttu-id="fc131-127">**问题**</span><span class="sxs-lookup"><span data-stu-id="fc131-127">**Problem**</span></span>  
  
 <span data-ttu-id="fc131-128">当你卸载 BTARN 时，某些程序集将保留在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="fc131-128">When you uninstall BTARN, some assemblies remain in the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="fc131-129">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fc131-129">**Resolution**</span></span>  
  
 <span data-ttu-id="fc131-130">重新安装 BTARN 前，从 GAC 中删除程序集。</span><span class="sxs-lookup"><span data-stu-id="fc131-130">Remove the assemblies from the GAC before reinstalling BTARN.</span></span>  
  
 <span data-ttu-id="fc131-131">使用**BtarnClean**实用工具从 SDK 以移除程序集。</span><span class="sxs-lookup"><span data-stu-id="fc131-131">Use the **BtarnClean** utility from the SDK to remove the assemblies.</span></span> <span data-ttu-id="fc131-132">该实用程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fc131-132">The utility performs the following actions:</span></span>  
  
-   <span data-ttu-id="fc131-133">停止和取消登记所有 BTARN 业务流程。</span><span class="sxs-lookup"><span data-stu-id="fc131-133">Stops and unenlists all the BTARN orchestrations.</span></span>  
  
-   <span data-ttu-id="fc131-134">停止和删除所有关联的端口。</span><span class="sxs-lookup"><span data-stu-id="fc131-134">Stops and deletes all the associated ports.</span></span>  
  
-   <span data-ttu-id="fc131-135">取消部署所有 Microsoft.Solutions.BTARN.\* 程序集。</span><span class="sxs-lookup"><span data-stu-id="fc131-135">Undeploys all the Microsoft.Solutions.BTARN.\* assemblies.</span></span>  
  
 <span data-ttu-id="fc131-136">运行该实用程序后，如果仍有程序集保留在 GAC 中，请打开 Windows 资源管理器，转到“C:\Windows\Assembly”文件夹，然后手动删除所有以 Microsoft.Solutions.BTARN 开头的程序集。</span><span class="sxs-lookup"><span data-stu-id="fc131-136">After running the utility, if there are assemblies remaining in the GAC, open Windows Explorer, go to the "C:\Windows\Assembly" folder, and then manually delete all assemblies starting with Microsoft.Solutions.BTARN.</span></span>  
  
### <a name="service-unavailable-error-on-64-bit-os"></a><span data-ttu-id="fc131-137">64 位操作系统上的服务不可用错误</span><span class="sxs-lookup"><span data-stu-id="fc131-137">Service Unavailable error on 64-bit OS</span></span>
 <span data-ttu-id="fc131-138">**问题**</span><span class="sxs-lookup"><span data-stu-id="fc131-138">**Problem**</span></span>  
  
 <span data-ttu-id="fc131-139">你可能会收到`Service Unavailable`错误尝试访问 BTARN HTTP 时接收在 64 位 Windows 操作系统上的位置。</span><span class="sxs-lookup"><span data-stu-id="fc131-139">You may get a `Service Unavailable` error when trying to access the BTARN HTTP receive location on 64-bit Windows operating systems.</span></span>  
  
 <span data-ttu-id="fc131-140">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fc131-140">**Cause**</span></span>  
  
 <span data-ttu-id="fc131-141">此问题可能是由“RPCProxy.dll”ISAPI 筛选器造成的。</span><span class="sxs-lookup"><span data-stu-id="fc131-141">This issue can be caused by the "RPCProxy.dll" ISAPI filter.</span></span>  
  
 <span data-ttu-id="fc131-142">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fc131-142">**Resolution**</span></span>  
  
<span data-ttu-id="fc131-143">删除对 RPC 代理 ISAPI 筛选器的引用并重新启动 IIS:</span><span class="sxs-lookup"><span data-stu-id="fc131-143">Remove references to the RPC proxy ISAPI filter and restart IIS:</span></span>
  
1.  <span data-ttu-id="fc131-144">在 Internet 信息服务 (IIS) 管理器中，右键单击**网站**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="fc131-144">In Internet Information Services (IIS) Manager, right-click **Web Sites**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fc131-145">在**Web 站点属性**对话框中，单击**ISAPI 筛选器**选项卡上，删除**RPC 代理**筛选，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="fc131-145">In the **Web Site Properties** dialog box, click the **ISAPI filters** tab, remove **RPC Proxy** filter, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fc131-146">重新启动 IIS。</span><span class="sxs-lookup"><span data-stu-id="fc131-146">Restart IIS.</span></span>  
  
4.  <span data-ttu-id="fc131-147">在重新启动 IIS 后，请尝试访问http://localhost。</span><span class="sxs-lookup"><span data-stu-id="fc131-147">After you have restarted IIS, try accessing http://localhost.</span></span> <span data-ttu-id="fc131-148">你会收到从 Internet 浏览器返回的 400 消息。</span><span class="sxs-lookup"><span data-stu-id="fc131-148">You should get the 400 message back from the Internet browser.</span></span>  
  
### <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="fc131-149">SQL Server 混合模式不支持</span><span class="sxs-lookup"><span data-stu-id="fc131-149">SQL Server Mixed Mode not supported</span></span>  
<span data-ttu-id="fc131-150">在混合模式下，BTARN 不支持 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="fc131-150">BTARN does not support SQL Server in mixed mode.</span></span>  
  
### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a><span data-ttu-id="fc131-151">运行 setupx64.bat 设置双操作 PIPAutomation 业务流程示例</span><span class="sxs-lookup"><span data-stu-id="fc131-151">Run setupx64.bat to set up the double action PIPAutomation orchestration sample</span></span> 

<span data-ttu-id="fc131-152">运行 setupx64.bat files\microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹设置双操作 PIPAutomation 业务流程示例中。</span><span class="sxs-lookup"><span data-stu-id="fc131-152">Run setupx64.bat in \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder to set up the Double Action PIPAutomation Orchestration sample.</span></span>
  
### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a><span data-ttu-id="fc131-153">将 BTARN 安装文件从 Web 下载到临时文件夹</span><span class="sxs-lookup"><span data-stu-id="fc131-153">Download the BTARN Setup File from the Web to a Temp Folder</span></span>  
 <span data-ttu-id="fc131-154">**问题**</span><span class="sxs-lookup"><span data-stu-id="fc131-154">**Problem**</span></span>  
  
 <span data-ttu-id="fc131-155">如果您下载 BTARN 自解压可执行文件从 Web 中，并将其保存到 BizTalk Server 根文件夹中，当你尝试运行可执行文件，BizTalk**安装向导**运行，而不是 BTARN 安装向导。</span><span class="sxs-lookup"><span data-stu-id="fc131-155">If you download the BTARN self-extracting executable file from the Web, and save it to the BizTalk Server root folder, when you attempt to run the executable, the BizTalk **Setup Wizard** runs, instead of the BTARN Setup wizard.</span></span>  
  
 <span data-ttu-id="fc131-156">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fc131-156">**Resolution**</span></span>  
  
 <span data-ttu-id="fc131-157">下载 BTARN 自解压可执行文件，并将文件保存到临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="fc131-157">Download the BTARN self-extracting executable, and save the file to a temp folder.</span></span>
