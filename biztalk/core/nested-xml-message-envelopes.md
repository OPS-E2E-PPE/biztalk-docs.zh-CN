---
title: 嵌套 XML 消息信封 |Microsoft Docs
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
ms.openlocfilehash: b341930a30c8653cb2db378a24c6600f48de0891
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263369"
---
# <a name="nested-xml-message-envelopes"></a><span data-ttu-id="05b5f-102">嵌套 XML 消息信封</span><span class="sxs-lookup"><span data-stu-id="05b5f-102">Nested XML Message Envelopes</span></span>
<span data-ttu-id="05b5f-103">可以嵌套 XML 信封以创建复杂的文档结构。</span><span class="sxs-lookup"><span data-stu-id="05b5f-103">XML envelopes can be nested to create complex document structures.</span></span> <span data-ttu-id="05b5f-104">嵌套的 XML 信封可以有两种形式，灵活格式和规范。</span><span class="sxs-lookup"><span data-stu-id="05b5f-104">Nested XML envelopes can occur in two forms, known as flexible and canonical.</span></span> <span data-ttu-id="05b5f-105">下面的示例显示了封装的文档，在其文档和信封 （以粗体显示） 可以出现在封闭信封中的级别相同的灵活的窗体。</span><span class="sxs-lookup"><span data-stu-id="05b5f-105">The following example shows the flexible form of enveloped documents, in which documents and envelopes (shown in bold type) can appear at the same level within an enclosing envelope.</span></span>  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="05b5f-106">下面的示例显示了类似的实例消息，符合封装的文档，所有文档都显示在最内层信封中的相同级别的规范格式。</span><span class="sxs-lookup"><span data-stu-id="05b5f-106">The following example shows a similar instance message that conforms to the canonical form of enveloped documents, in which all documents appear at the same level within the innermost envelope.</span></span>  
  
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
  
 <span data-ttu-id="05b5f-107">给定的实例消息中所述的窗体，XML 拆装器将生成 document1、 document2、 document3 和 document4。</span><span class="sxs-lookup"><span data-stu-id="05b5f-107">Given an instance message in either of the forms described, the XML disassembler will produce document1, document2, document3, and document4.</span></span> <span data-ttu-id="05b5f-108">每个文档的消息上下文包括从相应文档升级的属性，以及每个封闭信封内升级的属性。</span><span class="sxs-lookup"><span data-stu-id="05b5f-108">The message context of each of these documents includes the properties promoted from the corresponding document as well as the properties promoted within each of the enclosing envelopes.</span></span> <span data-ttu-id="05b5f-109">下表显示了这两种灵活和规范格式示例中，在各种信封的第一列中指定属性升级每个未包装文档的消息上下文中包括的已升级的属性将成为和文档数。</span><span class="sxs-lookup"><span data-stu-id="05b5f-109">The following table shows the promoted properties that will be include in the message context of each unwrapped documents for both the flexible and canonical examples, given the property promotions specified in the first column for the various envelopes and documents.</span></span>  
  
|<span data-ttu-id="05b5f-110">指定的属性升级</span><span class="sxs-lookup"><span data-stu-id="05b5f-110">Specified property promotions</span></span>|<span data-ttu-id="05b5f-111">灵活格式示例的生成的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="05b5f-111">Resulting message context properties for flexible example</span></span>|<span data-ttu-id="05b5f-112">规范格式示例的生成的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="05b5f-112">Resulting message context properties for canonical example</span></span>|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|<span data-ttu-id="05b5f-113">envelope1: p1</span><span class="sxs-lookup"><span data-stu-id="05b5f-113">envelope1: p1</span></span><br /><br /> <span data-ttu-id="05b5f-114">envelope2: p3</span><span class="sxs-lookup"><span data-stu-id="05b5f-114">envelope2: p3</span></span><br /><br /> <span data-ttu-id="05b5f-115">document1: p2</span><span class="sxs-lookup"><span data-stu-id="05b5f-115">document1: p2</span></span><br /><br /> <span data-ttu-id="05b5f-116">document2: p4 和 p5</span><span class="sxs-lookup"><span data-stu-id="05b5f-116">document2: p4 and p5</span></span><br /><br /> <span data-ttu-id="05b5f-117">document3： 无升级</span><span class="sxs-lookup"><span data-stu-id="05b5f-117">document3: no promotions</span></span><br /><br /> <span data-ttu-id="05b5f-118">document4： 无升级</span><span class="sxs-lookup"><span data-stu-id="05b5f-118">document4: no promotions</span></span>|<span data-ttu-id="05b5f-119">文档 1: p1、 p2</span><span class="sxs-lookup"><span data-stu-id="05b5f-119">document1: p1, p2</span></span><br /><br /> <span data-ttu-id="05b5f-120">document2: p1、 p3、 p4，p5</span><span class="sxs-lookup"><span data-stu-id="05b5f-120">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="05b5f-121">document3: p1，p3</span><span class="sxs-lookup"><span data-stu-id="05b5f-121">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="05b5f-122">document4: p1</span><span class="sxs-lookup"><span data-stu-id="05b5f-122">document4: p1</span></span>|<span data-ttu-id="05b5f-123">文档 1: p1、 p2、 p3</span><span class="sxs-lookup"><span data-stu-id="05b5f-123">document1: p1, p2, p3</span></span><br /><br /> <span data-ttu-id="05b5f-124">document2: p1、 p3、 p4，p5</span><span class="sxs-lookup"><span data-stu-id="05b5f-124">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="05b5f-125">document3: p1，p3</span><span class="sxs-lookup"><span data-stu-id="05b5f-125">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="05b5f-126">document4: p1，p3</span><span class="sxs-lookup"><span data-stu-id="05b5f-126">document4: p1, p3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05b5f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="05b5f-127">See Also</span></span>  
 <span data-ttu-id="05b5f-128">[XML 消息信封](../core/xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="05b5f-128">[XML Message Envelopes](../core/xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="05b5f-129">[XML 消息的结构](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="05b5f-129">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="05b5f-130">如何为信封创建架构</span><span class="sxs-lookup"><span data-stu-id="05b5f-130">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)