---
title: "如何将数据存储用于入站的 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60cc8743cd945ad231f3a42f9cbd4f0e76b418d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a><span data-ttu-id="38fd8-102">入站 EDI 消息数据的存储方式</span><span class="sxs-lookup"><span data-stu-id="38fd8-102">How Data Is Stored for Inbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="38fd8-103">执行以下操作来生成状态报表项的入站的交换以及在到它的响应中发送该确认：</span><span class="sxs-lookup"><span data-stu-id="38fd8-103"> does the following to generate a status report entry for an inbound interchange and the acknowledgment sent in response to it:</span></span>  
  
1.  <span data-ttu-id="38fd8-104">当 EDI 接收管道将入站消息 XML 发送到 MessageBox 时，接收管道会在状态报告数据存储区中使用以下值创建以下条目：</span><span class="sxs-lookup"><span data-stu-id="38fd8-104">When inbound message XML is sent by the EDI receive pipeline to the MessageBox, the receive pipeline creates the following entries in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="38fd8-105">为收到的每个交换创建一个状态报告条目，并将“状态”设置为“已接受”、“部分接受”或“已拒绝”</span><span class="sxs-lookup"><span data-stu-id="38fd8-105">One status report entry for each interchange received, with Status set to Accepted/Partially Accepted/Rejected</span></span>  
  
    -   <span data-ttu-id="38fd8-106">为每个技术（交换）确认创建一个状态报告条目（为每个交换创建一个条目），并将“状态”设置为“已生成”</span><span class="sxs-lookup"><span data-stu-id="38fd8-106">One status report entry for each technical (interchange) acknowledgment, one per interchange, with Status set to Generated</span></span>  
  
    -   <span data-ttu-id="38fd8-107">为每个功能确认创建一个状态报告条目（在 X12 中为每个组分别创建一个条目，在 EDIFACT 中则为所有组仅创建一个条目），同时将“状态”设置为“已生成”。</span><span class="sxs-lookup"><span data-stu-id="38fd8-107">One status report entry for each functional acknowledgment, one per group in X12 and one for all groups in EDIFACT, with Status set to Generated.</span></span>  
  
2.  <span data-ttu-id="38fd8-108">在发送管道将确认发送到贸易合作伙伴之后，EDI 发送管道会相应地将“交换确认”状态和“功能确认”状态条目更新为“已发送”。</span><span class="sxs-lookup"><span data-stu-id="38fd8-108">After the send pipeline has sent the acknowledgments to the trading partner, the EDI send pipeline updates the Interchange ACK status and Functional ACK status entries to Sent, as appropriate.</span></span> <span data-ttu-id="38fd8-109">不会对“交换”状态条目进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="38fd8-109">No changes are made to the Interchange status entry.</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a><span data-ttu-id="38fd8-110">接收管道为入站交换存储的数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-110">Data Stored by the Receive Pipeline for Inbound Interchanges</span></span>  
 <span data-ttu-id="38fd8-111">接收管道在状态报告数据存储区中为它接收的每个交换创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="38fd8-111">The receive pipeline creates a record in the status report data store for each interchange that it receives.</span></span> <span data-ttu-id="38fd8-112">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="38fd8-112">The data stored includes:</span></span>  
  
-   <span data-ttu-id="38fd8-113">记录类型 = 交换状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-113">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="38fd8-114">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="38fd8-114">Interchange Direction = Receive</span></span>  
  
-   <span data-ttu-id="38fd8-115">交换接收器 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-115">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-116">交换发件人 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-116">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-117">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-117">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-118">交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-118">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-119">交换控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-119">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-120">交换状态： 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-120">Interchange Status: Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-121">交换中组的计数 = 更新数据（在 EDIFACT 中，组是可选的，如果不存在，值为“不可用”）</span><span class="sxs-lookup"><span data-stu-id="38fd8-121">Count of Groups in Interchange = Update Data (In EDIFACT Groups are optional and if not present, valued as ‘Not Applicable’)</span></span>  
  
-   <span data-ttu-id="38fd8-122">交换接收端口 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-122">Interchange Receive Port ID = Update Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="38fd8-123">接收管道为每个为了响应入站交换而生成的技术确认存储的数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-123">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="38fd8-124">发送管道在状态报告数据存储区中为其发送的每个技术确认创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="38fd8-124">The send pipeline creates a record in the status report data store for each technical acknowledgment that it sends.</span></span> <span data-ttu-id="38fd8-125">技术确认是使用仅对于 EDIFACT 了 UCI 段 X12 和 CONTRL 消息 TA1。</span><span class="sxs-lookup"><span data-stu-id="38fd8-125">The technical acknowledgement is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="38fd8-126">所需的项的大多数数据是可从交换标头/预告片段 （ISA/IEA 或 UNB/UNZ）。</span><span class="sxs-lookup"><span data-stu-id="38fd8-126">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="38fd8-127">从发送端口属性提供了其他数据。</span><span class="sxs-lookup"><span data-stu-id="38fd8-127">Other data is available from send port properties.</span></span> <span data-ttu-id="38fd8-128">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="38fd8-128">The data stored includes:</span></span>  
  
-   <span data-ttu-id="38fd8-129">记录类型 = 交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-129">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="38fd8-130">交换确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="38fd8-130">Interchange ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="38fd8-131">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-131">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-132">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-132">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-133">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-133">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-134">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-134">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-135">交换 ACK 状态 =\<预期或不适用 >。</span><span class="sxs-lookup"><span data-stu-id="38fd8-135">Interchange ACK Status = \< Expected or Not Applicable>.</span></span> <span data-ttu-id="38fd8-136">如果在传入的交换中配置了技术确认或对其进行了赋值，状态 = 预期。</span><span class="sxs-lookup"><span data-stu-id="38fd8-136">If the technical ACK is configured or valued in the incoming interchange, status = Expected.</span></span> <span data-ttu-id="38fd8-137">否则，状态 = 不可用。</span><span class="sxs-lookup"><span data-stu-id="38fd8-137">Otherwise, status = Not Applicable.</span></span>  
  
-   <span data-ttu-id="38fd8-138">交换 ACK 控件 ID =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-138">Interchange ACK Control ID= \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-139">交换 ACK 日期 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-139">Interchange ACK Date = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-140">交换 ACK 时间 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-140">Interchange ACK Time = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-141">确认/操作代码 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-141">ACK/Action Code = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-142">ACK 注意代码 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-142">ACK Note Code = \<not valued></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="38fd8-143">发送管道为每个为了响应入站交换而生成的技术确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-143">Data Updated by the Send Pipeline for Each Technical Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="38fd8-144">对于发送管道发送的每个技术确认，发送管道会更新所接收相关交换的状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="38fd8-144">For each technical acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="38fd8-145">数据的来源为发送管道创建的交换信封。</span><span class="sxs-lookup"><span data-stu-id="38fd8-145">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="38fd8-146">EDI 组装器使用传入的确认的 UCI 和 TA1 段中的数据来定位数据存储区中的记录：</span><span class="sxs-lookup"><span data-stu-id="38fd8-146">The EDI Assembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="38fd8-147">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="38fd8-147">Fields in ACK</span></span>|<span data-ttu-id="38fd8-148">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="38fd8-148">Fields in Data store</span></span>|<span data-ttu-id="38fd8-149">注释</span><span class="sxs-lookup"><span data-stu-id="38fd8-149">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="38fd8-150">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-150">Interchange Sender ID</span></span>|<span data-ttu-id="38fd8-151">交换收件人</span><span class="sxs-lookup"><span data-stu-id="38fd8-151">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="38fd8-152">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-152">Interchange Receiver ID</span></span>|<span data-ttu-id="38fd8-153">交换发件人</span><span class="sxs-lookup"><span data-stu-id="38fd8-153">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="38fd8-154">交换日期</span><span class="sxs-lookup"><span data-stu-id="38fd8-154">Interchange Date</span></span>|-|  
|<span data-ttu-id="38fd8-155">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="38fd8-155">Interchange Control Number</span></span>|<span data-ttu-id="38fd8-156">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-156">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="38fd8-157">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="38fd8-157">Interchange Direction = Receive</span></span>|<span data-ttu-id="38fd8-158">在保留交换方案中是必需的，以便实现唯一性。</span><span class="sxs-lookup"><span data-stu-id="38fd8-158">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="38fd8-159">记录类型</span><span class="sxs-lookup"><span data-stu-id="38fd8-159">Record Type</span></span>|<span data-ttu-id="38fd8-160">交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-160">Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="38fd8-161">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="38fd8-161">The data stored includes:</span></span>  
  
-   <span data-ttu-id="38fd8-162">记录类型 = 交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-162">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="38fd8-163">交换确认方向 = 发送 - 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-163">Interchange ACK Direction = Send- Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-164">交换确认状态 = “已处理”或“已发送” – 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-164">Interchange ACK Status = Processed or Sent – Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-165">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-165">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-166">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-166">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-167">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-167">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-168">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-168">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-169">交换 ACK 控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-169">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-170">交换 ACK 日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-170">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-171">交换 ACK 时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-171">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-172">确认/操作代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-172">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-173">确认注释代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-173">ACK Note Code = Existing Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="38fd8-174">接收管道为每个为了响应入站交换而生成的功能确认存储的数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-174">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="38fd8-175">发送管道在状态报告数据存储区中为其发送的每个功能确认创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="38fd8-175">The send pipeline creates a record in the status report data store for each functional acknowledgment that it sends.</span></span> <span data-ttu-id="38fd8-176">发送管道在状态报告数据存储区为其发送的每个功能确认（为了响应收到的交换）创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="38fd8-176">The send pipeline creates a record of each functional acknowledgment sent (in response to an interchange received) in the status report data store.</span></span> <span data-ttu-id="38fd8-177">如果 EDIFACT 中不存在任何组，仍然会创建一个功能确认。</span><span class="sxs-lookup"><span data-stu-id="38fd8-177">If no group is present in EDIFACT, one functional ACK will still be created.</span></span> <span data-ttu-id="38fd8-178">将使用功能组标头/尾部（GS/GE 或 UNG/UNE）中的数据填充功能确认状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="38fd8-178">The functional ACK status report entry will be populated from the functional group header/trailer (GS/GE or UNG/UNE).</span></span> <span data-ttu-id="38fd8-179">技术确认是 997 X12 和完整 CONTRL 消息 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="38fd8-179">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="38fd8-180">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="38fd8-180">The data stored includes:</span></span>  
  
-   <span data-ttu-id="38fd8-181">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-181">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="38fd8-182">功能确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="38fd8-182">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="38fd8-183">功能 ACK 状态 =\<预期或不适用 >。</span><span class="sxs-lookup"><span data-stu-id="38fd8-183">Functional ACK Status = \< Expected or Not Applicable>.</span></span> <span data-ttu-id="38fd8-184">如果选中了 PAM 中的功能确认选项卡，则状态将设置为“预期”。</span><span class="sxs-lookup"><span data-stu-id="38fd8-184">If the functional acknowledgment tab in PAM is selected, status will set to Expected.</span></span> <span data-ttu-id="38fd8-185">否则，状态将设置为“不可用”。</span><span class="sxs-lookup"><span data-stu-id="38fd8-185">Otherwise, status will be set to Not Applicable.</span></span>  
  
-   <span data-ttu-id="38fd8-186">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-186">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-187">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-187">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-188">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-188">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-189">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-189">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="38fd8-190">组控制编号 = 更新数据（对于关联是必需的。</span><span class="sxs-lookup"><span data-stu-id="38fd8-190">Group Control Number = Update Data (required for correlation.</span></span> <span data-ttu-id="38fd8-191">在 EDIFACT 中，如果不存在任何组段，则使用 UNH.1 对此字段进行赋值）</span><span class="sxs-lookup"><span data-stu-id="38fd8-191">In EDIFACT if no group segments present this field is valued using UNH.1)</span></span>  
  
-   <span data-ttu-id="38fd8-192">功能 ID 代码 = 更新数据（如果不存在组，则在 EDIFACT 中不赋值）</span><span class="sxs-lookup"><span data-stu-id="38fd8-192">Functional ID Code = Update Data (not valued in EDIFACT if group is not present)</span></span>  
  
-   <span data-ttu-id="38fd8-193">事务集的计数 = 数据（在 EDIFACT 中，映射到 UNE.1 并且 UNG/UNE 存在；如果不存在任何组段，则映射到 UNZ.1）</span><span class="sxs-lookup"><span data-stu-id="38fd8-193">Count of Transaction Sets = Data (in EDIFACT this is mapped to UNE.1 while UNG/UNE are present or UNZ.1 if no group segments are present)</span></span>  
  
-   <span data-ttu-id="38fd8-194">功能 ACK 交换的控件 ID =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-194">Functional ACK Interchange Control ID= \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-195">功能 ACK 交换日期 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-195">Functional ACK Interchange Date = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-196">功能 ACK 交换时间 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-196">Functional ACK Interchange Time = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-197">计数的事务集传递 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-197">Count of Transaction Sets Delivered = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-198">计数的事务集接受 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-198">Count of Transaction Sets Accepted = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-199">确认/操作代码 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-199">ACK/Action Code = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-200">错误/语法错误代码 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-200">Error/Syntax Error Code  = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-201">其他 X12 ACK 错误代码 2 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-201">Additional X12 ACK Error Code 2 = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-202">其他 X12 ACK 错误代码 3 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-202">Additional X12 ACK Error Code 3 = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-203">其他 X12 ACK 错误代码 4 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-203">Additional X12 ACK Error Code 4 = \<not valued></span></span>  
  
-   <span data-ttu-id="38fd8-204">其他 X12 ACK 错误代码 5 =\<不值 ></span><span class="sxs-lookup"><span data-stu-id="38fd8-204">Additional X12 ACK Error Code 5 = \<not valued></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="38fd8-205">发送管道为每个为了响应入站交换而生成的功能确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-205">Data Updated by the Send Pipeline for Each Functional Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="38fd8-206">对于发送管道发送的每个功能确认，发送管道会更新所接收相关交换的状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="38fd8-206">For each functional acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="38fd8-207">数据的来源为发送管道创建的交换信封。</span><span class="sxs-lookup"><span data-stu-id="38fd8-207">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="38fd8-208">EDI 组装器使用传入的确认的交换和组标头段中的数据来定位数据存储中的记录：</span><span class="sxs-lookup"><span data-stu-id="38fd8-208">The EDI Assembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="38fd8-209">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="38fd8-209">Fields in ACK</span></span>|<span data-ttu-id="38fd8-210">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="38fd8-210">Fields in Data store</span></span>|<span data-ttu-id="38fd8-211">注释</span><span class="sxs-lookup"><span data-stu-id="38fd8-211">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="38fd8-212">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-212">Interchange Sender ID</span></span>|<span data-ttu-id="38fd8-213">交换收件人</span><span class="sxs-lookup"><span data-stu-id="38fd8-213">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="38fd8-214">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-214">Interchange Receiver ID</span></span>|<span data-ttu-id="38fd8-215">交换发件人</span><span class="sxs-lookup"><span data-stu-id="38fd8-215">Interchange Sender</span></span>|-|  
|<span data-ttu-id="38fd8-216">交换日期</span><span class="sxs-lookup"><span data-stu-id="38fd8-216">Interchange Date</span></span>|<span data-ttu-id="38fd8-217">交换日期</span><span class="sxs-lookup"><span data-stu-id="38fd8-217">Interchange Date</span></span>|-|  
|<span data-ttu-id="38fd8-218">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="38fd8-218">Interchange Control Number</span></span>|<span data-ttu-id="38fd8-219">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="38fd8-219">Interchange Control ID</span></span>|-|  
|<span data-ttu-id="38fd8-220">组控制编号</span><span class="sxs-lookup"><span data-stu-id="38fd8-220">Group Control Number</span></span>|<span data-ttu-id="38fd8-221">组控制编号</span><span class="sxs-lookup"><span data-stu-id="38fd8-221">Group Control Number</span></span>|<span data-ttu-id="38fd8-222">在 EDIFACT 中可选</span><span class="sxs-lookup"><span data-stu-id="38fd8-222">Optional in EDIFACT</span></span>|  
|-|<span data-ttu-id="38fd8-223">交换方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="38fd8-223">Interchange Direction = Receive</span></span>|<span data-ttu-id="38fd8-224">在保留交换方案中是必需的，以便实现唯一性。</span><span class="sxs-lookup"><span data-stu-id="38fd8-224">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="38fd8-225">记录类型</span><span class="sxs-lookup"><span data-stu-id="38fd8-225">Record Type</span></span>|<span data-ttu-id="38fd8-226">功能确认状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-226">Functional ACK Status</span></span>|-|  
  
 <span data-ttu-id="38fd8-227">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="38fd8-227">The data stored includes:</span></span>  
  
-   <span data-ttu-id="38fd8-228">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="38fd8-228">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="38fd8-229">功能确认方向 = 发送 - 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-229">Functional ACK Direction = Send – Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-230">功能确认状态 = 已处理/已发送 – 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-230">Functional ACK Status = Sent/Processed – Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-231">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-231">Interchange Receiver =  Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-232">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-232">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-233">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-233">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-234">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-234">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-235">组控制编号 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-235">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-236">功能 ID 代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-236">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-237">事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-237">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-238">功能确认交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-238">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-239">功能确认交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-239">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-240">功能确认交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-240">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="38fd8-241">接收的事务集的计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-241">Count of Transaction Sets Received = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-242">接受的事务集的计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-242">Count of Transaction Sets Accepted = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-243">确认/操作代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-243">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-244">错误/语法错误代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-244">Error/Syntax Error Code  = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-245">附加 X12 确认错误代码 2 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-245">Additional X12 ACK Error Code 2 = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-246">其他 X12 ACK 错误代码 3 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-246">Additional X12 ACK Error Code 3 = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-247">其他 X12 ACK 错误代码 4 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-247">Additional X12 ACK Error Code 4 = Existing Data</span></span>  
  
-   <span data-ttu-id="38fd8-248">其他 X12 ACK 错误代码 5 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="38fd8-248">Additional X12 ACK Error Code 5 = Existing Data</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fd8-249">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38fd8-249">See Also</span></span>  
 <span data-ttu-id="38fd8-250">[如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="38fd8-250">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="38fd8-251">如何将数据存储用于出站 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="38fd8-251">How Data Is Stored for Outbound EDI Messages</span></span>](../core/how-data-is-stored-for-outbound-edi-messages.md)