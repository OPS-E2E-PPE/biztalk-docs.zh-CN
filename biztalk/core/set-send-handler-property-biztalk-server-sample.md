---
title: 设置发送处理程序属性 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d1abddd497ad1f6d20c18bf7e5ff580b1ddc1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393272"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a><span data-ttu-id="4bd6e-102">设置发送处理程序属性 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4bd6e-102">Set Send Handler Property (BizTalk Server Sample)</span></span>
<span data-ttu-id="4bd6e-103">设置发送处理程序属性示例演示如何设置简单邮件传输协议 (SMTP) 发送处理程序的 XML 配置信息。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-103">The Set Send Handler Property sample demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4bd6e-104">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="4bd6e-105">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4bd6e-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="4bd6e-106">What This Sample Does</span></span>  
 <span data-ttu-id="4bd6e-107">构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="4bd6e-108">给定的发送处理程序名称，查询匹配的发送处理程序的列表。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-108">Given a send handler name, query for a list of matching send handlers.</span></span>  
  
-   <span data-ttu-id="4bd6e-109">设置 SMTP 发送处理程序的 XML 配置信息。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-109">Set the XML configuration information for an SMTP send handler.</span></span>  
  
-   <span data-ttu-id="4bd6e-110">处理任何错误，以便向用户返回有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-110">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4bd6e-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="4bd6e-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="4bd6e-112">示例文件位于以下 SDK 位置：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-112">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="4bd6e-113">\<*示例路径*\>\Admin\WMI\Set Send Handler Property\\</span><span class="sxs-lookup"><span data-stu-id="4bd6e-113">\<*Samples Path*\>\Admin\WMI\Set Send Handler Property\\</span></span>  
  
 <span data-ttu-id="4bd6e-114">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="4bd6e-115">文件</span><span class="sxs-lookup"><span data-stu-id="4bd6e-115">File(s)</span></span>|<span data-ttu-id="4bd6e-116">Description</span><span class="sxs-lookup"><span data-stu-id="4bd6e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4bd6e-117">\VBScript 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-117">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="4bd6e-118">ConfigureSMTP.vbs</span><span class="sxs-lookup"><span data-stu-id="4bd6e-118">ConfigureSMTP.vbs</span></span>|<span data-ttu-id="4bd6e-119">VBScript 文件，采用参数指定了 SMTP 发送处理程序和 From 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-119">VBScript file that takes parameters that specify an SMTP send handler and a From e-mail address.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="4bd6e-120">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="4bd6e-120">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="4bd6e-121">设置发送处理程序属性示例包含一个 VBScript 文件，不需生成或初始化文件。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-121">The Set Send Handler Property sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="4bd6e-122">运行本示例</span><span class="sxs-lookup"><span data-stu-id="4bd6e-122">Running This Sample</span></span>  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a><span data-ttu-id="4bd6e-123">若要运行设置发送处理程序属性示例</span><span class="sxs-lookup"><span data-stu-id="4bd6e-123">To run the Set Send Handler Property sample</span></span>  
  
1.  <span data-ttu-id="4bd6e-124">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-124">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="4bd6e-125">\<*示例路径*\>\Admin\WMI\Set Send Handler Property\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="4bd6e-125">\<*Samples Path*\>\Admin\WMI\Set Send Handler Property\VBScript\\</span></span>  
  
2.  <span data-ttu-id="4bd6e-126">运行文件 ConfigureSMTP.vbs 使用 cscript 程序，并传递以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-126">Run the file ConfigureSMTP.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
    -   <span data-ttu-id="4bd6e-127">**\<** ***SMTPServerName* \>.**</span><span class="sxs-lookup"><span data-stu-id="4bd6e-127">**\<** ***SMTPServerName* \>.**</span></span> <span data-ttu-id="4bd6e-128">将用于发送邮件的 SMTP 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-128">The name of the SMTP server that will be used to send mail.</span></span>  
  
    -   <span data-ttu-id="4bd6e-129">**\<** ***FromEmailAddress* \>。**</span><span class="sxs-lookup"><span data-stu-id="4bd6e-129">**\<** ***FromEmailAddress* \>.**</span></span> <span data-ttu-id="4bd6e-130">电子邮件地址将用作发件人地址。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-130">An e-mail address that will be used as the From address.</span></span>  
  
         <span data-ttu-id="4bd6e-131">例如：</span><span class="sxs-lookup"><span data-stu-id="4bd6e-131">For example:</span></span>  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a><span data-ttu-id="4bd6e-132">注释</span><span class="sxs-lookup"><span data-stu-id="4bd6e-132">Comments</span></span>  
 <span data-ttu-id="4bd6e-133">可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="4bd6e-134">ConfigureSMTP.vbs 脚本文件包含详细的注释了进一步说明，它执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-134">The script file ConfigureSMTP.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="4bd6e-135">有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。</span><span class="sxs-lookup"><span data-stu-id="4bd6e-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd6e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bd6e-136">See Also</span></span>  
 [<span data-ttu-id="4bd6e-137">Admin-WMI（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="4bd6e-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)