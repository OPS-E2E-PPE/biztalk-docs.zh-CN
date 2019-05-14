---
title: 使用 BizTalk 适配器跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b381e869597c11281f715ba0d05d504671cd062
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401705"
---
# <a name="using-biztalk-adapter-tracing"></a><span data-ttu-id="85d0a-102">使用 BizTalk 适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="85d0a-102">Using BizTalk Adapter Tracing</span></span>
<span data-ttu-id="85d0a-103">本主题介绍如何安装 Trace Log 工具以及如何启用 BizTalk 适配器跟踪。</span><span class="sxs-lookup"><span data-stu-id="85d0a-103">This topic describes how to install the Trace Log tool and how to enable BizTalk adapter tracing.</span></span>  
  
## <a name="install-the-trace-log-tool"></a><span data-ttu-id="85d0a-104">安装 Trace Log 工具</span><span class="sxs-lookup"><span data-stu-id="85d0a-104">Install the Trace Log Tool</span></span>  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a><span data-ttu-id="85d0a-105">安装 Trace Log 工具 (tracelog.exe)</span><span class="sxs-lookup"><span data-stu-id="85d0a-105">To install the Trace Log tool (tracelog.exe)</span></span>  
  
1. <span data-ttu-id="85d0a-106">从 [适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新](http://go.microsoft.com/fwlink/?LinkId=128279) 网站下载跟踪日志工具。</span><span class="sxs-lookup"><span data-stu-id="85d0a-106">Download the Trace Log tool from the [Microsoft® Windows® Software Development Kit Update for Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) Web site.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85d0a-107">即使您运行的是 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，也要安装 6.0 版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="85d0a-107">Install this version (6.0) of the SDK even if you are running [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="85d0a-108">如果您在安装**Windows SDK for Windows Server 2008 和.NET Framework 3.5**版本 (v。</span><span class="sxs-lookup"><span data-stu-id="85d0a-108">If you install the **Windows SDK for Windows Server 2008 and .NET Framework 3.5** version (v.</span></span> <span data-ttu-id="85d0a-109">6.1)，则不会安装跟踪日志工具。</span><span class="sxs-lookup"><span data-stu-id="85d0a-109">6.1), it will not install the Trace Log tool.</span></span>  
  
2. <span data-ttu-id="85d0a-110">通过在网页底部单击 **PSDK-x86.exe** 文件的链接，启动 **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** Web 安装程序。</span><span class="sxs-lookup"><span data-stu-id="85d0a-110">Start the **Microsoft® Windows® Software Development Kit Update for Windows Vista** Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85d0a-111">如果您使用的是 64 位版本的 Windows，请为您的系统选择正确的下载文件。</span><span class="sxs-lookup"><span data-stu-id="85d0a-111">If you are using a 64-bit version of Windows choose the correct files to download for your system.</span></span>  
  
3. <span data-ttu-id="85d0a-112">在“选择安装类型”  对话框中，选择“自定义”  安装选项，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="85d0a-112">In the **Select an Installation Type** dialog box, choose the option for a **Custom** installation, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="85d0a-113">接受默认安装位置，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="85d0a-113">Accept the default installation location and then click **Next**.</span></span>  
  
5. <span data-ttu-id="85d0a-114">在“自定义安装”  对话框中，单击以清除所有可用的功能。</span><span class="sxs-lookup"><span data-stu-id="85d0a-114">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  
  
6. <span data-ttu-id="85d0a-115">展开“Microsoft Windows Core SDK”  功能，然后展开“工具”  功能。</span><span class="sxs-lookup"><span data-stu-id="85d0a-115">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  
  
7. <span data-ttu-id="85d0a-116">选择“工具 (Intel 64 位)”  功能，然后单击“将安装到本地硬盘” 。</span><span class="sxs-lookup"><span data-stu-id="85d0a-116">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  
  
8. <span data-ttu-id="85d0a-117">先后单击“下一步” 两次  以启动安装。</span><span class="sxs-lookup"><span data-stu-id="85d0a-117">Click **Next**, and then click **Next** again to start the installation.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85d0a-118">安装 **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** 后，系统可能会提示您重新启动计算机，具体取决于您选择随跟踪日志工具一起安装的其他功能。</span><span class="sxs-lookup"><span data-stu-id="85d0a-118">After installing the **Microsoft® Windows® Software Development Kit Update for Windows Vista** you may be prompted to reboot depending upon what other features you chose to install along with the Trace Log tool.</span></span> <span data-ttu-id="85d0a-119">这是因为， **适用于 Windows Vista 的 Microsoft® Windows® 软件开发包更新** 的某些组件只有在完成重新启动后才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="85d0a-119">This is because certain components of the **Microsoft® Windows® Software Development Kit Update for Windows Vista** will not function correctly until the reboot has been completed.</span></span> <span data-ttu-id="85d0a-120">不需要重新启动即可使用 Trace Log 工具。</span><span class="sxs-lookup"><span data-stu-id="85d0a-120">You do not need to reboot to use the Trace Log tool.</span></span>  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a><span data-ttu-id="85d0a-121">使用 trace.cmd 启用 BizTalk 适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="85d0a-121">Enable BizTalk Adapter Tracing with trace.cmd</span></span>  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a><span data-ttu-id="85d0a-122">启用 BizTalk 适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="85d0a-122">To enable BizTalk adapter tracing</span></span>  
  
1. <span data-ttu-id="85d0a-123">在命令提示符下，将当前目录更改到安装了 BizTalk Server 的目录。</span><span class="sxs-lookup"><span data-stu-id="85d0a-123">At a command prompt, change the current directory to the directory where BizTalk Server is installed.</span></span> <span data-ttu-id="85d0a-124">默认情况下，BizTalk Server 安装在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]目录。</span><span class="sxs-lookup"><span data-stu-id="85d0a-124">By default, BizTalk Server is installed in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] directory.</span></span>  <span data-ttu-id="85d0a-125">如果使用 64 位版本的 Windows 和 BizTalk Server，安装路径是[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="85d0a-125">If using a 64-bit version of Windows and BizTalk Server, the installation path is [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)].</span></span>  
  
2. <span data-ttu-id="85d0a-126">键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="85d0a-126">Type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="85d0a-127">**trace-tools"Trace Log 工具的路径"**</span><span class="sxs-lookup"><span data-stu-id="85d0a-127">**trace -tools "Path of the Trace Log tool"**</span></span>  
  
    <span data-ttu-id="85d0a-128">默认情况下，跟踪日志工具 (tracelog.exe) 位于 **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** 目录下。</span><span class="sxs-lookup"><span data-stu-id="85d0a-128">By default, the Trace Log tool (tracelog.exe) is located in the **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** directory.</span></span> <span data-ttu-id="85d0a-129">如果使用的是 64 位版本的 Windows，则跟踪日志工具位于 **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**下。</span><span class="sxs-lookup"><span data-stu-id="85d0a-129">If using a 64-bit version of Windows the Trace Log tool is located at **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**.</span></span>  <span data-ttu-id="85d0a-130">必须将 Trace Log 工具的路径用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="85d0a-130">You must enclose the path of the Trace Log tool in quotation marks.</span></span>  
  
    <span data-ttu-id="85d0a-131">例如，请键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="85d0a-131">For example, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="85d0a-132">**trace -tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span><span class="sxs-lookup"><span data-stu-id="85d0a-132">**trace -tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85d0a-133"> *\*-tools** 开关向 Trace.cmd 文件指明 Tracelog.exe 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="85d0a-133">The **-tools** switch indicates to the Trace.cmd file the location of the Tracelog.exe file.</span></span>  
   >   
   >  <span data-ttu-id="85d0a-134">如果成功运行该命令，输出结果将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="85d0a-134">If the command successfully runs, the output will be like below:</span></span>  
   >   
   >  <span data-ttu-id="85d0a-135">**跟踪 2.0-管理 BizTalk 2006 版本位跟踪。**</span><span class="sxs-lookup"><span data-stu-id="85d0a-135">**trace 2.0 - Manage BizTalk 2006 Release Bits Tracing.**</span></span>  
   >   
   >  <span data-ttu-id="85d0a-136">**设置为"C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"TRACE_TOOL_SEARCH_PATH**</span><span class="sxs-lookup"><span data-stu-id="85d0a-136">**Setting TRACE_TOOL_SEARCH_PATH to "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin "**</span></span>  
  
## <a name="capture-trace-output-with-tracecmd"></a><span data-ttu-id="85d0a-137">使用 trace.cmd 捕获跟踪输出</span><span class="sxs-lookup"><span data-stu-id="85d0a-137">Capture Trace output with trace.cmd</span></span>  
  
#### <a name="to-capture-trace-output"></a><span data-ttu-id="85d0a-138">捕获跟踪输出</span><span class="sxs-lookup"><span data-stu-id="85d0a-138">To capture trace output</span></span>  
  
1. <span data-ttu-id="85d0a-139">在命令提示符下，将当前目录更改到安装了 BizTalk Server 的目录。</span><span class="sxs-lookup"><span data-stu-id="85d0a-139">At a command prompt, change the current directory to the directory where BizTalk Server is installed.</span></span>  
  
2. <span data-ttu-id="85d0a-140">在命令提示符下，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="85d0a-140">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="85d0a-141">**trace -start**</span><span class="sxs-lookup"><span data-stu-id="85d0a-141">**trace -start**</span></span>  
  
3. <span data-ttu-id="85d0a-142">重现要捕获其跟踪输出的方案。</span><span class="sxs-lookup"><span data-stu-id="85d0a-142">Reproduce the scenario for which you want to capture trace output.</span></span>  
  
4. <span data-ttu-id="85d0a-143">在命令提示符下，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="85d0a-143">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="85d0a-144">**trace -stop**</span><span class="sxs-lookup"><span data-stu-id="85d0a-144">**trace -stop**</span></span>  
  
5. <span data-ttu-id="85d0a-145">停止跟踪之后，将在安装 **的文件夹中生成一个名为** Btstrace.bin [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="85d0a-145">After you stop the trace, a binary file that is named **Btstrace.bin** is generated in the folder where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span>  
  
6. <span data-ttu-id="85d0a-146">将 **Btstrace.bin** 文件发送到 Microsoft 产品支持服务部门进行分析。</span><span class="sxs-lookup"><span data-stu-id="85d0a-146">Send the **Btstrace.bin** file to Microsoft Product Support Services for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d0a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="85d0a-147">See Also</span></span>  
 <span data-ttu-id="85d0a-148">[使用适配器](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="85d0a-148">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="85d0a-149">Windows SharePoint Services 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="85d0a-149">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)