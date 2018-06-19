---
title: 如何将数据存储用于出站 EDI 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6e576fc-37fd-417d-ae68-607a0a8bcc0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98d5113c63e29f3f4b85834b7ca1aa0836d0a5d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25975817"
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a><span data-ttu-id="13b08-102">出站 EDI 消息数据的存储方式</span><span class="sxs-lookup"><span data-stu-id="13b08-102">How Data Is Stored for Outbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="13b08-103"> 执行以下操作来生成状态报表项的出站交换：</span><span class="sxs-lookup"><span data-stu-id="13b08-103"> does the following to generate a status report entry for an outbound interchange:</span></span>  
  
1.  <span data-ttu-id="13b08-104">当出站消息 XML 发送到 EDI 发送管道时，发送管道中的状态报告具有以下值的数据存储区创建一项︰</span><span class="sxs-lookup"><span data-stu-id="13b08-104">When outbound message XML is sent to the EDI send pipeline, the send pipeline creates an entry in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="13b08-105">交换状态条目将设置为处理</span><span class="sxs-lookup"><span data-stu-id="13b08-105">Interchange status entry is set to Processed</span></span>  
  
    -   <span data-ttu-id="13b08-106">交换 ACK 状态条目 （交换每一个） 设置为预期</span><span class="sxs-lookup"><span data-stu-id="13b08-106">Interchange ACK status entry (one per interchange) is set to Expected</span></span>  
  
    -   <span data-ttu-id="13b08-107">（一个每个组中的 X12，一个用于 EDIFACT 中的所有组） 的功能 ACK 状态条目已设置为预期</span><span class="sxs-lookup"><span data-stu-id="13b08-107">Functional ACK status entries (one per group in X12, one for all groups in EDIFACT) are set to Expected</span></span>  
  
2.  <span data-ttu-id="13b08-108">在 edi 消息具有已发送到贸易合作伙伴，并且确认已返回从贸易合作伙伴，交换状态、 交换 ACK 状态和功能的 ACK 状态条目向已接受/部分接受/拒绝，根据需要，EDI 接收管道接收确认的更新。</span><span class="sxs-lookup"><span data-stu-id="13b08-108">After the EDI message has been sent to the trading partner, and the acknowledgment has been returned from the trading partner, the EDI receive pipeline that receives the acknowledgment updates the Interchange status, the Interchange ACK status, and the Functional ACK status entries to Accepted/Partially Accepted/Rejected, as appropriate.</span></span>  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a><span data-ttu-id="13b08-109">存储发送管道的出站的交换的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-109">Data Stored by the Send Pipeline for Outbound Interchanges</span></span>  
 <span data-ttu-id="13b08-110">发送管道发送每个交换的状态报表数据存储区中创建记录。</span><span class="sxs-lookup"><span data-stu-id="13b08-110">The send pipeline creates a record in the status report data store for each interchange that it sends.</span></span> <span data-ttu-id="13b08-111">所需的项的大多数数据是可从交换标头/预告片段 （ISA/IEA 或 UNB/UNZ）。</span><span class="sxs-lookup"><span data-stu-id="13b08-111">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="13b08-112">从发送端口属性提供了其他数据。</span><span class="sxs-lookup"><span data-stu-id="13b08-112">Other data is available from send port properties.</span></span> <span data-ttu-id="13b08-113">存储的数据包括︰</span><span class="sxs-lookup"><span data-stu-id="13b08-113">The data stored includes:</span></span>  
  
-   <span data-ttu-id="13b08-114">记录类型 = 交换状态</span><span class="sxs-lookup"><span data-stu-id="13b08-114">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="13b08-115">交换方向 = 更新数据 = 发送</span><span class="sxs-lookup"><span data-stu-id="13b08-115">Interchange Direction = Update Data = Send</span></span>  
  
-   <span data-ttu-id="13b08-116">交换接收器 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-116">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-117">交换发件人 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-117">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-118">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-118">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-119">交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-119">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-120">交换控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-120">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-121">交换︰ 处理/发送状态。</span><span class="sxs-lookup"><span data-stu-id="13b08-121">Interchange Status: Processed/Sent.</span></span> <span data-ttu-id="13b08-122">处理状态指示已成功处理该交换和设备移交给传递发送适配器发送管道。</span><span class="sxs-lookup"><span data-stu-id="13b08-122">A status of Processed indicates that the send pipeline has successfully processed the interchange and handed it over to the send adapter for delivery.</span></span>  
  
-   <span data-ttu-id="13b08-123">交换控件计数 (组/消息中的 X12 分别) = 数据</span><span class="sxs-lookup"><span data-stu-id="13b08-123">Interchange Control Count (Groups/Messages in X12 respectively) = Data</span></span>  
  
-   <span data-ttu-id="13b08-124">交换发送端口 ID = 数据</span><span class="sxs-lookup"><span data-stu-id="13b08-124">Interchange Send Port ID = Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="13b08-125">存储的每个对的出站交换响应中收到的技术确认接收管道的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-125">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="13b08-126">接收管道在每个技术确认它收到的状态报表数据存储中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="13b08-126">The receive pipeline creates a record in the status report data store for each technical acknowledgment that it receives.</span></span> <span data-ttu-id="13b08-127">接收管道创建一条记录的每个状态报表数据存储区中收到的交换。</span><span class="sxs-lookup"><span data-stu-id="13b08-127">The receive pipeline creates a record of each interchange received in the status report data store.</span></span> <span data-ttu-id="13b08-128">在每个技术 ACK 作为响应发送到贸易合作伙伴交换接收的数据存储中创建一个技术确认状态报表项。</span><span class="sxs-lookup"><span data-stu-id="13b08-128">creates one technical acknowledgment status report entry in the data store for each technical ACK received as a response to an interchange sent to a trading partner.</span></span> <span data-ttu-id="13b08-129">技术确认是使用仅对于 EDIFACT 了 UCI 段 X12 和 CONTRL 消息 TA1。</span><span class="sxs-lookup"><span data-stu-id="13b08-129">The technical acknowledge is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="13b08-130">存储的数据包括︰</span><span class="sxs-lookup"><span data-stu-id="13b08-130">The data stored includes:</span></span>  
  
-   <span data-ttu-id="13b08-131">记录类型 = 交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="13b08-131">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="13b08-132">交换 ACK 方向 = 发送 – 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-132">Interchange ACK Direction = Send – Update Data</span></span>  
  
-   <span data-ttu-id="13b08-133">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-133">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-134">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-134">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-135">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="13b08-135">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="13b08-136">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-136">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-137">交换 ACK 状态 = 生成或不适用\<注意 0，请参阅\>-更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-137">Interchange ACK Status = Generated or Not Applicable \<Refer Note 0\> - Update Data</span></span>  
  
-   <span data-ttu-id="13b08-138">交换 ACK 控件 ID = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-138">Interchange ACK Control ID= Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-139">交换 ACK 日期 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-139">Interchange ACK Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-140">交换 ACK 时间 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-140">Interchange ACK Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-141">确认/操作代码 = 更新数据\<，请参阅备注 1\> （来自 X12 TA104 或 EDIFACT UCI4） \*</span><span class="sxs-lookup"><span data-stu-id="13b08-141">ACK/Action Code = Update Data  \<refer note 1\> (from X12-TA104 or EDIFACT-UCI4)\*</span></span>  
  
-   <span data-ttu-id="13b08-142">ACK 注意代码 = 更新数据\<，请参阅备注 2\> （从 X12-TA105，不适用于 EDIFACT) \*</span><span class="sxs-lookup"><span data-stu-id="13b08-142">ACK Note Code = Update Data \<Refer Note 2\> (from X12-TA105, not applicable for EDIFACT)\*</span></span>  
  
 <span data-ttu-id="13b08-143">使用以下确认/操作代码︰</span><span class="sxs-lookup"><span data-stu-id="13b08-143">The following ACK/Action Codes are used:</span></span>  
  
|<span data-ttu-id="13b08-144">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-144">Data in ACK/Action Code</span></span>|<span data-ttu-id="13b08-145">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-145">Error description for Reporting</span></span>|<span data-ttu-id="13b08-146">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="13b08-146">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="13b08-147">指向</span><span class="sxs-lookup"><span data-stu-id="13b08-147">A</span></span>|<span data-ttu-id="13b08-148">已接受</span><span class="sxs-lookup"><span data-stu-id="13b08-148">Accepted</span></span>|<span data-ttu-id="13b08-149">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-149">X12</span></span>|  
|<span data-ttu-id="13b08-150">E</span><span class="sxs-lookup"><span data-stu-id="13b08-150">E</span></span>|<span data-ttu-id="13b08-151">记下的已被接受，错误</span><span class="sxs-lookup"><span data-stu-id="13b08-151">Accepted, errors noted</span></span>|<span data-ttu-id="13b08-152">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-152">X12</span></span>|  
|<span data-ttu-id="13b08-153">P</span><span class="sxs-lookup"><span data-stu-id="13b08-153">P</span></span>|<span data-ttu-id="13b08-154">部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-154">Partially Accepted</span></span>|<span data-ttu-id="13b08-155">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-155">X12</span></span>|  
|<span data-ttu-id="13b08-156">R</span><span class="sxs-lookup"><span data-stu-id="13b08-156">R</span></span>|<span data-ttu-id="13b08-157">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-157">Rejected</span></span>|<span data-ttu-id="13b08-158">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-158">X12</span></span>|  
|<span data-ttu-id="13b08-159">4</span><span class="sxs-lookup"><span data-stu-id="13b08-159">4</span></span>|<span data-ttu-id="13b08-160">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-160">Rejected</span></span>|<span data-ttu-id="13b08-161">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-161">EDIFACT</span></span>|  
|<span data-ttu-id="13b08-162">8</span><span class="sxs-lookup"><span data-stu-id="13b08-162">8</span></span>|<span data-ttu-id="13b08-163">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-163">Accepted/Partially Accepted</span></span>|<span data-ttu-id="13b08-164">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-164">EDIFACT</span></span>|  
  
 <span data-ttu-id="13b08-165">使用以下 ACK 注意代码︰</span><span class="sxs-lookup"><span data-stu-id="13b08-165">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="13b08-166">（在 X12) 的 ACK 注意代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-166">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="13b08-167">Description</span><span class="sxs-lookup"><span data-stu-id="13b08-167">Description</span></span>|  
|--------------------------------------|-----------------|  
|<span data-ttu-id="13b08-168">000</span><span class="sxs-lookup"><span data-stu-id="13b08-168">000</span></span>|<span data-ttu-id="13b08-169">成功</span><span class="sxs-lookup"><span data-stu-id="13b08-169">Success</span></span>|  
|<span data-ttu-id="13b08-170">001</span><span class="sxs-lookup"><span data-stu-id="13b08-170">001</span></span>|<span data-ttu-id="13b08-171">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-171">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="13b08-172">002</span><span class="sxs-lookup"><span data-stu-id="13b08-172">002</span></span>|<span data-ttu-id="13b08-173">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="13b08-173">Standard not supported</span></span>|  
|<span data-ttu-id="13b08-174">003</span><span class="sxs-lookup"><span data-stu-id="13b08-174">003</span></span>|<span data-ttu-id="13b08-175">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="13b08-175">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="13b08-176">004</span><span class="sxs-lookup"><span data-stu-id="13b08-176">004</span></span>|<span data-ttu-id="13b08-177">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-177">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="13b08-178">005</span><span class="sxs-lookup"><span data-stu-id="13b08-178">005</span></span>|<span data-ttu-id="13b08-179">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-179">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="13b08-180">006</span><span class="sxs-lookup"><span data-stu-id="13b08-180">006</span></span>|<span data-ttu-id="13b08-181">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="13b08-181">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="13b08-182">007</span><span class="sxs-lookup"><span data-stu-id="13b08-182">007</span></span>|<span data-ttu-id="13b08-183">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-183">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="13b08-184">008</span><span class="sxs-lookup"><span data-stu-id="13b08-184">008</span></span>|<span data-ttu-id="13b08-185">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="13b08-185">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="13b08-186">009</span><span class="sxs-lookup"><span data-stu-id="13b08-186">009</span></span>|<span data-ttu-id="13b08-187">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-187">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="13b08-188">010</span><span class="sxs-lookup"><span data-stu-id="13b08-188">010</span></span>|<span data-ttu-id="13b08-189">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="13b08-189">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="13b08-190">011</span><span class="sxs-lookup"><span data-stu-id="13b08-190">011</span></span>|<span data-ttu-id="13b08-191">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="13b08-191">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="13b08-192">012</span><span class="sxs-lookup"><span data-stu-id="13b08-192">012</span></span>|<span data-ttu-id="13b08-193">无效的安全信息限定符值</span><span class="sxs-lookup"><span data-stu-id="13b08-193">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="13b08-194">013</span><span class="sxs-lookup"><span data-stu-id="13b08-194">013</span></span>|<span data-ttu-id="13b08-195">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="13b08-195">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="13b08-196">014</span><span class="sxs-lookup"><span data-stu-id="13b08-196">014</span></span>|<span data-ttu-id="13b08-197">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="13b08-197">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="13b08-198">015</span><span class="sxs-lookup"><span data-stu-id="13b08-198">015</span></span>|<span data-ttu-id="13b08-199">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="13b08-199">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="13b08-200">016</span><span class="sxs-lookup"><span data-stu-id="13b08-200">016</span></span>|<span data-ttu-id="13b08-201">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="13b08-201">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="13b08-202">017</span><span class="sxs-lookup"><span data-stu-id="13b08-202">017</span></span>|<span data-ttu-id="13b08-203">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="13b08-203">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="13b08-204">018</span><span class="sxs-lookup"><span data-stu-id="13b08-204">018</span></span>|<span data-ttu-id="13b08-205">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="13b08-205">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="13b08-206">019</span><span class="sxs-lookup"><span data-stu-id="13b08-206">019</span></span>|<span data-ttu-id="13b08-207">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="13b08-207">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="13b08-208">020</span><span class="sxs-lookup"><span data-stu-id="13b08-208">020</span></span>|<span data-ttu-id="13b08-209">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="13b08-209">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="13b08-210">021</span><span class="sxs-lookup"><span data-stu-id="13b08-210">021</span></span>|<span data-ttu-id="13b08-211">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="13b08-211">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="13b08-212">022</span><span class="sxs-lookup"><span data-stu-id="13b08-212">022</span></span>|<span data-ttu-id="13b08-213">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="13b08-213">Invalid Control Structure</span></span>|  
|<span data-ttu-id="13b08-214">023</span><span class="sxs-lookup"><span data-stu-id="13b08-214">023</span></span>|<span data-ttu-id="13b08-215">不正确文件尾</span><span class="sxs-lookup"><span data-stu-id="13b08-215">Improper End-of-File</span></span>|  
|<span data-ttu-id="13b08-216">024</span><span class="sxs-lookup"><span data-stu-id="13b08-216">024</span></span>|<span data-ttu-id="13b08-217">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="13b08-217">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="13b08-218">025</span><span class="sxs-lookup"><span data-stu-id="13b08-218">025</span></span>|<span data-ttu-id="13b08-219">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="13b08-219">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="13b08-220">026</span><span class="sxs-lookup"><span data-stu-id="13b08-220">026</span></span>|<span data-ttu-id="13b08-221">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-221">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="13b08-222">027</span><span class="sxs-lookup"><span data-stu-id="13b08-222">027</span></span>|<span data-ttu-id="13b08-223">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-223">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="13b08-224">028</span><span class="sxs-lookup"><span data-stu-id="13b08-224">028</span></span>|<span data-ttu-id="13b08-225">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="13b08-225">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="13b08-226">029</span><span class="sxs-lookup"><span data-stu-id="13b08-226">029</span></span>|<span data-ttu-id="13b08-227">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="13b08-227">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="13b08-228">030</span><span class="sxs-lookup"><span data-stu-id="13b08-228">030</span></span>|<span data-ttu-id="13b08-229">延迟的传递请求中的无效传递时代码</span><span class="sxs-lookup"><span data-stu-id="13b08-229">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="13b08-230">031</span><span class="sxs-lookup"><span data-stu-id="13b08-230">031</span></span>|<span data-ttu-id="13b08-231">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="13b08-231">Invalid Grade of Service</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="13b08-232">接收管道针对每个技术确认对出站交换响应中收到的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-232">Data Updated by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="13b08-233">为每个接收管道接收的技术确认，它会更新状态报表项时为关联的已发送交换。</span><span class="sxs-lookup"><span data-stu-id="13b08-233">For each technical acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="13b08-234">EDI 拆装器定位在数据存储，如下所示使用 UCI 和的传入确认，TA1 段中的数据的记录︰</span><span class="sxs-lookup"><span data-stu-id="13b08-234">The EDI Disassembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="13b08-235">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="13b08-235">Fields in ACK</span></span>|<span data-ttu-id="13b08-236">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="13b08-236">Fields in Data store</span></span>|<span data-ttu-id="13b08-237">注释</span><span class="sxs-lookup"><span data-stu-id="13b08-237">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="13b08-238">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-238">Interchange Sender ID</span></span>|<span data-ttu-id="13b08-239">交换收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-239">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="13b08-240">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-240">Interchange Receiver ID</span></span>|<span data-ttu-id="13b08-241">交换发件人</span><span class="sxs-lookup"><span data-stu-id="13b08-241">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="13b08-242">交换日期</span><span class="sxs-lookup"><span data-stu-id="13b08-242">Interchange Date</span></span>|-|  
|<span data-ttu-id="13b08-243">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="13b08-243">Interchange Control Number</span></span>|<span data-ttu-id="13b08-244">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-244">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="13b08-245">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="13b08-245">Interchange Direction = Send</span></span>|<span data-ttu-id="13b08-246">在保留的批处理方案唯一性必需的</span><span class="sxs-lookup"><span data-stu-id="13b08-246">Required in preserved batch scenario for uniqueness</span></span>|  
|<span data-ttu-id="13b08-247">记录类型</span><span class="sxs-lookup"><span data-stu-id="13b08-247">Record Type</span></span>|<span data-ttu-id="13b08-248">交换状态和交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="13b08-248">Interchange Status and Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="13b08-249">存储的数据包括︰</span><span class="sxs-lookup"><span data-stu-id="13b08-249">The data stored includes:</span></span>  
  
-   <span data-ttu-id="13b08-250">交换 ACK 方向 = 接收 – 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-250">Interchange ACK Direction = Receive – Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-251">交换 ACK 状态 = 收到</span><span class="sxs-lookup"><span data-stu-id="13b08-251">Interchange ACK Status = Received</span></span>  
  
-   <span data-ttu-id="13b08-252">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-252">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-253">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-253">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-254">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-254">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-255">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-255">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-256">交换 ACK 控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-256">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="13b08-257">交换 ACK 日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-257">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-258">交换 ACK 时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-258">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-259">确认/操作代码 = 更新数据 （来自 X12 TA104 或 EDIFACT UCI4） \* \<，请参阅备注 1\></span><span class="sxs-lookup"><span data-stu-id="13b08-259">ACK/Action Code = Update Data (from X12-TA104 or EDIFACT-UCI4)\* \<Refer Note 1\></span></span>  
  
-   <span data-ttu-id="13b08-260">ACK 注意代码 2 = 更新数据 (从 X12 TA105 和不值对于 EDIFACT) \* \<，请参阅备注 2\></span><span class="sxs-lookup"><span data-stu-id="13b08-260">ACK Note Code 2 = Update Data (from X12-TA105 and not valued for EDIFACT)\* \<Refer Note 2\></span></span>  
  
 <span data-ttu-id="13b08-261">ACK X12 中的数据︰ TA1 104 或 EDIFACT UCI4 是，如下所示映射︰</span><span class="sxs-lookup"><span data-stu-id="13b08-261">The data from the ACK X12:TA1-104 or EDIFACT UCI4 is to be mapped as follows:</span></span>  
  
|<span data-ttu-id="13b08-262">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-262">Data in ACK/Action Code</span></span>|<span data-ttu-id="13b08-263">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="13b08-263">Mapped for Status Reporting</span></span>|<span data-ttu-id="13b08-264">注释</span><span class="sxs-lookup"><span data-stu-id="13b08-264">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="13b08-265">指向</span><span class="sxs-lookup"><span data-stu-id="13b08-265">A</span></span>|<span data-ttu-id="13b08-266">已接受</span><span class="sxs-lookup"><span data-stu-id="13b08-266">Accepted</span></span>|<span data-ttu-id="13b08-267">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-267">X12</span></span>|  
|<span data-ttu-id="13b08-268">P</span><span class="sxs-lookup"><span data-stu-id="13b08-268">P</span></span>|<span data-ttu-id="13b08-269">部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-269">Partially Accepted</span></span>|<span data-ttu-id="13b08-270">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-270">X12</span></span>|  
|<span data-ttu-id="13b08-271">R、 M、 W 和 X</span><span class="sxs-lookup"><span data-stu-id="13b08-271">R, M, W, X</span></span>|<span data-ttu-id="13b08-272">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-272">Rejected</span></span>|<span data-ttu-id="13b08-273">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-273">X12</span></span>|  
|<span data-ttu-id="13b08-274">E</span><span class="sxs-lookup"><span data-stu-id="13b08-274">E</span></span>|<span data-ttu-id="13b08-275">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="13b08-275">Accepted with errors</span></span>|<span data-ttu-id="13b08-276">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-276">X12</span></span>|  
|<span data-ttu-id="13b08-277">4</span><span class="sxs-lookup"><span data-stu-id="13b08-277">4</span></span>|<span data-ttu-id="13b08-278">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-278">Rejected</span></span>|<span data-ttu-id="13b08-279">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-279">EDIFACT</span></span>|  
|<span data-ttu-id="13b08-280">7, 8</span><span class="sxs-lookup"><span data-stu-id="13b08-280">7, 8</span></span>|<span data-ttu-id="13b08-281">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-281">Accepted/Partially Accepted</span></span>|<span data-ttu-id="13b08-282">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-282">EDIFACT</span></span>|  
  
 <span data-ttu-id="13b08-283">使用以下 ACK 注意代码︰</span><span class="sxs-lookup"><span data-stu-id="13b08-283">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="13b08-284">（在 X12) 的 ACK 注意代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-284">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="13b08-285">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="13b08-285">Mapped for Status Reporting</span></span>|  
|--------------------------------------|---------------------------------|  
|<span data-ttu-id="13b08-286">000</span><span class="sxs-lookup"><span data-stu-id="13b08-286">000</span></span>|<span data-ttu-id="13b08-287">成功</span><span class="sxs-lookup"><span data-stu-id="13b08-287">Success</span></span>|  
|<span data-ttu-id="13b08-288">001</span><span class="sxs-lookup"><span data-stu-id="13b08-288">001</span></span>|<span data-ttu-id="13b08-289">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-289">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="13b08-290">002</span><span class="sxs-lookup"><span data-stu-id="13b08-290">002</span></span>|<span data-ttu-id="13b08-291">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="13b08-291">Standard not supported</span></span>|  
|<span data-ttu-id="13b08-292">003</span><span class="sxs-lookup"><span data-stu-id="13b08-292">003</span></span>|<span data-ttu-id="13b08-293">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="13b08-293">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="13b08-294">004</span><span class="sxs-lookup"><span data-stu-id="13b08-294">004</span></span>|<span data-ttu-id="13b08-295">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-295">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="13b08-296">005</span><span class="sxs-lookup"><span data-stu-id="13b08-296">005</span></span>|<span data-ttu-id="13b08-297">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-297">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="13b08-298">006</span><span class="sxs-lookup"><span data-stu-id="13b08-298">006</span></span>|<span data-ttu-id="13b08-299">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="13b08-299">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="13b08-300">007</span><span class="sxs-lookup"><span data-stu-id="13b08-300">007</span></span>|<span data-ttu-id="13b08-301">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-301">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="13b08-302">008</span><span class="sxs-lookup"><span data-stu-id="13b08-302">008</span></span>|<span data-ttu-id="13b08-303">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="13b08-303">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="13b08-304">009</span><span class="sxs-lookup"><span data-stu-id="13b08-304">009</span></span>|<span data-ttu-id="13b08-305">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-305">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="13b08-306">010</span><span class="sxs-lookup"><span data-stu-id="13b08-306">010</span></span>|<span data-ttu-id="13b08-307">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="13b08-307">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="13b08-308">011</span><span class="sxs-lookup"><span data-stu-id="13b08-308">011</span></span>|<span data-ttu-id="13b08-309">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="13b08-309">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="13b08-310">012</span><span class="sxs-lookup"><span data-stu-id="13b08-310">012</span></span>|<span data-ttu-id="13b08-311">无效的安全信息限定符值</span><span class="sxs-lookup"><span data-stu-id="13b08-311">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="13b08-312">013</span><span class="sxs-lookup"><span data-stu-id="13b08-312">013</span></span>|<span data-ttu-id="13b08-313">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="13b08-313">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="13b08-314">014</span><span class="sxs-lookup"><span data-stu-id="13b08-314">014</span></span>|<span data-ttu-id="13b08-315">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="13b08-315">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="13b08-316">015</span><span class="sxs-lookup"><span data-stu-id="13b08-316">015</span></span>|<span data-ttu-id="13b08-317">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="13b08-317">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="13b08-318">016</span><span class="sxs-lookup"><span data-stu-id="13b08-318">016</span></span>|<span data-ttu-id="13b08-319">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="13b08-319">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="13b08-320">017</span><span class="sxs-lookup"><span data-stu-id="13b08-320">017</span></span>|<span data-ttu-id="13b08-321">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="13b08-321">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="13b08-322">018</span><span class="sxs-lookup"><span data-stu-id="13b08-322">018</span></span>|<span data-ttu-id="13b08-323">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="13b08-323">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="13b08-324">019</span><span class="sxs-lookup"><span data-stu-id="13b08-324">019</span></span>|<span data-ttu-id="13b08-325">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="13b08-325">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="13b08-326">020</span><span class="sxs-lookup"><span data-stu-id="13b08-326">020</span></span>|<span data-ttu-id="13b08-327">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="13b08-327">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="13b08-328">021</span><span class="sxs-lookup"><span data-stu-id="13b08-328">021</span></span>|<span data-ttu-id="13b08-329">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="13b08-329">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="13b08-330">022</span><span class="sxs-lookup"><span data-stu-id="13b08-330">022</span></span>|<span data-ttu-id="13b08-331">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="13b08-331">Invalid Control Structure</span></span>|  
|<span data-ttu-id="13b08-332">023</span><span class="sxs-lookup"><span data-stu-id="13b08-332">023</span></span>|<span data-ttu-id="13b08-333">不正确文件尾</span><span class="sxs-lookup"><span data-stu-id="13b08-333">Improper End-of-File</span></span>|  
|<span data-ttu-id="13b08-334">024</span><span class="sxs-lookup"><span data-stu-id="13b08-334">024</span></span>|<span data-ttu-id="13b08-335">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="13b08-335">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="13b08-336">025</span><span class="sxs-lookup"><span data-stu-id="13b08-336">025</span></span>|<span data-ttu-id="13b08-337">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="13b08-337">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="13b08-338">026</span><span class="sxs-lookup"><span data-stu-id="13b08-338">026</span></span>|<span data-ttu-id="13b08-339">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-339">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="13b08-340">027</span><span class="sxs-lookup"><span data-stu-id="13b08-340">027</span></span>|<span data-ttu-id="13b08-341">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="13b08-341">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="13b08-342">028</span><span class="sxs-lookup"><span data-stu-id="13b08-342">028</span></span>|<span data-ttu-id="13b08-343">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="13b08-343">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="13b08-344">029</span><span class="sxs-lookup"><span data-stu-id="13b08-344">029</span></span>|<span data-ttu-id="13b08-345">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="13b08-345">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="13b08-346">030</span><span class="sxs-lookup"><span data-stu-id="13b08-346">030</span></span>|<span data-ttu-id="13b08-347">延迟的传递请求中的无效传递时代码</span><span class="sxs-lookup"><span data-stu-id="13b08-347">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="13b08-348">031</span><span class="sxs-lookup"><span data-stu-id="13b08-348">031</span></span>|<span data-ttu-id="13b08-349">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="13b08-349">Invalid Grade of Service</span></span>|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a><span data-ttu-id="13b08-350">存储接收管道的每个功能确认对出站交换响应中收到的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-350">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outbound Interchanges</span></span>  
 <span data-ttu-id="13b08-351">接收管道接收每个功能确认的状态报表数据存储区中创建记录。</span><span class="sxs-lookup"><span data-stu-id="13b08-351">The receive pipeline creates a record in the status report data store for each functional acknowledgment that it receives.</span></span>  <span data-ttu-id="13b08-352">技术确认是 997 X12 和完整 CONTRL 消息 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="13b08-352">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="13b08-353">每个组的一个条目将创建。</span><span class="sxs-lookup"><span data-stu-id="13b08-353">One entry per group will to be created.</span></span> <span data-ttu-id="13b08-354">此项时使用的交换和组标头中的数据。</span><span class="sxs-lookup"><span data-stu-id="13b08-354">Data from the interchange and group headers is used while making this entry.</span></span> <span data-ttu-id="13b08-355">存储的数据包括︰</span><span class="sxs-lookup"><span data-stu-id="13b08-355">The data stored includes:</span></span>  
  
-   <span data-ttu-id="13b08-356">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="13b08-356">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="13b08-357">功能 ACK 方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="13b08-357">Functional ACK Direction = Send</span></span>  
  
-   <span data-ttu-id="13b08-358">正常的 ACK 状态 = \<Generated 或不适用，请参阅备注 1\></span><span class="sxs-lookup"><span data-stu-id="13b08-358">Functional ACK Status = \<Generated or Not Applicable, refer note 1\></span></span>  
  
-   <span data-ttu-id="13b08-359">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-359">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-360">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-360">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-361">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="13b08-361">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="13b08-362">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-362">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="13b08-363">组控制编号 = 更新数据 (optional 对于 EDIFACT 和需要 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="13b08-363">Group Control Number = Update Data (‘optional for EDIFACT’ and required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="13b08-364">功能 ID 代码 = 更新数据 (GS01/UNG01)</span><span class="sxs-lookup"><span data-stu-id="13b08-364">Functional ID Code = Update Data (GS01/UNG01)</span></span>  
  
-   <span data-ttu-id="13b08-365">事务集的计数 = 更新数据 (UNE1/UNZ1)</span><span class="sxs-lookup"><span data-stu-id="13b08-365">Count of Transaction Sets = Update Data (UNE1/UNZ1)</span></span>  
  
-   <span data-ttu-id="13b08-366">功能 ACK 交换的控件 ID = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-366">Functional ACK Interchange Control ID= Not value – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-367">功能 ACK 交换日期 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-367">Functional ACK Interchange Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-368">功能 ACK 交换时间 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="13b08-368">Functional ACK Interchange Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="13b08-369">计数的事务集收到 = 更新数据 (X12 AK903 和计算由 EDIFACT 编码的引擎)</span><span class="sxs-lookup"><span data-stu-id="13b08-369">Count of Transaction Sets Received = Update Data (X12-AK903 and computed by Engine for EDIFACT encoding)</span></span>  
  
-   <span data-ttu-id="13b08-370">计数的事务集接受 = 更新数据 (X12 AK904 和计算由引擎 EDIFACT 引擎)</span><span class="sxs-lookup"><span data-stu-id="13b08-370">Count of Transaction Sets Accepted = Update Data (X12-AK904 and computed by Engine for EDIFACT engine)</span></span>  
  
-   <span data-ttu-id="13b08-371">确认/操作代码 = 更新数据\<，请参阅备注 2\> （来自 X12 AK901 或 EDIFACT UCI4） \*</span><span class="sxs-lookup"><span data-stu-id="13b08-371">ACK/Action Code = Update Data  \<refer note 2\> (from X12-AK901 or EDIFACT-UCI4)\*</span></span>  
  
-   <span data-ttu-id="13b08-372">错误/语法错误代码 = 更新数据 (X12 AK905，EDIFACT UCI5) 请注意 3</span><span class="sxs-lookup"><span data-stu-id="13b08-372">Error/Syntax Error Code  = Update Data (X12-AK905, EDIFACT UCI5) Note 3</span></span>  
  
-   <span data-ttu-id="13b08-373">其他 X12 ACK 错误代码 2 = 更新数据 (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="13b08-373">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="13b08-374">其他 X12 ACK 错误代码 3 = 更新数据 (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="13b08-374">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="13b08-375">其他 X12 ACK 错误代码 4 = 更新数据 (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="13b08-375">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="13b08-376">其他 X12 ACK 错误代码 5 = 更新数据 (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="13b08-376">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="13b08-377">将使用以下确认/操作代码︰</span><span class="sxs-lookup"><span data-stu-id="13b08-377">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="13b08-378">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-378">Data in ACK/Action Code</span></span>|<span data-ttu-id="13b08-379">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-379">Error description for Reporting</span></span>|<span data-ttu-id="13b08-380">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="13b08-380">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="13b08-381">指向</span><span class="sxs-lookup"><span data-stu-id="13b08-381">A</span></span>|<span data-ttu-id="13b08-382">已接受</span><span class="sxs-lookup"><span data-stu-id="13b08-382">Accepted</span></span>|<span data-ttu-id="13b08-383">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-383">X12</span></span>|  
|<span data-ttu-id="13b08-384">E</span><span class="sxs-lookup"><span data-stu-id="13b08-384">E</span></span>|<span data-ttu-id="13b08-385">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="13b08-385">Accepted  with errors</span></span>|<span data-ttu-id="13b08-386">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-386">X12</span></span>|  
|<span data-ttu-id="13b08-387">P</span><span class="sxs-lookup"><span data-stu-id="13b08-387">P</span></span>|<span data-ttu-id="13b08-388">部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-388">Partially Accepted</span></span>|<span data-ttu-id="13b08-389">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-389">X12</span></span>|  
|<span data-ttu-id="13b08-390">R</span><span class="sxs-lookup"><span data-stu-id="13b08-390">R</span></span>|<span data-ttu-id="13b08-391">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-391">Rejected</span></span>|<span data-ttu-id="13b08-392">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-392">X12</span></span>|  
|<span data-ttu-id="13b08-393">4</span><span class="sxs-lookup"><span data-stu-id="13b08-393">4</span></span>|<span data-ttu-id="13b08-394">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-394">Rejected</span></span>|<span data-ttu-id="13b08-395">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-395">EDIFACT</span></span>|  
|<span data-ttu-id="13b08-396">7</span><span class="sxs-lookup"><span data-stu-id="13b08-396">7</span></span>|<span data-ttu-id="13b08-397">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-397">Accepted/Partially Accepted</span></span>|<span data-ttu-id="13b08-398">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-398">EDIFACT</span></span>|  
  
 <span data-ttu-id="13b08-399">以下的错误/语法错误代码将用于 EDIFACT:</span><span class="sxs-lookup"><span data-stu-id="13b08-399">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="13b08-400">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="13b08-400">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="13b08-401">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="13b08-401">(applicable to EDIFACT)</span></span>|<span data-ttu-id="13b08-402">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-402">Error Description for reporting</span></span>|  
|--------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="13b08-403">2</span><span class="sxs-lookup"><span data-stu-id="13b08-403">2</span></span>|<span data-ttu-id="13b08-404">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="13b08-404">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="13b08-405">7</span><span class="sxs-lookup"><span data-stu-id="13b08-405">7</span></span>|<span data-ttu-id="13b08-406">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-406">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="13b08-407">12</span><span class="sxs-lookup"><span data-stu-id="13b08-407">12</span></span>|<span data-ttu-id="13b08-408">无效值</span><span class="sxs-lookup"><span data-stu-id="13b08-408">Invalid value</span></span>|  
|<span data-ttu-id="13b08-409">13</span><span class="sxs-lookup"><span data-stu-id="13b08-409">13</span></span>|<span data-ttu-id="13b08-410">缺少</span><span class="sxs-lookup"><span data-stu-id="13b08-410">Missing</span></span>|  
|<span data-ttu-id="13b08-411">14</span><span class="sxs-lookup"><span data-stu-id="13b08-411">14</span></span>|<span data-ttu-id="13b08-412">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="13b08-412">Value not supported in this position</span></span>|  
|<span data-ttu-id="13b08-413">15</span><span class="sxs-lookup"><span data-stu-id="13b08-413">15</span></span>|<span data-ttu-id="13b08-414">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="13b08-414">Not supported in this position</span></span>|  
|<span data-ttu-id="13b08-415">16</span><span class="sxs-lookup"><span data-stu-id="13b08-415">16</span></span>|<span data-ttu-id="13b08-416">组分过多</span><span class="sxs-lookup"><span data-stu-id="13b08-416">Too many constituents</span></span>|  
|<span data-ttu-id="13b08-417">17</span><span class="sxs-lookup"><span data-stu-id="13b08-417">17</span></span>|<span data-ttu-id="13b08-418">无协议</span><span class="sxs-lookup"><span data-stu-id="13b08-418">No agreement</span></span>|  
|<span data-ttu-id="13b08-419">18</span><span class="sxs-lookup"><span data-stu-id="13b08-419">18</span></span>|<span data-ttu-id="13b08-420">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="13b08-420">Unspecified error</span></span>|  
|<span data-ttu-id="13b08-421">19</span><span class="sxs-lookup"><span data-stu-id="13b08-421">19</span></span>|<span data-ttu-id="13b08-422">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="13b08-422">Invalid decimal notation</span></span>|  
|<span data-ttu-id="13b08-423">20</span><span class="sxs-lookup"><span data-stu-id="13b08-423">20</span></span>|<span data-ttu-id="13b08-424">字符无效，因为服务字符</span><span class="sxs-lookup"><span data-stu-id="13b08-424">Character invalid as service character</span></span>|  
|<span data-ttu-id="13b08-425">21</span><span class="sxs-lookup"><span data-stu-id="13b08-425">21</span></span>|<span data-ttu-id="13b08-426">无效字符</span><span class="sxs-lookup"><span data-stu-id="13b08-426">Invalid character(s)</span></span>|  
|<span data-ttu-id="13b08-427">22</span><span class="sxs-lookup"><span data-stu-id="13b08-427">22</span></span>|<span data-ttu-id="13b08-428">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="13b08-428">Invalid service character(s)</span></span>|  
|<span data-ttu-id="13b08-429">23</span><span class="sxs-lookup"><span data-stu-id="13b08-429">23</span></span>|<span data-ttu-id="13b08-430">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="13b08-430">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="13b08-431">24</span><span class="sxs-lookup"><span data-stu-id="13b08-431">24</span></span>|<span data-ttu-id="13b08-432">太旧</span><span class="sxs-lookup"><span data-stu-id="13b08-432">Too old</span></span>|  
|<span data-ttu-id="13b08-433">25</span><span class="sxs-lookup"><span data-stu-id="13b08-433">25</span></span>|<span data-ttu-id="13b08-434">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="13b08-434">Test indicator not supported</span></span>|  
|<span data-ttu-id="13b08-435">26</span><span class="sxs-lookup"><span data-stu-id="13b08-435">26</span></span>|<span data-ttu-id="13b08-436">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="13b08-436">Duplicate detected</span></span>|  
|<span data-ttu-id="13b08-437">27</span><span class="sxs-lookup"><span data-stu-id="13b08-437">27</span></span>|<span data-ttu-id="13b08-438">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="13b08-438">Security function not supported</span></span>|  
|<span data-ttu-id="13b08-439">28</span><span class="sxs-lookup"><span data-stu-id="13b08-439">28</span></span>|<span data-ttu-id="13b08-440">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-440">References do not match</span></span>|  
|<span data-ttu-id="13b08-441">29</span><span class="sxs-lookup"><span data-stu-id="13b08-441">29</span></span>|<span data-ttu-id="13b08-442">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-442">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="13b08-443">30</span><span class="sxs-lookup"><span data-stu-id="13b08-443">30</span></span>|<span data-ttu-id="13b08-444">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="13b08-444">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="13b08-445">31</span><span class="sxs-lookup"><span data-stu-id="13b08-445">31</span></span>|<span data-ttu-id="13b08-446">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="13b08-446">More than one message type in group</span></span>|  
|<span data-ttu-id="13b08-447">32</span><span class="sxs-lookup"><span data-stu-id="13b08-447">32</span></span>|<span data-ttu-id="13b08-448">低级别为空</span><span class="sxs-lookup"><span data-stu-id="13b08-448">Lower level empty</span></span>|  
|<span data-ttu-id="13b08-449">33</span><span class="sxs-lookup"><span data-stu-id="13b08-449">33</span></span>|<span data-ttu-id="13b08-450">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="13b08-450">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="13b08-451">34</span><span class="sxs-lookup"><span data-stu-id="13b08-451">34</span></span>|<span data-ttu-id="13b08-452">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="13b08-452">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="13b08-453">35</span><span class="sxs-lookup"><span data-stu-id="13b08-453">35</span></span>|<span data-ttu-id="13b08-454">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="13b08-454">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="13b08-455">36</span><span class="sxs-lookup"><span data-stu-id="13b08-455">36</span></span>|<span data-ttu-id="13b08-456">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="13b08-456">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="13b08-457">37</span><span class="sxs-lookup"><span data-stu-id="13b08-457">37</span></span>|<span data-ttu-id="13b08-458">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="13b08-458">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="13b08-459">38</span><span class="sxs-lookup"><span data-stu-id="13b08-459">38</span></span>|<span data-ttu-id="13b08-460">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="13b08-460">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="13b08-461">39</span><span class="sxs-lookup"><span data-stu-id="13b08-461">39</span></span>|<span data-ttu-id="13b08-462">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="13b08-462">Data element too long</span></span>|  
|<span data-ttu-id="13b08-463">40</span><span class="sxs-lookup"><span data-stu-id="13b08-463">40</span></span>|<span data-ttu-id="13b08-464">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="13b08-464">Data element too short</span></span>|  
|<span data-ttu-id="13b08-465">41</span><span class="sxs-lookup"><span data-stu-id="13b08-465">41</span></span>|<span data-ttu-id="13b08-466">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="13b08-466">Permanent communication network error</span></span>|  
|<span data-ttu-id="13b08-467">42</span><span class="sxs-lookup"><span data-stu-id="13b08-467">42</span></span>|<span data-ttu-id="13b08-468">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="13b08-468">Temporary communication network error</span></span>|  
|<span data-ttu-id="13b08-469">43</span><span class="sxs-lookup"><span data-stu-id="13b08-469">43</span></span>|<span data-ttu-id="13b08-470">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-470">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="13b08-471">45</span><span class="sxs-lookup"><span data-stu-id="13b08-471">45</span></span>|<span data-ttu-id="13b08-472">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="13b08-472">Trailing separator</span></span>|  
|<span data-ttu-id="13b08-473">46</span><span class="sxs-lookup"><span data-stu-id="13b08-473">46</span></span>|<span data-ttu-id="13b08-474">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="13b08-474">Character set not supported</span></span>|  
|<span data-ttu-id="13b08-475">47</span><span class="sxs-lookup"><span data-stu-id="13b08-475">47</span></span>|<span data-ttu-id="13b08-476">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="13b08-476">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="13b08-477">48</span><span class="sxs-lookup"><span data-stu-id="13b08-477">48</span></span>|<span data-ttu-id="13b08-478">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="13b08-478">Dependency condition violated</span></span>|  
|<span data-ttu-id="13b08-479">70</span><span class="sxs-lookup"><span data-stu-id="13b08-479">70</span></span>|<span data-ttu-id="13b08-480">事务集缺失或无效的事务集标识符</span><span class="sxs-lookup"><span data-stu-id="13b08-480">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="13b08-481">71</span><span class="sxs-lookup"><span data-stu-id="13b08-481">71</span></span>|<span data-ttu-id="13b08-482">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-482">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="13b08-483">72</span><span class="sxs-lookup"><span data-stu-id="13b08-483">72</span></span>|<span data-ttu-id="13b08-484">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-484">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="13b08-485">73</span><span class="sxs-lookup"><span data-stu-id="13b08-485">73</span></span>|<span data-ttu-id="13b08-486">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="13b08-486">XML not at correct position</span></span>|  
|<span data-ttu-id="13b08-487">74</span><span class="sxs-lookup"><span data-stu-id="13b08-487">74</span></span>|<span data-ttu-id="13b08-488">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="13b08-488">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="13b08-489">75</span><span class="sxs-lookup"><span data-stu-id="13b08-489">75</span></span>|<span data-ttu-id="13b08-490">段重复过少</span><span class="sxs-lookup"><span data-stu-id="13b08-490">Too few segment repetitions</span></span>|  
|<span data-ttu-id="13b08-491">76</span><span class="sxs-lookup"><span data-stu-id="13b08-491">76</span></span>|<span data-ttu-id="13b08-492">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="13b08-492">Too few data elements found</span></span>|  
  
 <span data-ttu-id="13b08-493">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="13b08-493">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="13b08-494">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="13b08-494">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="13b08-495">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="13b08-495">(applicable to X12)</span></span>|<span data-ttu-id="13b08-496">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-496">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="13b08-497">1</span><span class="sxs-lookup"><span data-stu-id="13b08-497">1</span></span>|<span data-ttu-id="13b08-498">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="13b08-498">Functional group not supported</span></span>|  
|<span data-ttu-id="13b08-499">2</span><span class="sxs-lookup"><span data-stu-id="13b08-499">2</span></span>|<span data-ttu-id="13b08-500">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="13b08-500">Functional group version not supported</span></span>|  
|<span data-ttu-id="13b08-501">3</span><span class="sxs-lookup"><span data-stu-id="13b08-501">3</span></span>|<span data-ttu-id="13b08-502">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="13b08-502">Functional group trailer missing</span></span>|  
|<span data-ttu-id="13b08-503">4</span><span class="sxs-lookup"><span data-stu-id="13b08-503">4</span></span>|<span data-ttu-id="13b08-504">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="13b08-504">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="13b08-505">5</span><span class="sxs-lookup"><span data-stu-id="13b08-505">5</span></span>|<span data-ttu-id="13b08-506">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-506">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="13b08-507">6-26</span><span class="sxs-lookup"><span data-stu-id="13b08-507">6-26</span></span>|<span data-ttu-id="13b08-508">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="13b08-508">Other unsupported validation errors</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a><span data-ttu-id="13b08-509">接收管道为每个为了响应传出交换而接收的功能确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-509">Data Updated by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outgoing Interchanges</span></span>  
 <span data-ttu-id="13b08-510">对于接收管道接收的每个功能确认，发送管道会更新所发送相关交换的状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="13b08-510">For each functional acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="13b08-511">EDI 拆装器使用传入确认的交换和组标头段中的数据来定位数据存储区中的记录：</span><span class="sxs-lookup"><span data-stu-id="13b08-511">The EDI Disassembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="13b08-512">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="13b08-512">Fields in ACK</span></span>|<span data-ttu-id="13b08-513">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="13b08-513">Fields in Data store</span></span>|<span data-ttu-id="13b08-514">注释</span><span class="sxs-lookup"><span data-stu-id="13b08-514">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="13b08-515">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-515">Interchange Sender ID</span></span>|<span data-ttu-id="13b08-516">交换收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-516">Interchange Receiver</span></span>|<span data-ttu-id="13b08-517">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-517">Applicable to both X12 and EDIFACT</span></span>|  
|<span data-ttu-id="13b08-518">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-518">Interchange Receiver ID</span></span>|<span data-ttu-id="13b08-519">交换发件人</span><span class="sxs-lookup"><span data-stu-id="13b08-519">Interchange Sender</span></span>|<span data-ttu-id="13b08-520">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-520">Applicable to both X12 and EDIFACT</span></span>|  
|-|<span data-ttu-id="13b08-521">交换日期</span><span class="sxs-lookup"><span data-stu-id="13b08-521">Interchange Date</span></span>|-|  
|<span data-ttu-id="13b08-522">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="13b08-522">Interchange Control Number</span></span>|<span data-ttu-id="13b08-523">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-523">Interchange Control ID</span></span>|<span data-ttu-id="13b08-524">仅适用于 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-524">Applicable only to EDIFACT</span></span>|  
|<span data-ttu-id="13b08-525">组控制编号</span><span class="sxs-lookup"><span data-stu-id="13b08-525">Group Control Number</span></span>|<span data-ttu-id="13b08-526">组控制编号</span><span class="sxs-lookup"><span data-stu-id="13b08-526">Group Control Number</span></span>|<span data-ttu-id="13b08-527">仅适用于 X12</span><span class="sxs-lookup"><span data-stu-id="13b08-527">Applicable only to X12</span></span>|  
|-|<span data-ttu-id="13b08-528">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="13b08-528">Interchange Direction = Send</span></span>|<span data-ttu-id="13b08-529">由于要在 BIBO 方案中实现唯一性，因此是必需</span><span class="sxs-lookup"><span data-stu-id="13b08-529">Required since in BIBO Scenario for uniqueness</span></span>|  
|<span data-ttu-id="13b08-530">记录类型</span><span class="sxs-lookup"><span data-stu-id="13b08-530">Record Type</span></span>|<span data-ttu-id="13b08-531">功能确认状态</span><span class="sxs-lookup"><span data-stu-id="13b08-531">Functional ACK Status</span></span>|<span data-ttu-id="13b08-532">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-532">Applicable to both X12 and EDIFACT</span></span>|  
  
 <span data-ttu-id="13b08-533">存储的数据包括︰</span><span class="sxs-lookup"><span data-stu-id="13b08-533">The data stored includes:</span></span>  
  
-   <span data-ttu-id="13b08-534">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="13b08-534">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="13b08-535">功能确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="13b08-535">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="13b08-536">功能确认状态 = 按照接收来更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-536">Functional ACK Status =Update Data as Received</span></span>  
  
-   <span data-ttu-id="13b08-537">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-537">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-538">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-538">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-539">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-539">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-540">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-540">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-541">组控制编号 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-541">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-542">功能 ID 代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-542">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-543">事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="13b08-543">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="13b08-544">功能确认交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-544">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="13b08-545">功能确认交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-545">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-546">功能确认交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="13b08-546">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="13b08-547">传送的事务集的计数 = 更新数据（X12 AK903，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="13b08-547">Count of Transaction Sets Delivered = Update Data (X12 AK903 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="13b08-548">接受的事务集的计数 = 更新数据（X12 AK904，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="13b08-548">Count of Transaction Sets Accepted = Update Data (X12 AK904 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="13b08-549">确认/操作代码 = 更新数据（X12 AK901 和 UCI4）引用注释 1</span><span class="sxs-lookup"><span data-stu-id="13b08-549">ACK/Action Code = Update Data (X12 AK901 and UCI4) Refer Note 1</span></span>  
  
-   <span data-ttu-id="13b08-550">错误/语法错误代码 =（X12 AK905 和 UCI5）引用注释 2</span><span class="sxs-lookup"><span data-stu-id="13b08-550">Error/Syntax Error Code  = (X12 AK905 and UCI5) Refer Note 2</span></span>  
  
-   <span data-ttu-id="13b08-551">其他 X12 ACK 错误代码 2 = 更新数据 (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="13b08-551">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="13b08-552">其他 X12 ACK 错误代码 3 = 更新数据 (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="13b08-552">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="13b08-553">其他 X12 ACK 错误代码 4 = 更新数据 (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="13b08-553">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="13b08-554">其他 X12 ACK 错误代码 5 = 更新数据 (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="13b08-554">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="13b08-555">将使用以下确认/操作代码︰</span><span class="sxs-lookup"><span data-stu-id="13b08-555">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="13b08-556">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-556">Data in ACK/Action Code</span></span>|<span data-ttu-id="13b08-557">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="13b08-557">Mapped for Status Reporting</span></span>|<span data-ttu-id="13b08-558">注释</span><span class="sxs-lookup"><span data-stu-id="13b08-558">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="13b08-559">指向</span><span class="sxs-lookup"><span data-stu-id="13b08-559">A</span></span>|<span data-ttu-id="13b08-560">已接受</span><span class="sxs-lookup"><span data-stu-id="13b08-560">Accepted</span></span>|<span data-ttu-id="13b08-561">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-561">X12</span></span>|  
|<span data-ttu-id="13b08-562">P</span><span class="sxs-lookup"><span data-stu-id="13b08-562">P</span></span>|<span data-ttu-id="13b08-563">部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-563">Partially Accepted</span></span>|<span data-ttu-id="13b08-564">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-564">X12</span></span>|  
|<span data-ttu-id="13b08-565">R、 M、 W 和 X</span><span class="sxs-lookup"><span data-stu-id="13b08-565">R, M, W, X</span></span>|<span data-ttu-id="13b08-566">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-566">Rejected</span></span>|<span data-ttu-id="13b08-567">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-567">X12</span></span>|  
|<span data-ttu-id="13b08-568">E</span><span class="sxs-lookup"><span data-stu-id="13b08-568">E</span></span>|<span data-ttu-id="13b08-569">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="13b08-569">Accepted with errors</span></span>|<span data-ttu-id="13b08-570">X12</span><span class="sxs-lookup"><span data-stu-id="13b08-570">X12</span></span>|  
|<span data-ttu-id="13b08-571">4</span><span class="sxs-lookup"><span data-stu-id="13b08-571">4</span></span>|<span data-ttu-id="13b08-572">已拒绝</span><span class="sxs-lookup"><span data-stu-id="13b08-572">Rejected</span></span>|<span data-ttu-id="13b08-573">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-573">EDIFACT</span></span>|  
|<span data-ttu-id="13b08-574">7, 8</span><span class="sxs-lookup"><span data-stu-id="13b08-574">7, 8</span></span>|<span data-ttu-id="13b08-575">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="13b08-575">Accepted/Partially Accepted</span></span>|<span data-ttu-id="13b08-576">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="13b08-576">EDIFACT</span></span>|  
  
 <span data-ttu-id="13b08-577">以下的错误/语法错误代码将用于 EDIFACT:</span><span class="sxs-lookup"><span data-stu-id="13b08-577">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="13b08-578">错误/语法错误 Cod 中的数据</span><span class="sxs-lookup"><span data-stu-id="13b08-578">Data in Error/Syntax Error Cod</span></span><br /><br /> <span data-ttu-id="13b08-579">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="13b08-579">(applicable to EDIFACT)</span></span>|<span data-ttu-id="13b08-580">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-580">Error Description for reporting</span></span>|  
|-------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="13b08-581">2</span><span class="sxs-lookup"><span data-stu-id="13b08-581">2</span></span>|<span data-ttu-id="13b08-582">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="13b08-582">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="13b08-583">7</span><span class="sxs-lookup"><span data-stu-id="13b08-583">7</span></span>|<span data-ttu-id="13b08-584">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-584">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="13b08-585">12</span><span class="sxs-lookup"><span data-stu-id="13b08-585">12</span></span>|<span data-ttu-id="13b08-586">无效值</span><span class="sxs-lookup"><span data-stu-id="13b08-586">Invalid value</span></span>|  
|<span data-ttu-id="13b08-587">13</span><span class="sxs-lookup"><span data-stu-id="13b08-587">13</span></span>|<span data-ttu-id="13b08-588">缺少</span><span class="sxs-lookup"><span data-stu-id="13b08-588">Missing</span></span>|  
|<span data-ttu-id="13b08-589">14</span><span class="sxs-lookup"><span data-stu-id="13b08-589">14</span></span>|<span data-ttu-id="13b08-590">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="13b08-590">Value not supported in this position</span></span>|  
|<span data-ttu-id="13b08-591">15</span><span class="sxs-lookup"><span data-stu-id="13b08-591">15</span></span>|<span data-ttu-id="13b08-592">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="13b08-592">Not supported in this position</span></span>|  
|<span data-ttu-id="13b08-593">16</span><span class="sxs-lookup"><span data-stu-id="13b08-593">16</span></span>|<span data-ttu-id="13b08-594">组分过多</span><span class="sxs-lookup"><span data-stu-id="13b08-594">Too many constituents</span></span>|  
|<span data-ttu-id="13b08-595">17</span><span class="sxs-lookup"><span data-stu-id="13b08-595">17</span></span>|<span data-ttu-id="13b08-596">无协议</span><span class="sxs-lookup"><span data-stu-id="13b08-596">No agreement</span></span>|  
|<span data-ttu-id="13b08-597">18</span><span class="sxs-lookup"><span data-stu-id="13b08-597">18</span></span>|<span data-ttu-id="13b08-598">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="13b08-598">Unspecified error</span></span>|  
|<span data-ttu-id="13b08-599">19</span><span class="sxs-lookup"><span data-stu-id="13b08-599">19</span></span>|<span data-ttu-id="13b08-600">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="13b08-600">Invalid decimal notation</span></span>|  
|<span data-ttu-id="13b08-601">20</span><span class="sxs-lookup"><span data-stu-id="13b08-601">20</span></span>|<span data-ttu-id="13b08-602">字符无效，因为服务字符</span><span class="sxs-lookup"><span data-stu-id="13b08-602">Character invalid as service character</span></span>|  
|<span data-ttu-id="13b08-603">21</span><span class="sxs-lookup"><span data-stu-id="13b08-603">21</span></span>|<span data-ttu-id="13b08-604">无效字符</span><span class="sxs-lookup"><span data-stu-id="13b08-604">Invalid character(s)</span></span>|  
|<span data-ttu-id="13b08-605">22</span><span class="sxs-lookup"><span data-stu-id="13b08-605">22</span></span>|<span data-ttu-id="13b08-606">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="13b08-606">Invalid service character(s)</span></span>|  
|<span data-ttu-id="13b08-607">23</span><span class="sxs-lookup"><span data-stu-id="13b08-607">23</span></span>|<span data-ttu-id="13b08-608">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="13b08-608">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="13b08-609">24</span><span class="sxs-lookup"><span data-stu-id="13b08-609">24</span></span>|<span data-ttu-id="13b08-610">太旧</span><span class="sxs-lookup"><span data-stu-id="13b08-610">Too old</span></span>|  
|<span data-ttu-id="13b08-611">25</span><span class="sxs-lookup"><span data-stu-id="13b08-611">25</span></span>|<span data-ttu-id="13b08-612">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="13b08-612">Test indicator not supported</span></span>|  
|<span data-ttu-id="13b08-613">26</span><span class="sxs-lookup"><span data-stu-id="13b08-613">26</span></span>|<span data-ttu-id="13b08-614">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="13b08-614">Duplicate detected</span></span>|  
|<span data-ttu-id="13b08-615">27</span><span class="sxs-lookup"><span data-stu-id="13b08-615">27</span></span>|<span data-ttu-id="13b08-616">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="13b08-616">Security function not supported</span></span>|  
|<span data-ttu-id="13b08-617">28</span><span class="sxs-lookup"><span data-stu-id="13b08-617">28</span></span>|<span data-ttu-id="13b08-618">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-618">References do not match</span></span>|  
|<span data-ttu-id="13b08-619">29</span><span class="sxs-lookup"><span data-stu-id="13b08-619">29</span></span>|<span data-ttu-id="13b08-620">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-620">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="13b08-621">30</span><span class="sxs-lookup"><span data-stu-id="13b08-621">30</span></span>|<span data-ttu-id="13b08-622">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="13b08-622">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="13b08-623">31</span><span class="sxs-lookup"><span data-stu-id="13b08-623">31</span></span>|<span data-ttu-id="13b08-624">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="13b08-624">More than one message type in group</span></span>|  
|<span data-ttu-id="13b08-625">32</span><span class="sxs-lookup"><span data-stu-id="13b08-625">32</span></span>|<span data-ttu-id="13b08-626">低级别为空</span><span class="sxs-lookup"><span data-stu-id="13b08-626">Lower level empty</span></span>|  
|<span data-ttu-id="13b08-627">33</span><span class="sxs-lookup"><span data-stu-id="13b08-627">33</span></span>|<span data-ttu-id="13b08-628">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="13b08-628">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="13b08-629">34</span><span class="sxs-lookup"><span data-stu-id="13b08-629">34</span></span>|<span data-ttu-id="13b08-630">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="13b08-630">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="13b08-631">35</span><span class="sxs-lookup"><span data-stu-id="13b08-631">35</span></span>|<span data-ttu-id="13b08-632">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="13b08-632">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="13b08-633">36</span><span class="sxs-lookup"><span data-stu-id="13b08-633">36</span></span>|<span data-ttu-id="13b08-634">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="13b08-634">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="13b08-635">37</span><span class="sxs-lookup"><span data-stu-id="13b08-635">37</span></span>|<span data-ttu-id="13b08-636">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="13b08-636">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="13b08-637">38</span><span class="sxs-lookup"><span data-stu-id="13b08-637">38</span></span>|<span data-ttu-id="13b08-638">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="13b08-638">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="13b08-639">39</span><span class="sxs-lookup"><span data-stu-id="13b08-639">39</span></span>|<span data-ttu-id="13b08-640">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="13b08-640">Data element too long</span></span>|  
|<span data-ttu-id="13b08-641">40</span><span class="sxs-lookup"><span data-stu-id="13b08-641">40</span></span>|<span data-ttu-id="13b08-642">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="13b08-642">Data element too short</span></span>|  
|<span data-ttu-id="13b08-643">41</span><span class="sxs-lookup"><span data-stu-id="13b08-643">41</span></span>|<span data-ttu-id="13b08-644">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="13b08-644">Permanent communication network error</span></span>|  
|<span data-ttu-id="13b08-645">42</span><span class="sxs-lookup"><span data-stu-id="13b08-645">42</span></span>|<span data-ttu-id="13b08-646">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="13b08-646">Temporary communication network error</span></span>|  
|<span data-ttu-id="13b08-647">43</span><span class="sxs-lookup"><span data-stu-id="13b08-647">43</span></span>|<span data-ttu-id="13b08-648">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="13b08-648">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="13b08-649">45</span><span class="sxs-lookup"><span data-stu-id="13b08-649">45</span></span>|<span data-ttu-id="13b08-650">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="13b08-650">Trailing separator</span></span>|  
|<span data-ttu-id="13b08-651">46</span><span class="sxs-lookup"><span data-stu-id="13b08-651">46</span></span>|<span data-ttu-id="13b08-652">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="13b08-652">Character set not supported</span></span>|  
|<span data-ttu-id="13b08-653">47</span><span class="sxs-lookup"><span data-stu-id="13b08-653">47</span></span>|<span data-ttu-id="13b08-654">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="13b08-654">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="13b08-655">48</span><span class="sxs-lookup"><span data-stu-id="13b08-655">48</span></span>|<span data-ttu-id="13b08-656">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="13b08-656">Dependency condition violated</span></span>|  
|<span data-ttu-id="13b08-657">70</span><span class="sxs-lookup"><span data-stu-id="13b08-657">70</span></span>|<span data-ttu-id="13b08-658">事务集缺失或无效的事务集标识符</span><span class="sxs-lookup"><span data-stu-id="13b08-658">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="13b08-659">71</span><span class="sxs-lookup"><span data-stu-id="13b08-659">71</span></span>|<span data-ttu-id="13b08-660">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-660">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="13b08-661">72</span><span class="sxs-lookup"><span data-stu-id="13b08-661">72</span></span>|<span data-ttu-id="13b08-662">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="13b08-662">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="13b08-663">73</span><span class="sxs-lookup"><span data-stu-id="13b08-663">73</span></span>|<span data-ttu-id="13b08-664">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="13b08-664">XML not at correct position</span></span>|  
|<span data-ttu-id="13b08-665">74</span><span class="sxs-lookup"><span data-stu-id="13b08-665">74</span></span>|<span data-ttu-id="13b08-666">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="13b08-666">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="13b08-667">75</span><span class="sxs-lookup"><span data-stu-id="13b08-667">75</span></span>|<span data-ttu-id="13b08-668">段重复过少</span><span class="sxs-lookup"><span data-stu-id="13b08-668">Too few segment repetitions</span></span>|  
|<span data-ttu-id="13b08-669">76</span><span class="sxs-lookup"><span data-stu-id="13b08-669">76</span></span>|<span data-ttu-id="13b08-670">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="13b08-670">Too few data elements found</span></span>|  
  
 <span data-ttu-id="13b08-671">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="13b08-671">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="13b08-672">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="13b08-672">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="13b08-673">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="13b08-673">(applicable to X12)</span></span>|<span data-ttu-id="13b08-674">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="13b08-674">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="13b08-675">1</span><span class="sxs-lookup"><span data-stu-id="13b08-675">1</span></span>|<span data-ttu-id="13b08-676">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="13b08-676">Functional group not supported</span></span>|  
|<span data-ttu-id="13b08-677">2</span><span class="sxs-lookup"><span data-stu-id="13b08-677">2</span></span>|<span data-ttu-id="13b08-678">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="13b08-678">Functional group version not supported</span></span>|  
|<span data-ttu-id="13b08-679">3</span><span class="sxs-lookup"><span data-stu-id="13b08-679">3</span></span>|<span data-ttu-id="13b08-680">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="13b08-680">Functional group trailer missing</span></span>|  
|<span data-ttu-id="13b08-681">4</span><span class="sxs-lookup"><span data-stu-id="13b08-681">4</span></span>|<span data-ttu-id="13b08-682">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="13b08-682">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="13b08-683">5</span><span class="sxs-lookup"><span data-stu-id="13b08-683">5</span></span>|<span data-ttu-id="13b08-684">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="13b08-684">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="13b08-685">6-26</span><span class="sxs-lookup"><span data-stu-id="13b08-685">6-26</span></span>|<span data-ttu-id="13b08-686">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="13b08-686">Other unsupported validation errors</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13b08-687">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13b08-687">See Also</span></span>  
 <span data-ttu-id="13b08-688">[如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="13b08-688">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="13b08-689">如何为入站 EDI 消息存储数据</span><span class="sxs-lookup"><span data-stu-id="13b08-689">How Data Is Stored for Inbound EDI Messages</span></span>](../core/how-data-is-stored-for-inbound-edi-messages.md)