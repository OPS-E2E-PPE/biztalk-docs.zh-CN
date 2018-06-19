---
title: 删除发送端口 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8b82af2be42342d51429e42d1952816ee0dd07a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971443"
---
# <a name="remove-send-port-biztalk-server-sample"></a><span data-ttu-id="8c446-102">删除发送端口 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="8c446-102">Remove Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="8c446-103">删除发送端口示例演示如何取消登记，并删除其中一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="8c446-103">The Remove Send Port sample demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8c446-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="8c446-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="8c446-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="8c446-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="8c446-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="8c446-106">What This Sample Does</span></span>  
 <span data-ttu-id="8c446-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8c446-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="8c446-108">根据给定的发送端口名称，查询匹配的发送端口的列表。</span><span class="sxs-lookup"><span data-stu-id="8c446-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8c446-109">通常，只有一个发送端口与给定名称匹配。</span><span class="sxs-lookup"><span data-stu-id="8c446-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="8c446-110">取消登记那些发送端口。</span><span class="sxs-lookup"><span data-stu-id="8c446-110">Unenlist those send ports.</span></span>  
  
-   <span data-ttu-id="8c446-111">删除那些发送端口。</span><span class="sxs-lookup"><span data-stu-id="8c446-111">Delete those send ports.</span></span>  
  
-   <span data-ttu-id="8c446-112">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="8c446-112">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8c446-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="8c446-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="8c446-114">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="8c446-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="8c446-115">\<*示例路径*\>\Admin\WMI\Remove 发送 Port\\</span><span class="sxs-lookup"><span data-stu-id="8c446-115">\<*Samples Path*\>\Admin\WMI\Remove Send Port\\</span></span>  
  
 <span data-ttu-id="8c446-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="8c446-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="8c446-117">文件</span><span class="sxs-lookup"><span data-stu-id="8c446-117">File(s)</span></span>|<span data-ttu-id="8c446-118">Description</span><span class="sxs-lookup"><span data-stu-id="8c446-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c446-119">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="8c446-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="8c446-120">RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="8c446-120">RemoveSendPort.vbs</span></span>|<span data-ttu-id="8c446-121">VBScript 文件采用一个参数，指定一个或多个发送端口中取消和删除。</span><span class="sxs-lookup"><span data-stu-id="8c446-121">VBScript file that takes a parameter that specifies one or more send ports to unenlist and remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="8c446-122">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="8c446-122">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="8c446-123">删除发送端口示例包含你不需要生成或初始化单个 VBScript 文件。</span><span class="sxs-lookup"><span data-stu-id="8c446-123">The Remove Send Port sample consists of a single VBScript file that you not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="8c446-124">运行本示例</span><span class="sxs-lookup"><span data-stu-id="8c446-124">Running This Sample</span></span>  
  
#### <a name="to-run-the-remove-send-port-sample"></a><span data-ttu-id="8c446-125">若要运行删除发送端口示例</span><span class="sxs-lookup"><span data-stu-id="8c446-125">To run the Remove Send Port sample</span></span>  
  
1.  <span data-ttu-id="8c446-126">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="8c446-126">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="8c446-127">\<*示例路径*\>\Admin\WMI\Remove 接收 Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="8c446-127">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="8c446-128">运行文件 RemoveSendPort.vbs 使用 cscript 程序中，将以下命令行自变量传递：</span><span class="sxs-lookup"><span data-stu-id="8c446-128">Run the file RemoveSendPort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="8c446-129">**\<** ***SendPortName* \>。**</span><span class="sxs-lookup"><span data-stu-id="8c446-129">**\<** ***SendPortName* \>.**</span></span> <span data-ttu-id="8c446-130">要删除的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="8c446-130">The name of the send port(s) to remove.</span></span> <span data-ttu-id="8c446-131">如果发送端口名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="8c446-131">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="8c446-132">例如：</span><span class="sxs-lookup"><span data-stu-id="8c446-132">For example:</span></span>  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="8c446-133">注释</span><span class="sxs-lookup"><span data-stu-id="8c446-133">Comments</span></span>  
 <span data-ttu-id="8c446-134">你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="8c446-134">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="8c446-135">脚本文件 RemoveSendPort.vbs 包含详细的注释，使用更多有关它执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="8c446-135">The script file RemoveSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="8c446-136">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="8c446-136">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c446-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c446-137">See Also</span></span>  
 [<span data-ttu-id="8c446-138">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="8c446-138">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)