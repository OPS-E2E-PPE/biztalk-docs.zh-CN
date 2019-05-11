---
title: 任意 XPath 属性处理程序 （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b66ae9dd0149e8172726ff882de11dcf35ba25
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528591"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a><span data-ttu-id="a5157-102">任意 XPath 属性处理程序 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="a5157-102">Arbitrary XPath Property Handler (BizTalk Server Sample)</span></span>
<span data-ttu-id="a5157-103">任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例) 演示如何编写自定义管道组件以升级提交到的 XML 文档的特定属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5157-103">The Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) demonstrates how to write a custom pipeline component to promote specific properties on an XML document that is submitted to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a5157-104">此示例中包含的功能可用于创建自定义的常规、 组装器和拆装器组件，以计算 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="a5157-104">You can use functionality contained in the sample to create custom regular, assembler, and disassembler components to evaluate XPath expressions.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a5157-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="a5157-105">What This Sample Does</span></span>  
 <span data-ttu-id="a5157-106">该示例包括处理，DocInstance.xml 的采购订单 (PO) XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a5157-106">The sample includes a purchase order (PO) XML document to process, DocInstance.xml.</span></span> <span data-ttu-id="a5157-107">此示例使用以下步骤处理 DocInstance.xml:</span><span class="sxs-lookup"><span data-stu-id="a5157-107">The sample uses the following steps to process DocInstance.xml:</span></span>  
  
1. <span data-ttu-id="a5157-108">检索 DocInstance.xml[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收端口和由任意 XPath 属性处理程序调用的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="a5157-108">DocInstance.xml is retrieved by a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive port and processed by a custom pipeline component called Arbitrary XPath Property Handler.</span></span>  
  
2. <span data-ttu-id="a5157-109">任意 XPath 属性处理程序组件将升级所有\<价格\>并\<Quantity\>采购订单架构中定义为任意 XPath 表达式的元素。</span><span class="sxs-lookup"><span data-stu-id="a5157-109">The arbitrary XPath property handler component promotes all \<Price\> and \<Quantity\> elements with an arbitrary XPath expression as defined in the PO schema.</span></span> <span data-ttu-id="a5157-110">XPath 表达式还包含与 PO 文档根元素的不明确的子元素一起使用的位置构造。</span><span class="sxs-lookup"><span data-stu-id="a5157-110">The XPath expression also contains the position construct for use with ambiguous child elements of the PO document root element.</span></span>  
  
3. <span data-ttu-id="a5157-111">任意 XPath 属性处理程序组件确定消息类型，并将其升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="a5157-111">The arbitrary XPath property handler component determines the message type and promotes it into the message context.</span></span>  
  
4. <span data-ttu-id="a5157-112">然后，组件将具有已升级元素的 XML 文档发送到业务流程以便进一步处理。</span><span class="sxs-lookup"><span data-stu-id="a5157-112">The component then sends the XML document with the promoted elements to an orchestration for further processing.</span></span>  
  
5. <span data-ttu-id="a5157-113">业务流程访问 PO 文档中的已升级的元素并计算 PO 中项的总数。</span><span class="sxs-lookup"><span data-stu-id="a5157-113">The orchestration accesses the promoted elements in the PO document and calculates the total number of items in the PO.</span></span>  
  
6. <span data-ttu-id="a5157-114">业务流程将创建包含原始采购订单和更新的总数中信息的新采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="a5157-114">The orchestration creates a new PO document that contains the information from the original PO as well as the updated total.</span></span>  
  
7. <span data-ttu-id="a5157-115">新 PO 文档写入 \Output 目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="a5157-115">The new PO document is written to a file in the \Output directory.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a5157-116">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="a5157-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="a5157-117">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="a5157-117">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
 <span data-ttu-id="a5157-118">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="a5157-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a5157-119">文件</span><span class="sxs-lookup"><span data-stu-id="a5157-119">File(s)</span></span>|<span data-ttu-id="a5157-120">Description</span><span class="sxs-lookup"><span data-stu-id="a5157-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5157-121">ArbitraryXPathPropertyHandler.sln</span><span class="sxs-lookup"><span data-stu-id="a5157-121">ArbitraryXPathPropertyHandler.sln</span></span>|<span data-ttu-id="a5157-122">自定义管道组件解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="a5157-122">Custom pipeline component solution file.</span></span>|  
|<span data-ttu-id="a5157-123">ArbitraryXPathPropertyHandler.resX</span><span class="sxs-lookup"><span data-stu-id="a5157-123">ArbitraryXPathPropertyHandler.resX</span></span>|<span data-ttu-id="a5157-124">资源文件。</span><span class="sxs-lookup"><span data-stu-id="a5157-124">Resource file.</span></span>|  
|<span data-ttu-id="a5157-125">ArbitraryXPathPropertyHandlerComp.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-125">ArbitraryXPathPropertyHandlerComp.cs</span></span>|<span data-ttu-id="a5157-126">主要组件实现。</span><span class="sxs-lookup"><span data-stu-id="a5157-126">Main component implementation.</span></span>|  
|<span data-ttu-id="a5157-127">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-127">AssemblyInfo.cs</span></span>|<span data-ttu-id="a5157-128">程序集信息。</span><span class="sxs-lookup"><span data-stu-id="a5157-128">Assembly information.</span></span>|  
|<span data-ttu-id="a5157-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a5157-129">Cleanup.bat</span></span>|<span data-ttu-id="a5157-130">示例清理文件。</span><span class="sxs-lookup"><span data-stu-id="a5157-130">Sample cleanup file.</span></span>|  
|<span data-ttu-id="a5157-131">PromotingMap.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-131">PromotingMap.cs</span></span>|<span data-ttu-id="a5157-132">属性升级为本机 CLR 类型的映射实现。</span><span class="sxs-lookup"><span data-stu-id="a5157-132">Property promotion as native CLR types map implementation.</span></span>|  
|<span data-ttu-id="a5157-133">PropertyAttributes.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-133">PropertyAttributes.cs</span></span>|<span data-ttu-id="a5157-134">自定义特性、 属性说明符和 ICustomTypePropertyDescriptor 实现。</span><span class="sxs-lookup"><span data-stu-id="a5157-134">Custom attributes, property descriptor, and ICustomTypePropertyDescriptor implementation.</span></span>|  
|<span data-ttu-id="a5157-135">SchemaMap.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-135">SchemaMap.cs</span></span>|<span data-ttu-id="a5157-136">从消息类型到 IDocumentSpec 若要解决架构不明确问题架构映射。</span><span class="sxs-lookup"><span data-stu-id="a5157-136">Schema mapping from message type to IDocumentSpec to resolve schema ambiguity.</span></span>|  
|<span data-ttu-id="a5157-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a5157-137">Setup.bat</span></span>|<span data-ttu-id="a5157-138">生成和安装示例管道组件。</span><span class="sxs-lookup"><span data-stu-id="a5157-138">Build and setup sample pipeline component.</span></span>|  
|<span data-ttu-id="a5157-139">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-139">VirtualStream.cs</span></span>|<span data-ttu-id="a5157-140">虚拟流实现。</span><span class="sxs-lookup"><span data-stu-id="a5157-140">Virtual stream implementation.</span></span>|  
|<span data-ttu-id="a5157-141">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="a5157-141">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="a5157-142">可查找只读流实现。</span><span class="sxs-lookup"><span data-stu-id="a5157-142">Seekable read-only stream implementation.</span></span>|  
|<span data-ttu-id="a5157-143">ArbitraryXPathSample.sln</span><span class="sxs-lookup"><span data-stu-id="a5157-143">ArbitraryXPathSample.sln</span></span>|<span data-ttu-id="a5157-144">示例业务流程解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="a5157-144">Sample orchestration solution file.</span></span>|  
|<span data-ttu-id="a5157-145">CalculateTotalAmount.odx</span><span class="sxs-lookup"><span data-stu-id="a5157-145">CalculateTotalAmount.odx</span></span>|<span data-ttu-id="a5157-146">示例业务流程。</span><span class="sxs-lookup"><span data-stu-id="a5157-146">Sample orchestration.</span></span>|  
|<span data-ttu-id="a5157-147">PODocument.xsd</span><span class="sxs-lookup"><span data-stu-id="a5157-147">PODocument.xsd</span></span>|<span data-ttu-id="a5157-148">采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="a5157-148">Purchase order schema.</span></span>|  
|<span data-ttu-id="a5157-149">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="a5157-149">DocInstance.xml</span></span>|<span data-ttu-id="a5157-150">示例采购订单实例。</span><span class="sxs-lookup"><span data-stu-id="a5157-150">Sample purchase order instance.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a5157-151">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="a5157-151">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="a5157-152">此示例设计为在运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有环境[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="a5157-152">This sample is designed to run in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on the same machine.</span></span> <span data-ttu-id="a5157-153">如果你的环境与此配置不匹配，则必须修改任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例) 以指向正确的 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="a5157-153">If your environment does not match this configuration, you must modify the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) to point to the correct SQL Server computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5157-154">Setup.bat 假定 Microsoft Windows 安装目录为 C:\Windows。</span><span class="sxs-lookup"><span data-stu-id="a5157-154">Setup.bat assumes your Microsoft Windows installation directory is C:\Windows.</span></span> <span data-ttu-id="a5157-155">如果您的 Windows 安装在另一个目录，必须修改 ArbitraryXPathPropertyHandler.csproj 文件以反映 Microsoft.BizTalk.Component.Utilities 程序集在全局程序集缓存中的位置。</span><span class="sxs-lookup"><span data-stu-id="a5157-155">If your Windows installation is in another directory, you must modify the ArbitraryXPathPropertyHandler.csproj file to reflect the location of the Microsoft.BizTalk.Component.Utilities assembly in the global assembly cache.</span></span> <span data-ttu-id="a5157-156">在引用元素中，更改\<SYSTEMROOT\>到 Windows 的安装位置 (例如，C:\WINNT\\)。</span><span class="sxs-lookup"><span data-stu-id="a5157-156">In the Reference element, change \<SYSTEMROOT\> to the location where Windows is installed (for example, C:\WINNT\\).</span></span>  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 <span data-ttu-id="a5157-157">使用以下过程生成并初始化任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例)。</span><span class="sxs-lookup"><span data-stu-id="a5157-157">Use the following procedure to build and initialize the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="a5157-158">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="a5157-158">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="a5157-159">在命令窗口中，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a5157-159">In a command window, change directories (**cd**) to the following folder:</span></span>  
  
    <span data-ttu-id="a5157-160">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="a5157-160">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
2. <span data-ttu-id="a5157-161">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a5157-161">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="a5157-162">生成任意 XPath 属性处理程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="a5157-162">Builds the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
   - <span data-ttu-id="a5157-163">要为其生成的副本管道组件*\<安装路径\>* \Pipeline Components 目录。</span><span class="sxs-lookup"><span data-stu-id="a5157-163">Copies built pipeline component to the *\<Installation Path\>* \Pipeline Components directory.</span></span>  
  
   - <span data-ttu-id="a5157-164">创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a5157-164">Creates the send and receive ports.</span></span>  
  
   - <span data-ttu-id="a5157-165">创建示例中使用的输入和输出目录。</span><span class="sxs-lookup"><span data-stu-id="a5157-165">Creates the input and output directories used in the sample.</span></span>  
  
   - <span data-ttu-id="a5157-166">将此示例安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程 ArbitraryXPathSample。</span><span class="sxs-lookup"><span data-stu-id="a5157-166">Installs the sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration ArbitraryXPathSample.</span></span>  
  
   - <span data-ttu-id="a5157-167">将端口绑定到示例业务流程。</span><span class="sxs-lookup"><span data-stu-id="a5157-167">Binds the ports to the sample orchestration.</span></span>  
  
   - <span data-ttu-id="a5157-168">启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="a5157-168">Starts the orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a5157-169">应在生成和初始化过程中不报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="a5157-169">No errors should be reported during the build and initialization.</span></span> <span data-ttu-id="a5157-170">如果出现任何错误，请确保已安装的所有必需软件，并且 Microsoft 生成工具的路径上可用。</span><span class="sxs-lookup"><span data-stu-id="a5157-170">If any errors occur, make sure that you have all necessary software installed and that Microsoft build tools are available on the path.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="a5157-171">若要撤消 Setup.bat 所做的更改，必须先停止并重新启动主机实例从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a5157-171">To undo changes made by Setup.bat, you must first stop and restart the host instance from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a5157-172">接下来，运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="a5157-172">Next, run Cleanup.bat.</span></span> <span data-ttu-id="a5157-173">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="a5157-173">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="a5157-174">运行本示例</span><span class="sxs-lookup"><span data-stu-id="a5157-174">Running This Sample</span></span>  
 <span data-ttu-id="a5157-175">使用以下过程运行任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例)。</span><span class="sxs-lookup"><span data-stu-id="a5157-175">Use the following procedure to run the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="a5157-176">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="a5157-176">To run this sample</span></span>  
  
1.  <span data-ttu-id="a5157-177">将采购订单 (PO) 文件 DocInstance.xml 复制到 \Input 目录。</span><span class="sxs-lookup"><span data-stu-id="a5157-177">Copy the purchase order (PO) file DocInstance.xml to the \Input directory.</span></span> <span data-ttu-id="a5157-178">PO 文件是将 XML 数据发送到任意 XPath 属性处理程序管道组件的接收端口提取。</span><span class="sxs-lookup"><span data-stu-id="a5157-178">The PO file is picked up by a receive port, which sends the XML data to the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
2.  <span data-ttu-id="a5157-179">查看 \Output 目录中的内容。</span><span class="sxs-lookup"><span data-stu-id="a5157-179">View the contents in the \Output directory.</span></span> <span data-ttu-id="a5157-180">请注意，新的文件创建包含复制到 \Input 目录的 DocInstance.xml 文件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="a5157-180">Notice that a new file is created that contains all the information from the DocInstance.xml file that you copied to the \Input directory.</span></span> <span data-ttu-id="a5157-181">在文件中的区别在于现在\<TotalAmount\>元素填入采购订单的总金额。</span><span class="sxs-lookup"><span data-stu-id="a5157-181">The difference in the file is that now the \<TotalAmount\> element has been populated with the total amount for the PO.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a5157-182">注释</span><span class="sxs-lookup"><span data-stu-id="a5157-182">Comments</span></span>  
 <span data-ttu-id="a5157-183">规范化 XPath 表达式是简单表达式，如"/ \* [local-name = 元素的 name and =http://MyUri.org] /\*[本地名称 （) = 元素的 name] / @\*[本地名称 = attribute name]"。</span><span class="sxs-lookup"><span data-stu-id="a5157-183">Canonical XPath expressions are simple expressions such as "/\*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/\*[local-name()='element-name']/@\*[local-name='attribute-name']".</span></span>  
  
 <span data-ttu-id="a5157-184">任意 XPath 表达式可以是很复杂，比如"//element-name//\* [本地名称 （) = 元素名称和位置 （） = 2]"。</span><span class="sxs-lookup"><span data-stu-id="a5157-184">An arbitrary XPath expression can be as complex as "//element-name//\*[local-name()='element-name' and position()=2]".</span></span> <span data-ttu-id="a5157-185">如果这一事实，您将收到一个运行时错误，指出，不受非规范化 XPath 表达式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果架构的 XPath 正文或某个 XPath 属性中使用了非规范化 XPath。</span><span class="sxs-lookup"><span data-stu-id="a5157-185">If fact, you will receive a run-time error stating that non-canonical XPath expressions are not supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] if your schema has a non-canonical XPath used in the XPath body or an XPath property.</span></span> <span data-ttu-id="a5157-186">若要支持任意 XPath 表达式的解决方案是创建支持任意 XPath 正文和任意 XPath 属性表达式的自定义拆装器和组装器组件。</span><span class="sxs-lookup"><span data-stu-id="a5157-186">A solution to support arbitrary XPath expressions is to create custom disassembler and assembler components that support an arbitrary XPath body as well as arbitrary XPath property expressions.</span></span>  
  
 <span data-ttu-id="a5157-187">此示例使用以下步骤序列中的自定义管道组件时**IComponent.Execute**实现：</span><span class="sxs-lookup"><span data-stu-id="a5157-187">This sample uses the following sequence of steps in the custom pipeline component when **IComponent.Execute** is implemented:</span></span>  
  
1.  <span data-ttu-id="a5157-188">通过输入的消息正文部分流创建虚拟可查找的流。</span><span class="sxs-lookup"><span data-stu-id="a5157-188">Creates a virtual seekable stream over the input message body part stream.</span></span> <span data-ttu-id="a5157-189">（因为输入的消息可能很大，流不可查找，它应具有较小的内存需求量并且能够更改流位置。）</span><span class="sxs-lookup"><span data-stu-id="a5157-189">(Because the input message can be large and the stream can be non-seekable, it should have a small memory footprint and be able to change stream positions.)</span></span>  
  
2.  <span data-ttu-id="a5157-190">为其创建新的传出消息和新的正文部分、 将虚拟流分配给新正文部分，克隆正文部分属性和克隆消息上下文。</span><span class="sxs-lookup"><span data-stu-id="a5157-190">Creates a new outgoing message and a new body part for it, assigns a virtual stream to the new body part, clones body part properties, and clones message context.</span></span>  
  
3.  <span data-ttu-id="a5157-191">获取输入的消息或在设计时指定的基于的架构的架构。</span><span class="sxs-lookup"><span data-stu-id="a5157-191">Gets a schema for the input message or based on schemas specified during design time.</span></span>  
  
4.  <span data-ttu-id="a5157-192">将流加载到的实例**System.Xml.XmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="a5157-192">Loads the stream into an instance of **System.Xml.XmlDocument**.</span></span>  
  
5.  <span data-ttu-id="a5157-193">将引导完成升级的属性和可分辨的字段和升级或将其写入到传出消息的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="a5157-193">Walks through promoted properties and distinguished fields and promotes or writes them to the message context of the outgoing message.</span></span>  
  
6.  <span data-ttu-id="a5157-194">返回传出消息。</span><span class="sxs-lookup"><span data-stu-id="a5157-194">Returns the outgoing message.</span></span>  
  
7.  <span data-ttu-id="a5157-195">向文件写入传出消息。</span><span class="sxs-lookup"><span data-stu-id="a5157-195">Writes the outgoing message to a file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5157-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5157-196">See Also</span></span>  
 [<span data-ttu-id="a5157-197">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="a5157-197">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)