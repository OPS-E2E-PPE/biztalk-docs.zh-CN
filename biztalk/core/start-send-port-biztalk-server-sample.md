---
title: "开始发送端口 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb9db99f06e05877939631e4306be396c47ebda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="start-send-port-biztalk-server-sample"></a><span data-ttu-id="4a0f1-102">开始发送端口 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4a0f1-102">Start Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="4a0f1-103">启动发送端口示例演示如何在使用 FILE 适配器时启动发送端口和选择设置主传输地址。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-103">The Start Send Port sample demonstrates how to start a send port and optionally set the Primary Transport Address when using the FILE adapter.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4a0f1-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="4a0f1-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4a0f1-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="4a0f1-106">What This Sample Does</span></span>  
 <span data-ttu-id="4a0f1-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="4a0f1-108">根据给定的发送端口名称，查询匹配的发送端口的列表。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a0f1-109">通常，只有一个发送端口与给定名称匹配。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="4a0f1-110">为这些发送端口设置主传输地址（相对于安装路径）。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-110">Set the Primary Transport Address for those send ports (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="4a0f1-111">启动这些发送端口。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-111">Start those send ports.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4a0f1-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="4a0f1-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="4a0f1-113">本示例文件位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="4a0f1-114">\<*示例路径*> \Admin\WMI\Start 发送 Port\\</span><span class="sxs-lookup"><span data-stu-id="4a0f1-114">\<*Samples Path*>\Admin\WMI\Start Send Port\\</span></span>  
  
 <span data-ttu-id="4a0f1-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="4a0f1-116">文件</span><span class="sxs-lookup"><span data-stu-id="4a0f1-116">File(s)</span></span>|<span data-ttu-id="4a0f1-117">Description</span><span class="sxs-lookup"><span data-stu-id="4a0f1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a0f1-118">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="4a0f1-119">StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="4a0f1-119">StartSendPort.vbs</span></span>|<span data-ttu-id="4a0f1-120">VBScript 文件，采用指定要启动的发送端口以及与此端口关联的主传输地址的新值（可选）的参数。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-120">VBScript file that takes parameters that specify a send port to start, and optionally, a new value for the Primary Transport Address associated with that port.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="4a0f1-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="4a0f1-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="4a0f1-122">启动发送端口示例由一个 VBScript 文件组成，您无需生成或初始化此文件。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-122">The Start Send Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="4a0f1-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="4a0f1-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="4a0f1-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="4a0f1-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="4a0f1-125">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="4a0f1-126">\<*示例路径*> \Admin\WMI\Start 发送 Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="4a0f1-126">\<*Samples Path*>\Admin\WMI\Start Send Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="4a0f1-127">使用 cscript 程序运行 StartSendPort.vbs 文件，传递下列命令行参数，其中第二个参数是可选的：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-127">Run the file StartSendPort.vbs using the cscript program, passing the following command-line arguments, the second of which is optional:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="4a0f1-128">***SendPortName* >。**</span><span class="sxs-lookup"><span data-stu-id="4a0f1-128">***SendPortName* >.**</span></span> <span data-ttu-id="4a0f1-129">要启动的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-129">The name of the send port to start.</span></span> <span data-ttu-id="4a0f1-130">如果发送端口名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-130">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="4a0f1-131">***PrimaryTransportAddress* >。**</span><span class="sxs-lookup"><span data-stu-id="4a0f1-131">***PrimaryTransportAddress* >.**</span></span> <span data-ttu-id="4a0f1-132">相对于产品安装位置的主传输地址，通过指定此参数，您可以更改此地址。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-132">The Primary Transport Address, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="4a0f1-133">如果主适配器地址包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-133">If the primary adapter address contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="4a0f1-134">例如：</span><span class="sxs-lookup"><span data-stu-id="4a0f1-134">For example:</span></span>  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="4a0f1-135">注释</span><span class="sxs-lookup"><span data-stu-id="4a0f1-135">Comments</span></span>  
 <span data-ttu-id="4a0f1-136">你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-136">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="4a0f1-137">StartSendPort.vbs 脚本文件包含详细注释，对其执行的操作做了进一步说明。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-137">The script file StartSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="4a0f1-138">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="4a0f1-138">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0f1-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a0f1-139">See Also</span></span>  
 [<span data-ttu-id="4a0f1-140">管理员-WMI （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="4a0f1-140">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)