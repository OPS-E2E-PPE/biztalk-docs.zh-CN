---
title: XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 634d007e2545dfd89457239fe4d05f86a1c90aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246379"
---
# <a name="xml-disassembler-pipeline-component"></a><span data-ttu-id="b386f-102">XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="b386f-102">XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="b386f-103">XML 拆装器管道组件将 XML 解析功能和拆装到一个组件相结合。</span><span class="sxs-lookup"><span data-stu-id="b386f-103">The XML Disassembler pipeline component combines XML parsing and disassembling into one component.</span></span> <span data-ttu-id="b386f-104">其主要功能如下：</span><span class="sxs-lookup"><span data-stu-id="b386f-104">Its primary functions are:</span></span>  
  
- <span data-ttu-id="b386f-105">删除信封。</span><span class="sxs-lookup"><span data-stu-id="b386f-105">Removing envelopes.</span></span>  
  
- <span data-ttu-id="b386f-106">对交换进行拆装。</span><span class="sxs-lookup"><span data-stu-id="b386f-106">Disassembling the interchange.</span></span>  
  
- <span data-ttu-id="b386f-107">升级的内容属性从交换级别和单个文档级别到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="b386f-107">Promoting the content properties from interchange and individual document levels on to the message context.</span></span>  
  
  <span data-ttu-id="b386f-108">收到信封后，XML 拆装器组件执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b386f-108">The following actions occur in the XML Disassembler component after receiving an envelope:</span></span>  
  
1. <span data-ttu-id="b386f-109">使用以静态方式在设计时与组件关联的信封架构或动态确定在运行时从消息类型的信封架构，拆装器将对信封。</span><span class="sxs-lookup"><span data-stu-id="b386f-109">The disassembler parses the envelope by using the envelope schemas statically associated with the component at design time or dynamically by determining envelope schemas from the message type at run time.</span></span> <span data-ttu-id="b386f-110">架构用于验证在信封解析过程的信封的结构。</span><span class="sxs-lookup"><span data-stu-id="b386f-110">The schema is used to verify the structure of the envelope during envelope parsing.</span></span> <span data-ttu-id="b386f-111">如果未定义信封结构，它以递归方式找到通过使用根节点的命名空间和基名称查找架构。</span><span class="sxs-lookup"><span data-stu-id="b386f-111">If envelope structure is not defined, it is found recursively by using the root node's namespace and base name to look up the schemas.</span></span>  
  
2. <span data-ttu-id="b386f-112">拆装器组件将分析对信封内的每个文档。</span><span class="sxs-lookup"><span data-stu-id="b386f-112">The disassembler component parses each document within the envelope.</span></span> <span data-ttu-id="b386f-113">对于每个文档，使用它自己获取复制升级从信封和文档本身的所有属性创建 BizTalk 消息对象。</span><span class="sxs-lookup"><span data-stu-id="b386f-113">For each document, the BizTalk message object is created with its own context where all the properties promoted from the envelope and from the document itself get copied.</span></span> <span data-ttu-id="b386f-114">该组件通过使用预定义的 Xpath 编码为与信封和消息相关联的 XSD 架构中的批注中提取内容属性从信封和消息实例。</span><span class="sxs-lookup"><span data-stu-id="b386f-114">The component pulls the content properties from the envelope and message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the envelope and message.</span></span> <span data-ttu-id="b386f-115">信封架构，以及各文档架构相关联在管道设计器中的拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="b386f-115">The envelope schemas as well as the individual document schemas are associated with the disassembler component in Pipeline Designer.</span></span>  
  
   <span data-ttu-id="b386f-116">XML 拆装器只处理消息的正文部分中的数据。</span><span class="sxs-lookup"><span data-stu-id="b386f-116">The XML Disassembler only processes data in the body part of the message.</span></span> <span data-ttu-id="b386f-117">因此，可以升级仅从正文部分的属性。</span><span class="sxs-lookup"><span data-stu-id="b386f-117">Thus, only properties from body part can be promoted.</span></span> <span data-ttu-id="b386f-118">升级属性时，使用可提升的属性关联的字段中的日期时间值获取转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="b386f-118">Datetime values from the fields associated with the promotable properties get converted to UTC when property promotion occurs.</span></span> <span data-ttu-id="b386f-119">非正文部分将复制到输出消息保持不变。</span><span class="sxs-lookup"><span data-stu-id="b386f-119">Non-body parts are copied to the output message unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b386f-120">XML 拆装器管道组件当前强制转换为 UTC 的所有日期时间属性到达消息库之前。</span><span class="sxs-lookup"><span data-stu-id="b386f-120">The XML Disassembler pipeline component currently forces conversion of all datetime properties to UTC before they reach the message store.</span></span> <span data-ttu-id="b386f-121">BizTalk Server 使用 SQL 日期时间类型在内部，而不一定时间区域相关信息。</span><span class="sxs-lookup"><span data-stu-id="b386f-121">BizTalk Server uses an SQL datetime type internally, which does not have information about the time zone.</span></span> <span data-ttu-id="b386f-122">如果在业务流程中生成的日期时间属性，然后尝试将其用于与后续消息相关，它可能无法正常工作，因为 XML 拆装器管道组件将其转换为响应 UTC，并将 Microsoft SQL Server有没有办法识别为相同的原始和响应时间字段。</span><span class="sxs-lookup"><span data-stu-id="b386f-122">If you generate a datetime property in an orchestration, and then try to use it for correlation with subsequent messages, it may not work correctly, because the XML Disassembler pipeline component will convert it on response into UTC, and Microsoft SQL Server will have no way to identify the original and response time fields as identical.</span></span> <span data-ttu-id="b386f-123">同样，查看消息事件和服务实例跟踪数据时可能会遇到差异。</span><span class="sxs-lookup"><span data-stu-id="b386f-123">Similarly, you may encounter discrepancies when viewing message event and service instance tracking data.</span></span>  
  
 <span data-ttu-id="b386f-124">有关配置 XML 拆装器管道组件的信息，请参阅[如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="b386f-124">For information about configuring the XML Disassembler pipeline component, see [How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b386f-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="b386f-125">In This Section</span></span>  
  
-   [<span data-ttu-id="b386f-126">XML 反汇编程序管道组件中的 XML 信息集合元素</span><span class="sxs-lookup"><span data-stu-id="b386f-126">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b386f-127">XML 反汇编程序管道组件中无法识别的消息</span><span class="sxs-lookup"><span data-stu-id="b386f-127">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b386f-128">XML 反汇编程序管道组件中的文档验证</span><span class="sxs-lookup"><span data-stu-id="b386f-128">Document Validation in the XML Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b386f-129">XML 反汇编程序管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="b386f-129">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b386f-130">XML 反汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="b386f-130">Character Encoding in XML Disassembler Pipeline Component</span></span>](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b386f-131">演练：使用 XML 信封 （基础）</span><span class="sxs-lookup"><span data-stu-id="b386f-131">Walkthrough: Using XML Envelopes (Basic)</span></span>](../core/walkthrough-using-xml-envelopes-basic.md)