---
title: "停止业务流程 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ce53882b20f6615ef280a38eddc8c3e2ef7ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="stop-orchestration-biztalk-server-sample"></a><span data-ttu-id="e37d4-102">停止业务流程 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e37d4-102">Stop Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="e37d4-103">停止业务流程示例演示如何停止 BizTalk Server 业务流程和对其取消登记，后者可选。</span><span class="sxs-lookup"><span data-stu-id="e37d4-103">The Stop Orchestration sample demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e37d4-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="e37d4-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="e37d4-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="e37d4-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e37d4-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e37d4-106">What This Sample Does</span></span>  
 <span data-ttu-id="e37d4-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e37d4-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="e37d4-108">根据给定的业务流程名称和程序集名称，查询部署的特定 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e37d4-108">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="e37d4-109">停止此业务流程。</span><span class="sxs-lookup"><span data-stu-id="e37d4-109">Stop that orchestration.</span></span>  
  
-   <span data-ttu-id="e37d4-110">取消登记此业务流程（可选）。</span><span class="sxs-lookup"><span data-stu-id="e37d4-110">Unenlist that orchestration (optionally).</span></span>  
  
-   <span data-ttu-id="e37d4-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="e37d4-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e37d4-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e37d4-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="e37d4-113">本示例文件位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="e37d4-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="e37d4-114">\<*示例路径*> \Admin\WMI\Stop Orchestration\\</span><span class="sxs-lookup"><span data-stu-id="e37d4-114">\<*Samples Path*>\Admin\WMI\Stop Orchestration\\</span></span>  
  
 <span data-ttu-id="e37d4-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="e37d4-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e37d4-116">文件</span><span class="sxs-lookup"><span data-stu-id="e37d4-116">File(s)</span></span>|<span data-ttu-id="e37d4-117">Description</span><span class="sxs-lookup"><span data-stu-id="e37d4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e37d4-118">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="e37d4-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="e37d4-119">StopOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="e37d4-119">StopOrch.vbs</span></span>|<span data-ttu-id="e37d4-120">VBScript 文件，采用参数指定要停止的和选择取消登记的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e37d4-120">VBScript file that takes parameters to specify an orchestration to be stopped and, optionally, unenlisted.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e37d4-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="e37d4-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e37d4-122">停止业务流程示例由一个 VBScript 文件组成，您无需生成或初始化此文件。</span><span class="sxs-lookup"><span data-stu-id="e37d4-122">The Stop Orchestration sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e37d4-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="e37d4-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e37d4-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="e37d4-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="e37d4-125">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="e37d4-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="e37d4-126">\<*示例路径*> \Admin\WMI\Stop Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="e37d4-126">\<*Samples Path*>\Admin\WMI\Stop Orchestration\VBScript\\</span></span>  
  
2.  <span data-ttu-id="e37d4-127">使用 cscript 程序运行 StopOrch.vbs 文件，传递下列命令行参数，其中第三个参数是可选的：</span><span class="sxs-lookup"><span data-stu-id="e37d4-127">Run the file StopOrch.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="e37d4-128">***OrchestrationName* >。**</span><span class="sxs-lookup"><span data-stu-id="e37d4-128">***OrchestrationName* >.**</span></span> <span data-ttu-id="e37d4-129">要停止的和选择取消登记的 BizTalk Server 业务流程的名称。</span><span class="sxs-lookup"><span data-stu-id="e37d4-129">The name of the BizTalk Server orchestration to be stopped and, optionally, unenlisted.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="e37d4-130">***AssemblyName* >。**</span><span class="sxs-lookup"><span data-stu-id="e37d4-130">***AssemblyName* >.**</span></span> <span data-ttu-id="e37d4-131">在其中部署指定业务流程的 BizTalk 程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="e37d4-131">The name of the BizTalk assembly in which the specified orchestration was deployed.</span></span> <span data-ttu-id="e37d4-132">如果程序集名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="e37d4-132">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="e37d4-133">**取消登记。**</span><span class="sxs-lookup"><span data-stu-id="e37d4-133">**Unenlist.**</span></span> <span data-ttu-id="e37d4-134">用于指示除停止指定业务流程外还应取消登记该业务流程的可选文本字符串。</span><span class="sxs-lookup"><span data-stu-id="e37d4-134">An optional, literal string used to indicate that the specified orchestration should be unenlisted in addition to being stopped.</span></span>  
  
         <span data-ttu-id="e37d4-135">例如：</span><span class="sxs-lookup"><span data-stu-id="e37d4-135">For example:</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="e37d4-136">-或者-</span><span class="sxs-lookup"><span data-stu-id="e37d4-136">-OR-</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a><span data-ttu-id="e37d4-137">注释</span><span class="sxs-lookup"><span data-stu-id="e37d4-137">Comments</span></span>  
 <span data-ttu-id="e37d4-138">在 BizTalk Server 管理控制台中可执行的所有任务也可通过使用访问 Windows WMI 对象模型的脚本来执行。</span><span class="sxs-lookup"><span data-stu-id="e37d4-138">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using scripts that access the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="e37d4-139">StopOrch.vbs 脚本文件包含详细注释，对其执行的操作进行进一步说明。</span><span class="sxs-lookup"><span data-stu-id="e37d4-139">The script file StopOrch.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="e37d4-140">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="e37d4-140">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37d4-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e37d4-141">See Also</span></span>  
 [<span data-ttu-id="e37d4-142">管理员-WMI （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="e37d4-142">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)