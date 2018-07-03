---
title: EDI 标准支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ef14c5-5f12-40e2-93d7-59b5c5a0d641
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb4d85b4972991054914baea2014b6d268a24eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007126"
---
# <a name="edi-standards-support"></a><span data-ttu-id="fe169-102">EDI 标准支持</span><span class="sxs-lookup"><span data-stu-id="fe169-102">EDI Standards Support</span></span>
<span data-ttu-id="fe169-103">BizTalk Server 提供的四个编码标准的设计和运行时支持。</span><span class="sxs-lookup"><span data-stu-id="fe169-103">BizTalk Server provides for design- and run-time support for four encoding standards.</span></span> <span data-ttu-id="fe169-104">下表列出了使用的详细信息的链接的编码标准。</span><span class="sxs-lookup"><span data-stu-id="fe169-104">The following table lists the encoding standards with links to more information.</span></span>  
  
|<span data-ttu-id="fe169-105">编码标准</span><span class="sxs-lookup"><span data-stu-id="fe169-105">Encoding Standard</span></span>|<span data-ttu-id="fe169-106">行业细分市场</span><span class="sxs-lookup"><span data-stu-id="fe169-106">Industry Segment</span></span>|<span data-ttu-id="fe169-107">References</span><span class="sxs-lookup"><span data-stu-id="fe169-107">References</span></span>|  
|-----------------------|----------------------|----------------|  
|<span data-ttu-id="fe169-108">UN/EDIFACT</span><span class="sxs-lookup"><span data-stu-id="fe169-108">UN/EDIFACT</span></span>|<span data-ttu-id="fe169-109">常规行业</span><span class="sxs-lookup"><span data-stu-id="fe169-109">General Industry</span></span>|<span data-ttu-id="fe169-110">[标准网站](http://go.microsoft.com/fwlink/?LinkId=77532)（有效负载参考）</span><span class="sxs-lookup"><span data-stu-id="fe169-110">[Standards Website](http://go.microsoft.com/fwlink/?LinkId=77532) (reference to payload)</span></span><br /><br /> <span data-ttu-id="fe169-111">[编码规则](http://go.microsoft.com/fwlink/?LinkId=77534)根据 ISO 9735 4.1</span><span class="sxs-lookup"><span data-stu-id="fe169-111">[Encoding rule](http://go.microsoft.com/fwlink/?LinkId=77534) per ISO 9735-4.1</span></span>|  
|<span data-ttu-id="fe169-112">X12</span><span class="sxs-lookup"><span data-stu-id="fe169-112">X12</span></span>|<span data-ttu-id="fe169-113">常规行业</span><span class="sxs-lookup"><span data-stu-id="fe169-113">General Industry</span></span>|[<span data-ttu-id="fe169-114">标准网站</span><span class="sxs-lookup"><span data-stu-id="fe169-114">Standards Website</span></span>](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [<span data-ttu-id="fe169-115">规范开发</span><span class="sxs-lookup"><span data-stu-id="fe169-115">Specifications Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|<span data-ttu-id="fe169-116">EANCOM</span><span class="sxs-lookup"><span data-stu-id="fe169-116">EANCOM</span></span>|<span data-ttu-id="fe169-117">零售</span><span class="sxs-lookup"><span data-stu-id="fe169-117">Retail</span></span>|[<span data-ttu-id="fe169-118">标准网站</span><span class="sxs-lookup"><span data-stu-id="fe169-118">Standards Website</span></span>](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|<span data-ttu-id="fe169-119">HIPAA X12N</span><span class="sxs-lookup"><span data-stu-id="fe169-119">HIPAA X12N</span></span>|<span data-ttu-id="fe169-120">健康保健</span><span class="sxs-lookup"><span data-stu-id="fe169-120">Health Care</span></span>|[<span data-ttu-id="fe169-121">HIPAA 实施指南</span><span class="sxs-lookup"><span data-stu-id="fe169-121">HIPAA Implementation Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [<span data-ttu-id="fe169-122">HIPAA 规范</span><span class="sxs-lookup"><span data-stu-id="fe169-122">HIPAA Specifications</span></span>](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  <span data-ttu-id="fe169-123">EANCOM 架构是 EDIFACT 的子集。</span><span class="sxs-lookup"><span data-stu-id="fe169-123">EANCOM schemas are a subset of EDIFACT.</span></span> <span data-ttu-id="fe169-124">EANCOM 遵循相同的编码规则 EDIFACT 后面。</span><span class="sxs-lookup"><span data-stu-id="fe169-124">EANCOM follows the same encoding rules that EDIFACT follows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe169-125">KEDIFACT 是一个单独的标准，但严格基于 EDIFACT 标准。</span><span class="sxs-lookup"><span data-stu-id="fe169-125">KEDIFACT is a separate standard, but is closely based on the EDIFACT standard.</span></span>  
  
## <a name="x12-and-edifact"></a><span data-ttu-id="fe169-126">X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="fe169-126">X12 and EDIFACT</span></span>  
 <span data-ttu-id="fe169-127">这两个标准，ANSI X12 和 UN/EDIFACT，构成所有 EDI 交换的消息的全球超过 90%:</span><span class="sxs-lookup"><span data-stu-id="fe169-127">Two standards, ANSI X12 and UN/EDIFACT, constitute more than 90% of all EDI messages exchanged globally:</span></span>  
  
- <span data-ttu-id="fe169-128">UN/EDIFACT EDI 国际消息标准 (针对管理、 商务和贸易的 EDI) 开发的并继续由联合国经济委员会欧洲 (UN/ECE) 来维护。</span><span class="sxs-lookup"><span data-stu-id="fe169-128">The UN/EDIFACT EDI international message standard (EDI for Administration, Commerce, and Trade) was developed and continues to be maintained by the United Nations Economic Commission for Europe (UN/ECE).</span></span> <span data-ttu-id="fe169-129">该标准也简称为 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="fe169-129">Also known as just EDIFACT.</span></span>  
  
- <span data-ttu-id="fe169-130">X12 EDI U.S. 消息标准由美国国家标准协会 (ANSI) 设立的公认标准委员会 (ASC) X12 委员会制定并继续维护。</span><span class="sxs-lookup"><span data-stu-id="fe169-130">The X12 EDI U.S. message standard was developed and continues to be maintained by the Accredited Standards Committee (ASC) X12 committee chartered by the American National Standards Institute (ANSI).</span></span>  
  
  <span data-ttu-id="fe169-131">EDIFACT 很大程度上基于美国的X12 标准。</span><span class="sxs-lookup"><span data-stu-id="fe169-131">EDIFACT is based largely on the U.S. X12 standards.</span></span> <span data-ttu-id="fe169-132">这两个 EDI 标准在结构方面十分相似。</span><span class="sxs-lookup"><span data-stu-id="fe169-132">The two EDI standards are very similar in terms of structure.</span></span> <span data-ttu-id="fe169-133">不同点包括：</span><span class="sxs-lookup"><span data-stu-id="fe169-133">Differences include:</span></span>  
  
- <span data-ttu-id="fe169-134">结构元素在这两个标准中的名称不同。</span><span class="sxs-lookup"><span data-stu-id="fe169-134">Structural elements are named differently in the two standards.</span></span> <span data-ttu-id="fe169-135">例如，交换控制标头在 X12 中为 ISA 数据元素，而在 EDIFACT 中为 UNB 数据元素。</span><span class="sxs-lookup"><span data-stu-id="fe169-135">For example, the interchange control header is an ISA data element in X12 and a UNB data element in EDIFACT.</span></span>  
  
- <span data-ttu-id="fe169-136">很多事务集在这两个标准之间存在映射关系，但事务集在这两个标准中具有不同的名称。</span><span class="sxs-lookup"><span data-stu-id="fe169-136">While many transaction sets map between the two standards, the transaction sets are named differently in the two standards.</span></span> <span data-ttu-id="fe169-137">例如，采购订单在 X12 中为 850 事务集，而在 EDIFACT 中为 ORDERS 事务集。</span><span class="sxs-lookup"><span data-stu-id="fe169-137">For example, a purchase order is an 850 transaction set in X12 and an ORDERS transaction set in EDIFACT.</span></span>  
  
- <span data-ttu-id="fe169-138">EDIFACT 具有用于设置结构元素（如分隔符和十进制符号）的可选标头段 UNA，可替代管道中定义的默认值。</span><span class="sxs-lookup"><span data-stu-id="fe169-138">EDIFACT has an optional header segment UNA to set structural elements such as separators/delimiters and decimal notation, overriding the default values defined in a pipeline.</span></span>  
  
- <span data-ttu-id="fe169-139">X12 具有两个确认（名为 TA1 的技术确认和名为 997 的功能确认），而 EDIFACT 具有一个名为 CONTRL 的全面确认。</span><span class="sxs-lookup"><span data-stu-id="fe169-139">X12 has two acknowledgments (a technical acknowledgment called TA1 and a functional acknowledgment called 997), while EDIFACT has one comprehensive acknowledgment called CONTRL.</span></span>  
  
- <span data-ttu-id="fe169-140">X12 建议使用 ASCII 编码，而 EDIFACT 建议使用 UTF8 编码。</span><span class="sxs-lookup"><span data-stu-id="fe169-140">X12 recommends ASCII encoding, while EDIFACT recommends UTF8 encoding.</span></span>  
  
  <span data-ttu-id="fe169-141">BizTalk Server 支持 KEDIFACT (韩国 EDIFACT) 标准。</span><span class="sxs-lookup"><span data-stu-id="fe169-141">BizTalk Server supports the KEDIFACT (Korea EDIFACT) standard.</span></span> <span data-ttu-id="fe169-142">KEDIFACT 遵循 UN/EDIFACT 的消息实现指南，因此在很大程度上是以 EDIFACT 为基础。</span><span class="sxs-lookup"><span data-stu-id="fe169-142">KEDIFACT follows the Message Implementation Guide of UN/EDIFACT, so is closely based on EDIFACT.</span></span> <span data-ttu-id="fe169-143">但是，KEDIFACT 和 X12/EDIFACT 之间存在差异。</span><span class="sxs-lookup"><span data-stu-id="fe169-143">However, there are differences between KEDIFACT and X12/EDIFACT.</span></span> <span data-ttu-id="fe169-144">KEDIFACT 使用若干特定于 KEDIFACT 的 EDI 架构，并使用 KECA 代码页。</span><span class="sxs-lookup"><span data-stu-id="fe169-144">KEDIFACT uses several KEDIFACT-specific EDI schemas and uses the KECA code page.</span></span>  
  
## <a name="hipaa"></a><span data-ttu-id="fe169-145">HIPAA</span><span class="sxs-lookup"><span data-stu-id="fe169-145">HIPAA</span></span>  
 <span data-ttu-id="fe169-146">BizTalk Server 支持 X12 处理，而由于 HIPAA 处理由 x12 处理派生而来，BizTalk Server 支持 HIPAA 处理。</span><span class="sxs-lookup"><span data-stu-id="fe169-146">BizTalk Server supports X12 processing, and since HIPAA processing is a derivative of X12 processing, BizTalk Server supports HIPAA processing.</span></span> <span data-ttu-id="fe169-147">请参阅本文档中支持对 X12 引用，其中也适用于 HIPAA 处理。</span><span class="sxs-lookup"><span data-stu-id="fe169-147">Where you see references to X12 support in this document, it also applies to HIPAA processing.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fe169-148"> 提供了特定于 HIPAA 的更多支持：</span><span class="sxs-lookup"><span data-stu-id="fe169-148"> provides the additional HIPAA-specific support:</span></span>  
  
- <span data-ttu-id="fe169-149">一组 4010A1 版本的 HIPAA 文档架构。</span><span class="sxs-lookup"><span data-stu-id="fe169-149">A set of version 4010A1 HIPAA document schemas.</span></span> <span data-ttu-id="fe169-150">在 BizTalk Server 中的 EDI 和 HIPAA 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="fe169-150">For more information on EDI and HIPAA document schemas in BizTalk Server, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  
  
- <span data-ttu-id="fe169-151">一组 5010 版本的 HIPAA 文档架构。</span><span class="sxs-lookup"><span data-stu-id="fe169-151">A set of version 5010 HIPAA document schemas.</span></span> <span data-ttu-id="fe169-152">有关详细信息，请参阅[HIPAA 文档架构版本 5010](../core/hipaa-document-schema-version-5010.md)。</span><span class="sxs-lookup"><span data-stu-id="fe169-152">For more information, see [HIPAA Document Schema Version 5010](../core/hipaa-document-schema-version-5010.md).</span></span>  
  
- <span data-ttu-id="fe169-153">HIPAA 子文档拆分。</span><span class="sxs-lookup"><span data-stu-id="fe169-153">HIPAA subdocument splitting.</span></span> <span data-ttu-id="fe169-154">有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。</span><span class="sxs-lookup"><span data-stu-id="fe169-154">For more information, see [Splitting HIPAA Subdocuments](../core/splitting-hipaa-subdocuments.md).</span></span>  
  
- <span data-ttu-id="fe169-155">支持 WEDI SNIP 测试的前两个级别： X12 语法完整性和要求[HIPAA 实施指南](http://go.microsoft.com/fwlink/?LinkId=77541)。</span><span class="sxs-lookup"><span data-stu-id="fe169-155">Support for the first two levels of WEDI SNIP testing: X12 syntax integrity and requirements of the [HIPAA Implementation Guide](http://go.microsoft.com/fwlink/?LinkId=77541).</span></span>  
  
  <span data-ttu-id="fe169-156">BizTalk Server 提供 HIPAA 支持作为本机 BizTalk Server EDI 功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe169-156">BizTalk Server provides HIPAA support as part of the native BizTalk Server EDI functionality.</span></span> <span data-ttu-id="fe169-157">有关详细信息，请参阅[BizTalk Server 中的 EDI 支持](../core/edi-support-in-biztalk-server2.md)。</span><span class="sxs-lookup"><span data-stu-id="fe169-157">For more information, see [EDI Support in BizTalk Server](../core/edi-support-in-biztalk-server2.md).</span></span>  
  
## <a name="eancom"></a><span data-ttu-id="fe169-158">EANCOM</span><span class="sxs-lookup"><span data-stu-id="fe169-158">EANCOM</span></span>  
 <span data-ttu-id="fe169-159">BizTalk Server 支持 EDIFACT 处理，由于 EANCOM 处理由 EDIFACT 处理派生而来，BizTalk Server 支持 EANCOM 处理。</span><span class="sxs-lookup"><span data-stu-id="fe169-159">BizTalk Server supports EDIFACT processing, and since EANCOM processing is a derivative of EDIFACT processing, BizTalk Server supports EANCOM processing.</span></span> <span data-ttu-id="fe169-160">本文档中所有提及支持 EDIFACT 的部分也支持 EANCOM 处理。</span><span class="sxs-lookup"><span data-stu-id="fe169-160">Where you see references to EDIFACT support in this document, this support also applies to EANCOM processing.</span></span>  
  
 <span data-ttu-id="fe169-161">BizTalk Server 提供了其他特定于 EANCOM 的支持：</span><span class="sxs-lookup"><span data-stu-id="fe169-161">BizTalk Server provides the additional EANCOM-specific support:</span></span>  
  
-   <span data-ttu-id="fe169-162">一组 EAN94、EAN97 和 EAN02 版本的 EANCOM 文档架构。</span><span class="sxs-lookup"><span data-stu-id="fe169-162">A set of version EAN94, EAN97, and EAN02 EANCOM document schemas.</span></span> <span data-ttu-id="fe169-163">在 BizTalk Server 中的 EDI 和 EANCOM 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="fe169-163">For more information on EDI and EANCOM document schemas in BizTalk Server, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe169-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe169-164">See Also</span></span>  
 <span data-ttu-id="fe169-165">[EDI 消息结构](../core/edi-message-structure.md) </span><span class="sxs-lookup"><span data-stu-id="fe169-165">[EDI Message Structure](../core/edi-message-structure.md) </span></span>  
 [<span data-ttu-id="fe169-166">EDI 文档架构</span><span class="sxs-lookup"><span data-stu-id="fe169-166">EDI Document Schemas</span></span>](../core/edi-document-schemas.md)