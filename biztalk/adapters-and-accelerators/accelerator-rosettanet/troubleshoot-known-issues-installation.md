---
title: 进行故障排除和 BizTalk Server 上安装 BizTalk RosettaNet 加速器 (BTARN) 的已知的问题 |Microsoft Docs"
description: 用于安装 BizTalk Server 中的 BTARN 安装 SQL、 主机实例和已知的错误的服务帐户建议
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c169a0871826aaaae9341f3ccafcb3e888ffbdbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974622"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a><span data-ttu-id="d5804-103">安装进行故障排除，请参阅已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="d5804-103">Troubleshoot the installation and see the known install issues</span></span>


## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a><span data-ttu-id="d5804-104">不要在域控制器计算机上安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5804-104">Do not install SQL Server on the domain controller computer</span></span>  
 <span data-ttu-id="d5804-105">如果在域控制器计算机在同一计算机上安装 SQL Server，则尝试创建 SQL 发送端口时返回以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="d5804-105">If you install SQL Server on the same computer as your domain controller computer, it returns the following error message when it is trying to create the SQL send ports:</span></span>  

```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  
```

> [!IMPORTANT]
>  <span data-ttu-id="d5804-106">不要在域控制器计算机上安装 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="d5804-106">Do not install SQL Server on the domain controller computer.</span></span>  

## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a><span data-ttu-id="d5804-107">应用程序池的服务帐户必须与独立主机和主机实例的服务帐户相同</span><span class="sxs-lookup"><span data-stu-id="d5804-107">Service account for the application pools must be the same as the service account for the Isolated Host and Host instances</span></span>  
 <span data-ttu-id="d5804-108">如果为 BTARN 应用程序池设置的服务帐户与独立主机帐户不同，BTARN 不正确处理传入的消息。</span><span class="sxs-lookup"><span data-stu-id="d5804-108">If the service account set for the BTARN application pools is different from the Isolated Host account, BTARN does not process incoming messages correctly.</span></span> <span data-ttu-id="d5804-109">当接收.aspx 页调用管道时，管道无法访问相应的证书。</span><span class="sxs-lookup"><span data-stu-id="d5804-109">When the receive .aspx page calls the pipeline, the pipeline does not have access to the appropriate certificates.</span></span> <span data-ttu-id="d5804-110">因此，它不解密传入消息或验证签名。</span><span class="sxs-lookup"><span data-stu-id="d5804-110">Therefore, it does not decrypt the incoming message or validate the signature.</span></span> <span data-ttu-id="d5804-111">此外，它将无法访问 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="d5804-111">Also, it won't be able to access the MessageBox database.</span></span>  


## <a name="known-install-issues"></a><span data-ttu-id="d5804-112">已知的安装问题</span><span class="sxs-lookup"><span data-stu-id="d5804-112">Known install issues</span></span>


### <a name="btarn-http-front-end-feature-configuration-fails"></a><span data-ttu-id="d5804-113">BTARN HTTP 前端功能配置失败</span><span class="sxs-lookup"><span data-stu-id="d5804-113">BTARN HTTP Front End Feature configuration fails</span></span>  
 <span data-ttu-id="d5804-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="d5804-114">**Problem**</span></span>  

 <span data-ttu-id="d5804-115">如果通过执行自定义安装来仅安装 BTARN HTTP 前端功能，安装完成后，BTARN 配置可能会因以下错误而失败：</span><span class="sxs-lookup"><span data-stu-id="d5804-115">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail with the following error after setup has completed:</span></span> 

`Failed to create object for feature: WebApp`  

 <span data-ttu-id="d5804-116">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d5804-116">**Resolution**</span></span>  

<span data-ttu-id="d5804-117">手动复制文件并重新配置：</span><span class="sxs-lookup"><span data-stu-id="d5804-117">Manually copy files and reconfigure:</span></span> 

1. <span data-ttu-id="d5804-118">将以下两个文件从 BizTalk Server 的计算机复制到安装了 BTARN HTTP 前端功能的计算机：</span><span class="sxs-lookup"><span data-stu-id="d5804-118">Copy the following two files from an BizTalk Server computer to the computer on which you installed the BTARN HTTP Front End feature:</span></span>

   - <span data-ttu-id="d5804-119">Microsoft.VC80.ATL.manifest</span><span class="sxs-lookup"><span data-stu-id="d5804-119">Microsoft.VC80.ATL.manifest</span></span>  

   - <span data-ttu-id="d5804-120">atl80.dll</span><span class="sxs-lookup"><span data-stu-id="d5804-120">atl80.dll</span></span>  

     <span data-ttu-id="d5804-121">如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 <*驱动器*>: \Program Files\Microsoft Visual Studio < 版本\>\VC\redist\x86\Microsoft.VC100.ATL.</span><span class="sxs-lookup"><span data-stu-id="d5804-121">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is <*drive*>:\Program Files\Microsoft Visual Studio <version\>\VC\redist\x86\Microsoft.VC100.ATL.</span></span>  

     <span data-ttu-id="d5804-122">如果在同一 BizTalk Server 计算机上未安装 Visual Studio，两个文件的源文件夹是在 <*驱动器*>: \WINDOWS\WinSxS。</span><span class="sxs-lookup"><span data-stu-id="d5804-122">If Visual Studio is not installed on the same BizTalk Server computer, the source folder for the two files is under <*drive*>:\WINDOWS\WinSxS.</span></span>  

2. <span data-ttu-id="d5804-123">将复制的文件添加到安装了 BTARN HTTP 前端功能的计算机。</span><span class="sxs-lookup"><span data-stu-id="d5804-123">Add the copied files to the computer on which you installed BTARN HTTP Front End feature.</span></span> <span data-ttu-id="d5804-124">默认情况下，将文件复制到 <*驱动器*>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet。</span><span class="sxs-lookup"><span data-stu-id="d5804-124">By default, copy the files to <*drive*>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet.</span></span>  

3. <span data-ttu-id="d5804-125">文件复制到 HTTP 前端计算机后，运行**Configuration.exe**试。</span><span class="sxs-lookup"><span data-stu-id="d5804-125">After you have copied the files to the HTTP Front End computer, run **Configuration.exe** again.</span></span>  

### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a><span data-ttu-id="d5804-126">某些 BTARN 程序集后仍保持在 GAC 中卸载</span><span class="sxs-lookup"><span data-stu-id="d5804-126">Some BTARN Assemblies stay in GAC after uninstalling</span></span>  
 <span data-ttu-id="d5804-127">**问题**</span><span class="sxs-lookup"><span data-stu-id="d5804-127">**Problem**</span></span>  

 <span data-ttu-id="d5804-128">当你卸载 BTARN 后时，某些程序集保留在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="d5804-128">When you uninstall BTARN, some assemblies remain in the global assembly cache (GAC).</span></span>  

 <span data-ttu-id="d5804-129">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d5804-129">**Resolution**</span></span>  

 <span data-ttu-id="d5804-130">重新安装 BTARN 前，从 GAC 中删除程序集。</span><span class="sxs-lookup"><span data-stu-id="d5804-130">Remove the assemblies from the GAC before reinstalling BTARN.</span></span>  

 <span data-ttu-id="d5804-131">使用**BtarnClean**实用程序删除程序集的 SDK。</span><span class="sxs-lookup"><span data-stu-id="d5804-131">Use the **BtarnClean** utility from the SDK to remove the assemblies.</span></span> <span data-ttu-id="d5804-132">该实用程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d5804-132">The utility performs the following actions:</span></span>  

- <span data-ttu-id="d5804-133">停止和取消登记所有 BTARN 业务流程。</span><span class="sxs-lookup"><span data-stu-id="d5804-133">Stops and unenlists all the BTARN orchestrations.</span></span>  

- <span data-ttu-id="d5804-134">停止和删除所有关联的端口。</span><span class="sxs-lookup"><span data-stu-id="d5804-134">Stops and deletes all the associated ports.</span></span>  

- <span data-ttu-id="d5804-135">取消部署所有 Microsoft.Solutions.BTARN.\* 程序集。</span><span class="sxs-lookup"><span data-stu-id="d5804-135">Undeploys all the Microsoft.Solutions.BTARN.\* assemblies.</span></span>  

  <span data-ttu-id="d5804-136">运行该实用程序后，如果仍有程序集保留在 GAC 中，请打开 Windows 资源管理器，转到“C:\Windows\Assembly”文件夹，然后手动删除所有以 Microsoft.Solutions.BTARN 开头的程序集。</span><span class="sxs-lookup"><span data-stu-id="d5804-136">After running the utility, if there are assemblies remaining in the GAC, open Windows Explorer, go to the "C:\Windows\Assembly" folder, and then manually delete all assemblies starting with Microsoft.Solutions.BTARN.</span></span>  

### <a name="service-unavailable-error-on-64-bit-os"></a><span data-ttu-id="d5804-137">64 位操作系统上的服务不可用错误</span><span class="sxs-lookup"><span data-stu-id="d5804-137">Service Unavailable error on 64-bit OS</span></span>
 <span data-ttu-id="d5804-138">**问题**</span><span class="sxs-lookup"><span data-stu-id="d5804-138">**Problem**</span></span>  

 <span data-ttu-id="d5804-139">你可能会收到`Service Unavailable`错误时尝试访问 BTARN HTTP 接收位置在 64 位 Windows 操作系统上的。</span><span class="sxs-lookup"><span data-stu-id="d5804-139">You may get a `Service Unavailable` error when trying to access the BTARN HTTP receive location on 64-bit Windows operating systems.</span></span>  

 <span data-ttu-id="d5804-140">**原因**</span><span class="sxs-lookup"><span data-stu-id="d5804-140">**Cause**</span></span>  

 <span data-ttu-id="d5804-141">此问题可能是由“RPCProxy.dll”ISAPI 筛选器造成的。</span><span class="sxs-lookup"><span data-stu-id="d5804-141">This issue can be caused by the "RPCProxy.dll" ISAPI filter.</span></span>  

 <span data-ttu-id="d5804-142">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d5804-142">**Resolution**</span></span>  

<span data-ttu-id="d5804-143">删除对 RPC 代理 ISAPI 筛选器的引用并重新启动 IIS:</span><span class="sxs-lookup"><span data-stu-id="d5804-143">Remove references to the RPC proxy ISAPI filter and restart IIS:</span></span>

1.  <span data-ttu-id="d5804-144">在 Internet 信息服务 (IIS) 管理器中，右键单击**网站**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d5804-144">In Internet Information Services (IIS) Manager, right-click **Web Sites**, and then click **Properties**.</span></span>  

2.  <span data-ttu-id="d5804-145">在中**的 Web 站点属性**对话框中，单击**ISAPI 筛选器**选项卡上，删除**RPC 代理**筛选，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5804-145">In the **Web Site Properties** dialog box, click the **ISAPI filters** tab, remove **RPC Proxy** filter, and then click **OK**.</span></span>  

3.  <span data-ttu-id="d5804-146">重新启动 IIS。</span><span class="sxs-lookup"><span data-stu-id="d5804-146">Restart IIS.</span></span>  

4.  <span data-ttu-id="d5804-147">在重新启动 IIS 后，请尝试访问http://localhost。</span><span class="sxs-lookup"><span data-stu-id="d5804-147">After you have restarted IIS, try accessing http://localhost.</span></span> <span data-ttu-id="d5804-148">你会收到从 Internet 浏览器返回的 400 消息。</span><span class="sxs-lookup"><span data-stu-id="d5804-148">You should get the 400 message back from the Internet browser.</span></span>  

### <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="d5804-149">不支持 SQL Server 混合模式</span><span class="sxs-lookup"><span data-stu-id="d5804-149">SQL Server Mixed Mode not supported</span></span>  
<span data-ttu-id="d5804-150">在混合模式下，BTARN 不支持 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d5804-150">BTARN does not support SQL Server in mixed mode.</span></span>  

### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a><span data-ttu-id="d5804-151">运行 setupx64.bat 设置双操作 PIPAutomation 业务流程示例</span><span class="sxs-lookup"><span data-stu-id="d5804-151">Run setupx64.bat to set up the double action PIPAutomation orchestration sample</span></span> 

<span data-ttu-id="d5804-152">运行 \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹来安装双操作 PIPAutomation Orchestration 示例中的 setupx64.bat。</span><span class="sxs-lookup"><span data-stu-id="d5804-152">Run setupx64.bat in \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder to set up the Double Action PIPAutomation Orchestration sample.</span></span>

### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a><span data-ttu-id="d5804-153">将 BTARN 安装文件从 Web 下载到临时文件夹</span><span class="sxs-lookup"><span data-stu-id="d5804-153">Download the BTARN Setup File from the Web to a Temp Folder</span></span>  
 <span data-ttu-id="d5804-154">**问题**</span><span class="sxs-lookup"><span data-stu-id="d5804-154">**Problem**</span></span>  

 <span data-ttu-id="d5804-155">如果您下载 BTARN 自解压可执行文件从 Web，并将其保存到 BizTalk Server 根文件夹中，当您尝试运行可执行文件，BizTalk**安装向导**运行，而不是 BTARN 安装向导。</span><span class="sxs-lookup"><span data-stu-id="d5804-155">If you download the BTARN self-extracting executable file from the Web, and save it to the BizTalk Server root folder, when you attempt to run the executable, the BizTalk **Setup Wizard** runs, instead of the BTARN Setup wizard.</span></span>  

 <span data-ttu-id="d5804-156">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d5804-156">**Resolution**</span></span>  

 <span data-ttu-id="d5804-157">下载 BTARN 自解压可执行文件，并将文件保存到临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5804-157">Download the BTARN self-extracting executable, and save the file to a temp folder.</span></span>
