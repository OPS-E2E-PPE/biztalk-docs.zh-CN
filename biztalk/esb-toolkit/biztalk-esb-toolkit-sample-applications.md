---
title: "BizTalk ESB 工具包示例应用程序 |Microsoft 文档"
description: "安装 ESB 工具包示例应用程序，并获取有关如何在 BizTalk Server 中使用它们快速链接"
caps.latest.revision: "5"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="07b25-103">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="07b25-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="07b25-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个示例应用程序可以安装和运行，以查看如何 ESB 工作原理以及如何使用某些 ESB 管道组件。</span><span class="sxs-lookup"><span data-stu-id="07b25-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="07b25-105">您可以调整和修改的代码和在这些示例用于自己的应用程序的技术。</span><span class="sxs-lookup"><span data-stu-id="07b25-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="07b25-106">安装示例应用程序</span><span class="sxs-lookup"><span data-stu-id="07b25-106">Install the sample applications</span></span>  
  
1.  <span data-ttu-id="07b25-107">创建一个名为 c： 驱动器的根目录中的项目文件夹并创建名 Microsoft.Practices.ESB 为在此文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="07b25-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07b25-108">在当前版本中，支持的安装为要驻留在 C:\Projects\Microsoft.Practices.ESB 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="07b25-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="07b25-109">这些示例会随附的 BizTalk 绑定文件取决于此路径。</span><span class="sxs-lookup"><span data-stu-id="07b25-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2.  <span data-ttu-id="07b25-110">当你安装[ESB 工具包](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)，它包括在你指定的安装位置中调用 ESBSource.zip 的.zip 文件 (默认情况下，C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="07b25-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]).</span></span> <span data-ttu-id="07b25-111">将 ESBSource.zip 文件解压缩到 C:\Projects\Microsoft.Practices.ESB 文件夹。</span><span class="sxs-lookup"><span data-stu-id="07b25-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="07b25-112">这将创建名为的文件夹**密钥**和**源**包含示例密钥和与源代码示例。</span><span class="sxs-lookup"><span data-stu-id="07b25-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="07b25-113">源文件夹包含示例应用程序的源代码，密钥文件夹包含用于对示例应用程序中的程序集进行签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="07b25-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3.  <span data-ttu-id="07b25-114">运行示例之前，删除 C:\Projects\Microsoft.Practices.ESB\ 文件夹的只读特性，以便正确安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="07b25-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4.  <span data-ttu-id="07b25-115">如果你不使用 PowerShell 脚本之前，必须以管理员身份打开 PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="07b25-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="07b25-116">有关 PowerShell 的详细信息，请参阅[Windows PowerShell 博客](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) 和[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="07b25-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5.  <span data-ttu-id="07b25-117">打开管理员命令提示符并运行以下命令以确保注册 WCF 脚本映射：</span><span class="sxs-lookup"><span data-stu-id="07b25-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="07b25-118">你需要以获取对示例代码的访问权限打开 ESBSource.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="07b25-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="07b25-119">示例应用程序</span><span class="sxs-lookup"><span data-stu-id="07b25-119">Sample applications</span></span>  
 <span data-ttu-id="07b25-120">以下主题描述了示例应用程序，并包括其他安装说明 （如果适用）：</span><span class="sxs-lookup"><span data-stu-id="07b25-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="07b25-121">安装异常管理示例</span><span class="sxs-lookup"><span data-stu-id="07b25-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="07b25-122">运行修复并重新提交自定义异常处理程序示例</span><span class="sxs-lookup"><span data-stu-id="07b25-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="07b25-123">运行保留自定义异常处理程序的示例消息</span><span class="sxs-lookup"><span data-stu-id="07b25-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="07b25-124">运行 BizTalk 失败消息路由 ESB 处理示例</span><span class="sxs-lookup"><span data-stu-id="07b25-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="07b25-125">安装和运行路线上负载增加示例</span><span class="sxs-lookup"><span data-stu-id="07b25-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="07b25-126">安装和运行 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="07b25-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="07b25-127">安装和运行 Namespace 组件示例</span><span class="sxs-lookup"><span data-stu-id="07b25-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="07b25-128">安装和运行转换服务示例</span><span class="sxs-lookup"><span data-stu-id="07b25-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="07b25-129">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="07b25-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="07b25-130">安装和运行 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="07b25-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="07b25-131">安装和运行解析程序服务示例</span><span class="sxs-lookup"><span data-stu-id="07b25-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="07b25-132">安装和运行散播-聚集示例</span><span class="sxs-lookup"><span data-stu-id="07b25-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="07b25-133">安装和运行消息扩充示例</span><span class="sxs-lookup"><span data-stu-id="07b25-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="07b25-134">安装和运行多个 Web 服务示例</span><span class="sxs-lookup"><span data-stu-id="07b25-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="07b25-135">安装和运行设计器扩展性示例</span><span class="sxs-lookup"><span data-stu-id="07b25-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="07b25-136">运行的异常处理服务示例</span><span class="sxs-lookup"><span data-stu-id="07b25-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)