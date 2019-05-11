---
title: XSLT 转换组件 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7695bfd51eced669ab4bc71cd2823ec694d4284d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279107"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a><span data-ttu-id="ef1a8-102">XSLT 转换组件 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ef1a8-102">XSLT Transform Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="ef1a8-103">XSLT 转换组件示例演示如何编写自定义管道组件以转换 XML 消息使用 XSLT。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-103">The XSLT Transform Component sample demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ef1a8-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="ef1a8-104">What This Sample Does</span></span>  
 <span data-ttu-id="ef1a8-105">该示例来实现转换通过执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ef1a8-105">The sample accomplishes the transformation with the following steps:</span></span>  
  
1.  <span data-ttu-id="ef1a8-106">从文件夹检索 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="ef1a8-107">管道将 XML 文档转换为使用 Transform.xsl 一封电子邮件的 HTML 正文中。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-107">The pipeline transforms the XML document into the HTML body of an e-mail message using Transform.xsl.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ef1a8-108">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="ef1a8-108">Where to Find This Sample</span></span>  
 <span data-ttu-id="ef1a8-109">*\<Samples Path\>* \Pipelines\XslTransformComponent\\</span><span class="sxs-lookup"><span data-stu-id="ef1a8-109">*\<Samples Path\>* \Pipelines\XslTransformComponent\\</span></span>  
  
 <span data-ttu-id="ef1a8-110">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="ef1a8-110">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ef1a8-111">文件</span><span class="sxs-lookup"><span data-stu-id="ef1a8-111">File(s)</span></span>|<span data-ttu-id="ef1a8-112">Description</span><span class="sxs-lookup"><span data-stu-id="ef1a8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef1a8-113">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="ef1a8-113">AssemblyInfo.cs</span></span>|<span data-ttu-id="ef1a8-114">C#程序集文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-114">C# assembly file.</span></span>|  
|<span data-ttu-id="ef1a8-115">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ef1a8-115">Cleanup.bat</span></span>|<span data-ttu-id="ef1a8-116">示例清理文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-116">Sample cleanup file.</span></span>|  
|<span data-ttu-id="ef1a8-117">Confirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="ef1a8-117">Confirmation.xsd</span></span>|<span data-ttu-id="ef1a8-118">示例架构文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-118">Sample schema file.</span></span>|  
|<span data-ttu-id="ef1a8-119">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="ef1a8-119">DocInstance.xml</span></span>|<span data-ttu-id="ef1a8-120">要转换的示例.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-120">Sample .xml file to transform.</span></span>|  
|<span data-ttu-id="ef1a8-121">SendHtmlMessage.btproj</span><span class="sxs-lookup"><span data-stu-id="ef1a8-121">SendHtmlMessage.btproj</span></span>|<span data-ttu-id="ef1a8-122">BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-122">BizTalk project.</span></span>|  
|<span data-ttu-id="ef1a8-123">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ef1a8-123">Setup.bat</span></span>|<span data-ttu-id="ef1a8-124">配置批处理文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-124">Configuration batch file.</span></span>|  
|<span data-ttu-id="ef1a8-125">Xml2HtmlSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="ef1a8-125">Xml2HtmlSendPipeline.btp</span></span>|<span data-ttu-id="ef1a8-126">BizTalk Server 管道文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-126">BizTalk Server pipeline file.</span></span>|  
|<span data-ttu-id="ef1a8-127">XslTransform.csproj</span><span class="sxs-lookup"><span data-stu-id="ef1a8-127">XslTransform.csproj</span></span>|<span data-ttu-id="ef1a8-128">C#项目。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-128">C# project.</span></span>|  
|<span data-ttu-id="ef1a8-129">XslTransformComponent.sln</span><span class="sxs-lookup"><span data-stu-id="ef1a8-129">XslTransformComponent.sln</span></span>|<span data-ttu-id="ef1a8-130">示例解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-130">Sample solution file.</span></span>|  
|<span data-ttu-id="ef1a8-131">XslTransformComponentBinding.XML</span><span class="sxs-lookup"><span data-stu-id="ef1a8-131">XslTransformComponentBinding.XML</span></span>|<span data-ttu-id="ef1a8-132">XML 绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-132">XML binding file.</span></span>|  
|<span data-ttu-id="ef1a8-133">XslTransformer.cs</span><span class="sxs-lookup"><span data-stu-id="ef1a8-133">XslTransformer.cs</span></span>|<span data-ttu-id="ef1a8-134">C#源代码。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-134">C# source code.</span></span>|  
|<span data-ttu-id="ef1a8-135">Transform.xsl</span><span class="sxs-lookup"><span data-stu-id="ef1a8-135">Transform.xsl</span></span>|<span data-ttu-id="ef1a8-136">用于转换 DocInstance.xml 的 XSLT 文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-136">XSLT file used to transform DocInstance.xml.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="ef1a8-137">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="ef1a8-137">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="ef1a8-138">使用以下过程生成并初始化 XSLT 转换组件示例。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-138">Use the following procedure to build and initialize the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="ef1a8-139">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="ef1a8-139">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="ef1a8-140">在命令窗口中，将目录更改 (**cd)** 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="ef1a8-140">In a command window, change directory (**cd)** to the following folder:</span></span>  
  
     <span data-ttu-id="ef1a8-141">*\<Samples Path\>* \Pipelines\XslTransformComponent</span><span class="sxs-lookup"><span data-stu-id="ef1a8-141">*\<Samples Path\>* \Pipelines\XslTransformComponent</span></span>  
  
2.  <span data-ttu-id="ef1a8-142">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ef1a8-142">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="ef1a8-143">创建输入 (\In) 和本示例中使用的输出 (\Out) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-143">Creates the input (\In) and output (\Out) folders used in the sample.</span></span>  
  
    -   <span data-ttu-id="ef1a8-144">生成新的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-144">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="ef1a8-145">生成并部署 XSLT 转换组件管道。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-145">Builds and deploys the XSLT Transform Component pipeline.</span></span>  
  
    -   <span data-ttu-id="ef1a8-146">将复制到生成的管道组件\<安装路径\>\Pipeline Components 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-146">Copies the built pipeline component to the \<Installation Path\>\Pipeline Components folder.</span></span>  
  
    -   <span data-ttu-id="ef1a8-147">创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-147">Creates the send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef1a8-148">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-148">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef1a8-149">若要撤消 Setup.bat 所做的更改，必须先停止并重新启动主机实例从 BizTalk Server 管理 MMC 控制台。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-149">To undo changes made by Setup.bat, you must first stop and restart the host instance from the BizTalk Server Administration MMC console.</span></span> <span data-ttu-id="ef1a8-150">接下来，运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-150">Next, run Cleanup.bat.</span></span> <span data-ttu-id="ef1a8-151">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="ef1a8-152">运行本示例</span><span class="sxs-lookup"><span data-stu-id="ef1a8-152">Running This Sample</span></span>  
 <span data-ttu-id="ef1a8-153">使用以下过程运行 XSLT 转换组件示例。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-153">Use the following procedure to run the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ef1a8-154">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="ef1a8-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="ef1a8-155">将 DocInstance.xml 复制到 \In 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-155">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="ef1a8-156">检查 （输出文件名为 guid.htm） \Out 文件夹中的结果。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-156">Examine the results in the \Out folder (the output filename is guid.htm).</span></span>  
  
## <a name="configuring-this-sample-using-smtp"></a><span data-ttu-id="ef1a8-157">配置此示例使用 SMTP</span><span class="sxs-lookup"><span data-stu-id="ef1a8-157">Configuring This Sample Using SMTP</span></span>  
 <span data-ttu-id="ef1a8-158">使用以下过程配置以使用 SMTP 服务器的 XSLT 转换组件示例。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-158">Use the following procedure to configure the XSLT Transform Component sample to work with an SMTP server.</span></span>  
  
#### <a name="to-configure-this-sample-using-smtp"></a><span data-ttu-id="ef1a8-159">若要配置此示例使用 SMTP</span><span class="sxs-lookup"><span data-stu-id="ef1a8-159">To configure this sample using SMTP</span></span>  
  
1.  <span data-ttu-id="ef1a8-160">重新配置要使用 SMTP 传输类型的 XSLT 转换组件发送端口。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-160">Reconfigure the XSLT Transform Component send port to use an SMTP transport type.</span></span>  
  
2.  <span data-ttu-id="ef1a8-161">配置 SMTP 设置，通过更改地址 (URI) 参数以匹配您的 SMTP 配置。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-161">Configure the SMTP setting by changing the address (URI) parameters to match your SMTP configuration.</span></span>  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="ef1a8-162">运行此示例使用输出到 SMTP 端口</span><span class="sxs-lookup"><span data-stu-id="ef1a8-162">Running This Sample with Output to an SMTP Port</span></span>  
 <span data-ttu-id="ef1a8-163">使用以下过程使用输出到 SMTP 端口运行 XSLT 转换组件示例。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-163">Use the following procedure to run the XSLT Transform Component sample with output to an SMTP port.</span></span>  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="ef1a8-164">若要输出到 SMTP 端口运行此示例</span><span class="sxs-lookup"><span data-stu-id="ef1a8-164">To run this sample with output to an SMTP port</span></span>  
  
1.  <span data-ttu-id="ef1a8-165">将 DocInstance.xml 复制到 \In 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-165">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="ef1a8-166">检查到配置了 SMTP 的收件人的邮件客户端中的结果将发送到。</span><span class="sxs-lookup"><span data-stu-id="ef1a8-166">Examine the results in the mail client for the recipient that SMTP is configured to send to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1a8-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef1a8-167">See Also</span></span>  
 [<span data-ttu-id="ef1a8-168">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="ef1a8-168">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)