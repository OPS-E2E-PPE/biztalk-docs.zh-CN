---
title: 删除接收端口 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39d8264e00b239eaffbb24fb53e3a0f99998720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397940"
---
# <a name="remove-receive-port-biztalk-server-sample"></a><span data-ttu-id="c7313-102">删除接收端口 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c7313-102">Remove Receive Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="c7313-103">删除接收端口示例演示如何删除一个或多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="c7313-103">The Remove Receive Port sample demonstrates how to remove one or more receive ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c7313-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="c7313-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="c7313-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="c7313-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="c7313-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="c7313-106">What This Sample Does</span></span>  
 <span data-ttu-id="c7313-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="c7313-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="c7313-108">指定接收端口名称，查询匹配的接收端口的列表。</span><span class="sxs-lookup"><span data-stu-id="c7313-108">Given a receive port name, query for a list of matching receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7313-109">通常情况下，仅有一个接收与给定名称匹配的端口。</span><span class="sxs-lookup"><span data-stu-id="c7313-109">Generally, there will only be one receive port that matches a given name.</span></span>  
  
-   <span data-ttu-id="c7313-110">删除这些接收端口。</span><span class="sxs-lookup"><span data-stu-id="c7313-110">Remove those receive ports.</span></span>  
  
-   <span data-ttu-id="c7313-111">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="c7313-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="c7313-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="c7313-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="c7313-113">这些示例位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="c7313-113">The samples are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="c7313-114">\<*示例路径*\>\Admin\WMI\Remove 接收 Port\\</span><span class="sxs-lookup"><span data-stu-id="c7313-114">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\\</span></span>  
  
 <span data-ttu-id="c7313-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="c7313-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="c7313-116">文件</span><span class="sxs-lookup"><span data-stu-id="c7313-116">File(s)</span></span>|<span data-ttu-id="c7313-117">Description</span><span class="sxs-lookup"><span data-stu-id="c7313-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7313-118">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="c7313-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="c7313-119">RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="c7313-119">RemoveReceivePort.vbs</span></span>|<span data-ttu-id="c7313-120">VBScript 文件，采用一个参数，指定一个或多个接收端口，以删除。</span><span class="sxs-lookup"><span data-stu-id="c7313-120">VBScript file that takes a parameter that specifies one or more receive ports to remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="c7313-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="c7313-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="c7313-122">删除接收端口示例由一个不需要生成或初始化的 VBScript 文件组成。</span><span class="sxs-lookup"><span data-stu-id="c7313-122">The Remove Receive Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="c7313-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="c7313-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="c7313-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="c7313-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="c7313-125">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="c7313-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="c7313-126">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="c7313-126">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="c7313-127">运行文件 RemoveReceivePort.vbs 使用 cscript 程序，并传递以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="c7313-127">Run the file RemoveReceivePort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="c7313-128">**\<** ***ReceivePortName* \>** 。</span><span class="sxs-lookup"><span data-stu-id="c7313-128">**\<** ***ReceivePortName* \>**.</span></span> <span data-ttu-id="c7313-129">若要删除的接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="c7313-129">The name of the receive port(s) to remove.</span></span> <span data-ttu-id="c7313-130">如果接收端口名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="c7313-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="c7313-131">例如：</span><span class="sxs-lookup"><span data-stu-id="c7313-131">For example:</span></span>  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="c7313-132">注释</span><span class="sxs-lookup"><span data-stu-id="c7313-132">Comments</span></span>  
 <span data-ttu-id="c7313-133">可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="c7313-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="c7313-134">脚本文件 RemoveReceivePort.vbs 包含详细的注释了进一步说明，它执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c7313-134">The script file RemoveReceivePort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="c7313-135">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="c7313-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7313-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7313-136">See Also</span></span>  
 [<span data-ttu-id="c7313-137">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="c7313-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)