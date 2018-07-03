---
title: 使用分析 MQSeries 适配器错误跟踪工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de3ac3f94edb6ca1c3f7f366ef5c0578eb69d76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999030"
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a><span data-ttu-id="71e4f-102">使用跟踪工具分析 MQSeries 适配器错误</span><span class="sxs-lookup"><span data-stu-id="71e4f-102">Analyzing MQSeries Adapter Errors with the Trace Tools</span></span>
<span data-ttu-id="71e4f-103">在运行应用程序时，使用跟踪工具可以分析消息传送故障。</span><span class="sxs-lookup"><span data-stu-id="71e4f-103">You use the trace tools to analyze messaging failures when you run your application.</span></span> <span data-ttu-id="71e4f-104">对于 MQSeries 适配器，您必须使用两个工具：一个用于该适配器和 BizTalk 应用程序 (trace.cmd)，另一个用于 MQSAgent (MQSTrace.cmd)。</span><span class="sxs-lookup"><span data-stu-id="71e4f-104">With the MQSeries adapter you must use two tools, one for the adapter and your BizTalk application (trace.cmd), and the other for the MQSAgent (MQSTrace.cmd).</span></span> <span data-ttu-id="71e4f-105">这两个工具使用 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="71e4f-105">Both tools use tracelog.exe.</span></span> <span data-ttu-id="71e4f-106">您必须安装 tracelog.exe，如果你还没有它。</span><span class="sxs-lookup"><span data-stu-id="71e4f-106">You have to install tracelog.exe if you do not already have it.</span></span>  

 <span data-ttu-id="71e4f-107">使用 trace.cmd 和 mqstrace.cmd 时您必须设置一个选项 (**-工具**)，以便这些工具能够找到 tracelog.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="71e4f-107">With both trace.cmd and MQSTrace.cmd you have to set an option (**-tools**) so that these tools can find the tracelog.exe file.</span></span>  

## <a name="install-the-trace-utility"></a><span data-ttu-id="71e4f-108">安装跟踪实用工具</span><span class="sxs-lookup"><span data-stu-id="71e4f-108">Install the Trace Utility</span></span>  
 <span data-ttu-id="71e4f-109">若要安装 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="71e4f-109">To install the BizTalk Adapter Trace Utility, follow these steps:</span></span>  

1.  <span data-ttu-id="71e4f-110">若要下载 Tracelog.exe 文件，请访问 Microsoft Platform SDK 下载网站上[ http://go.microsoft.com/fwlink/?LinkId=21975 ](http://go.microsoft.com/fwlink/?LinkId=21975)。</span><span class="sxs-lookup"><span data-stu-id="71e4f-110">To download the Tracelog.exe file, visit the Microsoft Platform SDK download Web site at [http://go.microsoft.com/fwlink/?LinkId=21975](http://go.microsoft.com/fwlink/?LinkId=21975).</span></span>  

2.  <span data-ttu-id="71e4f-111">首先单击的链接的 Platform SDK Web 安装程序**PSDK-x86.exe** Web 页面底部的文件。</span><span class="sxs-lookup"><span data-stu-id="71e4f-111">Start the Platform SDK Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  

3.  <span data-ttu-id="71e4f-112">出现提示时，选择自定义安装选项。</span><span class="sxs-lookup"><span data-stu-id="71e4f-112">When you are prompted, choose the option for a custom installation.</span></span>  

4.  <span data-ttu-id="71e4f-113">在“自定义安装”  对话框中，单击以清除所有可用的功能。</span><span class="sxs-lookup"><span data-stu-id="71e4f-113">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  

5.  <span data-ttu-id="71e4f-114">展开“Microsoft Windows Core SDK”  功能，然后展开“工具”  功能。</span><span class="sxs-lookup"><span data-stu-id="71e4f-114">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  

6.  <span data-ttu-id="71e4f-115">选择“工具 (Intel 64 位)”  功能，然后单击“将安装到本地硬盘” 。</span><span class="sxs-lookup"><span data-stu-id="71e4f-115">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  

7.  <span data-ttu-id="71e4f-116">先后单击“下一步” 两次  以启动安装。</span><span class="sxs-lookup"><span data-stu-id="71e4f-116">Click **Next**, and then click **Next** again to start the installation.</span></span>  

8.  <span data-ttu-id="71e4f-117">找到*驱动器*:\\*MicrosoftPlatformSDKInstallationFolder\bin*文件夹，并复制 Tracelog.exe 文件的 Microsoft BizTalk Server 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="71e4f-117">Locate the *drive*:\\*MicrosoftPlatformSDKInstallationFolder\bin* folder, and then copy the Tracelog.exe file to the Microsoft BizTalk Server installation folder.</span></span> <span data-ttu-id="71e4f-118">BizTalk Server 安装文件夹还包含 Trace.cmd 文件。</span><span class="sxs-lookup"><span data-stu-id="71e4f-118">The BizTalk Server installation folder also contains the Trace.cmd file.</span></span>  

## <a name="enable-the-trace-utility"></a><span data-ttu-id="71e4f-119">启用跟踪实用工具</span><span class="sxs-lookup"><span data-stu-id="71e4f-119">Enable the Trace Utility</span></span>  
 <span data-ttu-id="71e4f-120">若要在 BizTalk Server 中启用 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="71e4f-120">To enable the BizTalk Adapter Trace Utility in BizTalk Server, follow these steps:</span></span>  

1.  <span data-ttu-id="71e4f-121">将移动到包含 trace.cmd 的目录。</span><span class="sxs-lookup"><span data-stu-id="71e4f-121">Move to the directory that contains trace.cmd.</span></span> <span data-ttu-id="71e4f-122">默认位置是 Microsoft BizTalk Server 目录。</span><span class="sxs-lookup"><span data-stu-id="71e4f-122">The default location is the Microsoft BizTalk Server directory.</span></span>  

2.  <span data-ttu-id="71e4f-123">键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="71e4f-123">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  

     <span data-ttu-id="71e4f-124">**trace-tools"c:\Program Files\Microsoft SDK\Bin"**</span><span class="sxs-lookup"><span data-stu-id="71e4f-124">**trace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  

3.  <span data-ttu-id="71e4f-125">转至包含 MQSTrace.cmd 的目录。</span><span class="sxs-lookup"><span data-stu-id="71e4f-125">Move to the directory that contains MQSTrace.cmd.</span></span>  

4.  <span data-ttu-id="71e4f-126">键入以下命令（该命令将使用引号中的目录来替换您的计算机上包含 tracelog.exe 文件的目录），然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="71e4f-126">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  

     <span data-ttu-id="71e4f-127">**MQSTrace-工具"c:\Program Files\Microsoft SDK\Bin"**</span><span class="sxs-lookup"><span data-stu-id="71e4f-127">**MQSTrace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  

## <a name="run-the-trace-utility"></a><span data-ttu-id="71e4f-128">运行跟踪实用工具</span><span class="sxs-lookup"><span data-stu-id="71e4f-128">Run the Trace Utility</span></span>  
 <span data-ttu-id="71e4f-129">若要运行 BizTalk 适配器跟踪实用工具，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="71e4f-129">To run the BizTalk Adapter Trace Utility, follow these steps:</span></span>  

1. <span data-ttu-id="71e4f-130">在命令提示符处，键入**trace.cmd-start-high**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="71e4f-130">At the command prompt, type **trace.cmd -start -high**, and then press ENTER.</span></span>  

2. <span data-ttu-id="71e4f-131">运行您的故障方案。</span><span class="sxs-lookup"><span data-stu-id="71e4f-131">Run your failure scenario.</span></span>  

3. <span data-ttu-id="71e4f-132">在命令提示符处，键入**trace.cmd-停止**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="71e4f-132">At the command prompt, type **trace.cmd -stop**, and then press ENTER.</span></span>  

4. <span data-ttu-id="71e4f-133">bts2006.bin 文件包含了跟踪工具的输出。</span><span class="sxs-lookup"><span data-stu-id="71e4f-133">The bts2006.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="71e4f-134">请与 Microsoft 产品支持服务联系以进行分析。</span><span class="sxs-lookup"><span data-stu-id="71e4f-134">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="71e4f-135">有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。</span><span class="sxs-lookup"><span data-stu-id="71e4f-135">For more information, see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>  

   <span data-ttu-id="71e4f-136">若要运行 MQSAgent 跟踪实用工具，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="71e4f-136">To run the MQSAgent Trace Utility, follow these steps:</span></span>  

5. <span data-ttu-id="71e4f-137">在命令提示符处，键入**MQSTrace.cmd-start-high**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="71e4f-137">At the command prompt, type **MQSTrace.cmd -start -high**, and then press ENTER.</span></span>  

6. <span data-ttu-id="71e4f-138">运行您的故障方案。</span><span class="sxs-lookup"><span data-stu-id="71e4f-138">Run your failure scenario.</span></span>  

7. <span data-ttu-id="71e4f-139">在命令提示符处，键入**MQSTrace.cmd-停止**。</span><span class="sxs-lookup"><span data-stu-id="71e4f-139">At the command prompt, type **MQSTrace.cmd -stop**.</span></span>  

8. <span data-ttu-id="71e4f-140">MQSAdapterTrace.bin 文件包含了跟踪工具的输出。</span><span class="sxs-lookup"><span data-stu-id="71e4f-140">The MQSAdapterTrace.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="71e4f-141">请与 Microsoft 产品支持服务联系以进行分析。</span><span class="sxs-lookup"><span data-stu-id="71e4f-141">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="71e4f-142">有关详细信息请参阅[ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645)。</span><span class="sxs-lookup"><span data-stu-id="71e4f-142">For more information see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>
