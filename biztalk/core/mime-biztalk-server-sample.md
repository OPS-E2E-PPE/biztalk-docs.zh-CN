---
title: "MIME （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec6e6e290761ba6d1be2ed08c8519e96c2846fa7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="mime-biztalk-server-sample"></a><span data-ttu-id="a916d-102">MIME （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="a916d-102">MIME (BizTalk Server Sample)</span></span>
<span data-ttu-id="a916d-103">MIME 示例演示如何在发送管道中执行 MIME 编码。</span><span class="sxs-lookup"><span data-stu-id="a916d-103">The MIME sample demonstrates how to perform MIME encoding within a send pipeline.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a916d-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="a916d-104">What This Sample Does</span></span>  
 <span data-ttu-id="a916d-105">本示例将 MIMEIn 文件夹配置为接收位置。</span><span class="sxs-lookup"><span data-stu-id="a916d-105">This sample configures the folder MIMEIn as a receive location.</span></span> <span data-ttu-id="a916d-106">在将文件（例如示例文件 ImageInput.gif）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下步骤处理此文件内的消息：</span><span class="sxs-lookup"><span data-stu-id="a916d-106">When you place a file, such as the sample file ImageInput.gif, in this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following steps:</span></span>  
  
1.  <span data-ttu-id="a916d-107">从接收位置文件夹 MIMEIn 接收消息文件。</span><span class="sxs-lookup"><span data-stu-id="a916d-107">Retrieve the message file from the receive location folder MIMEIn.</span></span>  
  
2.  <span data-ttu-id="a916d-108">在接收管道中，不做任何改变地传递该消息。</span><span class="sxs-lookup"><span data-stu-id="a916d-108">In the receive pipeline, pass the message through unchanged.</span></span>  
  
3.  <span data-ttu-id="a916d-109">在 MessageBox 数据库中，将消息路由至发送管道。</span><span class="sxs-lookup"><span data-stu-id="a916d-109">In the MessageBox database, route the message to the send pipeline.</span></span>  
  
4.  <span data-ttu-id="a916d-110">在发送管道中，执行 MIME 编码并将文件放置到发送适配器文件夹 MIMEOut 中。</span><span class="sxs-lookup"><span data-stu-id="a916d-110">In the send pipeline, perform MIME encoding and place the file into the send adapter folder MIMEOut.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a916d-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="a916d-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="a916d-112">\<*示例路径*\>\Pipelines\MIME\\</span><span class="sxs-lookup"><span data-stu-id="a916d-112">\<*Samples Path*\>\Pipelines\MIME\\</span></span>  
  
 <span data-ttu-id="a916d-113">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="a916d-113">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a916d-114">文件</span><span class="sxs-lookup"><span data-stu-id="a916d-114">File(s)</span></span>|<span data-ttu-id="a916d-115">Description</span><span class="sxs-lookup"><span data-stu-id="a916d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a916d-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a916d-116">Cleanup.bat</span></span>|<span data-ttu-id="a916d-117">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="a916d-117">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="a916d-118">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a916d-118">Removes send and receive ports.</span></span> <span data-ttu-id="a916d-119">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="a916d-119">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="a916d-120">ImageInput.GIF</span><span class="sxs-lookup"><span data-stu-id="a916d-120">ImageInput.GIF</span></span>|<span data-ttu-id="a916d-121">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="a916d-121">Sample input file.</span></span>|  
|<span data-ttu-id="a916d-122">SampleMimeEncoding.btproj</span><span class="sxs-lookup"><span data-stu-id="a916d-122">SampleMimeEncoding.btproj</span></span><br /><br /> <span data-ttu-id="a916d-123">SampleMimeEncoding.sln</span><span class="sxs-lookup"><span data-stu-id="a916d-123">SampleMimeEncoding.sln</span></span>|<span data-ttu-id="a916d-124">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="a916d-124">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="a916d-125">SampleMimeEncodingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="a916d-125">SampleMimeEncodingBinding.xml</span></span>|<span data-ttu-id="a916d-126">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="a916d-126">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="a916d-127">SendMimePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="a916d-127">SendMimePipeline.btp</span></span>|<span data-ttu-id="a916d-128">带 MIME 编码器组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送管道文件。</span><span class="sxs-lookup"><span data-stu-id="a916d-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send pipeline file with the MIME Encoder component.</span></span>|  
|<span data-ttu-id="a916d-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a916d-129">Setup.bat</span></span>|<span data-ttu-id="a916d-130">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="a916d-130">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a916d-131">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="a916d-131">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="a916d-132">使用以下过程可以生成并初始化 MIME 示例。</span><span class="sxs-lookup"><span data-stu-id="a916d-132">Use the following procedure to build and initialize the MIME sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="a916d-133">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="a916d-133">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="a916d-134">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="a916d-134">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="a916d-135">\<*示例路径*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="a916d-135">\<*Samples Path*\>\Pipelines\MIME</span></span>  
  
2.  <span data-ttu-id="a916d-136">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a916d-136">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="a916d-137">在下面的文件夹中，为本示例创建输入 (MIMEIn) 和输出 (MIMEOut) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="a916d-137">Creates the input (MIMEIn) and output (MIMEOut) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="a916d-138">\<*示例路径*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="a916d-138">\<*Samples Path*\>\Pipelines\MIME</span></span>  
  
    -   <span data-ttu-id="a916d-139">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。</span><span class="sxs-lookup"><span data-stu-id="a916d-139">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="a916d-140">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a916d-140">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a916d-141">此示例显示以下警告时创建和绑定的端口：</span><span class="sxs-lookup"><span data-stu-id="a916d-141">This sample displays the following warning when creating and binding the ports:</span></span>  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  <span data-ttu-id="a916d-142">可以安全地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="a916d-142">You can safely ignore these warnings.</span></span> <span data-ttu-id="a916d-143">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="a916d-143">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="a916d-144">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="a916d-144">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a916d-145">如果从安装位置以外的位置运行此示例，必须首先将添加到的引用**Microsoft.BizTalk.Pipeline.Components**程序集。</span><span class="sxs-lookup"><span data-stu-id="a916d-145">If you run this sample from a location other than where it is installed, you must first add a reference to the **Microsoft.BizTalk.Pipeline.Components** assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a916d-146">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="a916d-146">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a916d-147">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="a916d-147">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="a916d-148">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="a916d-148">Use this key pair to sign the resulting assembly.</span></span> <span data-ttu-id="a916d-149">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="a916d-149">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="a916d-150">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="a916d-150">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="a916d-151">运行本示例</span><span class="sxs-lookup"><span data-stu-id="a916d-151">Running This Sample</span></span>  
 <span data-ttu-id="a916d-152">使用以下过程运行 MIME 示例。</span><span class="sxs-lookup"><span data-stu-id="a916d-152">Use the following procedure to run the MIME sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="a916d-153">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="a916d-153">To run this sample</span></span>  
  
1.  <span data-ttu-id="a916d-154">将 ImageInput.gif 文件的副本放到 MIMEIn 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a916d-154">Put a copy of the file ImageInput.gif into the folder MIMEIn.</span></span>  
  
2.  <span data-ttu-id="a916d-155">查看在 MIMEOut 文件夹中创建的文本文件。</span><span class="sxs-lookup"><span data-stu-id="a916d-155">Observe the text file created in the folder MIMEOut.</span></span> <span data-ttu-id="a916d-156">此文本文件是根据消息 ID GUID 命名的。</span><span class="sxs-lookup"><span data-stu-id="a916d-156">The name of this text file is based on the message ID GUID.</span></span> <span data-ttu-id="a916d-157">此文件包含输入文件 ImageInput.gif 的 MIME 编码的内容。</span><span class="sxs-lookup"><span data-stu-id="a916d-157">This file contains MIME-encoded content of the input file ImageInput.gif.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a916d-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a916d-158">See Also</span></span>  
 [<span data-ttu-id="a916d-159">管道（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="a916d-159">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)