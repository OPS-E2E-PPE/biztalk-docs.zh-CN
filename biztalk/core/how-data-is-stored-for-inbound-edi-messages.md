---
title: 如何为入站的 EDI 消息存储数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a117bb89989977ab0050d0d6b4704002f316315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387467"
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a><span data-ttu-id="89fc5-102">如何为入站的 EDI 消息存储数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-102">How Data Is Stored for Inbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="89fc5-103">执行以下操作生成的入站的交换和确认已发送到它的响应的状态报告条目：</span><span class="sxs-lookup"><span data-stu-id="89fc5-103">does the following to generate a status report entry for an inbound interchange and the acknowledgment sent in response to it:</span></span>  
  
1.  <span data-ttu-id="89fc5-104">入站的消息 XML 发送时 EDI 接收管道到 MessageBox，接收管道在状态报告功能，使用以下值的数据存储区中创建以下条目：</span><span class="sxs-lookup"><span data-stu-id="89fc5-104">When inbound message XML is sent by the EDI receive pipeline to the MessageBox, the receive pipeline creates the following entries in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="89fc5-105">每个接收的交换，状态设置为已接受/部分接受/拒绝的一个状态报告条目</span><span class="sxs-lookup"><span data-stu-id="89fc5-105">One status report entry for each interchange received, with Status set to Accepted/Partially Accepted/Rejected</span></span>  
  
    -   <span data-ttu-id="89fc5-106">对于每个技术 （交换） 确认一个状态报告条目，每个状态的交换，一个设置为生成</span><span class="sxs-lookup"><span data-stu-id="89fc5-106">One status report entry for each technical (interchange) acknowledgment, one per interchange, with Status set to Generated</span></span>  
  
    -   <span data-ttu-id="89fc5-107">每个功能确认的一个状态报告条目，为每个组在 X12，另一个用于所有组在 EDIFACT 中，状态将设置为生成。</span><span class="sxs-lookup"><span data-stu-id="89fc5-107">One status report entry for each functional acknowledgment, one per group in X12 and one for all groups in EDIFACT, with Status set to Generated.</span></span>  
  
2.  <span data-ttu-id="89fc5-108">发送管道发送后为贸易合作伙伴，EDI 确认管道将更新发送的交换确认状态和功能确认状态条目到已发送的根据需要。</span><span class="sxs-lookup"><span data-stu-id="89fc5-108">After the send pipeline has sent the acknowledgments to the trading partner, the EDI send pipeline updates the Interchange ACK status and Functional ACK status entries to Sent, as appropriate.</span></span> <span data-ttu-id="89fc5-109">交换状态条目不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="89fc5-109">No changes are made to the Interchange status entry.</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a><span data-ttu-id="89fc5-110">接收管道为入站交换存储的数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-110">Data Stored by the Receive Pipeline for Inbound Interchanges</span></span>  
 <span data-ttu-id="89fc5-111">接收管道接收每个交换状态报告数据存储区创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="89fc5-111">The receive pipeline creates a record in the status report data store for each interchange that it receives.</span></span> <span data-ttu-id="89fc5-112">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="89fc5-112">The data stored includes:</span></span>  
  
-   <span data-ttu-id="89fc5-113">记录类型 = 交换状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-113">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="89fc5-114">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="89fc5-114">Interchange Direction = Receive</span></span>  
  
-   <span data-ttu-id="89fc5-115">交换接收方 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-115">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-116">交换发送方 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-116">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-117">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-117">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-118">交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-118">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-119">交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-119">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-120">交换状态：更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-120">Interchange Status: Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-121">交换中组的计数 = 更新数据 （在 EDIFACT 中，组是可选的如果不存在，值为不适用)</span><span class="sxs-lookup"><span data-stu-id="89fc5-121">Count of Groups in Interchange = Update Data (In EDIFACT Groups are optional and if not present, valued as ‘Not Applicable’)</span></span>  
  
-   <span data-ttu-id="89fc5-122">交换接收端口 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-122">Interchange Receive Port ID = Update Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="89fc5-123">接收管道为每个技术而生成的响应的入站交换确认存储的数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-123">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="89fc5-124">发送管道创建状态报告数据存储区中的每个技术确认，它将发送一条记录。</span><span class="sxs-lookup"><span data-stu-id="89fc5-124">The send pipeline creates a record in the status report data store for each technical acknowledgment that it sends.</span></span> <span data-ttu-id="89fc5-125">只有 UCI 段对于 EDIFACT 具有用于 CONTRL 消息和 X12 TA1 技术确认。</span><span class="sxs-lookup"><span data-stu-id="89fc5-125">The technical acknowledgement is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="89fc5-126">可从交换标头/尾部段 （ISA/IEA 或 UNB/UNZ） 最多的数据所需的条目。</span><span class="sxs-lookup"><span data-stu-id="89fc5-126">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="89fc5-127">可从发送端口的属性的其他数据。</span><span class="sxs-lookup"><span data-stu-id="89fc5-127">Other data is available from send port properties.</span></span> <span data-ttu-id="89fc5-128">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="89fc5-128">The data stored includes:</span></span>  
  
-   <span data-ttu-id="89fc5-129">记录类型 = 交换确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-129">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="89fc5-130">交换确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="89fc5-130">Interchange ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="89fc5-131">交换接收方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-131">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-132">交换发送方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-132">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-133">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-133">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-134">交换控制 ID = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-134">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-135">交换确认状态 =\<预期或不适用\>。</span><span class="sxs-lookup"><span data-stu-id="89fc5-135">Interchange ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="89fc5-136">如果配置了技术确认或将其值在传入的交换中，状态 = 预期。</span><span class="sxs-lookup"><span data-stu-id="89fc5-136">If the technical ACK is configured or valued in the incoming interchange, status = Expected.</span></span> <span data-ttu-id="89fc5-137">否则为状态 = 不可用。</span><span class="sxs-lookup"><span data-stu-id="89fc5-137">Otherwise, status = Not Applicable.</span></span>  
  
-   <span data-ttu-id="89fc5-138">交换确认控制 ID =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-138">Interchange ACK Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-139">交换确认日期 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-139">Interchange ACK Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-140">交换确认时间 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-140">Interchange ACK Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-141">确认/操作代码 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-141">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-142">确认注释代码 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-142">ACK Note Code = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="89fc5-143">为生成响应入站交换中每个技术确认更新的发送管道的数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-143">Data Updated by the Send Pipeline for Each Technical Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="89fc5-144">对于每个技术确认，发送管道发送，会更新接收相关交换状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="89fc5-144">For each technical acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="89fc5-145">数据源将是由发送管道创建的交换信封。</span><span class="sxs-lookup"><span data-stu-id="89fc5-145">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="89fc5-146">EDI 组装器定位在数据存储中使用的 UCI 和 TA1 段传入的确认中的数据，如下所示的记录：</span><span class="sxs-lookup"><span data-stu-id="89fc5-146">The EDI Assembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="89fc5-147">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="89fc5-147">Fields in ACK</span></span>|<span data-ttu-id="89fc5-148">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="89fc5-148">Fields in Data store</span></span>|<span data-ttu-id="89fc5-149">注释</span><span class="sxs-lookup"><span data-stu-id="89fc5-149">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="89fc5-150">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-150">Interchange Sender ID</span></span>|<span data-ttu-id="89fc5-151">交换接收方</span><span class="sxs-lookup"><span data-stu-id="89fc5-151">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="89fc5-152">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-152">Interchange Receiver ID</span></span>|<span data-ttu-id="89fc5-153">交换发送方</span><span class="sxs-lookup"><span data-stu-id="89fc5-153">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="89fc5-154">交换日期</span><span class="sxs-lookup"><span data-stu-id="89fc5-154">Interchange Date</span></span>|-|  
|<span data-ttu-id="89fc5-155">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="89fc5-155">Interchange Control Number</span></span>|<span data-ttu-id="89fc5-156">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-156">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="89fc5-157">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="89fc5-157">Interchange Direction = Receive</span></span>|<span data-ttu-id="89fc5-158">在保留的交换方案中的唯一性要求</span><span class="sxs-lookup"><span data-stu-id="89fc5-158">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="89fc5-159">记录类型</span><span class="sxs-lookup"><span data-stu-id="89fc5-159">Record Type</span></span>|<span data-ttu-id="89fc5-160">交换确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-160">Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="89fc5-161">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="89fc5-161">The data stored includes:</span></span>  
  
-   <span data-ttu-id="89fc5-162">记录类型 = 交换确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-162">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="89fc5-163">交换确认方向 = 发送-现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-163">Interchange ACK Direction = Send- Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-164">交换确认状态 = 处理或发送 – 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-164">Interchange ACK Status = Processed or Sent – Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-165">交换接收方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-165">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-166">交换发送方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-166">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-167">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-167">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-168">交换控制 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-168">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-169">交换确认控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-169">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-170">交换确认日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-170">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-171">交换确认时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-171">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-172">确认/操作代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-172">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-173">确认注释代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-173">ACK Note Code = Existing Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="89fc5-174">接收管道为每个功能而生成的响应的入站交换确认存储的数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-174">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="89fc5-175">发送管道在发送每个功能确认状态报告数据存储区中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="89fc5-175">The send pipeline creates a record in the status report data store for each functional acknowledgment that it sends.</span></span> <span data-ttu-id="89fc5-176">发送管道在状态报告数据存储区中创建每个功能确认 （为了响应接收的交换） 发送一条的记录。</span><span class="sxs-lookup"><span data-stu-id="89fc5-176">The send pipeline creates a record of each functional acknowledgment sent (in response to an interchange received) in the status report data store.</span></span> <span data-ttu-id="89fc5-177">如果不不在 EDIFACT 中存在任何组，则仍将创建一个功能确认。</span><span class="sxs-lookup"><span data-stu-id="89fc5-177">If no group is present in EDIFACT, one functional ACK will still be created.</span></span> <span data-ttu-id="89fc5-178">将从功能组标头/尾部 （GS/GE 或 UNG/UNE） 填充功能确认状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="89fc5-178">The functional ACK status report entry will be populated from the functional group header/trailer (GS/GE or UNG/UNE).</span></span> <span data-ttu-id="89fc5-179">技术确认是 997 的 X12 和完整 CONTRL 消息的 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="89fc5-179">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="89fc5-180">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="89fc5-180">The data stored includes:</span></span>  
  
-   <span data-ttu-id="89fc5-181">记录类型 = 功能确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-181">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="89fc5-182">功能确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="89fc5-182">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="89fc5-183">功能确认状态 =\<预期或不适用\>。</span><span class="sxs-lookup"><span data-stu-id="89fc5-183">Functional ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="89fc5-184">如果选择了 PAM 中的功能确认选项卡，状态将设置为预期。</span><span class="sxs-lookup"><span data-stu-id="89fc5-184">If the functional acknowledgment tab in PAM is selected, status will set to Expected.</span></span> <span data-ttu-id="89fc5-185">否则，状态将设置为不适用。</span><span class="sxs-lookup"><span data-stu-id="89fc5-185">Otherwise, status will be set to Not Applicable.</span></span>  
  
-   <span data-ttu-id="89fc5-186">交换接收方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-186">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-187">交换发送方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-187">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-188">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-188">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-189">交换控制 ID = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="89fc5-189">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="89fc5-190">组控制编号 = 更新数据 （所需的相关。</span><span class="sxs-lookup"><span data-stu-id="89fc5-190">Group Control Number = Update Data (required for correlation.</span></span> <span data-ttu-id="89fc5-191">在 EDIFACT 中如果不存在此字段的任何组段，则使用 UNH.1）</span><span class="sxs-lookup"><span data-stu-id="89fc5-191">In EDIFACT if no group segments present this field is valued using UNH.1)</span></span>  
  
-   <span data-ttu-id="89fc5-192">功能 ID 代码 = 更新数据 （非值在 EDIFACT 中如果组不存在）</span><span class="sxs-lookup"><span data-stu-id="89fc5-192">Functional ID Code = Update Data (not valued in EDIFACT if group is not present)</span></span>  
  
-   <span data-ttu-id="89fc5-193">事务集的计数 = 数据 （在 EDIFACT 中是否存在任何组段它映射到 UNE.1 并且 UNG/UNE 都存在或 UNZ.1)</span><span class="sxs-lookup"><span data-stu-id="89fc5-193">Count of Transaction Sets = Data (in EDIFACT this is mapped to UNE.1 while UNG/UNE are present or UNZ.1 if no group segments are present)</span></span>  
  
-   <span data-ttu-id="89fc5-194">功能 ACK 交换控制 ID =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-194">Functional ACK Interchange Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-195">功能确认交换日期 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-195">Functional ACK Interchange Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-196">功能确认交换时间 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-196">Functional ACK Interchange Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-197">计数传送的事务集 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-197">Count of Transaction Sets Delivered = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-198">接受的事务计数集 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-198">Count of Transaction Sets Accepted = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-199">确认/操作代码 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-199">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-200">错误/语法错误代码 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-200">Error/Syntax Error Code  = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-201">附加 X12 确认错误代码 2 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-201">Additional X12 ACK Error Code 2 = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-202">附加 X12 确认错误代码 3 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-202">Additional X12 ACK Error Code 3 = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-203">附加 X12 确认错误代码 4 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-203">Additional X12 ACK Error Code 4 = \<not valued\></span></span>  
  
-   <span data-ttu-id="89fc5-204">附加 X12 确认错误代码 5 =\<未赋值\></span><span class="sxs-lookup"><span data-stu-id="89fc5-204">Additional X12 ACK Error Code 5 = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="89fc5-205">为生成响应入站交换中每个功能确认更新的发送管道的数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-205">Data Updated by the Send Pipeline for Each Functional Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="89fc5-206">对于发送管道发送每个功能确认，它更新接收相关交换状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="89fc5-206">For each functional acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="89fc5-207">数据源将是由发送管道创建的交换信封。</span><span class="sxs-lookup"><span data-stu-id="89fc5-207">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="89fc5-208">EDI 组装器定位在数据存储中使用的交换和组标头传入的确认段中的数据，如下所示的记录：</span><span class="sxs-lookup"><span data-stu-id="89fc5-208">The EDI Assembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="89fc5-209">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="89fc5-209">Fields in ACK</span></span>|<span data-ttu-id="89fc5-210">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="89fc5-210">Fields in Data store</span></span>|<span data-ttu-id="89fc5-211">注释</span><span class="sxs-lookup"><span data-stu-id="89fc5-211">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="89fc5-212">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-212">Interchange Sender ID</span></span>|<span data-ttu-id="89fc5-213">交换接收方</span><span class="sxs-lookup"><span data-stu-id="89fc5-213">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="89fc5-214">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-214">Interchange Receiver ID</span></span>|<span data-ttu-id="89fc5-215">交换发送方</span><span class="sxs-lookup"><span data-stu-id="89fc5-215">Interchange Sender</span></span>|-|  
|<span data-ttu-id="89fc5-216">交换日期</span><span class="sxs-lookup"><span data-stu-id="89fc5-216">Interchange Date</span></span>|<span data-ttu-id="89fc5-217">交换日期</span><span class="sxs-lookup"><span data-stu-id="89fc5-217">Interchange Date</span></span>|-|  
|<span data-ttu-id="89fc5-218">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="89fc5-218">Interchange Control Number</span></span>|<span data-ttu-id="89fc5-219">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="89fc5-219">Interchange Control ID</span></span>|-|  
|<span data-ttu-id="89fc5-220">组控制编号</span><span class="sxs-lookup"><span data-stu-id="89fc5-220">Group Control Number</span></span>|<span data-ttu-id="89fc5-221">组控制编号</span><span class="sxs-lookup"><span data-stu-id="89fc5-221">Group Control Number</span></span>|<span data-ttu-id="89fc5-222">在 EDIFACT 中可选</span><span class="sxs-lookup"><span data-stu-id="89fc5-222">Optional in EDIFACT</span></span>|  
|-|<span data-ttu-id="89fc5-223">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="89fc5-223">Interchange Direction = Receive</span></span>|<span data-ttu-id="89fc5-224">在保留的交换方案中的唯一性要求</span><span class="sxs-lookup"><span data-stu-id="89fc5-224">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="89fc5-225">记录类型</span><span class="sxs-lookup"><span data-stu-id="89fc5-225">Record Type</span></span>|<span data-ttu-id="89fc5-226">功能确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-226">Functional ACK Status</span></span>|-|  
  
 <span data-ttu-id="89fc5-227">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="89fc5-227">The data stored includes:</span></span>  
  
-   <span data-ttu-id="89fc5-228">记录类型 = 功能确认状态</span><span class="sxs-lookup"><span data-stu-id="89fc5-228">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="89fc5-229">功能确认方向 = 发送-现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-229">Functional ACK Direction = Send – Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-230">功能确认状态 = 处理/已发送 – 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-230">Functional ACK Status = Sent/Processed – Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-231">交换接收方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-231">Interchange Receiver =  Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-232">交换发送方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-232">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-233">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-233">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-234">交换控制 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-234">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-235">组控制编号 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-235">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-236">功能 ID 代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-236">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-237">事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-237">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-238">功能 ACK 交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-238">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-239">功能 ACK 交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-239">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-240">功能 ACK 交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-240">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="89fc5-241">接收的事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-241">Count of Transaction Sets Received = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-242">接受的事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-242">Count of Transaction Sets Accepted = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-243">确认/操作代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-243">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-244">错误/语法错误代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-244">Error/Syntax Error Code  = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-245">附加 X12 确认错误代码 2 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-245">Additional X12 ACK Error Code 2 = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-246">附加 X12 确认错误代码 3 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-246">Additional X12 ACK Error Code 3 = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-247">附加 X12 确认错误代码 4 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-247">Additional X12 ACK Error Code 4 = Existing Data</span></span>  
  
-   <span data-ttu-id="89fc5-248">附加 X12 确认错误代码 5 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-248">Additional X12 ACK Error Code 5 = Existing Data</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fc5-249">请参阅</span><span class="sxs-lookup"><span data-stu-id="89fc5-249">See Also</span></span>  
 <span data-ttu-id="89fc5-250">[如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="89fc5-250">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="89fc5-251">如何为出站 EDI 消息存储数据</span><span class="sxs-lookup"><span data-stu-id="89fc5-251">How Data Is Stored for Outbound EDI Messages</span></span>](../core/how-data-is-stored-for-outbound-edi-messages.md)