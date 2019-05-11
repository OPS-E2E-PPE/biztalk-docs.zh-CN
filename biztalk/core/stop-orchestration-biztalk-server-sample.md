---
title: 停止业务流程 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f6294442311f2644f6f0bc7efd2261af7712c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244160"
---
# <a name="stop-orchestration-biztalk-server-sample"></a><span data-ttu-id="94a3f-102">停止业务流程 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="94a3f-102">Stop Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="94a3f-103">停止业务流程示例演示如何停止 BizTalk Server 业务流程和 （可选） 若要取消登记它。</span><span class="sxs-lookup"><span data-stu-id="94a3f-103">The Stop Orchestration sample demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="94a3f-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="94a3f-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="94a3f-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="94a3f-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="94a3f-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="94a3f-106">What This Sample Does</span></span>  
 <span data-ttu-id="94a3f-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="94a3f-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="94a3f-108">给定的业务流程名称和程序集名称，查询的特定部署 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="94a3f-108">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="94a3f-109">停止此业务流程。</span><span class="sxs-lookup"><span data-stu-id="94a3f-109">Stop that orchestration.</span></span>  
  
-   <span data-ttu-id="94a3f-110">（可选） 取消登记该业务流程。</span><span class="sxs-lookup"><span data-stu-id="94a3f-110">Unenlist that orchestration (optionally).</span></span>  
  
-   <span data-ttu-id="94a3f-111">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="94a3f-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="94a3f-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="94a3f-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="94a3f-113">示例文件位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="94a3f-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="94a3f-114">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\\</span><span class="sxs-lookup"><span data-stu-id="94a3f-114">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\\</span></span>  
  
 <span data-ttu-id="94a3f-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="94a3f-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="94a3f-116">文件</span><span class="sxs-lookup"><span data-stu-id="94a3f-116">File(s)</span></span>|<span data-ttu-id="94a3f-117">Description</span><span class="sxs-lookup"><span data-stu-id="94a3f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94a3f-118">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="94a3f-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="94a3f-119">StopOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="94a3f-119">StopOrch.vbs</span></span>|<span data-ttu-id="94a3f-120">采用参数指定要停止的和选择取消登记业务流程的 VBScript 文件。</span><span class="sxs-lookup"><span data-stu-id="94a3f-120">VBScript file that takes parameters to specify an orchestration to be stopped and, optionally, unenlisted.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="94a3f-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="94a3f-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="94a3f-122">停止业务流程示例由一个不需要生成或初始化的 VBScript 文件组成。</span><span class="sxs-lookup"><span data-stu-id="94a3f-122">The Stop Orchestration sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="94a3f-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="94a3f-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="94a3f-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="94a3f-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="94a3f-125">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="94a3f-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="94a3f-126">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="94a3f-126">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\VBScript\\</span></span>  
  
2.  <span data-ttu-id="94a3f-127">运行 StopOrch.vbs 使用 cscript 程序中，传递下列命令行参数，第三个是可选的文件：</span><span class="sxs-lookup"><span data-stu-id="94a3f-127">Run the file StopOrch.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   <span data-ttu-id="94a3f-128">**\<** ***OrchestrationName* \>.**</span><span class="sxs-lookup"><span data-stu-id="94a3f-128">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="94a3f-129">BizTalk Server 业务流程要停止的和选择取消登记的名称。</span><span class="sxs-lookup"><span data-stu-id="94a3f-129">The name of the BizTalk Server orchestration to be stopped and, optionally, unenlisted.</span></span>  
  
    -   <span data-ttu-id="94a3f-130">**\<** ***AssemblyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="94a3f-130">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="94a3f-131">在其中部署指定业务流程的 BizTalk 程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="94a3f-131">The name of the BizTalk assembly in which the specified orchestration was deployed.</span></span> <span data-ttu-id="94a3f-132">如果程序集名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="94a3f-132">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="94a3f-133">**取消登记。**</span><span class="sxs-lookup"><span data-stu-id="94a3f-133">**Unenlist.**</span></span> <span data-ttu-id="94a3f-134">用于指示指定的业务流程应在除正在停止已取消登记可选的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="94a3f-134">An optional, literal string used to indicate that the specified orchestration should be unenlisted in addition to being stopped.</span></span>  
  
         <span data-ttu-id="94a3f-135">例如：</span><span class="sxs-lookup"><span data-stu-id="94a3f-135">For example:</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="94a3f-136">-或-</span><span class="sxs-lookup"><span data-stu-id="94a3f-136">-OR-</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a><span data-ttu-id="94a3f-137">注释</span><span class="sxs-lookup"><span data-stu-id="94a3f-137">Comments</span></span>  
 <span data-ttu-id="94a3f-138">可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="94a3f-138">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using scripts that access the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="94a3f-139">StopOrch.vbs 脚本文件包含详细的注释了进一步说明，它执行的操作。</span><span class="sxs-lookup"><span data-stu-id="94a3f-139">The script file StopOrch.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="94a3f-140">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="94a3f-140">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a3f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="94a3f-141">See Also</span></span>  
 [<span data-ttu-id="94a3f-142">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="94a3f-142">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)