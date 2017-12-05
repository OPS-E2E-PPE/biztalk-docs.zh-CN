---
title: "启用接收位置 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2df85f051285e999660dc3765855d22c708939
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a><span data-ttu-id="3eb88-102">启用接收位置 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="3eb88-102">Enable Receive Location (BizTalk Server Sample)</span></span>
<span data-ttu-id="3eb88-103">启用接收位置示例演示如何启用接收位置和 （可选） 设置对该接收位置的入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="3eb88-103">The Enable Receive Location sample demonstrates how to enable a receive location and optionally set the Inbound Transport URL for that receive location.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3eb88-104">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="3eb88-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="3eb88-105">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="3eb88-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3eb88-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="3eb88-106">What This Sample Does</span></span>  
 <span data-ttu-id="3eb88-107">Microsoft Visual Basic Scripting Edition (VBScript) 脚本中的脚本文件的构成此示例演示如何执行以下操作使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="3eb88-107">The Microsoft Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="3eb88-108">给定接收端口名称和接收位置，查询匹配的接收位置的列表。</span><span class="sxs-lookup"><span data-stu-id="3eb88-108">Given a receive port name and receive location, query for a list of matching receive locations.</span></span>  
  
-   <span data-ttu-id="3eb88-109">设置为接收位置 （相对于的安装路径） 的入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="3eb88-109">Set the Inbound Transport URL for a receive location (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="3eb88-110">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="3eb88-110">Enable a receive location.</span></span>  
  
-   <span data-ttu-id="3eb88-111">处理所有错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="3eb88-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3eb88-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="3eb88-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="3eb88-113">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="3eb88-113">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="3eb88-114">\<*示例路径*\>\Admin\WMI\Enable 接收位置 \\</span><span class="sxs-lookup"><span data-stu-id="3eb88-114">\<*Samples Path*\>\Admin\WMI\Enable Receive Location\\</span></span>  
  
 <span data-ttu-id="3eb88-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="3eb88-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3eb88-116">文件</span><span class="sxs-lookup"><span data-stu-id="3eb88-116">File(s)</span></span>|<span data-ttu-id="3eb88-117">Description</span><span class="sxs-lookup"><span data-stu-id="3eb88-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3eb88-118">\VBScript 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="3eb88-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="3eb88-119">EnableRecLoc.vbs</span><span class="sxs-lookup"><span data-stu-id="3eb88-119">EnableRecLoc.vbs</span></span>|<span data-ttu-id="3eb88-120">采用参数的 VBScript 文件指定接收位置启用，并 （可选） 与该接收位置关联的入站传输 url 的新值。</span><span class="sxs-lookup"><span data-stu-id="3eb88-120">VBScript file that takes parameters that specify a receive location to be enabled, and optionally, a new value for the Inbound Transport URL associated with that receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="3eb88-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="3eb88-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="3eb88-122">启用接收位置示例包含一个 VBScript 文件不需要生成或初始化。</span><span class="sxs-lookup"><span data-stu-id="3eb88-122">The Enable Receive Location sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="3eb88-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="3eb88-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="3eb88-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="3eb88-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="3eb88-125">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="3eb88-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="3eb88-126">\<*示例路径*\>\Admin\WMI\Enable 接收 Location\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="3eb88-126">\<*Samples Path*\>\Admin\WMI\Enable Receive Location\VBScript\\</span></span>  
  
2.  <span data-ttu-id="3eb88-127">运行该文件使用 cscript 程序传递以下命令行自变量，而第三个是可选的 EnableRecLoc.vbs:</span><span class="sxs-lookup"><span data-stu-id="3eb88-127">Run the file EnableRecLoc.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   <span data-ttu-id="3eb88-128">**\<** ***ReceivePortName* \>。**</span><span class="sxs-lookup"><span data-stu-id="3eb88-128">**\<** ***ReceivePortName* \>.**</span></span> <span data-ttu-id="3eb88-129">包含要启用的接收位置的接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="3eb88-129">The name of the receive port that contains the receive location to be enabled.</span></span> <span data-ttu-id="3eb88-130">如果接收端口名称包含空格，请将名称括在引号中。</span><span class="sxs-lookup"><span data-stu-id="3eb88-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="3eb88-131">**\<** ***ReceiveLocationName* \>。**</span><span class="sxs-lookup"><span data-stu-id="3eb88-131">**\<** ***ReceiveLocationName* \>.**</span></span> <span data-ttu-id="3eb88-132">位于要启用的指定接收端口中的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="3eb88-132">The name of the receive location within the specified receive port to be enabled.</span></span> <span data-ttu-id="3eb88-133">如果接收位置名称包含空格，则将该名称置于引号中。</span><span class="sxs-lookup"><span data-stu-id="3eb88-133">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="3eb88-134">**\<** ***InboundTransportURI* \>。**</span><span class="sxs-lookup"><span data-stu-id="3eb88-134">**\<** ***InboundTransportURI* \>.**</span></span> <span data-ttu-id="3eb88-135">接收适配器 URI，相对于产品安装位置的主传输地址，通过指定该参数，您可以更改此地址。</span><span class="sxs-lookup"><span data-stu-id="3eb88-135">A receive adapter URI, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="3eb88-136">如果入站的适配器 URI 包含空格，括起来的 URI。</span><span class="sxs-lookup"><span data-stu-id="3eb88-136">If the inbound adapter URI contains spaces, enclose the URI in quotes.</span></span>  
  
         <span data-ttu-id="3eb88-137">例如：</span><span class="sxs-lookup"><span data-stu-id="3eb88-137">For example:</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         <span data-ttu-id="3eb88-138">-或者-</span><span class="sxs-lookup"><span data-stu-id="3eb88-138">-OR-</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="3eb88-139">注释</span><span class="sxs-lookup"><span data-stu-id="3eb88-139">Comments</span></span>  
 <span data-ttu-id="3eb88-140">你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="3eb88-140">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="3eb88-141">脚本文件 EnableRecLoc.vbs 包含详细的注释，使用更多有关它执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="3eb88-141">The script file EnableRecLoc.vbs contains detailed comments with further explanation about the operations that it performs.</span></span>  
  
 <span data-ttu-id="3eb88-142">有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="3eb88-142">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb88-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3eb88-143">See Also</span></span>  
 [<span data-ttu-id="3eb88-144">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="3eb88-144">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)