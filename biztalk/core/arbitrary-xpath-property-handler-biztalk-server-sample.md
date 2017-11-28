---
title: "任意 XPath 属性处理程序 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3ce40931caaf8f247afeacdae48721f31a7d99b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a><span data-ttu-id="b58b7-102">任意 XPath 属性处理程序 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="b58b7-102">Arbitrary XPath Property Handler (BizTalk Server Sample)</span></span>
<span data-ttu-id="b58b7-103">任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）演示了如何编写自定义管道组件以升级提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 XML 文档中的特定属性。</span><span class="sxs-lookup"><span data-stu-id="b58b7-103">The Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) demonstrates how to write a custom pipeline component to promote specific properties on an XML document that is submitted to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b58b7-104">您可以使用示例中包含的功能创建自定义常规组装器和拆装器组件以评估 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="b58b7-104">You can use functionality contained in the sample to create custom regular, assembler, and disassembler components to evaluate XPath expressions.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b58b7-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="b58b7-105">What This Sample Does</span></span>  
 <span data-ttu-id="b58b7-106">本示例包括要处理的采购订单 (PO) XML 文档 DocInstance.xml。</span><span class="sxs-lookup"><span data-stu-id="b58b7-106">The sample includes a purchase order (PO) XML document to process, DocInstance.xml.</span></span> <span data-ttu-id="b58b7-107">本示例将使用以下步骤处理 DocInstance.xml：</span><span class="sxs-lookup"><span data-stu-id="b58b7-107">The sample uses the following steps to process DocInstance.xml:</span></span>  
  
1.  <span data-ttu-id="b58b7-108">DocInstance.xml 由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收端口检索并由称为“任意 XPath 属性处理程序”的自定义管道组件进行处理。</span><span class="sxs-lookup"><span data-stu-id="b58b7-108">DocInstance.xml is retrieved by a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive port and processed by a custom pipeline component called Arbitrary XPath Property Handler.</span></span>  
  
2.  <span data-ttu-id="b58b7-109">任意 XPath 属性处理程序组件将升级所有\<价格 > 和\<数量 > 采购订单架构中定义任意的 XPath 表达式作为元素。</span><span class="sxs-lookup"><span data-stu-id="b58b7-109">The arbitrary XPath property handler component promotes all \<Price> and \<Quantity> elements with an arbitrary XPath expression as defined in the PO schema.</span></span> <span data-ttu-id="b58b7-110">XPath 表达式还包含与 PO 文档根元素的不明确的子元素一起使用的位置构造。</span><span class="sxs-lookup"><span data-stu-id="b58b7-110">The XPath expression also contains the position construct for use with ambiguous child elements of the PO document root element.</span></span>  
  
3.  <span data-ttu-id="b58b7-111">任意 XPath 属性处理程序组件可确定消息类型并将其升级到消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="b58b7-111">The arbitrary XPath property handler component determines the message type and promotes it into the message context.</span></span>  
  
4.  <span data-ttu-id="b58b7-112">然后，该组件将具有已升级元素的 XML 文档发送到业务流程以便进一步处理。</span><span class="sxs-lookup"><span data-stu-id="b58b7-112">The component then sends the XML document with the promoted elements to an orchestration for further processing.</span></span>  
  
5.  <span data-ttu-id="b58b7-113">该业务流程将访问 PO 文档中的已升级元素并计算 PO 中项的总数。</span><span class="sxs-lookup"><span data-stu-id="b58b7-113">The orchestration accesses the promoted elements in the PO document and calculates the total number of items in the PO.</span></span>  
  
6.  <span data-ttu-id="b58b7-114">该业务流程将创建包含原始 PO 中的信息及已更新总数的新 PO 文档。</span><span class="sxs-lookup"><span data-stu-id="b58b7-114">The orchestration creates a new PO document that contains the information from the original PO as well as the updated total.</span></span>  
  
7.  <span data-ttu-id="b58b7-115">新 PO 文档将写入 \Output 目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-115">The new PO document is written to a file in the \Output directory.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b58b7-116">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="b58b7-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="b58b7-117">*\<示例路径 >*\Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="b58b7-117">*\<Samples Path>*\Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
 <span data-ttu-id="b58b7-118">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="b58b7-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b58b7-119">文件</span><span class="sxs-lookup"><span data-stu-id="b58b7-119">File(s)</span></span>|<span data-ttu-id="b58b7-120">Description</span><span class="sxs-lookup"><span data-stu-id="b58b7-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b58b7-121">ArbitraryXPathPropertyHandler.sln</span><span class="sxs-lookup"><span data-stu-id="b58b7-121">ArbitraryXPathPropertyHandler.sln</span></span>|<span data-ttu-id="b58b7-122">自定义管道组件解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-122">Custom pipeline component solution file.</span></span>|  
|<span data-ttu-id="b58b7-123">ArbitraryXPathPropertyHandler.resX</span><span class="sxs-lookup"><span data-stu-id="b58b7-123">ArbitraryXPathPropertyHandler.resX</span></span>|<span data-ttu-id="b58b7-124">资源文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-124">Resource file.</span></span>|  
|<span data-ttu-id="b58b7-125">ArbitraryXPathPropertyHandlerComp.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-125">ArbitraryXPathPropertyHandlerComp.cs</span></span>|<span data-ttu-id="b58b7-126">主要组件实现。</span><span class="sxs-lookup"><span data-stu-id="b58b7-126">Main component implementation.</span></span>|  
|<span data-ttu-id="b58b7-127">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-127">AssemblyInfo.cs</span></span>|<span data-ttu-id="b58b7-128">程序集信息。</span><span class="sxs-lookup"><span data-stu-id="b58b7-128">Assembly information.</span></span>|  
|<span data-ttu-id="b58b7-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="b58b7-129">Cleanup.bat</span></span>|<span data-ttu-id="b58b7-130">示例清理文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-130">Sample cleanup file.</span></span>|  
|<span data-ttu-id="b58b7-131">PromotingMap.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-131">PromotingMap.cs</span></span>|<span data-ttu-id="b58b7-132">属性升级为本机 CLR 类型的映射实现。</span><span class="sxs-lookup"><span data-stu-id="b58b7-132">Property promotion as native CLR types map implementation.</span></span>|  
|<span data-ttu-id="b58b7-133">PropertyAttributes.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-133">PropertyAttributes.cs</span></span>|<span data-ttu-id="b58b7-134">自定义属性、属性说明符和 ICustomTypePropertyDescriptor 实现。</span><span class="sxs-lookup"><span data-stu-id="b58b7-134">Custom attributes, property descriptor, and ICustomTypePropertyDescriptor implementation.</span></span>|  
|<span data-ttu-id="b58b7-135">SchemaMap.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-135">SchemaMap.cs</span></span>|<span data-ttu-id="b58b7-136">从消息类型映射到 IDocumentSpec 的架构，用于解决架构不明确问题。</span><span class="sxs-lookup"><span data-stu-id="b58b7-136">Schema mapping from message type to IDocumentSpec to resolve schema ambiguity.</span></span>|  
|<span data-ttu-id="b58b7-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="b58b7-137">Setup.bat</span></span>|<span data-ttu-id="b58b7-138">生成和安装示例管道组件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-138">Build and setup sample pipeline component.</span></span>|  
|<span data-ttu-id="b58b7-139">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-139">VirtualStream.cs</span></span>|<span data-ttu-id="b58b7-140">虚拟流实现。</span><span class="sxs-lookup"><span data-stu-id="b58b7-140">Virtual stream implementation.</span></span>|  
|<span data-ttu-id="b58b7-141">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="b58b7-141">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="b58b7-142">可查找的只读流实现。</span><span class="sxs-lookup"><span data-stu-id="b58b7-142">Seekable read-only stream implementation.</span></span>|  
|<span data-ttu-id="b58b7-143">ArbitraryXPathSample.sln</span><span class="sxs-lookup"><span data-stu-id="b58b7-143">ArbitraryXPathSample.sln</span></span>|<span data-ttu-id="b58b7-144">示例业务流程解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-144">Sample orchestration solution file.</span></span>|  
|<span data-ttu-id="b58b7-145">CalculateTotalAmount.odx</span><span class="sxs-lookup"><span data-stu-id="b58b7-145">CalculateTotalAmount.odx</span></span>|<span data-ttu-id="b58b7-146">示例业务流程。</span><span class="sxs-lookup"><span data-stu-id="b58b7-146">Sample orchestration.</span></span>|  
|<span data-ttu-id="b58b7-147">PODocument.xsd</span><span class="sxs-lookup"><span data-stu-id="b58b7-147">PODocument.xsd</span></span>|<span data-ttu-id="b58b7-148">采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="b58b7-148">Purchase order schema.</span></span>|  
|<span data-ttu-id="b58b7-149">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="b58b7-149">DocInstance.xml</span></span>|<span data-ttu-id="b58b7-150">示例采购订单实例。</span><span class="sxs-lookup"><span data-stu-id="b58b7-150">Sample purchase order instance.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="b58b7-151">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="b58b7-151">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="b58b7-152">本示例设计为在同一台计算机上运行有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 环境中运行。</span><span class="sxs-lookup"><span data-stu-id="b58b7-152">This sample is designed to run in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on the same machine.</span></span> <span data-ttu-id="b58b7-153">如果您的环境与此配置不匹配，则您必须修改任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）以指向 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="b58b7-153">If your environment does not match this configuration, you must modify the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) to point to the correct SQL Server computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b58b7-154">Setup.bat 假定 Microsoft Windows 安装目录为 C:\Windows。</span><span class="sxs-lookup"><span data-stu-id="b58b7-154">Setup.bat assumes your Microsoft Windows installation directory is C:\Windows.</span></span> <span data-ttu-id="b58b7-155">如果 Windows 安装在其他目录中，则必须修改 ArbitraryXPathPropertyHandler.csproj 文件以反映 Microsoft.BizTalk.Component.Utilities 程序集在全局程序集缓存中的位置。</span><span class="sxs-lookup"><span data-stu-id="b58b7-155">If your Windows installation is in another directory, you must modify the ArbitraryXPathPropertyHandler.csproj file to reflect the location of the Microsoft.BizTalk.Component.Utilities assembly in the global assembly cache.</span></span> <span data-ttu-id="b58b7-156">在引用元素中，更改\<SYSTEMROOT > 到 Windows 的安装位置 (例如，C:\WINNT\\)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-156">In the Reference element, change \<SYSTEMROOT> to the location where Windows is installed (for example, C:\WINNT\\).</span></span>  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 <span data-ttu-id="b58b7-157">使用以下过程生成并初始化任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）。</span><span class="sxs-lookup"><span data-stu-id="b58b7-157">Use the following procedure to build and initialize the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="b58b7-158">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="b58b7-158">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="b58b7-159">在命令窗口中，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b58b7-159">In a command window, change directories (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="b58b7-160">*\<示例路径 >*\Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="b58b7-160">*\<Samples Path>*\Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
2.  <span data-ttu-id="b58b7-161">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b58b7-161">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="b58b7-162">生成任意 XPath 属性处理程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-162">Builds the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
    -   <span data-ttu-id="b58b7-163">要为其生成的副本管道组件*\<安装路径 >*\Pipeline 组件的目录。</span><span class="sxs-lookup"><span data-stu-id="b58b7-163">Copies built pipeline component to the *\<Installation Path>*\Pipeline Components directory.</span></span>  
  
    -   <span data-ttu-id="b58b7-164">创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="b58b7-164">Creates the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="b58b7-165">创建示例中使用的输入和输出目录。</span><span class="sxs-lookup"><span data-stu-id="b58b7-165">Creates the input and output directories used in the sample.</span></span>  
  
    -   <span data-ttu-id="b58b7-166">安装示例 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程 ArbitraryXPathSample。</span><span class="sxs-lookup"><span data-stu-id="b58b7-166">Installs the sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration ArbitraryXPathSample.</span></span>  
  
    -   <span data-ttu-id="b58b7-167">将端口绑定到示例业务流程。</span><span class="sxs-lookup"><span data-stu-id="b58b7-167">Binds the ports to the sample orchestration.</span></span>  
  
    -   <span data-ttu-id="b58b7-168">启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="b58b7-168">Starts the orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b58b7-169">在生成和初始化期间不应报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="b58b7-169">No errors should be reported during the build and initialization.</span></span> <span data-ttu-id="b58b7-170">如果出现任何错误，请确保安装了所有所需软件并且路径中的 Microsoft 生成工具可用。</span><span class="sxs-lookup"><span data-stu-id="b58b7-170">If any errors occur, make sure that you have all necessary software installed and that Microsoft build tools are available on the path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b58b7-171">若要撤消 Setup.bat 所做的更改，必须首先从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台停止并重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="b58b7-171">To undo changes made by Setup.bat, you must first stop and restart the host instance from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b58b7-172">然后运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="b58b7-172">Next, run Cleanup.bat.</span></span> <span data-ttu-id="b58b7-173">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="b58b7-173">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="b58b7-174">运行本示例</span><span class="sxs-lookup"><span data-stu-id="b58b7-174">Running This Sample</span></span>  
 <span data-ttu-id="b58b7-175">使用以下过程运行任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）。</span><span class="sxs-lookup"><span data-stu-id="b58b7-175">Use the following procedure to run the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="b58b7-176">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="b58b7-176">To run this sample</span></span>  
  
1.  <span data-ttu-id="b58b7-177">将采购订单 (PO) 文件 DocInstance.xml 复制到 \Input 目录。</span><span class="sxs-lookup"><span data-stu-id="b58b7-177">Copy the purchase order (PO) file DocInstance.xml to the \Input directory.</span></span> <span data-ttu-id="b58b7-178">接收端口提取该 PO 文件，并将 XML 数据发送到任意 XPath 属性处理程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-178">The PO file is picked up by a receive port, which sends the XML data to the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
2.  <span data-ttu-id="b58b7-179">查看 \Output 目录中的内容。</span><span class="sxs-lookup"><span data-stu-id="b58b7-179">View the contents in the \Output directory.</span></span> <span data-ttu-id="b58b7-180">请注意，创建了一个新文件，它包含复制到 \Input 目录的 DocInstance.xml 文件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b58b7-180">Notice that a new file is created that contains all the information from the DocInstance.xml file that you copied to the \Input directory.</span></span> <span data-ttu-id="b58b7-181">文件中的差异在于现在\<TotalAmount > 元素中填入了采购订单的总金额。</span><span class="sxs-lookup"><span data-stu-id="b58b7-181">The difference in the file is that now the \<TotalAmount> element has been populated with the total amount for the PO.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="b58b7-182">注释</span><span class="sxs-lookup"><span data-stu-id="b58b7-182">Comments</span></span>  
 <span data-ttu-id="b58b7-183">规范的 XPath 表达式是简单表达式，如"/ * [本地名称 （) = 元素名称和 namespaceURI() = http://MyUri.org'] /\*[本地名称 （) =' 元素-name'] / @\*[本地名称 = attribute name]"。</span><span class="sxs-lookup"><span data-stu-id="b58b7-183">Canonical XPath expressions are simple expressions such as "/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/\*[local-name()='element-name']/@\*[local-name='attribute-name']".</span></span>  
  
 <span data-ttu-id="b58b7-184">任意 XPath 表达式是复杂表达式，例如“//element-name//*[local-name()='element-name' and position()=2]”。</span><span class="sxs-lookup"><span data-stu-id="b58b7-184">An arbitrary XPath expression can be as complex as "//element-name//*[local-name()='element-name' and position()=2]".</span></span> <span data-ttu-id="b58b7-185">事实上，如果架构的 XPath 正文或某个 XPath 属性中使用了非规范化 XPath，则您将收到一个运行时错误，指出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持非规范化 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="b58b7-185">If fact, you will receive a run-time error stating that non-canonical XPath expressions are not supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] if your schema has a non-canonical XPath used in the XPath body or an XPath property.</span></span> <span data-ttu-id="b58b7-186">支持任意 XPath 表达式的解决方案是，创建支持任意 XPath 正文和任意 XPath 属性表达式的自定义拆装器和组装器组件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-186">A solution to support arbitrary XPath expressions is to create custom disassembler and assembler components that support an arbitrary XPath body as well as arbitrary XPath property expressions.</span></span>  
  
 <span data-ttu-id="b58b7-187">此示例使用下面的步骤序列中的自定义管道组件时**IComponent.Execute**实现：</span><span class="sxs-lookup"><span data-stu-id="b58b7-187">This sample uses the following sequence of steps in the custom pipeline component when **IComponent.Execute** is implemented:</span></span>  
  
1.  <span data-ttu-id="b58b7-188">通过输入消息正文部分流创建虚拟可查找的流。</span><span class="sxs-lookup"><span data-stu-id="b58b7-188">Creates a virtual seekable stream over the input message body part stream.</span></span> <span data-ttu-id="b58b7-189">（因为输入消息可能较大并且该流可能不可查找，它应具有较小的内存需求量并且能够更改流位置。）</span><span class="sxs-lookup"><span data-stu-id="b58b7-189">(Because the input message can be large and the stream can be non-seekable, it should have a small memory footprint and be able to change stream positions.)</span></span>  
  
2.  <span data-ttu-id="b58b7-190">为输入消息创建一个新的传出消息和新的正文部分，将虚拟流分配给新正文部分，克隆正文部分属性，然后克隆消息上下文。</span><span class="sxs-lookup"><span data-stu-id="b58b7-190">Creates a new outgoing message and a new body part for it, assigns a virtual stream to the new body part, clones body part properties, and clones message context.</span></span>  
  
3.  <span data-ttu-id="b58b7-191">为输入消息获取一个架构或基于设计时指定的架构。</span><span class="sxs-lookup"><span data-stu-id="b58b7-191">Gets a schema for the input message or based on schemas specified during design time.</span></span>  
  
4.  <span data-ttu-id="b58b7-192">将流加载到的实例**System.Xml.XmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-192">Loads the stream into an instance of **System.Xml.XmlDocument**.</span></span>  
  
5.  <span data-ttu-id="b58b7-193">演练升级属性和可分辨字段并将其升级到或写入传出消息的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="b58b7-193">Walks through promoted properties and distinguished fields and promotes or writes them to the message context of the outgoing message.</span></span>  
  
6.  <span data-ttu-id="b58b7-194">返回传出消息。</span><span class="sxs-lookup"><span data-stu-id="b58b7-194">Returns the outgoing message.</span></span>  
  
7.  <span data-ttu-id="b58b7-195">将传出消息写入文件。</span><span class="sxs-lookup"><span data-stu-id="b58b7-195">Writes the outgoing message to a file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58b7-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b58b7-196">See Also</span></span>  
 [<span data-ttu-id="b58b7-197">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="b58b7-197">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)