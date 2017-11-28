---
title: "ESB 添加 Namespace 和删除 Namespace 组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21df1b21-b73c-4e31-a234-49a1a6b53cc7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bcbe519cfd8c6796569da4de87f59fa6a16d8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a><span data-ttu-id="db0d8-102">ESB 添加 Namespace 和删除 Namespace 组件</span><span class="sxs-lookup"><span data-stu-id="db0d8-102">The ESB Add Namespace and Remove Namespace Components</span></span>
<span data-ttu-id="db0d8-103">许多公司已在时间仍已新兴标准，文档共享已不常见的 XML 技术的早期采用者。</span><span class="sxs-lookup"><span data-stu-id="db0d8-103">Many companies were early adopters of XML technologies at the time when standards were still emerging and document sharing was uncommon.</span></span> <span data-ttu-id="db0d8-104">因此，它们未不严格强制包括唯一的根命名空间，这通常这种情况今天的要求。</span><span class="sxs-lookup"><span data-stu-id="db0d8-104">Therefore, they did not strictly enforce the requirements for including unique root namespaces, which is usually the case today.</span></span>  
  
 <span data-ttu-id="db0d8-105">但是，Microsoft BizTalk Server 执行文档标识基于的根节点命名空间和根节点名称的组合，因此根节点没有命名空间的文档难以正确标识如果多个不同的文档类型使用的相同的根节点名称。</span><span class="sxs-lookup"><span data-stu-id="db0d8-105">However, Microsoft BizTalk Server performs document identification based on a combination of the root node namespace and the root node name, so documents that have no namespace for the root node are difficult to positively identify if several different document types use the same root node name.</span></span>  
  
 <span data-ttu-id="db0d8-106">添加 Namespace 和删除 Namespace 组件通过使其能够在到达时向文档中添加命名空间以及能够从文档中删除命名空间，然后将他们传送解决此问题。</span><span class="sxs-lookup"><span data-stu-id="db0d8-106">The Add Namespace and Remove Namespace components solve this problem by making it possible to add namespaces to documents when they are received and to remove the namespace from the documents before they are delivered.</span></span> <span data-ttu-id="db0d8-107">因此，文档可以位于默认命名空间中 （或共有多种不同的文档类型的命名空间中） 时发送和接收但位于暂时性唯一的根命名空间中的 ESB 和 BizTalk 中的处理过程。</span><span class="sxs-lookup"><span data-stu-id="db0d8-107">Therefore, documents can reside in the default namespace (or in a namespace common to several different document types) when they are sent and received but reside in a transient unique root namespace during processing within the ESB and BizTalk.</span></span>  
  
 <span data-ttu-id="db0d8-108">组件也是有用的集成，而不是 XML 架构定义中使用文档类型定义 (DTD) 或使用不能创建包含的根命名空间的文档的旧 XML 分析器的旧系统时。</span><span class="sxs-lookup"><span data-stu-id="db0d8-108">The components are also useful when integrating legacy systems that use a Document Type Definition (DTD) instead of an XML Schema definition or that use legacy XML parsers that cannot create documents that contain a root namespace.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="db0d8-109">安装</span><span class="sxs-lookup"><span data-stu-id="db0d8-109">Installation</span></span>  
 <span data-ttu-id="db0d8-110">自动安装 ESB 核心安装**添加 Namespace**和**删除 Namespace** BizTalk Server 管道组件文件夹中的组件。</span><span class="sxs-lookup"><span data-stu-id="db0d8-110">Installing the ESB Core automatically installs the **Add Namespace** and **Remove Namespace** components in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="db0d8-111">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="db0d8-111">How It Works</span></span>  
 <span data-ttu-id="db0d8-112">添加 Namespace 组件将指定的命名空间添加到 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="db0d8-112">The Add Namespace component adds a specified namespace to an XML document.</span></span> <span data-ttu-id="db0d8-113">组件可以将单个命名空间添加到文档。</span><span class="sxs-lookup"><span data-stu-id="db0d8-113">The component can add only a single namespace to a document.</span></span> <span data-ttu-id="db0d8-114">在已有的根节点命名空间的文档中使用添加 Namespace 组件不受支持的方案，因为单个唯一的命名空间是所有所需。</span><span class="sxs-lookup"><span data-stu-id="db0d8-114">Using the Add Namespace component on a document that already has a root node namespace is not a supported scenario because a single unique namespace is all that is required.</span></span>  
  
 <span data-ttu-id="db0d8-115">组件是不识别命名空间，并且不会保留的任何命名空间值。</span><span class="sxs-lookup"><span data-stu-id="db0d8-115">The components are not namespace-aware and do not persist any of the namespace values.</span></span> <span data-ttu-id="db0d8-116">但是，添加 Namespace 组件将请求的消息的现有命名空间中的命名空间进行比较，并只是返回到管道原始消息，如果它们匹配。</span><span class="sxs-lookup"><span data-stu-id="db0d8-116">However, the Add Namespace component compares the requested namespace in the existing namespace of the message and simply returns the original message to the pipeline if they match.</span></span>  
  
 <span data-ttu-id="db0d8-117">开发人员将添加 Namespace 组件包括在接收管道或发送管道，并设置适当的属性。</span><span class="sxs-lookup"><span data-stu-id="db0d8-117">Developers include the Add Namespace component in a receive pipeline or a send pipeline and set the appropriate properties.</span></span> <span data-ttu-id="db0d8-118">在运行时执行以下验证：</span><span class="sxs-lookup"><span data-stu-id="db0d8-118">The following validation is performed at run time:</span></span>  
  
-   <span data-ttu-id="db0d8-119">**Xpath**属性或**NamespaceBase**属性必须包含一个值。</span><span class="sxs-lookup"><span data-stu-id="db0d8-119">The **XPaths** property or the **NamespaceBase** property must contain a value.</span></span>  
  
-   <span data-ttu-id="db0d8-120">**分隔符**属性只能包含有效字符 (如 **/** 或 **\\** ) 或空字符串。</span><span class="sxs-lookup"><span data-stu-id="db0d8-120">The **Separator** property can contain only valid characters (such as **/** or **\\**) or an empty string.</span></span>  
  
-   <span data-ttu-id="db0d8-121">**NamespacePrefix**属性值不能是保留的值之一 (**ns0**到**ns6**) 并且必须是字母数字。</span><span class="sxs-lookup"><span data-stu-id="db0d8-121">The **NamespacePrefix** property value cannot be one of the reserved values (**ns0** to **ns6**) and must be alpha numeric.</span></span>  
  
 <span data-ttu-id="db0d8-122">利用这些规则的任何变体导致要引发运行时异常时，挂起消息的组件 (标记为**挂起 – 可恢复**)，并写入 Windows 应用程序事件日志中的条目。</span><span class="sxs-lookup"><span data-stu-id="db0d8-122">Any variation from these rules causes the component to throw an exception at run time, suspend the message (marked as **Suspended – Resumable**), and write an entry in Windows Application Event Log.</span></span>  
  
 <span data-ttu-id="db0d8-123">删除 Namespace 组件从 XML 文档中移除所有的根命名空间。</span><span class="sxs-lookup"><span data-stu-id="db0d8-123">The Remove Namespace component removes all root namespaces from an XML document.</span></span> <span data-ttu-id="db0d8-124">该组件，可移除单个文档的命名空间的数量受可用于在处理过程中保存当前节点的物理内存的约束。</span><span class="sxs-lookup"><span data-stu-id="db0d8-124">The number of namespaces that the component can remove from a single document is constrained by the physical memory available to hold the current node during processing.</span></span> <span data-ttu-id="db0d8-125">但是，该组件使用标准的 BizTalk Server 2009 管道消息流式处理进程，并且将仅在文档中的当前节点加载到内存而不是加载整个文档。</span><span class="sxs-lookup"><span data-stu-id="db0d8-125">However, the component uses standard BizTalk Server 2009 pipeline message streaming processes and loads only the current node in the document into memory instead of loading the entire document.</span></span>  
  
 <span data-ttu-id="db0d8-126">删除 Namespace 组件还重新会编码到指定的编码的文档 (**ascii、 unicode/utf16**或**utf8**)，并可以删除字节顺序标记 (BOM) 从开始处流，如果必填。</span><span class="sxs-lookup"><span data-stu-id="db0d8-126">The Remove Namespace component also re-encodes the document to the specified encoding (**ascii, unicode/utf16,** or **utf8**) and can remove the Byte Order Mark (BOM) from the beginning of the stream, if required.</span></span>  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a><span data-ttu-id="db0d8-127">使用添加 Namespace 和删除 Namespace 组件</span><span class="sxs-lookup"><span data-stu-id="db0d8-127">Using the Add Namespace and Remove Namespace Components</span></span>  
 <span data-ttu-id="db0d8-128">在任何以下情况下，开发人员可以使用添加 Namespace 组件：</span><span class="sxs-lookup"><span data-stu-id="db0d8-128">Developers might use the Add Namespace component in any of the following circumstances:</span></span>  
  
-   <span data-ttu-id="db0d8-129">入站的消息具有没有根命名空间。</span><span class="sxs-lookup"><span data-stu-id="db0d8-129">The inbound message has no root namespace.</span></span>  
  
-   <span data-ttu-id="db0d8-130">入站的消息使用元素数据或属性数据来描述消息类型。</span><span class="sxs-lookup"><span data-stu-id="db0d8-130">The inbound message uses element data or attribute data to describe the message type.</span></span>  
  
-   <span data-ttu-id="db0d8-131">描述消息类型的数据将一致，可使用 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="db0d8-131">The data describing the message type is consistent and available using XPath queries.</span></span>  
  
 <span data-ttu-id="db0d8-132">添加 Namespace 和删除 Namespace 组件可以驻留在任何阶段接收管道或发送管道。</span><span class="sxs-lookup"><span data-stu-id="db0d8-132">The Add Namespace and Remove Namespace components can reside in any stage of a receive pipeline or a send pipeline.</span></span> <span data-ttu-id="db0d8-133">你可以链接组件必要情况下，如就像使用跟添加 Namespace 组件删除 Namespace 组件来更改文档的根命名空间的实例。</span><span class="sxs-lookup"><span data-stu-id="db0d8-133">You can chain instances of the component if required, such as if you are using the Remove Namespace component followed by the Add Namespace component to change the root namespace of a document.</span></span>  
  
 <span data-ttu-id="db0d8-134">如果你有多个接收需要的这些组件使用的位置，你可以创建单个管道，并使用 BizTalk Server 组件配置设置的发送每个实例的组件属性，或接收管道"每个实例"。</span><span class="sxs-lookup"><span data-stu-id="db0d8-134">If you have multiple receive locations that require the use of these components, you can create a single pipeline and use the BizTalk Server "per instance" component configuration to set the component properties for each instance of the send or receive pipeline.</span></span> <span data-ttu-id="db0d8-135">使用 BizTalk Server 2009，您可以设置属性管道为每个实例运行，这意味着，你可以重用单个管道，在多个接收位置，并且可能有每个实例的不同的组件属性。</span><span class="sxs-lookup"><span data-stu-id="db0d8-135">Using BizTalk Server 2009, you can set properties on a per-instance basis for pipelines, which means that you can reuse a single pipeline across multiple receive locations and perhaps have different component properties for each instance.</span></span> <span data-ttu-id="db0d8-136">这是运行时设置，使管理员能够进行无需更改代码或重新部署中使用 BizTalk Server 管理控制台的更改。</span><span class="sxs-lookup"><span data-stu-id="db0d8-136">This is a run-time setting that allows administrators to make the change using the BizTalk Server Administration Console without requiring changes to the code or redeployment.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="db0d8-137">组件属性</span><span class="sxs-lookup"><span data-stu-id="db0d8-137">Component Properties</span></span>  
 <span data-ttu-id="db0d8-138">添加 Namespace 组件公开五个公共属性：</span><span class="sxs-lookup"><span data-stu-id="db0d8-138">The Add Namespace component exposes five public properties:</span></span>  
  
-   <span data-ttu-id="db0d8-139">**NamespacePrefix**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-139">**NamespacePrefix**.</span></span> <span data-ttu-id="db0d8-140">此为前缀的命名空间，之间插入**xmlns:**部分，并在以下等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="db0d8-140">This is the prefix of the namespace, inserted between the **xmlns:** part and the following equals sign ( = ).</span></span> <span data-ttu-id="db0d8-141">若要避免与标准 BizTalk 架构命名空间前缀的冲突，应避免使用值**ns0**通过**ns9**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-141">To avoid conflicts with standard BizTalk Schema namespace prefixes, avoid using the values **ns0** through **ns9**.</span></span>  
  
-   <span data-ttu-id="db0d8-142">**NamespaceBase**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-142">**NamespaceBase**.</span></span> <span data-ttu-id="db0d8-143">这是将前缀中的值生成的结果的命名空间的静态部分**分隔符**和**Xpath**属性。</span><span class="sxs-lookup"><span data-stu-id="db0d8-143">This is the static section of the namespace that will prefix the result generated by the values in the **Separator** and **XPaths** properties.</span></span>  
  
-   <span data-ttu-id="db0d8-144">**ExtractionNodeXPath**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-144">**ExtractionNodeXPath**.</span></span> <span data-ttu-id="db0d8-145">这是可解析为包含你想要的命名空间的生成部分使用的元素或属性值的文档中的单个元素的 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="db0d8-145">This is an XPath statement that resolves to a single element in the document that contains the element or attribute values you want to use for the generated parts of the namespace.</span></span>  
  
-   <span data-ttu-id="db0d8-146">**Xpath**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-146">**XPaths**.</span></span> <span data-ttu-id="db0d8-147">这是一种管道 (**&#124;** ) 分隔的 XPath 查询用于提取每个组合到一起以形成命名空间的组件列表。</span><span class="sxs-lookup"><span data-stu-id="db0d8-147">This is a pipe (**&#124;** ) delimited list of XPath queries used to extract each of the components that will combine to form the namespace.</span></span>  
  
-   <span data-ttu-id="db0d8-148">**分隔符**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-148">**Separator**.</span></span> <span data-ttu-id="db0d8-149">这是要使用的命名空间段之间的分隔符。</span><span class="sxs-lookup"><span data-stu-id="db0d8-149">This is the separator to use between the namespace segments.</span></span> <span data-ttu-id="db0d8-150">最常用的值为正斜杠 ( **/**  )，但如果需要，也可以是一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="db0d8-150">The most common value is a forward slash (**/** ), but it can be an empty string, if required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db0d8-151">所有的 XML 节点，如元素和属性名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="db0d8-151">All XML nodes, such as element and attribute names, are case sensitive.</span></span>  
  
 <span data-ttu-id="db0d8-152">删除 Namespace 组件公开两个公共属性：</span><span class="sxs-lookup"><span data-stu-id="db0d8-152">The Remove Namespace component exposes two public properties:</span></span>  
  
-   <span data-ttu-id="db0d8-153">**编码**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-153">**Encoding**.</span></span> <span data-ttu-id="db0d8-154">这是输出消息，下列值之一的编码： **ascii、 unicode/utf16**或**utf8**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-154">This is the encoding for the output message, one of the following values: **ascii, unicode/utf16,** or **utf8**.</span></span>  
  
-   <span data-ttu-id="db0d8-155">**RemoveByteOrderMark**。</span><span class="sxs-lookup"><span data-stu-id="db0d8-155">**RemoveByteOrderMark**.</span></span> <span data-ttu-id="db0d8-156">这是布尔值属性，该值指示组件是否应删除的字节顺序标记 (通常**0xEFBB、 0xBFFFFE，**或**0xFEFF**) 从 XML 文档流的开始位置。</span><span class="sxs-lookup"><span data-stu-id="db0d8-156">This is a Boolean property that indicates whether the component should remove the byte order mark (usually **0xEFBB, 0xBFFFFE,** or **0xFEFF**) from the beginning of the XML document stream.</span></span>  
  
 <span data-ttu-id="db0d8-157">有关如何使用这些组件的示例，请参阅[安装和运行 Namespace 组件示例](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="db0d8-157">For an example of how to use these components, see [Installing and Running the Namespace Component Sample](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).</span></span>