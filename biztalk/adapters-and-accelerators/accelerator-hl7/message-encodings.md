---
title: 消息编码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36063416e1c5d1f30c9cb9c26056299f0b926a50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204789"
---
# <a name="message-encodings"></a><span data-ttu-id="df3cb-102">消息编码</span><span class="sxs-lookup"><span data-stu-id="df3cb-102">Message Encodings</span></span>
<span data-ttu-id="df3cb-103">不满足需求，以定义顺序有用的 HL7 消息语义。</span><span class="sxs-lookup"><span data-stu-id="df3cb-103">It is not sufficient to define message semantics in order for HL7 to be useful.</span></span> <span data-ttu-id="df3cb-104">一旦已确定消息内容，标准将具有以解释如何表示实际接口中的该内容。</span><span class="sxs-lookup"><span data-stu-id="df3cb-104">Once message content has been determined, the standard has to explain how to represent that content in an actual interface.</span></span> <span data-ttu-id="df3cb-105">也就是说，必须有指定"消息编码"。</span><span class="sxs-lookup"><span data-stu-id="df3cb-105">That is to say, there must be a specified "message encoding".</span></span> <span data-ttu-id="df3cb-106">HL7 版本 2 支持两种形式的消息编码、 自定义基于分隔符的编码，和的 XML 编码。</span><span class="sxs-lookup"><span data-stu-id="df3cb-106">HL7 Version 2 supports two forms of message encoding, a custom delimiter-based encoding, and an XML encoding.</span></span>  
  
 <span data-ttu-id="df3cb-107">HL7 选择原始基于分隔符的编码，从而减少的尽可能多的消息的大小。</span><span class="sxs-lookup"><span data-stu-id="df3cb-107">HL7 chose the original delimiter-based encoding to reduce the size of messages as much as possible.</span></span> <span data-ttu-id="df3cb-108">例如，如果比较顺序分隔符分隔到结构，它定位在一组固定的位置中的每个元素的元素的数据结构，基于分隔符的结构是更经济，如果 a） 消息不包含一些元素和 b） 某些元素不能填充所有允许的空间。</span><span class="sxs-lookup"><span data-stu-id="df3cb-108">For example, if you compare a data structure in which delimiters separate elements to a structure that positions each element in a fixed set of positions, the delimiter-based structure is far more economical if a) messages do not contain some elements, and b) some elements do not fill all the space allowed.</span></span> <span data-ttu-id="df3cb-109">基于分隔符的结构的唯一系统开销是本身的分隔符。</span><span class="sxs-lookup"><span data-stu-id="df3cb-109">The only overhead in delimiter-based structures is the delimiters themselves.</span></span>  
  
 <span data-ttu-id="df3cb-110">原始的 HL7 编码定义每个消息声明 MSH 段内的五个分隔符。</span><span class="sxs-lookup"><span data-stu-id="df3cb-110">The original HL7 encoding defines five delimiters, which each message declares within the MSH segment.</span></span> <span data-ttu-id="df3cb-111">这些警报表示：</span><span class="sxs-lookup"><span data-stu-id="df3cb-111">These indicate:</span></span>  
  
-   <span data-ttu-id="df3cb-112">段</span><span class="sxs-lookup"><span data-stu-id="df3cb-112">Segments</span></span>  
  
-   <span data-ttu-id="df3cb-113">字段</span><span class="sxs-lookup"><span data-stu-id="df3cb-113">Fields</span></span>  
  
-   <span data-ttu-id="df3cb-114">Components</span><span class="sxs-lookup"><span data-stu-id="df3cb-114">Components</span></span>  
  
-   <span data-ttu-id="df3cb-115">子组件</span><span class="sxs-lookup"><span data-stu-id="df3cb-115">Subcomponents</span></span>  
  
-   <span data-ttu-id="df3cb-116">（的字段、 组件或子组件） 重复</span><span class="sxs-lookup"><span data-stu-id="df3cb-116">Repetition (of a field, component, or subcomponent)</span></span>  
  
 <span data-ttu-id="df3cb-117">请注意，由于分隔符的编码的一个基本方面，你必须定义其第一次。</span><span class="sxs-lookup"><span data-stu-id="df3cb-117">Note that since delimiters are a fundamental aspect of the encoding, you must define them first.</span></span> <span data-ttu-id="df3cb-118">一个操作的结果不是可以是任何子子分隔符。</span><span class="sxs-lookup"><span data-stu-id="df3cb-118">One result of this is that there can be no sub-sub-delimiter.</span></span> <span data-ttu-id="df3cb-119">有时，此限制已在新的数据类型的设计时面对效果。</span><span class="sxs-lookup"><span data-stu-id="df3cb-119">At times, this limitation has unfortunate effects upon the design of new data types.</span></span>  
  
 <span data-ttu-id="df3cb-120">在 2003 年 6 月 HL7 发布 HL7 版本 2、 编码的 XML 语法、 发行版 1。</span><span class="sxs-lookup"><span data-stu-id="df3cb-120">In June 2003, HL7 published HL7 Version 2, XML Encoding Syntax, Release 1.</span></span> <span data-ttu-id="df3cb-121">此标准定义备用的编码规则，用以 HL7 版本 2.3.1 和 2.4 消息，并提供用于确定后续 HL7 备选的编码规则的机制 2.X 版本。</span><span class="sxs-lookup"><span data-stu-id="df3cb-121">This standard defines alternate encoding rules for HL7 Version 2.3.1 and 2.4 messages, and provides a mechanism for determining alternate encoding rules for subsequent HL7 2.X versions.</span></span> <span data-ttu-id="df3cb-122">实质上，此新的标准版本 2.3.1 和 V2.4 抽象的消息、 段、 字段和数据类型定义 XML 元素标记，并创建用于定义所需的标准为版本 2 的后续版本创建的任何新结构的标记的规则。</span><span class="sxs-lookup"><span data-stu-id="df3cb-122">In essence, this new standard defines XML element tags for the Version 2.3.1 and V2.4 abstract messages, segments, fields, and data types, and creates rules for defining the tags needed for any new structures created for subsequent versions of the Version 2 standard.</span></span> <span data-ttu-id="df3cb-123">定义此标准的过程会导致一系列版本 2.4 和 2.5 中的改进。</span><span class="sxs-lookup"><span data-stu-id="df3cb-123">The process of defining this standard led to a series of improvements in versions 2.4 and 2.5.</span></span> <span data-ttu-id="df3cb-124">发生此情况由于创建 XML 标记导致需要解决基础标准中的某些种长期存在多义性。</span><span class="sxs-lookup"><span data-stu-id="df3cb-124">This happened because creation of XML tags led to the need to address some longstanding ambiguities in the underlying standard.</span></span> <span data-ttu-id="df3cb-125">As a result，创建 a） 定义完善的消息结构代码以指示抽象触发事件，b） 重复的段与抽象的消息的组已正式标识和指定，与关联的消息中的变体和 c) 本地定义的数据类型，CM 已替换为更具体的类型。</span><span class="sxs-lookup"><span data-stu-id="df3cb-125">As a result, a) well-defined message structure codes were created to indicate variations in the abstract messages associated with trigger events, b) repeating groups of segments with an abstract message were formally identified and named, and c) the locally defined data type, CM was replaced with more specific types.</span></span>  
  
 <span data-ttu-id="df3cb-126">例如，下面是使用传统管道分隔格式的简单的确认消息：</span><span class="sxs-lookup"><span data-stu-id="df3cb-126">For example, the following is a simple acknowledgment message using the traditional pipe delimited format:</span></span>  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 <span data-ttu-id="df3cb-127">与此相反，下面是表示为 XML 文档，同一消息：</span><span class="sxs-lookup"><span data-stu-id="df3cb-127">By contrast, the following is the same message represented as an XML document:</span></span>  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 <span data-ttu-id="df3cb-128">下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="df3cb-128">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="df3cb-129">分隔的管道和 XML 编码的支持。</span><span class="sxs-lookup"><span data-stu-id="df3cb-129">Support of pipe delimited and XML encoding.</span></span>  
  
-   <span data-ttu-id="df3cb-130">支持 XML 和管道之间的转换分隔编码。</span><span class="sxs-lookup"><span data-stu-id="df3cb-130">Support of translation between XML and pipe delimited encodings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3cb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df3cb-131">See Also</span></span>  
 <span data-ttu-id="df3cb-132">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="df3cb-132">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="df3cb-133">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="df3cb-133">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="df3cb-134">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="df3cb-134">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)