---
title: BizTalk ESB 工具包示例应用程序 |Microsoft Docs
description: 安装 ESB 工具包示例应用程序，并获取有关如何在 BizTalk Server 中使用这些快速链接
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: bfbae558e0f140b561010debd063f171bd5ee04f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302257"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="6d505-103">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="6d505-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="6d505-104">Microsoft BizTalk ESB 工具包包括几个示例应用程序可以安装并运行以查看如何 ESB 工作原理以及它如何使用一些 ESB 管道组件。</span><span class="sxs-lookup"><span data-stu-id="6d505-104">The Microsoft BizTalk ESB Toolkit includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="6d505-105">您可以调整和修改的代码和示例中使用的自己的应用程序的技术。</span><span class="sxs-lookup"><span data-stu-id="6d505-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="6d505-106">安装示例应用程序</span><span class="sxs-lookup"><span data-stu-id="6d505-106">Install the sample applications</span></span>  
  
1. <span data-ttu-id="6d505-107">创建一个名为 c： 驱动器的根目录中的项目文件夹并创建名 Microsoft.Practices.ESB 为在此文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d505-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d505-108">在当前版本中，支持的安装文件位于文件夹 C:\Projects\Microsoft.Practices.ESB 是。</span><span class="sxs-lookup"><span data-stu-id="6d505-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="6d505-109">附带示例的 BizTalk 绑定文件取决于此路径。</span><span class="sxs-lookup"><span data-stu-id="6d505-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2. <span data-ttu-id="6d505-110">当你安装[ESB 工具包](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)，它包括 ESBSource.zip 中指定的安装位置 （默认情况下调用，C:\Program Files\Microsoft BizTalk ESB 工具包） 的.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="6d505-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\Microsoft BizTalk ESB Toolkit).</span></span> <span data-ttu-id="6d505-111">将 ESBSource.zip 文件解压缩到 C:\Projects\Microsoft.Practices.ESB 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d505-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="6d505-112">这将创建名为的文件夹**密钥**并**源**包含示例密钥和包含源代码示例。</span><span class="sxs-lookup"><span data-stu-id="6d505-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="6d505-113">源文件夹包含示例应用程序的源代码和密钥文件夹包含用于签名的示例应用程序中的程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="6d505-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3. <span data-ttu-id="6d505-114">运行示例之前，请删除 C:\Projects\Microsoft.Practices.ESB\ 文件夹的只读属性，以便正确地安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6d505-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4. <span data-ttu-id="6d505-115">如果没有使用 PowerShell 脚本之前，必须以管理员身份打开 PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6d505-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
   ```  
   set-executionpolicy unrestricted  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6d505-116">有关 PowerShell 的详细信息，请参阅[Windows PowerShell 博客](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) 和[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([ http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="6d505-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5. <span data-ttu-id="6d505-117">打开命令提示符下以管理员身份并运行以下命令以确保注册 WCF 脚本映射：</span><span class="sxs-lookup"><span data-stu-id="6d505-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
   ```  
   C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
   ```  
  
> [!NOTE]
>  <span data-ttu-id="6d505-118">您需要打开 ESBSource.zip 文件才能获取对示例代码的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d505-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="6d505-119">示例应用程序</span><span class="sxs-lookup"><span data-stu-id="6d505-119">Sample applications</span></span>  
 <span data-ttu-id="6d505-120">以下主题介绍示例应用程序，以及在适用的情况包括其他安装说明：</span><span class="sxs-lookup"><span data-stu-id="6d505-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="6d505-121">安装异常管理示例</span><span class="sxs-lookup"><span data-stu-id="6d505-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="6d505-122">运行修复和重新提交自定义异常处理程序示例</span><span class="sxs-lookup"><span data-stu-id="6d505-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="6d505-123">运行消息保留自定义异常处理程序示例</span><span class="sxs-lookup"><span data-stu-id="6d505-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="6d505-124">运行 BizTalk 故障消息路由 ESB 处理示例</span><span class="sxs-lookup"><span data-stu-id="6d505-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="6d505-125">安装和运行路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="6d505-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="6d505-126">安装和运行 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="6d505-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="6d505-127">安装和运行命名空间组件示例</span><span class="sxs-lookup"><span data-stu-id="6d505-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="6d505-128">安装和运行转换服务示例</span><span class="sxs-lookup"><span data-stu-id="6d505-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="6d505-129">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="6d505-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="6d505-130">安装和运行 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="6d505-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="6d505-131">安装和运行解析程序服务示例</span><span class="sxs-lookup"><span data-stu-id="6d505-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="6d505-132">安装和运行“分散-集中”示例</span><span class="sxs-lookup"><span data-stu-id="6d505-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="6d505-133">安装和运行消息充实示例</span><span class="sxs-lookup"><span data-stu-id="6d505-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="6d505-134">安装和运行多个 Web 服务示例</span><span class="sxs-lookup"><span data-stu-id="6d505-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="6d505-135">安装和运行设计器扩展性示例</span><span class="sxs-lookup"><span data-stu-id="6d505-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="6d505-136">运行异常处理服务示例</span><span class="sxs-lookup"><span data-stu-id="6d505-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)