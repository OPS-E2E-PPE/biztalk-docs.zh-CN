---
title: 删除发送端口 （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 4edb148d1627d596f98684b09d18da111b4e435c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397934"
---
# <a name="remove-send-port-biztalk-server-sample"></a><span data-ttu-id="b03b8-102">删除发送端口 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="b03b8-102">Remove Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="b03b8-103">删除发送端口示例演示如何取消登记和删除一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="b03b8-103">The Remove Send Port sample demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b03b8-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="b03b8-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="b03b8-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="b03b8-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b03b8-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="b03b8-106">What This Sample Does</span></span>  
 <span data-ttu-id="b03b8-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="b03b8-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="b03b8-108">给定的发送端口名称，查询匹配的发送端口的列表。</span><span class="sxs-lookup"><span data-stu-id="b03b8-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b03b8-109">通常情况下，将仅有一个与给定名称匹配的发送端口。</span><span class="sxs-lookup"><span data-stu-id="b03b8-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="b03b8-110">取消登记这些发送端口。</span><span class="sxs-lookup"><span data-stu-id="b03b8-110">Unenlist those send ports.</span></span>  
  
-   <span data-ttu-id="b03b8-111">删除这些发送端口。</span><span class="sxs-lookup"><span data-stu-id="b03b8-111">Delete those send ports.</span></span>  
  
-   <span data-ttu-id="b03b8-112">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="b03b8-112">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b03b8-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="b03b8-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="b03b8-114">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="b03b8-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="b03b8-115">\<*示例路径*\>\Admin\WMI\Remove 发送 Port\\</span><span class="sxs-lookup"><span data-stu-id="b03b8-115">\<*Samples Path*\>\Admin\WMI\Remove Send Port\\</span></span>  
  
 <span data-ttu-id="b03b8-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="b03b8-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b03b8-117">文件</span><span class="sxs-lookup"><span data-stu-id="b03b8-117">File(s)</span></span>|<span data-ttu-id="b03b8-118">Description</span><span class="sxs-lookup"><span data-stu-id="b03b8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b03b8-119">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="b03b8-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="b03b8-120">RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="b03b8-120">RemoveSendPort.vbs</span></span>|<span data-ttu-id="b03b8-121">VBScript 文件，采用一个参数，指定一个或多个发送端口将取消登记和删除。</span><span class="sxs-lookup"><span data-stu-id="b03b8-121">VBScript file that takes a parameter that specifies one or more send ports to unenlist and remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="b03b8-122">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="b03b8-122">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="b03b8-123">删除发送端口示例由一个 VBScript 文件，不需要生成或初始化组成。</span><span class="sxs-lookup"><span data-stu-id="b03b8-123">The Remove Send Port sample consists of a single VBScript file that you not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="b03b8-124">运行本示例</span><span class="sxs-lookup"><span data-stu-id="b03b8-124">Running This Sample</span></span>  
  
#### <a name="to-run-the-remove-send-port-sample"></a><span data-ttu-id="b03b8-125">若要运行删除发送端口示例</span><span class="sxs-lookup"><span data-stu-id="b03b8-125">To run the Remove Send Port sample</span></span>  
  
1.  <span data-ttu-id="b03b8-126">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b03b8-126">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="b03b8-127">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="b03b8-127">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="b03b8-128">运行文件 RemoveSendPort.vbs 使用 cscript 程序，并传递以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="b03b8-128">Run the file RemoveSendPort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="b03b8-129">**\<** ***SendPortName* \>。**</span><span class="sxs-lookup"><span data-stu-id="b03b8-129">**\<** ***SendPortName* \>.**</span></span> <span data-ttu-id="b03b8-130">若要删除的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="b03b8-130">The name of the send port(s) to remove.</span></span> <span data-ttu-id="b03b8-131">如果发送端口名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="b03b8-131">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="b03b8-132">例如：</span><span class="sxs-lookup"><span data-stu-id="b03b8-132">For example:</span></span>  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="b03b8-133">注释</span><span class="sxs-lookup"><span data-stu-id="b03b8-133">Comments</span></span>  
 <span data-ttu-id="b03b8-134">可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="b03b8-134">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="b03b8-135">脚本文件 RemoveSendPort.vbs 包含详细的注释了进一步说明，它执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b03b8-135">The script file RemoveSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="b03b8-136">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="b03b8-136">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03b8-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b03b8-137">See Also</span></span>  
 [<span data-ttu-id="b03b8-138">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="b03b8-138">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)