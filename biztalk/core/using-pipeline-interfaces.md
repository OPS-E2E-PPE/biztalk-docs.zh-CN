---
title: "使用管道接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c365a8d7bdf37564d3d9b2dceac1c8615e126ebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-pipeline-interfaces"></a><span data-ttu-id="843b0-102">使用管道接口</span><span class="sxs-lookup"><span data-stu-id="843b0-102">Using Pipeline Interfaces</span></span>
<span data-ttu-id="843b0-103">管道组件一种 .NET 或 COM 组件，它实现一组预定义的接口以便与 BizTalk 消息引擎交互。</span><span class="sxs-lookup"><span data-stu-id="843b0-103">A pipeline component is a .NET or COM component that implements a set of predefined interfaces for interaction with the BizTalk Messaging Engine.</span></span> <span data-ttu-id="843b0-104">根据组件的功能，必须实现不同接口。</span><span class="sxs-lookup"><span data-stu-id="843b0-104">Depending on the functionality of the component, different interfaces must be implemented.</span></span> <span data-ttu-id="843b0-105">本主题介绍这些接口及其一些方法。</span><span class="sxs-lookup"><span data-stu-id="843b0-105">This topic discusses these interfaces and some of their methods.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="843b0-106">如果您在使用 COM 构建自定义管道组件，则必须配置您的组件以便使用多线程单元 (MTA) 模型。</span><span class="sxs-lookup"><span data-stu-id="843b0-106">If you are building a custom pipeline component using COM, you must configure your component to use the Multi-Threaded Apartment (MTA) model.</span></span> <span data-ttu-id="843b0-107">如果没有这样做，则组件的调用将失败并且具有 E_NOINTERFACE 错误。</span><span class="sxs-lookup"><span data-stu-id="843b0-107">If you do not, invocation of your component will fail with an E_NOINTERFACE error.</span></span>  
  
## <a name="ipipelinecontext"></a><span data-ttu-id="843b0-108">IPipelineContext</span><span class="sxs-lookup"><span data-stu-id="843b0-108">IPipelineContext</span></span>  
 <span data-ttu-id="843b0-109">可以使用所有管道组件**IPipelineContext**用于访问所有文档处理特定接口的方法。</span><span class="sxs-lookup"><span data-stu-id="843b0-109">All pipeline components can use **IPipelineContext** methods to access all document processing-specific interfaces.</span></span> <span data-ttu-id="843b0-110">**IPipelineContext**接口提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="843b0-110">The **IPipelineContext** interface provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="843b0-111">允许组件检索环境管道和阶段设置。</span><span class="sxs-lookup"><span data-stu-id="843b0-111">Allows components to retrieve the ambient pipeline and stage settings.</span></span>  
  
-   <span data-ttu-id="843b0-112">允许组件检索消息和消息工厂。</span><span class="sxs-lookup"><span data-stu-id="843b0-112">Allows components to retrieve message and message factories.</span></span> <span data-ttu-id="843b0-113">使用这些工厂，组件可以创建执行组件所需的不同对象。</span><span class="sxs-lookup"><span data-stu-id="843b0-113">With these factories, components can create various objects required for the execution of the component.</span></span>  
  
-   <span data-ttu-id="843b0-114">允许组件检索文档规范。</span><span class="sxs-lookup"><span data-stu-id="843b0-114">Allows components to retrieve the document specifications.</span></span> <span data-ttu-id="843b0-115">文档规范是 XSD 架构以及附加的批注。</span><span class="sxs-lookup"><span data-stu-id="843b0-115">A document specification is an XSD schema plus additional annotations.</span></span>  
  
## <a name="ibasecomponent"></a><span data-ttu-id="843b0-116">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="843b0-116">IBaseComponent</span></span>  
 <span data-ttu-id="843b0-117">所有管道组件都需要实现此接口，以便提供有关组件的基本信息。</span><span class="sxs-lookup"><span data-stu-id="843b0-117">All pipeline components need to implement this interface to provide basic information about the component.</span></span>  
  
## <a name="icomponent"></a><span data-ttu-id="843b0-118">为 IComponent</span><span class="sxs-lookup"><span data-stu-id="843b0-118">IComponent</span></span>  
 <span data-ttu-id="843b0-119">除组装器和拆装器之外的所有管道组件都实现此接口，以便从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎获取消息以供处理并将已处理的消息传递回引擎。</span><span class="sxs-lookup"><span data-stu-id="843b0-119">All pipeline components except assemblers and disassemblers implement this interface to get messages from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine for processing and to pass processed messages back to the engine.</span></span>  
  
 <span data-ttu-id="843b0-120">**执行。**</span><span class="sxs-lookup"><span data-stu-id="843b0-120">**Execute.**</span></span> <span data-ttu-id="843b0-121">由引擎调用以便将输入消息传递到组件并从组件检索已处理的消息的方法。</span><span class="sxs-lookup"><span data-stu-id="843b0-121">Method called by the engine to pass the input message to the component and retrieve the processed message from the component.</span></span>  
  
## <a name="ipropertybag-ipersistpropertybag"></a><span data-ttu-id="843b0-122">IPropertyBag、IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="843b0-122">IPropertyBag, IPersistPropertyBag</span></span>  
 <span data-ttu-id="843b0-123">管道组件需要实现**IPersistPropertyBag**接收其配置信息。</span><span class="sxs-lookup"><span data-stu-id="843b0-123">Pipeline components need to implement **IPersistPropertyBag** to receive its configuration information.</span></span> <span data-ttu-id="843b0-124">此接口和**IPropertyBag**是标准的接口。</span><span class="sxs-lookup"><span data-stu-id="843b0-124">This interface and **IPropertyBag** are the standard interfaces.</span></span> <span data-ttu-id="843b0-125">有关这些接口的详细信息，请参考 Microsoft .NET Framework 软件开发工具包 (SDK) 文档。</span><span class="sxs-lookup"><span data-stu-id="843b0-125">For more information about these interfaces, refer to the Microsoft .NET Framework Software Development Kit (SDK) documentation.</span></span>  
  
## <a name="idisassemblercomponent"></a><span data-ttu-id="843b0-126">IDisassemblerComponent</span><span class="sxs-lookup"><span data-stu-id="843b0-126">IDisassemblerComponent</span></span>  
 <span data-ttu-id="843b0-127">拆装组件是一种管道组件，它在输入端接收单个消息并在输出端生成零个或多个消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-127">A disassembling component is a pipeline component that receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="843b0-128">拆装组件用于将消息交换拆分成单个文档。</span><span class="sxs-lookup"><span data-stu-id="843b0-128">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="843b0-129">反汇编程序组件必须实现的方法**IDisassemblerComponent**要获取来自消息接口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档以进行处理并传递反汇编回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="843b0-129">A disassembler component must implement the methods of the **IDisassemblerComponent** interface to get messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing and to pass disassembled documents back to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
|<span data-ttu-id="843b0-130">方法</span><span class="sxs-lookup"><span data-stu-id="843b0-130">Method</span></span>|<span data-ttu-id="843b0-131">Description</span><span class="sxs-lookup"><span data-stu-id="843b0-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="843b0-132">**反汇编**</span><span class="sxs-lookup"><span data-stu-id="843b0-132">**Disassemble**</span></span>|<span data-ttu-id="843b0-133">执行传入文档的反汇编**pInMsg**。</span><span class="sxs-lookup"><span data-stu-id="843b0-133">Performs the disassembling of the incoming document **pInMsg**.</span></span>|  
|<span data-ttu-id="843b0-134">**GetNext**</span><span class="sxs-lookup"><span data-stu-id="843b0-134">**GetNext**</span></span>|<span data-ttu-id="843b0-135">从拆装器执行导致的消息集获取下一个消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-135">Gets the next message from the message set that resulted from disassembler execution.</span></span> <span data-ttu-id="843b0-136">返回**NULL**如果没有更多的消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-136">Returns **NULL** if there are no more messages.</span></span>|  
  
 <span data-ttu-id="843b0-137">如果您在编写将支持可恢复交换处理的拆装器组件，则必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="843b0-137">If you are writing a disassembler component that will support Recoverable Interchange Processing, you must do the following:</span></span>  
  
1.  <span data-ttu-id="843b0-138">通过在 VirtualStream() 中包装输入流，使输入流可查找。</span><span class="sxs-lookup"><span data-stu-id="843b0-138">Make the input streams seekable by wrapping them in a VirtualStream().</span></span>  
  
2.  <span data-ttu-id="843b0-139">在 GetNext() 中，具有可确定何时消息出错的逻辑。</span><span class="sxs-lookup"><span data-stu-id="843b0-139">In GetNext(), have logic to determine when a message is bad.</span></span> <span data-ttu-id="843b0-140">如果某一消息是错误的，则设置 BTS.MessageDestination = "SuspendQueue" 并在 GetNext() 中返回该消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-140">If a message is bad, set BTS.MessageDestination = "SuspendQueue" and return the message in GetNext().</span></span>  
  
3.  <span data-ttu-id="843b0-141">如果消息是正确的，则设置 BTS.SuspendMessageOnRoutingFailure = True 并在 GetNext() 中返回该消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-141">If the message is good, set BTS.SuspendMessageOnRoutingFailure = True and return the message in GetNext().</span></span>  
  
## <a name="iassemblercomponent"></a><span data-ttu-id="843b0-142">IAssemblerComponent</span><span class="sxs-lookup"><span data-stu-id="843b0-142">IAssemblerComponent</span></span>  
 <span data-ttu-id="843b0-143">组装组件一种管道组件，它在输入端接收若干消息，在输出端生成一个消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-143">An assembling component is a pipeline component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="843b0-144">组装组件用于将若干单独的文档收集到消息交换批中。</span><span class="sxs-lookup"><span data-stu-id="843b0-144">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="843b0-145">在此版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，未采用组装功能，因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 始终将一个文档传递到组件输入。</span><span class="sxs-lookup"><span data-stu-id="843b0-145">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], assembling functionality is not used, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="843b0-146">汇编程序组件实现**IAssemblerComponent**由调用的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时引擎。</span><span class="sxs-lookup"><span data-stu-id="843b0-146">An assembler component implements the **IAssemblerComponent** methods that are called by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine at run time.</span></span>  
  
|<span data-ttu-id="843b0-147">方法</span><span class="sxs-lookup"><span data-stu-id="843b0-147">Method</span></span>|<span data-ttu-id="843b0-148">Description</span><span class="sxs-lookup"><span data-stu-id="843b0-148">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="843b0-149">**AddDocument**</span><span class="sxs-lookup"><span data-stu-id="843b0-149">**AddDocument**</span></span>|<span data-ttu-id="843b0-150">将文档添加**pInMsg**到将包含在该交换的消息的列表。</span><span class="sxs-lookup"><span data-stu-id="843b0-150">Adds the document **pInMsg** to the list of messages that will be included in the interchange.</span></span>|  
|<span data-ttu-id="843b0-151">**将组合**</span><span class="sxs-lookup"><span data-stu-id="843b0-151">**Assemble**</span></span>|<span data-ttu-id="843b0-152">从以前方法所添加的消息生成交换。</span><span class="sxs-lookup"><span data-stu-id="843b0-152">Builds the interchange from the messages that were added by the previous method.</span></span> <span data-ttu-id="843b0-153">返回指向已组装消息的指针。</span><span class="sxs-lookup"><span data-stu-id="843b0-153">Returns a pointer to the assembled message.</span></span>|  
  
## <a name="iprobemessage"></a><span data-ttu-id="843b0-154">IProbeMessage</span><span class="sxs-lookup"><span data-stu-id="843b0-154">IProbeMessage</span></span>  
 <span data-ttu-id="843b0-155">任何管道组件 （常规、 组装，或分解） 可以实现**IProbeMessage**是否需要探测功能的消息。</span><span class="sxs-lookup"><span data-stu-id="843b0-155">Any pipeline component (general, assembling, or disassembling) can implement **IProbeMessage** if it requires message probing functionality.</span></span> <span data-ttu-id="843b0-156">探测组件用于中具有的管道阶段**匹配**执行模式。</span><span class="sxs-lookup"><span data-stu-id="843b0-156">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="843b0-157">在此类阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到组件时，会发送消息和**探测**方法检查以确定该组件是否识别的消息的格式的消息的开头。</span><span class="sxs-lookup"><span data-stu-id="843b0-157">In such stages, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] gives the message to the component, and the **Probe** method examines the beginning of the message to determine if the component recognizes the format of the message.</span></span>  
  
|<span data-ttu-id="843b0-158">方法</span><span class="sxs-lookup"><span data-stu-id="843b0-158">Method</span></span>|<span data-ttu-id="843b0-159">Description</span><span class="sxs-lookup"><span data-stu-id="843b0-159">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="843b0-160">**探测**</span><span class="sxs-lookup"><span data-stu-id="843b0-160">**Probe**</span></span>|<span data-ttu-id="843b0-161">此方法采用**pInMsg**消息，并返回**True**如果识别此格式或**False**否则为。</span><span class="sxs-lookup"><span data-stu-id="843b0-161">This method takes **pInMsg** message, and returns **True** if the format is recognized or **False** otherwise.</span></span>|  
  
## <a name="inameditem"></a><span data-ttu-id="843b0-162">INamedItem</span><span class="sxs-lookup"><span data-stu-id="843b0-162">INamedItem</span></span>  
 <span data-ttu-id="843b0-163">这是用于从托管代码和非托管代码访问文档架构的帮助程序接口。</span><span class="sxs-lookup"><span data-stu-id="843b0-163">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="inameditemlist"></a><span data-ttu-id="843b0-164">INamedItemList</span><span class="sxs-lookup"><span data-stu-id="843b0-164">INamedItemList</span></span>  
 <span data-ttu-id="843b0-165">这是用于从托管代码和非托管代码访问文档架构的帮助程序接口。</span><span class="sxs-lookup"><span data-stu-id="843b0-165">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="idocumentspec"></a><span data-ttu-id="843b0-166">IDocumentSpec</span><span class="sxs-lookup"><span data-stu-id="843b0-166">IDocumentSpec</span></span>  
 <span data-ttu-id="843b0-167">管道组件可以使用的方法**IDocumentSpec**接口以执行特定于文档的操作，例如，将内容属性移到上下文并返回，访问文档架构中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="843b0-167">Pipeline components can use methods of the **IDocumentSpec** interface to perform document-specific actions, such as moving content properties to context and back, accessing document schemas, and so on.</span></span>  
  
|<span data-ttu-id="843b0-168">方法</span><span class="sxs-lookup"><span data-stu-id="843b0-168">Method</span></span>|<span data-ttu-id="843b0-169">Description</span><span class="sxs-lookup"><span data-stu-id="843b0-169">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="843b0-170">**DocType**</span><span class="sxs-lookup"><span data-stu-id="843b0-170">**DocType**</span></span>|<span data-ttu-id="843b0-171">返回当前文档的类型。</span><span class="sxs-lookup"><span data-stu-id="843b0-171">Returns the type of the current document.</span></span>|  
|<span data-ttu-id="843b0-172">**DocSpecName**</span><span class="sxs-lookup"><span data-stu-id="843b0-172">**DocSpecName**</span></span>|<span data-ttu-id="843b0-173">返回当前文档的规范名称。</span><span class="sxs-lookup"><span data-stu-id="843b0-173">Returns the specification name of the current document.</span></span>|  
|<span data-ttu-id="843b0-174">**GetSchemaCollection**</span><span class="sxs-lookup"><span data-stu-id="843b0-174">**GetSchemaCollection**</span></span>|<span data-ttu-id="843b0-175">返回当前文档的文档架构列表。</span><span class="sxs-lookup"><span data-stu-id="843b0-175">Returns the list of document schemas for the current document.</span></span>|  
|<span data-ttu-id="843b0-176">**GetBodyPath**</span><span class="sxs-lookup"><span data-stu-id="843b0-176">**GetBodyPath**</span></span>|<span data-ttu-id="843b0-177">将 XPath 返回到文档中正文部分开始的节点。</span><span class="sxs-lookup"><span data-stu-id="843b0-177">Returns the XPath to the node in the document where the body part begins.</span></span>|  
|<span data-ttu-id="843b0-178">**GetDistinguishedPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="843b0-178">**GetDistinguishedPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="843b0-179">返回所有可分辨字段属性批注的字典枚举数。</span><span class="sxs-lookup"><span data-stu-id="843b0-179">Returns a dictionary enumerator of all distinguished field property annotations.</span></span>|  
|<span data-ttu-id="843b0-180">**GetPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="843b0-180">**GetPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="843b0-181">返回所有属性批注的枚举数。</span><span class="sxs-lookup"><span data-stu-id="843b0-181">Returns an enumerator of all property annotations.</span></span>|  
  
## <a name="icomponentui"></a><span data-ttu-id="843b0-182">IComponentUI</span><span class="sxs-lookup"><span data-stu-id="843b0-182">IComponentUI</span></span>  
 <span data-ttu-id="843b0-183">管道组件必须实现此接口，以便用于管道设计器环境。</span><span class="sxs-lookup"><span data-stu-id="843b0-183">Pipeline components must implement this interface to be used within the Pipeline Designer environment.</span></span>  
  
|<span data-ttu-id="843b0-184">方法</span><span class="sxs-lookup"><span data-stu-id="843b0-184">Method</span></span>|<span data-ttu-id="843b0-185">Description</span><span class="sxs-lookup"><span data-stu-id="843b0-185">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="843b0-186">**图标**</span><span class="sxs-lookup"><span data-stu-id="843b0-186">**Icon**</span></span>|<span data-ttu-id="843b0-187">提供与此组件关联的图标。</span><span class="sxs-lookup"><span data-stu-id="843b0-187">Provides the icon that is associated with this component.</span></span>|  
|<span data-ttu-id="843b0-188">**验证**</span><span class="sxs-lookup"><span data-stu-id="843b0-188">**Validate**</span></span>|<span data-ttu-id="843b0-189">管道设计器在管道编译前调用此方法，以便确认所有配置属性均正确设置。</span><span class="sxs-lookup"><span data-stu-id="843b0-189">Pipeline Designer calls this method before pipeline compilation to verify that all the configuration properties are set correctly.</span></span>|  
  
 <span data-ttu-id="843b0-190">**图标**属性返回**IntPtr**。</span><span class="sxs-lookup"><span data-stu-id="843b0-190">The **Icon** property returns an **IntPtr**.</span></span> <span data-ttu-id="843b0-191">下面的 C# 示例演示如何返回**IntPtr**。</span><span class="sxs-lookup"><span data-stu-id="843b0-191">The following C# example shows how to return an **IntPtr**.</span></span>  
  
```csharp  
static   ResourceManager resManager = new ResourceManager("ResourceManager", Assembly.GetExecutingAssembly());  
...  
[Browsable(false)]  
public IntPtr Icon  
{  
   get  
   {  
      return ((Bitmap)resManager.GetObject("MyIcon")).GetHicon();  
   }  
}  
```  
  
 <span data-ttu-id="843b0-192">有关详细信息，请参阅**IComponentUI 接口 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="843b0-192">For more information, see **IComponentUI Interface (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="843b0-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="843b0-193">See Also</span></span>  
 <span data-ttu-id="843b0-194">[开发自定义管道组件](../core/developing-custom-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="843b0-194">[Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md) </span></span>  
 [<span data-ttu-id="843b0-195">CustomComponent （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="843b0-195">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)