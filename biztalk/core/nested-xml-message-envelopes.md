---
title: 嵌套 XML 消息信封 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263837"
---
# <a name="nested-xml-message-envelopes"></a><span data-ttu-id="c6260-102">嵌套 XML 消息信封</span><span class="sxs-lookup"><span data-stu-id="c6260-102">Nested XML Message Envelopes</span></span>
<span data-ttu-id="c6260-103">可以嵌套 XML 信封以创建复杂的文档结构。</span><span class="sxs-lookup"><span data-stu-id="c6260-103">XML envelopes can be nested to create complex document structures.</span></span> <span data-ttu-id="c6260-104">嵌套的 XML 信封可以有两种格式（灵活格式和规范格式）。</span><span class="sxs-lookup"><span data-stu-id="c6260-104">Nested XML envelopes can occur in two forms, known as flexible and canonical.</span></span> <span data-ttu-id="c6260-105">以下示例显示了封装的文档的灵活格式，在该格式中，文档和信封（以粗体类型显示）可在封闭信封中的同一级别上出现。</span><span class="sxs-lookup"><span data-stu-id="c6260-105">The following example shows the flexible form of enveloped documents, in which documents and envelopes (shown in bold type) can appear at the same level within an enclosing envelope.</span></span>  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="c6260-106">以下示例显示了一个类似的实例消息，它符合封装的文档的规范格式，在该格式中，所有文档都在最内层信封中的同一级别上出现。</span><span class="sxs-lookup"><span data-stu-id="c6260-106">The following example shows a similar instance message that conforms to the canonical form of enveloped documents, in which all documents appear at the same level within the innermost envelope.</span></span>  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 <span data-ttu-id="c6260-107">假定实例消息采用上述格式之一，则 XML 拆装器将生成 document1、document2、document3 和 document4。</span><span class="sxs-lookup"><span data-stu-id="c6260-107">Given an instance message in either of the forms described, the XML disassembler will produce document1, document2, document3, and document4.</span></span> <span data-ttu-id="c6260-108">上述各文档的消息上下文包括从相应文档升级的属性以及在各封闭信封内升级的属性。</span><span class="sxs-lookup"><span data-stu-id="c6260-108">The message context of each of these documents includes the properties promoted from the corresponding document as well as the properties promoted within each of the enclosing envelopes.</span></span> <span data-ttu-id="c6260-109">下表显示了当属性升级在各种信封和文档的第一列中指定时，对于灵活格式和规范格式的示例，将包含在每个不自动换行的文档的消息上下文中的已升级属性。</span><span class="sxs-lookup"><span data-stu-id="c6260-109">The following table shows the promoted properties that will be include in the message context of each unwrapped documents for both the flexible and canonical examples, given the property promotions specified in the first column for the various envelopes and documents.</span></span>  
  
|<span data-ttu-id="c6260-110">指定的属性升级</span><span class="sxs-lookup"><span data-stu-id="c6260-110">Specified property promotions</span></span>|<span data-ttu-id="c6260-111">为灵活格式示例生成的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="c6260-111">Resulting message context properties for flexible example</span></span>|<span data-ttu-id="c6260-112">为规范格式示例生成的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="c6260-112">Resulting message context properties for canonical example</span></span>|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|<span data-ttu-id="c6260-113">envelope1：p1</span><span class="sxs-lookup"><span data-stu-id="c6260-113">envelope1: p1</span></span><br /><br /> <span data-ttu-id="c6260-114">envelope2：p3</span><span class="sxs-lookup"><span data-stu-id="c6260-114">envelope2: p3</span></span><br /><br /> <span data-ttu-id="c6260-115">document1：p2</span><span class="sxs-lookup"><span data-stu-id="c6260-115">document1: p2</span></span><br /><br /> <span data-ttu-id="c6260-116">document2：p4 和 p5</span><span class="sxs-lookup"><span data-stu-id="c6260-116">document2: p4 and p5</span></span><br /><br /> <span data-ttu-id="c6260-117">document3：无升级</span><span class="sxs-lookup"><span data-stu-id="c6260-117">document3: no promotions</span></span><br /><br /> <span data-ttu-id="c6260-118">document4：无升级</span><span class="sxs-lookup"><span data-stu-id="c6260-118">document4: no promotions</span></span>|<span data-ttu-id="c6260-119">document1：p1、p2</span><span class="sxs-lookup"><span data-stu-id="c6260-119">document1: p1, p2</span></span><br /><br /> <span data-ttu-id="c6260-120">document2：p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="c6260-120">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="c6260-121">document3：p1、p3</span><span class="sxs-lookup"><span data-stu-id="c6260-121">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="c6260-122">document4：p1</span><span class="sxs-lookup"><span data-stu-id="c6260-122">document4: p1</span></span>|<span data-ttu-id="c6260-123">document1：p1、p2、p3</span><span class="sxs-lookup"><span data-stu-id="c6260-123">document1: p1, p2, p3</span></span><br /><br /> <span data-ttu-id="c6260-124">document2：p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="c6260-124">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="c6260-125">document3：p1、p3</span><span class="sxs-lookup"><span data-stu-id="c6260-125">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="c6260-126">document4：p1、p3</span><span class="sxs-lookup"><span data-stu-id="c6260-126">document4: p1, p3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6260-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6260-127">See Also</span></span>  
 <span data-ttu-id="c6260-128">[XML 消息包络线](../core/xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="c6260-128">[XML Message Envelopes](../core/xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="c6260-129">[XML 消息的结构](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="c6260-129">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="c6260-130">如何为包络线创建架构</span><span class="sxs-lookup"><span data-stu-id="c6260-130">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)