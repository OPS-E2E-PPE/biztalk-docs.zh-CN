---
title: "XML 反汇编程序管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3346cdbfeed14e933039d7866e174c833f17212e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-pipeline-component"></a><span data-ttu-id="103b5-102">XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="103b5-102">XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="103b5-103">XML 拆装器管道组件将 XML 解析功能和拆装功能组合到一个组件中。</span><span class="sxs-lookup"><span data-stu-id="103b5-103">The XML Disassembler pipeline component combines XML parsing and disassembling into one component.</span></span> <span data-ttu-id="103b5-104">该组件的主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="103b5-104">Its primary functions are:</span></span>  
  
-   <span data-ttu-id="103b5-105">删除信封。</span><span class="sxs-lookup"><span data-stu-id="103b5-105">Removing envelopes.</span></span>  
  
-   <span data-ttu-id="103b5-106">对交换进行拆装。</span><span class="sxs-lookup"><span data-stu-id="103b5-106">Disassembling the interchange.</span></span>  
  
-   <span data-ttu-id="103b5-107">将内容属性从交换级别和单个文档级别升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="103b5-107">Promoting the content properties from interchange and individual document levels on to the message context.</span></span>  
  
 <span data-ttu-id="103b5-108">收到信封后，在 XML 拆装器组件中将发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="103b5-108">The following actions occur in the XML Disassembler component after receiving an envelope:</span></span>  
  
1.  <span data-ttu-id="103b5-109">该拆装器通过使用在设计时与该组件关联的信封架构来静态地解析信封，或通过在运行时根据消息类型确定信封架构来动态地解析信封。</span><span class="sxs-lookup"><span data-stu-id="103b5-109">The disassembler parses the envelope by using the envelope schemas statically associated with the component at design time or dynamically by determining envelope schemas from the message type at run time.</span></span> <span data-ttu-id="103b5-110">架构用于在信封解析过程中对信封的结构进行验证。</span><span class="sxs-lookup"><span data-stu-id="103b5-110">The schema is used to verify the structure of the envelope during envelope parsing.</span></span> <span data-ttu-id="103b5-111">如果未定义信封结构，则可通过使用根节点的命名空间和基名称查找架构，从而以递归方式确定信封结构。</span><span class="sxs-lookup"><span data-stu-id="103b5-111">If envelope structure is not defined, it is found recursively by using the root node's namespace and base name to look up the schemas.</span></span>  
  
2.  <span data-ttu-id="103b5-112">该拆装器组件将对信封内的每个文档进行解析。</span><span class="sxs-lookup"><span data-stu-id="103b5-112">The disassembler component parses each document within the envelope.</span></span> <span data-ttu-id="103b5-113">对于每个文档，BizTalk 消息对象都使用其本身的上下文创建，从信封和文档本身升级的所有属性均是从此上下文中复制而来。</span><span class="sxs-lookup"><span data-stu-id="103b5-113">For each document, the BizTalk message object is created with its own context where all the properties promoted from the envelope and from the document itself get copied.</span></span> <span data-ttu-id="103b5-114">该组件通过使用预定义的 XPath（编码为与信封和消息相关联的 XSD 架构中的批注）从信封和消息实例中提取内容属性。</span><span class="sxs-lookup"><span data-stu-id="103b5-114">The component pulls the content properties from the envelope and message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the envelope and message.</span></span> <span data-ttu-id="103b5-115">信封架构以及各文档架构均与管道设计器中的拆装器组件关联。</span><span class="sxs-lookup"><span data-stu-id="103b5-115">The envelope schemas as well as the individual document schemas are associated with the disassembler component in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="103b5-116">XML 拆装器只处理消息正文部分中的数据。</span><span class="sxs-lookup"><span data-stu-id="103b5-116">The XML Disassembler only processes data in the body part of the message.</span></span> <span data-ttu-id="103b5-117">因此，只有正文部分的属性可以升级。</span><span class="sxs-lookup"><span data-stu-id="103b5-117">Thus, only properties from body part can be promoted.</span></span> <span data-ttu-id="103b5-118">升级属性时，与可升级属性关联的字段中的日期时间值将转换为 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="103b5-118">Datetime values from the fields associated with the promotable properties get converted to UTC when property promotion occurs.</span></span> <span data-ttu-id="103b5-119">非正文部分将不做更改直接复制到输出消息。</span><span class="sxs-lookup"><span data-stu-id="103b5-119">Non-body parts are copied to the output message unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="103b5-120">目前，XML 拆装器管道组件在日期时间属性到达消息库前将所有日期时间属性强制转换为 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="103b5-120">The XML Disassembler pipeline component currently forces conversion of all datetime properties to UTC before they reach the message store.</span></span> <span data-ttu-id="103b5-121">BizTalk Server 在内部使用不包含时区信息的 SQL 日期时间类型。</span><span class="sxs-lookup"><span data-stu-id="103b5-121">BizTalk Server uses an SQL datetime type internally, which does not have information about the time zone.</span></span> <span data-ttu-id="103b5-122">如果在业务流程中生成一个日期时间属性，然后尝试使用该属性以便与后续消息相关，则该属性可能无法正常工作，因为 XML 拆装器管道组件会在响应时将其转换为 UTC 格式，而 Microsoft SQL Server 却无法将原始时间字段和响应时间字段识别为相同字段。</span><span class="sxs-lookup"><span data-stu-id="103b5-122">If you generate a datetime property in an orchestration, and then try to use it for correlation with subsequent messages, it may not work correctly, because the XML Disassembler pipeline component will convert it on response into UTC, and Microsoft SQL Server will have no way to identify the original and response time fields as identical.</span></span> <span data-ttu-id="103b5-123">同样，查看消息事件和服务实例跟踪数据时，也可能会遇到差异。</span><span class="sxs-lookup"><span data-stu-id="103b5-123">Similarly, you may encounter discrepancies when viewing message event and service instance tracking data.</span></span>  
  
 <span data-ttu-id="103b5-124">有关配置 XML 反汇编程序管道组件的信息，请参阅[如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="103b5-124">For information about configuring the XML Disassembler pipeline component, see [How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="103b5-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="103b5-125">In This Section</span></span>  
  
-   [<span data-ttu-id="103b5-126">XML 信息集 XML 反汇编程序管道组件中的元素</span><span class="sxs-lookup"><span data-stu-id="103b5-126">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="103b5-127">无法识别的消息中 XML 反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="103b5-127">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="103b5-128">XML 反汇编程序管道组件中的文档验证</span><span class="sxs-lookup"><span data-stu-id="103b5-128">Document Validation in the XML Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="103b5-129">XML 反汇编程序管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="103b5-129">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="103b5-130">XML 反汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="103b5-130">Character Encoding in XML Disassembler Pipeline Component</span></span>](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="103b5-131">演练： 使用 XML 信封 (Basic)</span><span class="sxs-lookup"><span data-stu-id="103b5-131">Walkthrough: Using XML Envelopes (Basic)</span></span>](../core/walkthrough-using-xml-envelopes-basic.md)