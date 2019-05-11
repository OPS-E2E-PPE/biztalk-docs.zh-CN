---
title: 启用接收位置 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f41353b17a3e393d865c381a5f6b6b15cb676cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349719"
---
# <a name="enable-receive-location-biztalk-server-sample"></a><span data-ttu-id="e5776-102">启用接收位置 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e5776-102">Enable Receive Location (BizTalk Server Sample)</span></span>
<span data-ttu-id="e5776-103">启用接收位置示例演示如何启用接收位置和 （可选） 设置该接收位置的入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="e5776-103">The Enable Receive Location sample demonstrates how to enable a receive location and optionally set the Inbound Transport URL for that receive location.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e5776-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="e5776-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="e5776-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="e5776-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e5776-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e5776-106">What This Sample Does</span></span>  
 <span data-ttu-id="e5776-107">构成本示例的脚本文件中的 Microsoft Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="e5776-107">The Microsoft Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="e5776-108">在给定接收端口名称和接收位置，查询匹配的接收位置的列表。</span><span class="sxs-lookup"><span data-stu-id="e5776-108">Given a receive port name and receive location, query for a list of matching receive locations.</span></span>  
  
-   <span data-ttu-id="e5776-109">设置接收位置 （相对于的安装路径） 的入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="e5776-109">Set the Inbound Transport URL for a receive location (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="e5776-110">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="e5776-110">Enable a receive location.</span></span>  
  
-   <span data-ttu-id="e5776-111">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="e5776-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e5776-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e5776-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="e5776-113">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="e5776-113">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="e5776-114">\<*示例路径*\>\Admin\WMI\Enable 接收位置 \\</span><span class="sxs-lookup"><span data-stu-id="e5776-114">\<*Samples Path*\>\Admin\WMI\Enable Receive Location\\</span></span>  
  
 <span data-ttu-id="e5776-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="e5776-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e5776-116">文件</span><span class="sxs-lookup"><span data-stu-id="e5776-116">File(s)</span></span>|<span data-ttu-id="e5776-117">Description</span><span class="sxs-lookup"><span data-stu-id="e5776-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5776-118">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="e5776-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="e5776-119">EnableRecLoc.vbs</span><span class="sxs-lookup"><span data-stu-id="e5776-119">EnableRecLoc.vbs</span></span>|<span data-ttu-id="e5776-120">VBScript 文件，采用参数指定接收位置，若要启用，并 （可选） 与该接收位置相关联的入站传输 URL 的新值。</span><span class="sxs-lookup"><span data-stu-id="e5776-120">VBScript file that takes parameters that specify a receive location to be enabled, and optionally, a new value for the Inbound Transport URL associated with that receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e5776-121">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="e5776-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e5776-122">启用接收位置示例包含一个 VBScript 文件，不需生成或初始化文件。</span><span class="sxs-lookup"><span data-stu-id="e5776-122">The Enable Receive Location sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e5776-123">运行本示例</span><span class="sxs-lookup"><span data-stu-id="e5776-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e5776-124">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="e5776-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="e5776-125">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="e5776-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="e5776-126">\<*示例路径*\>\Admin\WMI\Enable 接收 Location\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="e5776-126">\<*Samples Path*\>\Admin\WMI\Enable Receive Location\VBScript\\</span></span>  
  
2.  <span data-ttu-id="e5776-127">运行文件 EnableRecLoc.vbs 使用 cscript 程序中，传递下列命令行参数，第三个是可选的：</span><span class="sxs-lookup"><span data-stu-id="e5776-127">Run the file EnableRecLoc.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   <span data-ttu-id="e5776-128">**\<** ***ReceivePortName* \>.**</span><span class="sxs-lookup"><span data-stu-id="e5776-128">**\<** ***ReceivePortName* \>.**</span></span> <span data-ttu-id="e5776-129">包含要启用的接收位置的接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="e5776-129">The name of the receive port that contains the receive location to be enabled.</span></span> <span data-ttu-id="e5776-130">如果接收端口名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="e5776-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="e5776-131">**\<** ***ReceiveLocationName* \>.**</span><span class="sxs-lookup"><span data-stu-id="e5776-131">**\<** ***ReceiveLocationName* \>.**</span></span> <span data-ttu-id="e5776-132">中指定的接收端口启用的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="e5776-132">The name of the receive location within the specified receive port to be enabled.</span></span> <span data-ttu-id="e5776-133">如果接收位置名称包含空格，将名称括起来。</span><span class="sxs-lookup"><span data-stu-id="e5776-133">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="e5776-134">**\<** ***InboundTransportURI* \>.**</span><span class="sxs-lookup"><span data-stu-id="e5776-134">**\<** ***InboundTransportURI* \>.**</span></span> <span data-ttu-id="e5776-135">接收适配器 URI，相对于的产品安装位置，你可以通过指定此参数。</span><span class="sxs-lookup"><span data-stu-id="e5776-135">A receive adapter URI, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="e5776-136">如果入站的适配器 URI 包含空格，则 URI 将置于引号中。</span><span class="sxs-lookup"><span data-stu-id="e5776-136">If the inbound adapter URI contains spaces, enclose the URI in quotes.</span></span>  
  
         <span data-ttu-id="e5776-137">例如：</span><span class="sxs-lookup"><span data-stu-id="e5776-137">For example:</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         <span data-ttu-id="e5776-138">-或-</span><span class="sxs-lookup"><span data-stu-id="e5776-138">-OR-</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="e5776-139">注释</span><span class="sxs-lookup"><span data-stu-id="e5776-139">Comments</span></span>  
 <span data-ttu-id="e5776-140">可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="e5776-140">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="e5776-141">脚本文件 EnableRecLoc.vbs 包含详细的注释了进一步说明，它执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e5776-141">The script file EnableRecLoc.vbs contains detailed comments with further explanation about the operations that it performs.</span></span>  
  
 <span data-ttu-id="e5776-142">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="e5776-142">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5776-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5776-143">See Also</span></span>  
 [<span data-ttu-id="e5776-144">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="e5776-144">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)