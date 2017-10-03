---
title: "删除接收端口 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b97c3b6fe5e743e6bf19c979b994cc7eb5a942de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="remove-receive-port-biztalk-server-sample"></a><span data-ttu-id="900c8-102">删除接收端口 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="900c8-102">Remove Receive Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="900c8-103">删除接收端口示例演示了如何删除一个或多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="900c8-103">The Remove Receive Port sample demonstrates how to remove one or more receive ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="900c8-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="900c8-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="900c8-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="900c8-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="900c8-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="900c8-106">What This Sample Does</span></span>  
 <span data-ttu-id="900c8-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="900c8-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="900c8-108">给定接收端口名称，有关匹配接收端口的列表的查询。</span><span class="sxs-lookup"><span data-stu-id="900c8-108">Given a receive port name, query for a list of matching receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="900c8-109">通常情况下，将仅有一个接收与给定名称匹配的端口。</span><span class="sxs-lookup"><span data-stu-id="900c8-109">Generally, there will only be one receive port that matches a given name.</span></span>  
  
-   <span data-ttu-id="900c8-110">删除那些接收端口。</span><span class="sxs-lookup"><span data-stu-id="900c8-110">Remove those receive ports.</span></span>  
  
-   <span data-ttu-id="900c8-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="900c8-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="900c8-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="900c8-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="900c8-113">这些示例位于以下 SDK 的位置：</span><span class="sxs-lookup"><span data-stu-id="900c8-113">The samples are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="900c8-114">\<*示例路径*> \Admin\WMI\Remove 接收 Port\\</span><span class="sxs-lookup"><span data-stu-id="900c8-114">\<*Samples Path*>\Admin\WMI\Remove Receive Port\\</span></span>  
  
 <span data-ttu-id="900c8-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="900c8-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="900c8-116">文件</span><span class="sxs-lookup"><span data-stu-id="900c8-116">File(s)</span></span>|<span data-ttu-id="900c8-117">Description</span><span class="sxs-lookup"><span data-stu-id="900c8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="900c8-118">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="900c8-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="900c8-119">RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="900c8-119">RemoveReceivePort.vbs</span></span>|<span data-ttu-id="900c8-120">VBScript 文件采用一个参数，指定一个或多个接收删除的端口。</span><span class="sxs-lookup"><span data-stu-id="900c8-120">VBScript file that takes a parameter that specifies one or more receive ports to remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="900c8-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="900c8-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="900c8-122">删除接收端口示例包含一个 VBScript 文件不需要生成或初始化。</span><span class="sxs-lookup"><span data-stu-id="900c8-122">The Remove Receive Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="900c8-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="900c8-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="900c8-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="900c8-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="900c8-125">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="900c8-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="900c8-126">\<*示例路径*> \Admin\WMI\Remove 接收 Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="900c8-126">\<*Samples Path*>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="900c8-127">运行文件 RemoveReceivePort.vbs 使用 cscript 程序中，将以下命令行自变量传递：</span><span class="sxs-lookup"><span data-stu-id="900c8-127">Run the file RemoveReceivePort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     **\<**   
     <span data-ttu-id="900c8-128">***ReceivePortName* >**。</span><span class="sxs-lookup"><span data-stu-id="900c8-128">***ReceivePortName* >**.</span></span> <span data-ttu-id="900c8-129">接收端口，若要删除的名称。</span><span class="sxs-lookup"><span data-stu-id="900c8-129">The name of the receive port(s) to remove.</span></span> <span data-ttu-id="900c8-130">如果接收端口名称包含空格，请将名称括在引号中。</span><span class="sxs-lookup"><span data-stu-id="900c8-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="900c8-131">例如：</span><span class="sxs-lookup"><span data-stu-id="900c8-131">For example:</span></span>  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="900c8-132">注释</span><span class="sxs-lookup"><span data-stu-id="900c8-132">Comments</span></span>  
 <span data-ttu-id="900c8-133">你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="900c8-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="900c8-134">脚本文件 RemoveReceivePort.vbs 包含详细的注释，使用更多有关它执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="900c8-134">The script file RemoveReceivePort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="900c8-135">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="900c8-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900c8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="900c8-136">See Also</span></span>  
 [<span data-ttu-id="900c8-137">管理员-WMI （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="900c8-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)