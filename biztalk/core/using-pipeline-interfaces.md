---
title: 使用管道接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d76df29720f33d8c7433bc34f9be239cfee0a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395395"
---
# <a name="using-pipeline-interfaces"></a><span data-ttu-id="c75ef-102">使用管道接口</span><span class="sxs-lookup"><span data-stu-id="c75ef-102">Using Pipeline Interfaces</span></span>
<span data-ttu-id="c75ef-103">管道组件是实现一组预定义的接口，以便与 BizTalk 消息引擎进行交互的.NET 或 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="c75ef-103">A pipeline component is a .NET or COM component that implements a set of predefined interfaces for interaction with the BizTalk Messaging Engine.</span></span> <span data-ttu-id="c75ef-104">具体取决于组件的功能，必须实现不同的接口。</span><span class="sxs-lookup"><span data-stu-id="c75ef-104">Depending on the functionality of the component, different interfaces must be implemented.</span></span> <span data-ttu-id="c75ef-105">本主题介绍这些接口及其一些方法。</span><span class="sxs-lookup"><span data-stu-id="c75ef-105">This topic discusses these interfaces and some of their methods.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c75ef-106">如果要构建使用 COM 的自定义管道组件，必须配置您的组件以使用多线程单元 (MTA) 模型。</span><span class="sxs-lookup"><span data-stu-id="c75ef-106">If you are building a custom pipeline component using COM, you must configure your component to use the Multi-Threaded Apartment (MTA) model.</span></span> <span data-ttu-id="c75ef-107">如果不这样做，则组件的调用将失败具有 E_NOINTERFACE 错误。</span><span class="sxs-lookup"><span data-stu-id="c75ef-107">If you do not, invocation of your component will fail with an E_NOINTERFACE error.</span></span>  
  
## <a name="ipipelinecontext"></a><span data-ttu-id="c75ef-108">IPipelineContext</span><span class="sxs-lookup"><span data-stu-id="c75ef-108">IPipelineContext</span></span>  
 <span data-ttu-id="c75ef-109">所有管道组件可以都使用**IPipelineContext**方法来访问文档的所有特定于处理的接口。</span><span class="sxs-lookup"><span data-stu-id="c75ef-109">All pipeline components can use **IPipelineContext** methods to access all document processing-specific interfaces.</span></span> <span data-ttu-id="c75ef-110">**IPipelineContext**接口提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="c75ef-110">The **IPipelineContext** interface provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="c75ef-111">允许组件检索环境管道和阶段设置。</span><span class="sxs-lookup"><span data-stu-id="c75ef-111">Allows components to retrieve the ambient pipeline and stage settings.</span></span>  
  
-   <span data-ttu-id="c75ef-112">允许组件检索消息和消息工厂。</span><span class="sxs-lookup"><span data-stu-id="c75ef-112">Allows components to retrieve message and message factories.</span></span> <span data-ttu-id="c75ef-113">使用这些工厂，组件可以创建所需的组件的执行的各种对象。</span><span class="sxs-lookup"><span data-stu-id="c75ef-113">With these factories, components can create various objects required for the execution of the component.</span></span>  
  
-   <span data-ttu-id="c75ef-114">允许组件检索文档规范。</span><span class="sxs-lookup"><span data-stu-id="c75ef-114">Allows components to retrieve the document specifications.</span></span> <span data-ttu-id="c75ef-115">文档规范是 XSD 架构以及附加的批注。</span><span class="sxs-lookup"><span data-stu-id="c75ef-115">A document specification is an XSD schema plus additional annotations.</span></span>  
  
## <a name="ibasecomponent"></a><span data-ttu-id="c75ef-116">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="c75ef-116">IBaseComponent</span></span>  
 <span data-ttu-id="c75ef-117">所有管道组件都需要实现此接口可提供有关组件的基本信息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-117">All pipeline components need to implement this interface to provide basic information about the component.</span></span>  
  
## <a name="icomponent"></a><span data-ttu-id="c75ef-118">IComponent</span><span class="sxs-lookup"><span data-stu-id="c75ef-118">IComponent</span></span>  
 <span data-ttu-id="c75ef-119">所有管道组件除组装器和拆装器实现此接口可获取来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎进行处理和传递处理的消息返回给引擎。</span><span class="sxs-lookup"><span data-stu-id="c75ef-119">All pipeline components except assemblers and disassemblers implement this interface to get messages from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine for processing and to pass processed messages back to the engine.</span></span>  
  
 <span data-ttu-id="c75ef-120">**执行。**</span><span class="sxs-lookup"><span data-stu-id="c75ef-120">**Execute.**</span></span> <span data-ttu-id="c75ef-121">方法由引擎调用将传递给该组件的输入的消息并从组件中检索已处理的消息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-121">Method called by the engine to pass the input message to the component and retrieve the processed message from the component.</span></span>  
  
## <a name="ipropertybag-ipersistpropertybag"></a><span data-ttu-id="c75ef-122">IPropertyBag、 IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="c75ef-122">IPropertyBag, IPersistPropertyBag</span></span>  
 <span data-ttu-id="c75ef-123">管道组件需要实现**IPersistPropertyBag**接收其配置信息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-123">Pipeline components need to implement **IPersistPropertyBag** to receive its configuration information.</span></span> <span data-ttu-id="c75ef-124">此接口和**IPropertyBag**是标准接口。</span><span class="sxs-lookup"><span data-stu-id="c75ef-124">This interface and **IPropertyBag** are the standard interfaces.</span></span> <span data-ttu-id="c75ef-125">有关这些接口的详细信息，请参阅 Microsoft.NET Framework 软件开发工具包 (SDK) 文档。</span><span class="sxs-lookup"><span data-stu-id="c75ef-125">For more information about these interfaces, refer to the Microsoft .NET Framework Software Development Kit (SDK) documentation.</span></span>  
  
## <a name="idisassemblercomponent"></a><span data-ttu-id="c75ef-126">IDisassemblerComponent</span><span class="sxs-lookup"><span data-stu-id="c75ef-126">IDisassemblerComponent</span></span>  
 <span data-ttu-id="c75ef-127">拆装组件是接收输入一条消息，并生成输出的零个或多个消息的管道组件。</span><span class="sxs-lookup"><span data-stu-id="c75ef-127">A disassembling component is a pipeline component that receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="c75ef-128">拆装组件用于拆分成单个文档的消息交换。</span><span class="sxs-lookup"><span data-stu-id="c75ef-128">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="c75ef-129">拆装器组件必须实现的方法**IDisassemblerComponent**接口，用于获取来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行处理，并将传递已拆装的文档返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c75ef-129">A disassembler component must implement the methods of the **IDisassemblerComponent** interface to get messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing and to pass disassembled documents back to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
|<span data-ttu-id="c75ef-130">方法</span><span class="sxs-lookup"><span data-stu-id="c75ef-130">Method</span></span>|<span data-ttu-id="c75ef-131">Description</span><span class="sxs-lookup"><span data-stu-id="c75ef-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c75ef-132">**反汇编**</span><span class="sxs-lookup"><span data-stu-id="c75ef-132">**Disassemble**</span></span>|<span data-ttu-id="c75ef-133">执行传入文档的拆装**pInMsg**。</span><span class="sxs-lookup"><span data-stu-id="c75ef-133">Performs the disassembling of the incoming document **pInMsg**.</span></span>|  
|<span data-ttu-id="c75ef-134">**GetNext**</span><span class="sxs-lookup"><span data-stu-id="c75ef-134">**GetNext**</span></span>|<span data-ttu-id="c75ef-135">获取下一条消息由拆装器执行导致的消息集。</span><span class="sxs-lookup"><span data-stu-id="c75ef-135">Gets the next message from the message set that resulted from disassembler execution.</span></span> <span data-ttu-id="c75ef-136">返回**NULL**如果没有更多的消息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-136">Returns **NULL** if there are no more messages.</span></span>|  
  
 <span data-ttu-id="c75ef-137">如果你正在编写将支持可恢复交换处理的拆装器组件，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c75ef-137">If you are writing a disassembler component that will support Recoverable Interchange Processing, you must do the following:</span></span>  
  
1.  <span data-ttu-id="c75ef-138">通过将它们放置在 virtualstream （），使输入的流可查找。</span><span class="sxs-lookup"><span data-stu-id="c75ef-138">Make the input streams seekable by wrapping them in a VirtualStream().</span></span>  
  
2.  <span data-ttu-id="c75ef-139">在 getnext （），具有逻辑来确定消息无效。</span><span class="sxs-lookup"><span data-stu-id="c75ef-139">In GetNext(), have logic to determine when a message is bad.</span></span> <span data-ttu-id="c75ef-140">如果消息是错误的则设置 BTS。MessageDestination ="SuspendQueue"并在 getnext （） 中返回该消息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-140">If a message is bad, set BTS.MessageDestination = "SuspendQueue" and return the message in GetNext().</span></span>  
  
3.  <span data-ttu-id="c75ef-141">如果消息是很好，设置 BTS。SuspendMessageOnRoutingFailure = True，并在 getnext （） 中返回消息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-141">If the message is good, set BTS.SuspendMessageOnRoutingFailure = True and return the message in GetNext().</span></span>  
  
## <a name="iassemblercomponent"></a><span data-ttu-id="c75ef-142">IAssemblerComponent</span><span class="sxs-lookup"><span data-stu-id="c75ef-142">IAssemblerComponent</span></span>  
 <span data-ttu-id="c75ef-143">组装组件是接收输入的多条消息，并生成输出一条消息的管道组件。</span><span class="sxs-lookup"><span data-stu-id="c75ef-143">An assembling component is a pipeline component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="c75ef-144">组装组件用于到消息交换批中收集的各个文档。</span><span class="sxs-lookup"><span data-stu-id="c75ef-144">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c75ef-145">在此版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，未采用组装功能，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]始终将一个文档传递到组件输入。</span><span class="sxs-lookup"><span data-stu-id="c75ef-145">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], assembling functionality is not used, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="c75ef-146">组装器组件实现**IAssemblerComponent**方法调用的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时引擎。</span><span class="sxs-lookup"><span data-stu-id="c75ef-146">An assembler component implements the **IAssemblerComponent** methods that are called by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine at run time.</span></span>  
  
|<span data-ttu-id="c75ef-147">方法</span><span class="sxs-lookup"><span data-stu-id="c75ef-147">Method</span></span>|<span data-ttu-id="c75ef-148">Description</span><span class="sxs-lookup"><span data-stu-id="c75ef-148">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c75ef-149">**AddDocument**</span><span class="sxs-lookup"><span data-stu-id="c75ef-149">**AddDocument**</span></span>|<span data-ttu-id="c75ef-150">将该文档添加**pInMsg**到将交换中包含的消息的列表。</span><span class="sxs-lookup"><span data-stu-id="c75ef-150">Adds the document **pInMsg** to the list of messages that will be included in the interchange.</span></span>|  
|<span data-ttu-id="c75ef-151">**组合**</span><span class="sxs-lookup"><span data-stu-id="c75ef-151">**Assemble**</span></span>|<span data-ttu-id="c75ef-152">生成从上一个方法已添加的消息交换。</span><span class="sxs-lookup"><span data-stu-id="c75ef-152">Builds the interchange from the messages that were added by the previous method.</span></span> <span data-ttu-id="c75ef-153">返回一个指向已组装消息。</span><span class="sxs-lookup"><span data-stu-id="c75ef-153">Returns a pointer to the assembled message.</span></span>|  
  
## <a name="iprobemessage"></a><span data-ttu-id="c75ef-154">IProbeMessage</span><span class="sxs-lookup"><span data-stu-id="c75ef-154">IProbeMessage</span></span>  
 <span data-ttu-id="c75ef-155">任何管道组件 （一般、 组装或拆装） 都可以实现**IProbeMessage**如果它要求消息探测功能。</span><span class="sxs-lookup"><span data-stu-id="c75ef-155">Any pipeline component (general, assembling, or disassembling) can implement **IProbeMessage** if it requires message probing functionality.</span></span> <span data-ttu-id="c75ef-156">探测组件用于具有的管道阶段**第一个匹配**执行模式。</span><span class="sxs-lookup"><span data-stu-id="c75ef-156">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="c75ef-157">在此类阶段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息提供给组件，并**探测**方法将检查消息以确定组件是否识别消息格式的开始。</span><span class="sxs-lookup"><span data-stu-id="c75ef-157">In such stages, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] gives the message to the component, and the **Probe** method examines the beginning of the message to determine if the component recognizes the format of the message.</span></span>  
  
|<span data-ttu-id="c75ef-158">方法</span><span class="sxs-lookup"><span data-stu-id="c75ef-158">Method</span></span>|<span data-ttu-id="c75ef-159">Description</span><span class="sxs-lookup"><span data-stu-id="c75ef-159">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c75ef-160">**Probe**</span><span class="sxs-lookup"><span data-stu-id="c75ef-160">**Probe**</span></span>|<span data-ttu-id="c75ef-161">此方法采用**pInMsg**消息，并返回**True**如果识别格式或**False**否则为。</span><span class="sxs-lookup"><span data-stu-id="c75ef-161">This method takes **pInMsg** message, and returns **True** if the format is recognized or **False** otherwise.</span></span>|  
  
## <a name="inameditem"></a><span data-ttu-id="c75ef-162">INamedItem</span><span class="sxs-lookup"><span data-stu-id="c75ef-162">INamedItem</span></span>  
 <span data-ttu-id="c75ef-163">这是一个帮助器界面，用于从托管和非托管代码访问文档架构。</span><span class="sxs-lookup"><span data-stu-id="c75ef-163">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="inameditemlist"></a><span data-ttu-id="c75ef-164">INamedItemList</span><span class="sxs-lookup"><span data-stu-id="c75ef-164">INamedItemList</span></span>  
 <span data-ttu-id="c75ef-165">这是一个帮助器界面，用于从托管和非托管代码访问文档架构。</span><span class="sxs-lookup"><span data-stu-id="c75ef-165">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="idocumentspec"></a><span data-ttu-id="c75ef-166">IDocumentSpec</span><span class="sxs-lookup"><span data-stu-id="c75ef-166">IDocumentSpec</span></span>  
 <span data-ttu-id="c75ef-167">管道组件可以使用的方法**IDocumentSpec**接口来执行特定于文档的操作，例如，将内容属性移到上下文并返回，访问文档架构中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="c75ef-167">Pipeline components can use methods of the **IDocumentSpec** interface to perform document-specific actions, such as moving content properties to context and back, accessing document schemas, and so on.</span></span>  
  
|<span data-ttu-id="c75ef-168">方法</span><span class="sxs-lookup"><span data-stu-id="c75ef-168">Method</span></span>|<span data-ttu-id="c75ef-169">Description</span><span class="sxs-lookup"><span data-stu-id="c75ef-169">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c75ef-170">**DocType**</span><span class="sxs-lookup"><span data-stu-id="c75ef-170">**DocType**</span></span>|<span data-ttu-id="c75ef-171">返回当前文档的类型。</span><span class="sxs-lookup"><span data-stu-id="c75ef-171">Returns the type of the current document.</span></span>|  
|<span data-ttu-id="c75ef-172">**DocSpecName**</span><span class="sxs-lookup"><span data-stu-id="c75ef-172">**DocSpecName**</span></span>|<span data-ttu-id="c75ef-173">返回当前文档的规范名称。</span><span class="sxs-lookup"><span data-stu-id="c75ef-173">Returns the specification name of the current document.</span></span>|  
|<span data-ttu-id="c75ef-174">**GetSchemaCollection**</span><span class="sxs-lookup"><span data-stu-id="c75ef-174">**GetSchemaCollection**</span></span>|<span data-ttu-id="c75ef-175">返回当前文档的文档架构的列表。</span><span class="sxs-lookup"><span data-stu-id="c75ef-175">Returns the list of document schemas for the current document.</span></span>|  
|<span data-ttu-id="c75ef-176">**GetBodyPath**</span><span class="sxs-lookup"><span data-stu-id="c75ef-176">**GetBodyPath**</span></span>|<span data-ttu-id="c75ef-177">正文部分开始的位置将 XPath 返回到文档中的节点。</span><span class="sxs-lookup"><span data-stu-id="c75ef-177">Returns the XPath to the node in the document where the body part begins.</span></span>|  
|<span data-ttu-id="c75ef-178">**GetDistinguishedPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="c75ef-178">**GetDistinguishedPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="c75ef-179">返回所有可分辨的字段属性批注的字典枚举器。</span><span class="sxs-lookup"><span data-stu-id="c75ef-179">Returns a dictionary enumerator of all distinguished field property annotations.</span></span>|  
|<span data-ttu-id="c75ef-180">**GetPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="c75ef-180">**GetPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="c75ef-181">返回所有属性批注的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c75ef-181">Returns an enumerator of all property annotations.</span></span>|  
  
## <a name="icomponentui"></a><span data-ttu-id="c75ef-182">IComponentUI</span><span class="sxs-lookup"><span data-stu-id="c75ef-182">IComponentUI</span></span>  
 <span data-ttu-id="c75ef-183">管道组件必须实现此接口，以便用于在管道设计器环境。</span><span class="sxs-lookup"><span data-stu-id="c75ef-183">Pipeline components must implement this interface to be used within the Pipeline Designer environment.</span></span>  
  
|<span data-ttu-id="c75ef-184">方法</span><span class="sxs-lookup"><span data-stu-id="c75ef-184">Method</span></span>|<span data-ttu-id="c75ef-185">Description</span><span class="sxs-lookup"><span data-stu-id="c75ef-185">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c75ef-186">**图标**</span><span class="sxs-lookup"><span data-stu-id="c75ef-186">**Icon**</span></span>|<span data-ttu-id="c75ef-187">提供了与此组件关联的图标。</span><span class="sxs-lookup"><span data-stu-id="c75ef-187">Provides the icon that is associated with this component.</span></span>|  
|<span data-ttu-id="c75ef-188">**验证**</span><span class="sxs-lookup"><span data-stu-id="c75ef-188">**Validate**</span></span>|<span data-ttu-id="c75ef-189">管道设计器之前调用此方法以验证正确设置所有配置属性的管道编译。</span><span class="sxs-lookup"><span data-stu-id="c75ef-189">Pipeline Designer calls this method before pipeline compilation to verify that all the configuration properties are set correctly.</span></span>|  
  
 <span data-ttu-id="c75ef-190">**图标**属性将返回**IntPtr**。</span><span class="sxs-lookup"><span data-stu-id="c75ef-190">The **Icon** property returns an **IntPtr**.</span></span> <span data-ttu-id="c75ef-191">以下C#的示例演示如何返回**IntPtr**。</span><span class="sxs-lookup"><span data-stu-id="c75ef-191">The following C# example shows how to return an **IntPtr**.</span></span>  
  
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
  
 <span data-ttu-id="c75ef-192">有关详细信息，请参阅**IComponentUI 接口 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c75ef-192">For more information, see **IComponentUI Interface (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c75ef-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="c75ef-193">See Also</span></span>  
 <span data-ttu-id="c75ef-194">[开发自定义管道组件](../core/developing-custom-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c75ef-194">[Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md) </span></span>  
 [<span data-ttu-id="c75ef-195">CustomComponent（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c75ef-195">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)