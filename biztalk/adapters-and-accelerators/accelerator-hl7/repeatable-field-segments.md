---
title: "可重复字段段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a801e39fac0e0bdf0cfb9ee88811703fd1c4373d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="repeatable-field-segments"></a><span data-ttu-id="bc974-102">可重复字段段</span><span class="sxs-lookup"><span data-stu-id="bc974-102">Repeatable Field Segments</span></span>
<span data-ttu-id="bc974-103">段表 HL7 访问数据库中的包含的列段 （ADD、 RDT 和 QPD） 的最后一个字段， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 定义为可重复 (**Last_field_repeatable**  = **True**)。</span><span class="sxs-lookup"><span data-stu-id="bc974-103">The Segments table in the HL7 Access database contains a column for the last field of segments (ADD, RDT, and QPD) that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) defines as repeatable (**Last_field_repeatable** = **True**).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bc974-104">不支持添加。</span><span class="sxs-lookup"><span data-stu-id="bc974-104"> does not support ADD.</span></span> <span data-ttu-id="bc974-105">但是，RDT 和 QPD 查询的表存在，并且使用表值进行响应。</span><span class="sxs-lookup"><span data-stu-id="bc974-105">However, both RDT and QPD are present to query tables and respond with table values.</span></span> <span data-ttu-id="bc974-106">下面的示例演示如何[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]处理这些列。</span><span class="sxs-lookup"><span data-stu-id="bc974-106">The following sample demonstrates how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] handles these columns.</span></span>  
  
 <span data-ttu-id="bc974-107">客户端提交以下查询，并指示客户端通过设置想即时响应**RCP 1 响应优先级**到"**我**":</span><span class="sxs-lookup"><span data-stu-id="bc974-107">A client submits the following query and indicates that the client wants an immediate response by setting **RCP-1-Response priority** to "**I**":</span></span>  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 <span data-ttu-id="bc974-108">服务器的响应更高版本并显示以下消息的一分钟：</span><span class="sxs-lookup"><span data-stu-id="bc974-108">The server responds one minute later with the following message:</span></span>  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 <span data-ttu-id="bc974-109">在示例中，你看到 QPD 和 RDT 是定义的自定义/站点。</span><span class="sxs-lookup"><span data-stu-id="bc974-109">From the example, you see that QPD and RDT are custom/site defined.</span></span> <span data-ttu-id="bc974-110">HL7 规范，如下所示定义 QPD 和 RDT 段。</span><span class="sxs-lookup"><span data-stu-id="bc974-110">The HL7 specification defines QPD and RDT segments as follows.</span></span>  
  
## <a name="qpd---query-parameter-definition"></a><span data-ttu-id="bc974-111">QPD-查询参数定义</span><span class="sxs-lookup"><span data-stu-id="bc974-111">QPD - Query Parameter Definition</span></span>  
 <span data-ttu-id="bc974-112">下表显示 HL7 规范定义 QPD 的方式。</span><span class="sxs-lookup"><span data-stu-id="bc974-112">The following table shows how the HL7 specification defines QPD.</span></span>  
  
|<span data-ttu-id="bc974-113">SEQ</span><span class="sxs-lookup"><span data-stu-id="bc974-113">SEQ</span></span>|<span data-ttu-id="bc974-114">LEN</span><span class="sxs-lookup"><span data-stu-id="bc974-114">LEN</span></span>|<span data-ttu-id="bc974-115">DT</span><span class="sxs-lookup"><span data-stu-id="bc974-115">DT</span></span>|<span data-ttu-id="bc974-116">选择</span><span class="sxs-lookup"><span data-stu-id="bc974-116">OPT</span></span>|<span data-ttu-id="bc974-117">RP / #</span><span class="sxs-lookup"><span data-stu-id="bc974-117">RP/#</span></span>|<span data-ttu-id="bc974-118">TBL #</span><span class="sxs-lookup"><span data-stu-id="bc974-118">TBL#</span></span>|<span data-ttu-id="bc974-119">项 #</span><span class="sxs-lookup"><span data-stu-id="bc974-119">ITEM#</span></span>|<span data-ttu-id="bc974-120">元素名称</span><span class="sxs-lookup"><span data-stu-id="bc974-120">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="bc974-121">1</span><span class="sxs-lookup"><span data-stu-id="bc974-121">1</span></span>|<span data-ttu-id="bc974-122">250</span><span class="sxs-lookup"><span data-stu-id="bc974-122">250</span></span>|<span data-ttu-id="bc974-123">CE</span><span class="sxs-lookup"><span data-stu-id="bc974-123">CE</span></span>|<span data-ttu-id="bc974-124">R</span><span class="sxs-lookup"><span data-stu-id="bc974-124">R</span></span>||<span data-ttu-id="bc974-125">0471</span><span class="sxs-lookup"><span data-stu-id="bc974-125">0471</span></span>|<span data-ttu-id="bc974-126">01375</span><span class="sxs-lookup"><span data-stu-id="bc974-126">01375</span></span>|<span data-ttu-id="bc974-127">消息查询名称</span><span class="sxs-lookup"><span data-stu-id="bc974-127">Message Query Name</span></span>|  
|<span data-ttu-id="bc974-128">2</span><span class="sxs-lookup"><span data-stu-id="bc974-128">2</span></span>|<span data-ttu-id="bc974-129">32</span><span class="sxs-lookup"><span data-stu-id="bc974-129">32</span></span>|<span data-ttu-id="bc974-130">ST</span><span class="sxs-lookup"><span data-stu-id="bc974-130">ST</span></span>|<span data-ttu-id="bc974-131">C</span><span class="sxs-lookup"><span data-stu-id="bc974-131">C</span></span>|||<span data-ttu-id="bc974-132">00696</span><span class="sxs-lookup"><span data-stu-id="bc974-132">00696</span></span>|<span data-ttu-id="bc974-133">查询标记</span><span class="sxs-lookup"><span data-stu-id="bc974-133">Query Tag</span></span>|  
|<span data-ttu-id="bc974-134">3-n</span><span class="sxs-lookup"><span data-stu-id="bc974-134">3-n</span></span>|<span data-ttu-id="bc974-135">256</span><span class="sxs-lookup"><span data-stu-id="bc974-135">256</span></span>|<span data-ttu-id="bc974-136">不定</span><span class="sxs-lookup"><span data-stu-id="bc974-136">Varies</span></span>||||<span data-ttu-id="bc974-137">01435</span><span class="sxs-lookup"><span data-stu-id="bc974-137">01435</span></span>|<span data-ttu-id="bc974-138">连续字段中的用户参数</span><span class="sxs-lookup"><span data-stu-id="bc974-138">User parameters in successive fields</span></span>|  
  
## <a name="rdt---table-row-data"></a><span data-ttu-id="bc974-139">RDT-表行数据</span><span class="sxs-lookup"><span data-stu-id="bc974-139">RDT - Table Row Data</span></span>  
 <span data-ttu-id="bc974-140">下表显示 HL7 规范定义 RDT 的方式。</span><span class="sxs-lookup"><span data-stu-id="bc974-140">The following table shows how the HL7 specification defines RDT.</span></span>  
  
|<span data-ttu-id="bc974-141">SEQ</span><span class="sxs-lookup"><span data-stu-id="bc974-141">SEQ</span></span>|<span data-ttu-id="bc974-142">LEN</span><span class="sxs-lookup"><span data-stu-id="bc974-142">LEN</span></span>|<span data-ttu-id="bc974-143">DT</span><span class="sxs-lookup"><span data-stu-id="bc974-143">DT</span></span>|<span data-ttu-id="bc974-144">选择</span><span class="sxs-lookup"><span data-stu-id="bc974-144">OPT</span></span>|<span data-ttu-id="bc974-145">RP / #</span><span class="sxs-lookup"><span data-stu-id="bc974-145">RP/#</span></span>|<span data-ttu-id="bc974-146">TBL #</span><span class="sxs-lookup"><span data-stu-id="bc974-146">TBL#</span></span>|<span data-ttu-id="bc974-147">项 #</span><span class="sxs-lookup"><span data-stu-id="bc974-147">ITEM#</span></span>|<span data-ttu-id="bc974-148">元素名称</span><span class="sxs-lookup"><span data-stu-id="bc974-148">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="bc974-149">1-n</span><span class="sxs-lookup"><span data-stu-id="bc974-149">1-n</span></span>|<span data-ttu-id="bc974-150">变量</span><span class="sxs-lookup"><span data-stu-id="bc974-150">Variable</span></span>|<span data-ttu-id="bc974-151">变量</span><span class="sxs-lookup"><span data-stu-id="bc974-151">Variable</span></span>|<span data-ttu-id="bc974-152">R</span><span class="sxs-lookup"><span data-stu-id="bc974-152">R</span></span>|||<span data-ttu-id="bc974-153">00703</span><span class="sxs-lookup"><span data-stu-id="bc974-153">00703</span></span>|<span data-ttu-id="bc974-154">列的值</span><span class="sxs-lookup"><span data-stu-id="bc974-154">Column Value</span></span>|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bc974-155">将 QPD 和 RDT 解释为可以重复的站点定义的值。</span><span class="sxs-lookup"><span data-stu-id="bc974-155"> interprets QPD and RDT as site-defined values that can repeat.</span></span> <span data-ttu-id="bc974-156">由于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]仍然无法解决的数据类型和其他详细信息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 QPD.3 和 RDT.1 视为架构中的字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="bc974-156">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fix the data types and other details, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats QPD.3 and RDT.1 as String data types in the schemas.</span></span> <span data-ttu-id="bc974-157">你可能需要修改这些架构，具体取决于你自己站点的条件。</span><span class="sxs-lookup"><span data-stu-id="bc974-157">You may have to modify these schemas depending on your own site conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc974-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc974-158">See Also</span></span>  
 [<span data-ttu-id="bc974-159">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="bc974-159">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)