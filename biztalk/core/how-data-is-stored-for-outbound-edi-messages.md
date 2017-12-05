---
title: "如何将数据存储用于出站 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6e576fc-37fd-417d-ae68-607a0a8bcc0a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98d5113c63e29f3f4b85834b7ca1aa0836d0a5d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a><span data-ttu-id="45bd5-102">出站 EDI 消息数据的存储方式</span><span class="sxs-lookup"><span data-stu-id="45bd5-102">How Data Is Stored for Outbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="45bd5-103">执行以下操作来生成状态报表项的出站交换：</span><span class="sxs-lookup"><span data-stu-id="45bd5-103"> does the following to generate a status report entry for an outbound interchange:</span></span>  
  
1.  <span data-ttu-id="45bd5-104">当出站消息 XML 发送到 EDI 发送管道时，发送管道中的状态报告具有以下值的数据存储区创建一项：</span><span class="sxs-lookup"><span data-stu-id="45bd5-104">When outbound message XML is sent to the EDI send pipeline, the send pipeline creates an entry in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="45bd5-105">交换状态条目将设置为处理</span><span class="sxs-lookup"><span data-stu-id="45bd5-105">Interchange status entry is set to Processed</span></span>  
  
    -   <span data-ttu-id="45bd5-106">交换 ACK 状态条目 （交换每一个） 设置为预期</span><span class="sxs-lookup"><span data-stu-id="45bd5-106">Interchange ACK status entry (one per interchange) is set to Expected</span></span>  
  
    -   <span data-ttu-id="45bd5-107">（一个每个组中的 X12，一个用于 EDIFACT 中的所有组） 的功能 ACK 状态条目已设置为预期</span><span class="sxs-lookup"><span data-stu-id="45bd5-107">Functional ACK status entries (one per group in X12, one for all groups in EDIFACT) are set to Expected</span></span>  
  
2.  <span data-ttu-id="45bd5-108">具有已 EDI 消息发送到贸易合作伙伴，并从贸易合作伙伴返回已确认后，EDI 接收管道接收确认的更新的交换状态、 交换 ACK 状态和功能ACK 状态条目向已接受/部分接受/拒绝，根据需要。</span><span class="sxs-lookup"><span data-stu-id="45bd5-108">After the EDI message has been sent to the trading partner, and the acknowledgment has been returned from the trading partner, the EDI receive pipeline that receives the acknowledgment updates the Interchange status, the Interchange ACK status, and the Functional ACK status entries to Accepted/Partially Accepted/Rejected, as appropriate.</span></span>  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a><span data-ttu-id="45bd5-109">存储发送管道的出站的交换的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-109">Data Stored by the Send Pipeline for Outbound Interchanges</span></span>  
 <span data-ttu-id="45bd5-110">发送管道发送每个交换的状态报表数据存储区中创建记录。</span><span class="sxs-lookup"><span data-stu-id="45bd5-110">The send pipeline creates a record in the status report data store for each interchange that it sends.</span></span> <span data-ttu-id="45bd5-111">所需的项的大多数数据是可从交换标头/预告片段 （ISA/IEA 或 UNB/UNZ）。</span><span class="sxs-lookup"><span data-stu-id="45bd5-111">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="45bd5-112">从发送端口属性提供了其他数据。</span><span class="sxs-lookup"><span data-stu-id="45bd5-112">Other data is available from send port properties.</span></span> <span data-ttu-id="45bd5-113">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="45bd5-113">The data stored includes:</span></span>  
  
-   <span data-ttu-id="45bd5-114">记录类型 = 交换状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-114">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="45bd5-115">交换方向 = 更新数据 = 发送</span><span class="sxs-lookup"><span data-stu-id="45bd5-115">Interchange Direction = Update Data = Send</span></span>  
  
-   <span data-ttu-id="45bd5-116">交换接收器 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-116">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-117">交换发件人 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-117">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-118">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-118">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-119">交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-119">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-120">交换控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-120">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-121">交换： 处理/发送状态。</span><span class="sxs-lookup"><span data-stu-id="45bd5-121">Interchange Status: Processed/Sent.</span></span> <span data-ttu-id="45bd5-122">处理状态指示已成功处理该交换和设备移交给传递发送适配器发送管道。</span><span class="sxs-lookup"><span data-stu-id="45bd5-122">A status of Processed indicates that the send pipeline has successfully processed the interchange and handed it over to the send adapter for delivery.</span></span>  
  
-   <span data-ttu-id="45bd5-123">交换控件计数 (组/消息中的 X12 分别) = 数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-123">Interchange Control Count (Groups/Messages in X12 respectively) = Data</span></span>  
  
-   <span data-ttu-id="45bd5-124">交换发送端口 ID = 数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-124">Interchange Send Port ID = Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="45bd5-125">存储的每个对的出站交换响应中收到的技术确认接收管道的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-125">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="45bd5-126">接收管道在每个技术确认它收到的状态报表数据存储中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="45bd5-126">The receive pipeline creates a record in the status report data store for each technical acknowledgment that it receives.</span></span> <span data-ttu-id="45bd5-127">接收管道创建一条记录的每个状态报表数据存储区中收到的交换。</span><span class="sxs-lookup"><span data-stu-id="45bd5-127">The receive pipeline creates a record of each interchange received in the status report data store.</span></span> <span data-ttu-id="45bd5-128">在每个技术 ACK 作为响应发送到贸易合作伙伴交换接收的数据存储中创建一个技术确认状态报表项。</span><span class="sxs-lookup"><span data-stu-id="45bd5-128">creates one technical acknowledgment status report entry in the data store for each technical ACK received as a response to an interchange sent to a trading partner.</span></span> <span data-ttu-id="45bd5-129">技术确认是使用仅对于 EDIFACT 了 UCI 段 X12 和 CONTRL 消息 TA1。</span><span class="sxs-lookup"><span data-stu-id="45bd5-129">The technical acknowledge is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="45bd5-130">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="45bd5-130">The data stored includes:</span></span>  
  
-   <span data-ttu-id="45bd5-131">记录类型 = 交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-131">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="45bd5-132">交换 ACK 方向 = 发送 – 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-132">Interchange ACK Direction = Send – Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-133">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-133">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-134">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-134">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-135">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="45bd5-135">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-136">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-136">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-137">交换 ACK 状态 = 生成或不适用\<注意 0，请参阅\>-更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-137">Interchange ACK Status = Generated or Not Applicable \<Refer Note 0\> - Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-138">交换 ACK 控件 ID = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-138">Interchange ACK Control ID= Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-139">交换 ACK 日期 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-139">Interchange ACK Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-140">交换 ACK 时间 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-140">Interchange ACK Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-141">确认/操作代码 = 更新数据\<，请参阅备注 1\> （来自 X12 TA104 或 EDIFACT UCI4） *</span><span class="sxs-lookup"><span data-stu-id="45bd5-141">ACK/Action Code = Update Data  \<refer note 1\> (from X12-TA104 or EDIFACT-UCI4)*</span></span>  
  
-   <span data-ttu-id="45bd5-142">ACK 注意代码 = 更新数据\<，请参阅备注 2\> （从 X12-TA105，不适用于 EDIFACT) *</span><span class="sxs-lookup"><span data-stu-id="45bd5-142">ACK Note Code = Update Data \<Refer Note 2\> (from X12-TA105, not applicable for EDIFACT)*</span></span>  
  
 <span data-ttu-id="45bd5-143">使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="45bd5-143">The following ACK/Action Codes are used:</span></span>  
  
|<span data-ttu-id="45bd5-144">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-144">Data in ACK/Action Code</span></span>|<span data-ttu-id="45bd5-145">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-145">Error description for Reporting</span></span>|<span data-ttu-id="45bd5-146">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="45bd5-146">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="45bd5-147">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="45bd5-147">A</span></span>|<span data-ttu-id="45bd5-148">已接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-148">Accepted</span></span>|<span data-ttu-id="45bd5-149">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-149">X12</span></span>|  
|<span data-ttu-id="45bd5-150">E</span><span class="sxs-lookup"><span data-stu-id="45bd5-150">E</span></span>|<span data-ttu-id="45bd5-151">记下的已被接受，错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-151">Accepted, errors noted</span></span>|<span data-ttu-id="45bd5-152">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-152">X12</span></span>|  
|<span data-ttu-id="45bd5-153">P</span><span class="sxs-lookup"><span data-stu-id="45bd5-153">P</span></span>|<span data-ttu-id="45bd5-154">部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-154">Partially Accepted</span></span>|<span data-ttu-id="45bd5-155">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-155">X12</span></span>|  
|<span data-ttu-id="45bd5-156">R</span><span class="sxs-lookup"><span data-stu-id="45bd5-156">R</span></span>|<span data-ttu-id="45bd5-157">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-157">Rejected</span></span>|<span data-ttu-id="45bd5-158">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-158">X12</span></span>|  
|<span data-ttu-id="45bd5-159">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-159">4</span></span>|<span data-ttu-id="45bd5-160">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-160">Rejected</span></span>|<span data-ttu-id="45bd5-161">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-161">EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-162">8</span><span class="sxs-lookup"><span data-stu-id="45bd5-162">8</span></span>|<span data-ttu-id="45bd5-163">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-163">Accepted/Partially Accepted</span></span>|<span data-ttu-id="45bd5-164">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-164">EDIFACT</span></span>|  
  
 <span data-ttu-id="45bd5-165">使用以下 ACK 注意代码：</span><span class="sxs-lookup"><span data-stu-id="45bd5-165">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="45bd5-166">（在 X12) 的 ACK 注意代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-166">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="45bd5-167">Description</span><span class="sxs-lookup"><span data-stu-id="45bd5-167">Description</span></span>|  
|--------------------------------------|-----------------|  
|<span data-ttu-id="45bd5-168">000</span><span class="sxs-lookup"><span data-stu-id="45bd5-168">000</span></span>|<span data-ttu-id="45bd5-169">成功</span><span class="sxs-lookup"><span data-stu-id="45bd5-169">Success</span></span>|  
|<span data-ttu-id="45bd5-170">001</span><span class="sxs-lookup"><span data-stu-id="45bd5-170">001</span></span>|<span data-ttu-id="45bd5-171">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-171">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="45bd5-172">002</span><span class="sxs-lookup"><span data-stu-id="45bd5-172">002</span></span>|<span data-ttu-id="45bd5-173">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="45bd5-173">Standard not supported</span></span>|  
|<span data-ttu-id="45bd5-174">003</span><span class="sxs-lookup"><span data-stu-id="45bd5-174">003</span></span>|<span data-ttu-id="45bd5-175">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="45bd5-175">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="45bd5-176">004</span><span class="sxs-lookup"><span data-stu-id="45bd5-176">004</span></span>|<span data-ttu-id="45bd5-177">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-177">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="45bd5-178">005</span><span class="sxs-lookup"><span data-stu-id="45bd5-178">005</span></span>|<span data-ttu-id="45bd5-179">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-179">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="45bd5-180">006</span><span class="sxs-lookup"><span data-stu-id="45bd5-180">006</span></span>|<span data-ttu-id="45bd5-181">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-181">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="45bd5-182">007</span><span class="sxs-lookup"><span data-stu-id="45bd5-182">007</span></span>|<span data-ttu-id="45bd5-183">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-183">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="45bd5-184">008</span><span class="sxs-lookup"><span data-stu-id="45bd5-184">008</span></span>|<span data-ttu-id="45bd5-185">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-185">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="45bd5-186">009</span><span class="sxs-lookup"><span data-stu-id="45bd5-186">009</span></span>|<span data-ttu-id="45bd5-187">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-187">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="45bd5-188">010</span><span class="sxs-lookup"><span data-stu-id="45bd5-188">010</span></span>|<span data-ttu-id="45bd5-189">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-189">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="45bd5-190">011</span><span class="sxs-lookup"><span data-stu-id="45bd5-190">011</span></span>|<span data-ttu-id="45bd5-191">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="45bd5-191">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="45bd5-192">012</span><span class="sxs-lookup"><span data-stu-id="45bd5-192">012</span></span>|<span data-ttu-id="45bd5-193">无效的安全信息限定符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-193">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="45bd5-194">013</span><span class="sxs-lookup"><span data-stu-id="45bd5-194">013</span></span>|<span data-ttu-id="45bd5-195">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="45bd5-195">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="45bd5-196">014</span><span class="sxs-lookup"><span data-stu-id="45bd5-196">014</span></span>|<span data-ttu-id="45bd5-197">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="45bd5-197">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="45bd5-198">015</span><span class="sxs-lookup"><span data-stu-id="45bd5-198">015</span></span>|<span data-ttu-id="45bd5-199">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="45bd5-199">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="45bd5-200">016</span><span class="sxs-lookup"><span data-stu-id="45bd5-200">016</span></span>|<span data-ttu-id="45bd5-201">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-201">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="45bd5-202">017</span><span class="sxs-lookup"><span data-stu-id="45bd5-202">017</span></span>|<span data-ttu-id="45bd5-203">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="45bd5-203">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="45bd5-204">018</span><span class="sxs-lookup"><span data-stu-id="45bd5-204">018</span></span>|<span data-ttu-id="45bd5-205">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="45bd5-205">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="45bd5-206">019</span><span class="sxs-lookup"><span data-stu-id="45bd5-206">019</span></span>|<span data-ttu-id="45bd5-207">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="45bd5-207">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="45bd5-208">020</span><span class="sxs-lookup"><span data-stu-id="45bd5-208">020</span></span>|<span data-ttu-id="45bd5-209">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="45bd5-209">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="45bd5-210">021</span><span class="sxs-lookup"><span data-stu-id="45bd5-210">021</span></span>|<span data-ttu-id="45bd5-211">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-211">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="45bd5-212">022</span><span class="sxs-lookup"><span data-stu-id="45bd5-212">022</span></span>|<span data-ttu-id="45bd5-213">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-213">Invalid Control Structure</span></span>|  
|<span data-ttu-id="45bd5-214">023</span><span class="sxs-lookup"><span data-stu-id="45bd5-214">023</span></span>|<span data-ttu-id="45bd5-215">不正确文件尾</span><span class="sxs-lookup"><span data-stu-id="45bd5-215">Improper End-of-File</span></span>|  
|<span data-ttu-id="45bd5-216">024</span><span class="sxs-lookup"><span data-stu-id="45bd5-216">024</span></span>|<span data-ttu-id="45bd5-217">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-217">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="45bd5-218">025</span><span class="sxs-lookup"><span data-stu-id="45bd5-218">025</span></span>|<span data-ttu-id="45bd5-219">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="45bd5-219">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="45bd5-220">026</span><span class="sxs-lookup"><span data-stu-id="45bd5-220">026</span></span>|<span data-ttu-id="45bd5-221">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-221">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="45bd5-222">027</span><span class="sxs-lookup"><span data-stu-id="45bd5-222">027</span></span>|<span data-ttu-id="45bd5-223">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-223">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="45bd5-224">028</span><span class="sxs-lookup"><span data-stu-id="45bd5-224">028</span></span>|<span data-ttu-id="45bd5-225">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-225">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="45bd5-226">029</span><span class="sxs-lookup"><span data-stu-id="45bd5-226">029</span></span>|<span data-ttu-id="45bd5-227">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-227">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="45bd5-228">030</span><span class="sxs-lookup"><span data-stu-id="45bd5-228">030</span></span>|<span data-ttu-id="45bd5-229">延迟的传递请求中的无效传递时代码</span><span class="sxs-lookup"><span data-stu-id="45bd5-229">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="45bd5-230">031</span><span class="sxs-lookup"><span data-stu-id="45bd5-230">031</span></span>|<span data-ttu-id="45bd5-231">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-231">Invalid Grade of Service</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="45bd5-232">接收管道针对每个技术确认对出站交换响应中收到的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-232">Data Updated by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="45bd5-233">为每个接收管道接收的技术确认，它会更新状态报表项时为关联的已发送交换。</span><span class="sxs-lookup"><span data-stu-id="45bd5-233">For each technical acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="45bd5-234">EDI 反汇编程序中数据存储区中，如下所示使用 UCI 和的传入确认，TA1 段中的数据查找记录：</span><span class="sxs-lookup"><span data-stu-id="45bd5-234">The EDI Disassembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="45bd5-235">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="45bd5-235">Fields in ACK</span></span>|<span data-ttu-id="45bd5-236">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="45bd5-236">Fields in Data store</span></span>|<span data-ttu-id="45bd5-237">注释</span><span class="sxs-lookup"><span data-stu-id="45bd5-237">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="45bd5-238">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-238">Interchange Sender ID</span></span>|<span data-ttu-id="45bd5-239">交换收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-239">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="45bd5-240">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-240">Interchange Receiver ID</span></span>|<span data-ttu-id="45bd5-241">交换发件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-241">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="45bd5-242">交换日期</span><span class="sxs-lookup"><span data-stu-id="45bd5-242">Interchange Date</span></span>|-|  
|<span data-ttu-id="45bd5-243">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="45bd5-243">Interchange Control Number</span></span>|<span data-ttu-id="45bd5-244">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-244">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="45bd5-245">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="45bd5-245">Interchange Direction = Send</span></span>|<span data-ttu-id="45bd5-246">在保留的批处理方案唯一性必需的</span><span class="sxs-lookup"><span data-stu-id="45bd5-246">Required in preserved batch scenario for uniqueness</span></span>|  
|<span data-ttu-id="45bd5-247">记录类型</span><span class="sxs-lookup"><span data-stu-id="45bd5-247">Record Type</span></span>|<span data-ttu-id="45bd5-248">交换状态和交换 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-248">Interchange Status and Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="45bd5-249">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="45bd5-249">The data stored includes:</span></span>  
  
-   <span data-ttu-id="45bd5-250">交换 ACK 方向 = 接收 – 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-250">Interchange ACK Direction = Receive – Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-251">交换 ACK 状态 = 收到</span><span class="sxs-lookup"><span data-stu-id="45bd5-251">Interchange ACK Status = Received</span></span>  
  
-   <span data-ttu-id="45bd5-252">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-252">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-253">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-253">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-254">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-254">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-255">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-255">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-256">交换 ACK 控件 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-256">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-257">交换 ACK 日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-257">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-258">交换 ACK 时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-258">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-259">确认/操作代码 = 更新数据 （来自 X12 TA104 或 EDIFACT UCI4） * \<，请参阅备注 1\></span><span class="sxs-lookup"><span data-stu-id="45bd5-259">ACK/Action Code = Update Data (from X12-TA104 or EDIFACT-UCI4)* \<Refer Note 1\></span></span>  
  
-   <span data-ttu-id="45bd5-260">ACK 注意代码 2 = 更新数据 (从 X12 TA105 和不值对于 EDIFACT) * \<，请参阅备注 2\></span><span class="sxs-lookup"><span data-stu-id="45bd5-260">ACK Note Code 2 = Update Data (from X12-TA105 and not valued for EDIFACT)* \<Refer Note 2\></span></span>  
  
 <span data-ttu-id="45bd5-261">ACK X12 中的数据： TA1 104 或 EDIFACT UCI4 是，如下所示映射：</span><span class="sxs-lookup"><span data-stu-id="45bd5-261">The data from the ACK X12:TA1-104 or EDIFACT UCI4 is to be mapped as follows:</span></span>  
  
|<span data-ttu-id="45bd5-262">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-262">Data in ACK/Action Code</span></span>|<span data-ttu-id="45bd5-263">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="45bd5-263">Mapped for Status Reporting</span></span>|<span data-ttu-id="45bd5-264">注释</span><span class="sxs-lookup"><span data-stu-id="45bd5-264">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="45bd5-265">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="45bd5-265">A</span></span>|<span data-ttu-id="45bd5-266">已接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-266">Accepted</span></span>|<span data-ttu-id="45bd5-267">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-267">X12</span></span>|  
|<span data-ttu-id="45bd5-268">P</span><span class="sxs-lookup"><span data-stu-id="45bd5-268">P</span></span>|<span data-ttu-id="45bd5-269">部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-269">Partially Accepted</span></span>|<span data-ttu-id="45bd5-270">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-270">X12</span></span>|  
|<span data-ttu-id="45bd5-271">R、 M、 W 和 X</span><span class="sxs-lookup"><span data-stu-id="45bd5-271">R, M, W, X</span></span>|<span data-ttu-id="45bd5-272">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-272">Rejected</span></span>|<span data-ttu-id="45bd5-273">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-273">X12</span></span>|  
|<span data-ttu-id="45bd5-274">E</span><span class="sxs-lookup"><span data-stu-id="45bd5-274">E</span></span>|<span data-ttu-id="45bd5-275">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-275">Accepted with errors</span></span>|<span data-ttu-id="45bd5-276">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-276">X12</span></span>|  
|<span data-ttu-id="45bd5-277">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-277">4</span></span>|<span data-ttu-id="45bd5-278">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-278">Rejected</span></span>|<span data-ttu-id="45bd5-279">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-279">EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-280">7, 8</span><span class="sxs-lookup"><span data-stu-id="45bd5-280">7, 8</span></span>|<span data-ttu-id="45bd5-281">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-281">Accepted/Partially Accepted</span></span>|<span data-ttu-id="45bd5-282">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-282">EDIFACT</span></span>|  
  
 <span data-ttu-id="45bd5-283">使用以下 ACK 注意代码：</span><span class="sxs-lookup"><span data-stu-id="45bd5-283">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="45bd5-284">（在 X12) 的 ACK 注意代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-284">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="45bd5-285">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="45bd5-285">Mapped for Status Reporting</span></span>|  
|--------------------------------------|---------------------------------|  
|<span data-ttu-id="45bd5-286">000</span><span class="sxs-lookup"><span data-stu-id="45bd5-286">000</span></span>|<span data-ttu-id="45bd5-287">成功</span><span class="sxs-lookup"><span data-stu-id="45bd5-287">Success</span></span>|  
|<span data-ttu-id="45bd5-288">001</span><span class="sxs-lookup"><span data-stu-id="45bd5-288">001</span></span>|<span data-ttu-id="45bd5-289">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-289">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="45bd5-290">002</span><span class="sxs-lookup"><span data-stu-id="45bd5-290">002</span></span>|<span data-ttu-id="45bd5-291">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="45bd5-291">Standard not supported</span></span>|  
|<span data-ttu-id="45bd5-292">003</span><span class="sxs-lookup"><span data-stu-id="45bd5-292">003</span></span>|<span data-ttu-id="45bd5-293">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="45bd5-293">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="45bd5-294">004</span><span class="sxs-lookup"><span data-stu-id="45bd5-294">004</span></span>|<span data-ttu-id="45bd5-295">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-295">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="45bd5-296">005</span><span class="sxs-lookup"><span data-stu-id="45bd5-296">005</span></span>|<span data-ttu-id="45bd5-297">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-297">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="45bd5-298">006</span><span class="sxs-lookup"><span data-stu-id="45bd5-298">006</span></span>|<span data-ttu-id="45bd5-299">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-299">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="45bd5-300">007</span><span class="sxs-lookup"><span data-stu-id="45bd5-300">007</span></span>|<span data-ttu-id="45bd5-301">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-301">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="45bd5-302">008</span><span class="sxs-lookup"><span data-stu-id="45bd5-302">008</span></span>|<span data-ttu-id="45bd5-303">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-303">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="45bd5-304">009</span><span class="sxs-lookup"><span data-stu-id="45bd5-304">009</span></span>|<span data-ttu-id="45bd5-305">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-305">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="45bd5-306">010</span><span class="sxs-lookup"><span data-stu-id="45bd5-306">010</span></span>|<span data-ttu-id="45bd5-307">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-307">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="45bd5-308">011</span><span class="sxs-lookup"><span data-stu-id="45bd5-308">011</span></span>|<span data-ttu-id="45bd5-309">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="45bd5-309">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="45bd5-310">012</span><span class="sxs-lookup"><span data-stu-id="45bd5-310">012</span></span>|<span data-ttu-id="45bd5-311">无效的安全信息限定符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-311">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="45bd5-312">013</span><span class="sxs-lookup"><span data-stu-id="45bd5-312">013</span></span>|<span data-ttu-id="45bd5-313">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="45bd5-313">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="45bd5-314">014</span><span class="sxs-lookup"><span data-stu-id="45bd5-314">014</span></span>|<span data-ttu-id="45bd5-315">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="45bd5-315">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="45bd5-316">015</span><span class="sxs-lookup"><span data-stu-id="45bd5-316">015</span></span>|<span data-ttu-id="45bd5-317">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="45bd5-317">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="45bd5-318">016</span><span class="sxs-lookup"><span data-stu-id="45bd5-318">016</span></span>|<span data-ttu-id="45bd5-319">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="45bd5-319">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="45bd5-320">017</span><span class="sxs-lookup"><span data-stu-id="45bd5-320">017</span></span>|<span data-ttu-id="45bd5-321">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="45bd5-321">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="45bd5-322">018</span><span class="sxs-lookup"><span data-stu-id="45bd5-322">018</span></span>|<span data-ttu-id="45bd5-323">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="45bd5-323">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="45bd5-324">019</span><span class="sxs-lookup"><span data-stu-id="45bd5-324">019</span></span>|<span data-ttu-id="45bd5-325">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="45bd5-325">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="45bd5-326">020</span><span class="sxs-lookup"><span data-stu-id="45bd5-326">020</span></span>|<span data-ttu-id="45bd5-327">无效的测试指示器值</span><span class="sxs-lookup"><span data-stu-id="45bd5-327">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="45bd5-328">021</span><span class="sxs-lookup"><span data-stu-id="45bd5-328">021</span></span>|<span data-ttu-id="45bd5-329">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-329">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="45bd5-330">022</span><span class="sxs-lookup"><span data-stu-id="45bd5-330">022</span></span>|<span data-ttu-id="45bd5-331">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-331">Invalid Control Structure</span></span>|  
|<span data-ttu-id="45bd5-332">023</span><span class="sxs-lookup"><span data-stu-id="45bd5-332">023</span></span>|<span data-ttu-id="45bd5-333">不正确文件尾</span><span class="sxs-lookup"><span data-stu-id="45bd5-333">Improper End-of-File</span></span>|  
|<span data-ttu-id="45bd5-334">024</span><span class="sxs-lookup"><span data-stu-id="45bd5-334">024</span></span>|<span data-ttu-id="45bd5-335">无效的交换内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-335">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="45bd5-336">025</span><span class="sxs-lookup"><span data-stu-id="45bd5-336">025</span></span>|<span data-ttu-id="45bd5-337">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="45bd5-337">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="45bd5-338">026</span><span class="sxs-lookup"><span data-stu-id="45bd5-338">026</span></span>|<span data-ttu-id="45bd5-339">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-339">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="45bd5-340">027</span><span class="sxs-lookup"><span data-stu-id="45bd5-340">027</span></span>|<span data-ttu-id="45bd5-341">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-341">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="45bd5-342">028</span><span class="sxs-lookup"><span data-stu-id="45bd5-342">028</span></span>|<span data-ttu-id="45bd5-343">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-343">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="45bd5-344">029</span><span class="sxs-lookup"><span data-stu-id="45bd5-344">029</span></span>|<span data-ttu-id="45bd5-345">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-345">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="45bd5-346">030</span><span class="sxs-lookup"><span data-stu-id="45bd5-346">030</span></span>|<span data-ttu-id="45bd5-347">延迟的传递请求中的无效传递时代码</span><span class="sxs-lookup"><span data-stu-id="45bd5-347">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="45bd5-348">031</span><span class="sxs-lookup"><span data-stu-id="45bd5-348">031</span></span>|<span data-ttu-id="45bd5-349">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-349">Invalid Grade of Service</span></span>|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a><span data-ttu-id="45bd5-350">存储接收管道的每个功能确认对出站交换响应中收到的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-350">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outbound Interchanges</span></span>  
 <span data-ttu-id="45bd5-351">接收管道接收每个功能确认的状态报表数据存储区中创建记录。</span><span class="sxs-lookup"><span data-stu-id="45bd5-351">The receive pipeline creates a record in the status report data store for each functional acknowledgment that it receives.</span></span>  <span data-ttu-id="45bd5-352">技术确认是 997 X12 和完整 CONTRL 消息 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="45bd5-352">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="45bd5-353">每个组的一个条目将创建。</span><span class="sxs-lookup"><span data-stu-id="45bd5-353">One entry per group will to be created.</span></span> <span data-ttu-id="45bd5-354">此项时使用的交换和组标头中的数据。</span><span class="sxs-lookup"><span data-stu-id="45bd5-354">Data from the interchange and group headers is used while making this entry.</span></span> <span data-ttu-id="45bd5-355">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="45bd5-355">The data stored includes:</span></span>  
  
-   <span data-ttu-id="45bd5-356">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-356">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="45bd5-357">功能 ACK 方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="45bd5-357">Functional ACK Direction = Send</span></span>  
  
-   <span data-ttu-id="45bd5-358">正常的 ACK 状态 = \<Generated 或不适用，请参阅备注 1\></span><span class="sxs-lookup"><span data-stu-id="45bd5-358">Functional ACK Status = \<Generated or Not Applicable, refer note 1\></span></span>  
  
-   <span data-ttu-id="45bd5-359">交换接收器 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-359">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-360">交换发件人 = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-360">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-361">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="45bd5-361">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-362">交换控件 ID = （所需的相关） 的更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-362">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-363">组控制编号 = 更新数据 (optional 对于 EDIFACT 和需要 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="45bd5-363">Group Control Number = Update Data (‘optional for EDIFACT’ and required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="45bd5-364">功能 ID 代码 = 更新数据 (GS01/UNG01)</span><span class="sxs-lookup"><span data-stu-id="45bd5-364">Functional ID Code = Update Data (GS01/UNG01)</span></span>  
  
-   <span data-ttu-id="45bd5-365">事务集的计数 = 更新数据 (UNE1/UNZ1)</span><span class="sxs-lookup"><span data-stu-id="45bd5-365">Count of Transaction Sets = Update Data (UNE1/UNZ1)</span></span>  
  
-   <span data-ttu-id="45bd5-366">功能 ACK 交换的控件 ID = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-366">Functional ACK Interchange Control ID= Not value – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-367">功能 ACK 交换日期 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-367">Functional ACK Interchange Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-368">功能 ACK 交换时间 = 不值 – 将发送端的应用</span><span class="sxs-lookup"><span data-stu-id="45bd5-368">Functional ACK Interchange Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="45bd5-369">计数的事务集收到 = 更新数据 (X12 AK903 和计算由 EDIFACT 编码的引擎)</span><span class="sxs-lookup"><span data-stu-id="45bd5-369">Count of Transaction Sets Received = Update Data (X12-AK903 and computed by Engine for EDIFACT encoding)</span></span>  
  
-   <span data-ttu-id="45bd5-370">计数的事务集接受 = 更新数据 (X12 AK904 和计算由引擎 EDIFACT 引擎)</span><span class="sxs-lookup"><span data-stu-id="45bd5-370">Count of Transaction Sets Accepted = Update Data (X12-AK904 and computed by Engine for EDIFACT engine)</span></span>  
  
-   <span data-ttu-id="45bd5-371">确认/操作代码 = 更新数据\<，请参阅备注 2\> （来自 X12 AK901 或 EDIFACT UCI4） *</span><span class="sxs-lookup"><span data-stu-id="45bd5-371">ACK/Action Code = Update Data  \<refer note 2\> (from X12-AK901 or EDIFACT-UCI4)*</span></span>  
  
-   <span data-ttu-id="45bd5-372">错误/语法错误代码 = 更新数据 (X12 AK905，EDIFACT UCI5) 请注意 3</span><span class="sxs-lookup"><span data-stu-id="45bd5-372">Error/Syntax Error Code  = Update Data (X12-AK905, EDIFACT UCI5) Note 3</span></span>  
  
-   <span data-ttu-id="45bd5-373">其他 X12 ACK 错误代码 2 = 更新数据 (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="45bd5-373">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="45bd5-374">其他 X12 ACK 错误代码 3 = 更新数据 (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="45bd5-374">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="45bd5-375">其他 X12 ACK 错误代码 4 = 更新数据 (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="45bd5-375">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="45bd5-376">其他 X12 ACK 错误代码 5 = 更新数据 (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="45bd5-376">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="45bd5-377">将使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="45bd5-377">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="45bd5-378">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-378">Data in ACK/Action Code</span></span>|<span data-ttu-id="45bd5-379">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-379">Error description for Reporting</span></span>|<span data-ttu-id="45bd5-380">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="45bd5-380">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="45bd5-381">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="45bd5-381">A</span></span>|<span data-ttu-id="45bd5-382">已接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-382">Accepted</span></span>|<span data-ttu-id="45bd5-383">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-383">X12</span></span>|  
|<span data-ttu-id="45bd5-384">E</span><span class="sxs-lookup"><span data-stu-id="45bd5-384">E</span></span>|<span data-ttu-id="45bd5-385">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-385">Accepted  with errors</span></span>|<span data-ttu-id="45bd5-386">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-386">X12</span></span>|  
|<span data-ttu-id="45bd5-387">P</span><span class="sxs-lookup"><span data-stu-id="45bd5-387">P</span></span>|<span data-ttu-id="45bd5-388">部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-388">Partially Accepted</span></span>|<span data-ttu-id="45bd5-389">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-389">X12</span></span>|  
|<span data-ttu-id="45bd5-390">R</span><span class="sxs-lookup"><span data-stu-id="45bd5-390">R</span></span>|<span data-ttu-id="45bd5-391">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-391">Rejected</span></span>|<span data-ttu-id="45bd5-392">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-392">X12</span></span>|  
|<span data-ttu-id="45bd5-393">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-393">4</span></span>|<span data-ttu-id="45bd5-394">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-394">Rejected</span></span>|<span data-ttu-id="45bd5-395">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-395">EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-396">7</span><span class="sxs-lookup"><span data-stu-id="45bd5-396">7</span></span>|<span data-ttu-id="45bd5-397">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-397">Accepted/Partially Accepted</span></span>|<span data-ttu-id="45bd5-398">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-398">EDIFACT</span></span>|  
  
 <span data-ttu-id="45bd5-399">以下的错误/语法错误代码将用于 EDIFACT:</span><span class="sxs-lookup"><span data-stu-id="45bd5-399">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="45bd5-400">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="45bd5-400">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="45bd5-401">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="45bd5-401">(applicable to EDIFACT)</span></span>|<span data-ttu-id="45bd5-402">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-402">Error Description for reporting</span></span>|  
|--------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="45bd5-403">2</span><span class="sxs-lookup"><span data-stu-id="45bd5-403">2</span></span>|<span data-ttu-id="45bd5-404">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="45bd5-404">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="45bd5-405">7</span><span class="sxs-lookup"><span data-stu-id="45bd5-405">7</span></span>|<span data-ttu-id="45bd5-406">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-406">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="45bd5-407">12</span><span class="sxs-lookup"><span data-stu-id="45bd5-407">12</span></span>|<span data-ttu-id="45bd5-408">无效值</span><span class="sxs-lookup"><span data-stu-id="45bd5-408">Invalid value</span></span>|  
|<span data-ttu-id="45bd5-409">13</span><span class="sxs-lookup"><span data-stu-id="45bd5-409">13</span></span>|<span data-ttu-id="45bd5-410">Missing</span><span class="sxs-lookup"><span data-stu-id="45bd5-410">Missing</span></span>|  
|<span data-ttu-id="45bd5-411">14</span><span class="sxs-lookup"><span data-stu-id="45bd5-411">14</span></span>|<span data-ttu-id="45bd5-412">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="45bd5-412">Value not supported in this position</span></span>|  
|<span data-ttu-id="45bd5-413">15</span><span class="sxs-lookup"><span data-stu-id="45bd5-413">15</span></span>|<span data-ttu-id="45bd5-414">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="45bd5-414">Not supported in this position</span></span>|  
|<span data-ttu-id="45bd5-415">16</span><span class="sxs-lookup"><span data-stu-id="45bd5-415">16</span></span>|<span data-ttu-id="45bd5-416">组分过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-416">Too many constituents</span></span>|  
|<span data-ttu-id="45bd5-417">17</span><span class="sxs-lookup"><span data-stu-id="45bd5-417">17</span></span>|<span data-ttu-id="45bd5-418">无协议</span><span class="sxs-lookup"><span data-stu-id="45bd5-418">No agreement</span></span>|  
|<span data-ttu-id="45bd5-419">18</span><span class="sxs-lookup"><span data-stu-id="45bd5-419">18</span></span>|<span data-ttu-id="45bd5-420">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-420">Unspecified error</span></span>|  
|<span data-ttu-id="45bd5-421">19</span><span class="sxs-lookup"><span data-stu-id="45bd5-421">19</span></span>|<span data-ttu-id="45bd5-422">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-422">Invalid decimal notation</span></span>|  
|<span data-ttu-id="45bd5-423">20</span><span class="sxs-lookup"><span data-stu-id="45bd5-423">20</span></span>|<span data-ttu-id="45bd5-424">字符无效，因为服务字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-424">Character invalid as service character</span></span>|  
|<span data-ttu-id="45bd5-425">21</span><span class="sxs-lookup"><span data-stu-id="45bd5-425">21</span></span>|<span data-ttu-id="45bd5-426">无效字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-426">Invalid character(s)</span></span>|  
|<span data-ttu-id="45bd5-427">22</span><span class="sxs-lookup"><span data-stu-id="45bd5-427">22</span></span>|<span data-ttu-id="45bd5-428">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-428">Invalid service character(s)</span></span>|  
|<span data-ttu-id="45bd5-429">23</span><span class="sxs-lookup"><span data-stu-id="45bd5-429">23</span></span>|<span data-ttu-id="45bd5-430">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-430">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="45bd5-431">24</span><span class="sxs-lookup"><span data-stu-id="45bd5-431">24</span></span>|<span data-ttu-id="45bd5-432">太旧</span><span class="sxs-lookup"><span data-stu-id="45bd5-432">Too old</span></span>|  
|<span data-ttu-id="45bd5-433">25</span><span class="sxs-lookup"><span data-stu-id="45bd5-433">25</span></span>|<span data-ttu-id="45bd5-434">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="45bd5-434">Test indicator not supported</span></span>|  
|<span data-ttu-id="45bd5-435">26</span><span class="sxs-lookup"><span data-stu-id="45bd5-435">26</span></span>|<span data-ttu-id="45bd5-436">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-436">Duplicate detected</span></span>|  
|<span data-ttu-id="45bd5-437">27</span><span class="sxs-lookup"><span data-stu-id="45bd5-437">27</span></span>|<span data-ttu-id="45bd5-438">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="45bd5-438">Security function not supported</span></span>|  
|<span data-ttu-id="45bd5-439">28</span><span class="sxs-lookup"><span data-stu-id="45bd5-439">28</span></span>|<span data-ttu-id="45bd5-440">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-440">References do not match</span></span>|  
|<span data-ttu-id="45bd5-441">29</span><span class="sxs-lookup"><span data-stu-id="45bd5-441">29</span></span>|<span data-ttu-id="45bd5-442">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-442">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="45bd5-443">30</span><span class="sxs-lookup"><span data-stu-id="45bd5-443">30</span></span>|<span data-ttu-id="45bd5-444">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="45bd5-444">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="45bd5-445">31</span><span class="sxs-lookup"><span data-stu-id="45bd5-445">31</span></span>|<span data-ttu-id="45bd5-446">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="45bd5-446">More than one message type in group</span></span>|  
|<span data-ttu-id="45bd5-447">32</span><span class="sxs-lookup"><span data-stu-id="45bd5-447">32</span></span>|<span data-ttu-id="45bd5-448">低级别为空</span><span class="sxs-lookup"><span data-stu-id="45bd5-448">Lower level empty</span></span>|  
|<span data-ttu-id="45bd5-449">33</span><span class="sxs-lookup"><span data-stu-id="45bd5-449">33</span></span>|<span data-ttu-id="45bd5-450">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-450">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="45bd5-451">34</span><span class="sxs-lookup"><span data-stu-id="45bd5-451">34</span></span>|<span data-ttu-id="45bd5-452">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="45bd5-452">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="45bd5-453">35</span><span class="sxs-lookup"><span data-stu-id="45bd5-453">35</span></span>|<span data-ttu-id="45bd5-454">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-454">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="45bd5-455">36</span><span class="sxs-lookup"><span data-stu-id="45bd5-455">36</span></span>|<span data-ttu-id="45bd5-456">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-456">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="45bd5-457">37</span><span class="sxs-lookup"><span data-stu-id="45bd5-457">37</span></span>|<span data-ttu-id="45bd5-458">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-458">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="45bd5-459">38</span><span class="sxs-lookup"><span data-stu-id="45bd5-459">38</span></span>|<span data-ttu-id="45bd5-460">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="45bd5-460">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="45bd5-461">39</span><span class="sxs-lookup"><span data-stu-id="45bd5-461">39</span></span>|<span data-ttu-id="45bd5-462">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="45bd5-462">Data element too long</span></span>|  
|<span data-ttu-id="45bd5-463">40</span><span class="sxs-lookup"><span data-stu-id="45bd5-463">40</span></span>|<span data-ttu-id="45bd5-464">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="45bd5-464">Data element too short</span></span>|  
|<span data-ttu-id="45bd5-465">41</span><span class="sxs-lookup"><span data-stu-id="45bd5-465">41</span></span>|<span data-ttu-id="45bd5-466">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-466">Permanent communication network error</span></span>|  
|<span data-ttu-id="45bd5-467">42</span><span class="sxs-lookup"><span data-stu-id="45bd5-467">42</span></span>|<span data-ttu-id="45bd5-468">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-468">Temporary communication network error</span></span>|  
|<span data-ttu-id="45bd5-469">43</span><span class="sxs-lookup"><span data-stu-id="45bd5-469">43</span></span>|<span data-ttu-id="45bd5-470">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-470">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="45bd5-471">45</span><span class="sxs-lookup"><span data-stu-id="45bd5-471">45</span></span>|<span data-ttu-id="45bd5-472">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="45bd5-472">Trailing separator</span></span>|  
|<span data-ttu-id="45bd5-473">46</span><span class="sxs-lookup"><span data-stu-id="45bd5-473">46</span></span>|<span data-ttu-id="45bd5-474">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="45bd5-474">Character set not supported</span></span>|  
|<span data-ttu-id="45bd5-475">47</span><span class="sxs-lookup"><span data-stu-id="45bd5-475">47</span></span>|<span data-ttu-id="45bd5-476">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="45bd5-476">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="45bd5-477">48</span><span class="sxs-lookup"><span data-stu-id="45bd5-477">48</span></span>|<span data-ttu-id="45bd5-478">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="45bd5-478">Dependency condition violated</span></span>|  
|<span data-ttu-id="45bd5-479">70</span><span class="sxs-lookup"><span data-stu-id="45bd5-479">70</span></span>|<span data-ttu-id="45bd5-480">事务集缺失或无效的事务集标识符</span><span class="sxs-lookup"><span data-stu-id="45bd5-480">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="45bd5-481">71</span><span class="sxs-lookup"><span data-stu-id="45bd5-481">71</span></span>|<span data-ttu-id="45bd5-482">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-482">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="45bd5-483">72</span><span class="sxs-lookup"><span data-stu-id="45bd5-483">72</span></span>|<span data-ttu-id="45bd5-484">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-484">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="45bd5-485">73</span><span class="sxs-lookup"><span data-stu-id="45bd5-485">73</span></span>|<span data-ttu-id="45bd5-486">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="45bd5-486">XML not at correct position</span></span>|  
|<span data-ttu-id="45bd5-487">74</span><span class="sxs-lookup"><span data-stu-id="45bd5-487">74</span></span>|<span data-ttu-id="45bd5-488">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-488">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="45bd5-489">75</span><span class="sxs-lookup"><span data-stu-id="45bd5-489">75</span></span>|<span data-ttu-id="45bd5-490">段重复过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-490">Too few segment repetitions</span></span>|  
|<span data-ttu-id="45bd5-491">76</span><span class="sxs-lookup"><span data-stu-id="45bd5-491">76</span></span>|<span data-ttu-id="45bd5-492">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-492">Too few data elements found</span></span>|  
  
 <span data-ttu-id="45bd5-493">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="45bd5-493">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="45bd5-494">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="45bd5-494">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="45bd5-495">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="45bd5-495">(applicable to X12)</span></span>|<span data-ttu-id="45bd5-496">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-496">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="45bd5-497">1</span><span class="sxs-lookup"><span data-stu-id="45bd5-497">1</span></span>|<span data-ttu-id="45bd5-498">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="45bd5-498">Functional group not supported</span></span>|  
|<span data-ttu-id="45bd5-499">2</span><span class="sxs-lookup"><span data-stu-id="45bd5-499">2</span></span>|<span data-ttu-id="45bd5-500">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="45bd5-500">Functional group version not supported</span></span>|  
|<span data-ttu-id="45bd5-501">3</span><span class="sxs-lookup"><span data-stu-id="45bd5-501">3</span></span>|<span data-ttu-id="45bd5-502">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="45bd5-502">Functional group trailer missing</span></span>|  
|<span data-ttu-id="45bd5-503">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-503">4</span></span>|<span data-ttu-id="45bd5-504">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="45bd5-504">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="45bd5-505">5</span><span class="sxs-lookup"><span data-stu-id="45bd5-505">5</span></span>|<span data-ttu-id="45bd5-506">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-506">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="45bd5-507">6-26</span><span class="sxs-lookup"><span data-stu-id="45bd5-507">6-26</span></span>|<span data-ttu-id="45bd5-508">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-508">Other unsupported validation errors</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a><span data-ttu-id="45bd5-509">接收管道为每个为了响应传出交换而接收的功能确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-509">Data Updated by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outgoing Interchanges</span></span>  
 <span data-ttu-id="45bd5-510">对于接收管道接收的每个功能确认，发送管道会更新所发送相关交换的状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="45bd5-510">For each functional acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="45bd5-511">EDI 拆装器使用传入确认的交换和组标头段中的数据来定位数据存储区中的记录：</span><span class="sxs-lookup"><span data-stu-id="45bd5-511">The EDI Disassembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="45bd5-512">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="45bd5-512">Fields in ACK</span></span>|<span data-ttu-id="45bd5-513">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="45bd5-513">Fields in Data store</span></span>|<span data-ttu-id="45bd5-514">注释</span><span class="sxs-lookup"><span data-stu-id="45bd5-514">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="45bd5-515">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-515">Interchange Sender ID</span></span>|<span data-ttu-id="45bd5-516">交换收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-516">Interchange Receiver</span></span>|<span data-ttu-id="45bd5-517">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-517">Applicable to both X12 and EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-518">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-518">Interchange Receiver ID</span></span>|<span data-ttu-id="45bd5-519">交换发件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-519">Interchange Sender</span></span>|<span data-ttu-id="45bd5-520">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-520">Applicable to both X12 and EDIFACT</span></span>|  
|-|<span data-ttu-id="45bd5-521">交换日期</span><span class="sxs-lookup"><span data-stu-id="45bd5-521">Interchange Date</span></span>|-|  
|<span data-ttu-id="45bd5-522">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="45bd5-522">Interchange Control Number</span></span>|<span data-ttu-id="45bd5-523">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-523">Interchange Control ID</span></span>|<span data-ttu-id="45bd5-524">仅适用于 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-524">Applicable only to EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-525">组控制编号</span><span class="sxs-lookup"><span data-stu-id="45bd5-525">Group Control Number</span></span>|<span data-ttu-id="45bd5-526">组控制编号</span><span class="sxs-lookup"><span data-stu-id="45bd5-526">Group Control Number</span></span>|<span data-ttu-id="45bd5-527">仅适用于 X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-527">Applicable only to X12</span></span>|  
|-|<span data-ttu-id="45bd5-528">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="45bd5-528">Interchange Direction = Send</span></span>|<span data-ttu-id="45bd5-529">由于要在 BIBO 方案中实现唯一性，因此是必需</span><span class="sxs-lookup"><span data-stu-id="45bd5-529">Required since in BIBO Scenario for uniqueness</span></span>|  
|<span data-ttu-id="45bd5-530">记录类型</span><span class="sxs-lookup"><span data-stu-id="45bd5-530">Record Type</span></span>|<span data-ttu-id="45bd5-531">功能确认状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-531">Functional ACK Status</span></span>|<span data-ttu-id="45bd5-532">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-532">Applicable to both X12 and EDIFACT</span></span>|  
  
 <span data-ttu-id="45bd5-533">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="45bd5-533">The data stored includes:</span></span>  
  
-   <span data-ttu-id="45bd5-534">记录类型 = 功能 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="45bd5-534">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="45bd5-535">功能确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="45bd5-535">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="45bd5-536">功能确认状态 = 按照接收来更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-536">Functional ACK Status =Update Data as Received</span></span>  
  
-   <span data-ttu-id="45bd5-537">交换接收器 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-537">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-538">交换发件人 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-538">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-539">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-539">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-540">交换控件 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-540">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-541">组控制编号 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-541">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-542">功能 ID 代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-542">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-543">事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-543">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="45bd5-544">功能确认交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-544">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-545">功能确认交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-545">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-546">功能确认交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-546">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="45bd5-547">传送的事务集的计数 = 更新数据（X12 AK903，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="45bd5-547">Count of Transaction Sets Delivered = Update Data (X12 AK903 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="45bd5-548">接受的事务集的计数 = 更新数据（X12 AK904，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="45bd5-548">Count of Transaction Sets Accepted = Update Data (X12 AK904 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="45bd5-549">确认/操作代码 = 更新数据（X12 AK901 和 UCI4）引用注释 1</span><span class="sxs-lookup"><span data-stu-id="45bd5-549">ACK/Action Code = Update Data (X12 AK901 and UCI4) Refer Note 1</span></span>  
  
-   <span data-ttu-id="45bd5-550">错误/语法错误代码 =（X12 AK905 和 UCI5）引用注释 2</span><span class="sxs-lookup"><span data-stu-id="45bd5-550">Error/Syntax Error Code  = (X12 AK905 and UCI5) Refer Note 2</span></span>  
  
-   <span data-ttu-id="45bd5-551">其他 X12 ACK 错误代码 2 = 更新数据 (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="45bd5-551">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="45bd5-552">其他 X12 ACK 错误代码 3 = 更新数据 (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="45bd5-552">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="45bd5-553">其他 X12 ACK 错误代码 4 = 更新数据 (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="45bd5-553">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="45bd5-554">其他 X12 ACK 错误代码 5 = 更新数据 (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="45bd5-554">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="45bd5-555">将使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="45bd5-555">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="45bd5-556">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-556">Data in ACK/Action Code</span></span>|<span data-ttu-id="45bd5-557">状态报告的映射</span><span class="sxs-lookup"><span data-stu-id="45bd5-557">Mapped for Status Reporting</span></span>|<span data-ttu-id="45bd5-558">注释</span><span class="sxs-lookup"><span data-stu-id="45bd5-558">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="45bd5-559">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="45bd5-559">A</span></span>|<span data-ttu-id="45bd5-560">已接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-560">Accepted</span></span>|<span data-ttu-id="45bd5-561">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-561">X12</span></span>|  
|<span data-ttu-id="45bd5-562">P</span><span class="sxs-lookup"><span data-stu-id="45bd5-562">P</span></span>|<span data-ttu-id="45bd5-563">部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-563">Partially Accepted</span></span>|<span data-ttu-id="45bd5-564">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-564">X12</span></span>|  
|<span data-ttu-id="45bd5-565">R、 M、 W 和 X</span><span class="sxs-lookup"><span data-stu-id="45bd5-565">R, M, W, X</span></span>|<span data-ttu-id="45bd5-566">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-566">Rejected</span></span>|<span data-ttu-id="45bd5-567">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-567">X12</span></span>|  
|<span data-ttu-id="45bd5-568">E</span><span class="sxs-lookup"><span data-stu-id="45bd5-568">E</span></span>|<span data-ttu-id="45bd5-569">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-569">Accepted with errors</span></span>|<span data-ttu-id="45bd5-570">X12</span><span class="sxs-lookup"><span data-stu-id="45bd5-570">X12</span></span>|  
|<span data-ttu-id="45bd5-571">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-571">4</span></span>|<span data-ttu-id="45bd5-572">已拒绝</span><span class="sxs-lookup"><span data-stu-id="45bd5-572">Rejected</span></span>|<span data-ttu-id="45bd5-573">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-573">EDIFACT</span></span>|  
|<span data-ttu-id="45bd5-574">7, 8</span><span class="sxs-lookup"><span data-stu-id="45bd5-574">7, 8</span></span>|<span data-ttu-id="45bd5-575">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="45bd5-575">Accepted/Partially Accepted</span></span>|<span data-ttu-id="45bd5-576">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="45bd5-576">EDIFACT</span></span>|  
  
 <span data-ttu-id="45bd5-577">以下的错误/语法错误代码将用于 EDIFACT:</span><span class="sxs-lookup"><span data-stu-id="45bd5-577">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="45bd5-578">错误/语法错误 Cod 中的数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-578">Data in Error/Syntax Error Cod</span></span><br /><br /> <span data-ttu-id="45bd5-579">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="45bd5-579">(applicable to EDIFACT)</span></span>|<span data-ttu-id="45bd5-580">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-580">Error Description for reporting</span></span>|  
|-------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="45bd5-581">2</span><span class="sxs-lookup"><span data-stu-id="45bd5-581">2</span></span>|<span data-ttu-id="45bd5-582">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="45bd5-582">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="45bd5-583">7</span><span class="sxs-lookup"><span data-stu-id="45bd5-583">7</span></span>|<span data-ttu-id="45bd5-584">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-584">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="45bd5-585">12</span><span class="sxs-lookup"><span data-stu-id="45bd5-585">12</span></span>|<span data-ttu-id="45bd5-586">无效值</span><span class="sxs-lookup"><span data-stu-id="45bd5-586">Invalid value</span></span>|  
|<span data-ttu-id="45bd5-587">13</span><span class="sxs-lookup"><span data-stu-id="45bd5-587">13</span></span>|<span data-ttu-id="45bd5-588">Missing</span><span class="sxs-lookup"><span data-stu-id="45bd5-588">Missing</span></span>|  
|<span data-ttu-id="45bd5-589">14</span><span class="sxs-lookup"><span data-stu-id="45bd5-589">14</span></span>|<span data-ttu-id="45bd5-590">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="45bd5-590">Value not supported in this position</span></span>|  
|<span data-ttu-id="45bd5-591">15</span><span class="sxs-lookup"><span data-stu-id="45bd5-591">15</span></span>|<span data-ttu-id="45bd5-592">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="45bd5-592">Not supported in this position</span></span>|  
|<span data-ttu-id="45bd5-593">16</span><span class="sxs-lookup"><span data-stu-id="45bd5-593">16</span></span>|<span data-ttu-id="45bd5-594">组分过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-594">Too many constituents</span></span>|  
|<span data-ttu-id="45bd5-595">17</span><span class="sxs-lookup"><span data-stu-id="45bd5-595">17</span></span>|<span data-ttu-id="45bd5-596">无协议</span><span class="sxs-lookup"><span data-stu-id="45bd5-596">No agreement</span></span>|  
|<span data-ttu-id="45bd5-597">18</span><span class="sxs-lookup"><span data-stu-id="45bd5-597">18</span></span>|<span data-ttu-id="45bd5-598">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-598">Unspecified error</span></span>|  
|<span data-ttu-id="45bd5-599">19</span><span class="sxs-lookup"><span data-stu-id="45bd5-599">19</span></span>|<span data-ttu-id="45bd5-600">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-600">Invalid decimal notation</span></span>|  
|<span data-ttu-id="45bd5-601">20</span><span class="sxs-lookup"><span data-stu-id="45bd5-601">20</span></span>|<span data-ttu-id="45bd5-602">字符无效，因为服务字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-602">Character invalid as service character</span></span>|  
|<span data-ttu-id="45bd5-603">21</span><span class="sxs-lookup"><span data-stu-id="45bd5-603">21</span></span>|<span data-ttu-id="45bd5-604">无效字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-604">Invalid character(s)</span></span>|  
|<span data-ttu-id="45bd5-605">22</span><span class="sxs-lookup"><span data-stu-id="45bd5-605">22</span></span>|<span data-ttu-id="45bd5-606">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="45bd5-606">Invalid service character(s)</span></span>|  
|<span data-ttu-id="45bd5-607">23</span><span class="sxs-lookup"><span data-stu-id="45bd5-607">23</span></span>|<span data-ttu-id="45bd5-608">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-608">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="45bd5-609">24</span><span class="sxs-lookup"><span data-stu-id="45bd5-609">24</span></span>|<span data-ttu-id="45bd5-610">太旧</span><span class="sxs-lookup"><span data-stu-id="45bd5-610">Too old</span></span>|  
|<span data-ttu-id="45bd5-611">25</span><span class="sxs-lookup"><span data-stu-id="45bd5-611">25</span></span>|<span data-ttu-id="45bd5-612">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="45bd5-612">Test indicator not supported</span></span>|  
|<span data-ttu-id="45bd5-613">26</span><span class="sxs-lookup"><span data-stu-id="45bd5-613">26</span></span>|<span data-ttu-id="45bd5-614">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-614">Duplicate detected</span></span>|  
|<span data-ttu-id="45bd5-615">27</span><span class="sxs-lookup"><span data-stu-id="45bd5-615">27</span></span>|<span data-ttu-id="45bd5-616">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="45bd5-616">Security function not supported</span></span>|  
|<span data-ttu-id="45bd5-617">28</span><span class="sxs-lookup"><span data-stu-id="45bd5-617">28</span></span>|<span data-ttu-id="45bd5-618">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-618">References do not match</span></span>|  
|<span data-ttu-id="45bd5-619">29</span><span class="sxs-lookup"><span data-stu-id="45bd5-619">29</span></span>|<span data-ttu-id="45bd5-620">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-620">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="45bd5-621">30</span><span class="sxs-lookup"><span data-stu-id="45bd5-621">30</span></span>|<span data-ttu-id="45bd5-622">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="45bd5-622">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="45bd5-623">31</span><span class="sxs-lookup"><span data-stu-id="45bd5-623">31</span></span>|<span data-ttu-id="45bd5-624">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="45bd5-624">More than one message type in group</span></span>|  
|<span data-ttu-id="45bd5-625">32</span><span class="sxs-lookup"><span data-stu-id="45bd5-625">32</span></span>|<span data-ttu-id="45bd5-626">低级别为空</span><span class="sxs-lookup"><span data-stu-id="45bd5-626">Lower level empty</span></span>|  
|<span data-ttu-id="45bd5-627">33</span><span class="sxs-lookup"><span data-stu-id="45bd5-627">33</span></span>|<span data-ttu-id="45bd5-628">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="45bd5-628">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="45bd5-629">34</span><span class="sxs-lookup"><span data-stu-id="45bd5-629">34</span></span>|<span data-ttu-id="45bd5-630">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="45bd5-630">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="45bd5-631">35</span><span class="sxs-lookup"><span data-stu-id="45bd5-631">35</span></span>|<span data-ttu-id="45bd5-632">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-632">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="45bd5-633">36</span><span class="sxs-lookup"><span data-stu-id="45bd5-633">36</span></span>|<span data-ttu-id="45bd5-634">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="45bd5-634">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="45bd5-635">37</span><span class="sxs-lookup"><span data-stu-id="45bd5-635">37</span></span>|<span data-ttu-id="45bd5-636">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="45bd5-636">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="45bd5-637">38</span><span class="sxs-lookup"><span data-stu-id="45bd5-637">38</span></span>|<span data-ttu-id="45bd5-638">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="45bd5-638">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="45bd5-639">39</span><span class="sxs-lookup"><span data-stu-id="45bd5-639">39</span></span>|<span data-ttu-id="45bd5-640">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="45bd5-640">Data element too long</span></span>|  
|<span data-ttu-id="45bd5-641">40</span><span class="sxs-lookup"><span data-stu-id="45bd5-641">40</span></span>|<span data-ttu-id="45bd5-642">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="45bd5-642">Data element too short</span></span>|  
|<span data-ttu-id="45bd5-643">41</span><span class="sxs-lookup"><span data-stu-id="45bd5-643">41</span></span>|<span data-ttu-id="45bd5-644">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-644">Permanent communication network error</span></span>|  
|<span data-ttu-id="45bd5-645">42</span><span class="sxs-lookup"><span data-stu-id="45bd5-645">42</span></span>|<span data-ttu-id="45bd5-646">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-646">Temporary communication network error</span></span>|  
|<span data-ttu-id="45bd5-647">43</span><span class="sxs-lookup"><span data-stu-id="45bd5-647">43</span></span>|<span data-ttu-id="45bd5-648">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="45bd5-648">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="45bd5-649">45</span><span class="sxs-lookup"><span data-stu-id="45bd5-649">45</span></span>|<span data-ttu-id="45bd5-650">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="45bd5-650">Trailing separator</span></span>|  
|<span data-ttu-id="45bd5-651">46</span><span class="sxs-lookup"><span data-stu-id="45bd5-651">46</span></span>|<span data-ttu-id="45bd5-652">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="45bd5-652">Character set not supported</span></span>|  
|<span data-ttu-id="45bd5-653">47</span><span class="sxs-lookup"><span data-stu-id="45bd5-653">47</span></span>|<span data-ttu-id="45bd5-654">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="45bd5-654">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="45bd5-655">48</span><span class="sxs-lookup"><span data-stu-id="45bd5-655">48</span></span>|<span data-ttu-id="45bd5-656">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="45bd5-656">Dependency condition violated</span></span>|  
|<span data-ttu-id="45bd5-657">70</span><span class="sxs-lookup"><span data-stu-id="45bd5-657">70</span></span>|<span data-ttu-id="45bd5-658">事务集缺失或无效的事务集标识符</span><span class="sxs-lookup"><span data-stu-id="45bd5-658">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="45bd5-659">71</span><span class="sxs-lookup"><span data-stu-id="45bd5-659">71</span></span>|<span data-ttu-id="45bd5-660">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-660">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="45bd5-661">72</span><span class="sxs-lookup"><span data-stu-id="45bd5-661">72</span></span>|<span data-ttu-id="45bd5-662">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="45bd5-662">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="45bd5-663">73</span><span class="sxs-lookup"><span data-stu-id="45bd5-663">73</span></span>|<span data-ttu-id="45bd5-664">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="45bd5-664">XML not at correct position</span></span>|  
|<span data-ttu-id="45bd5-665">74</span><span class="sxs-lookup"><span data-stu-id="45bd5-665">74</span></span>|<span data-ttu-id="45bd5-666">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-666">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="45bd5-667">75</span><span class="sxs-lookup"><span data-stu-id="45bd5-667">75</span></span>|<span data-ttu-id="45bd5-668">段重复过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-668">Too few segment repetitions</span></span>|  
|<span data-ttu-id="45bd5-669">76</span><span class="sxs-lookup"><span data-stu-id="45bd5-669">76</span></span>|<span data-ttu-id="45bd5-670">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="45bd5-670">Too few data elements found</span></span>|  
  
 <span data-ttu-id="45bd5-671">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="45bd5-671">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="45bd5-672">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="45bd5-672">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="45bd5-673">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="45bd5-673">(applicable to X12)</span></span>|<span data-ttu-id="45bd5-674">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="45bd5-674">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="45bd5-675">1</span><span class="sxs-lookup"><span data-stu-id="45bd5-675">1</span></span>|<span data-ttu-id="45bd5-676">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="45bd5-676">Functional group not supported</span></span>|  
|<span data-ttu-id="45bd5-677">2</span><span class="sxs-lookup"><span data-stu-id="45bd5-677">2</span></span>|<span data-ttu-id="45bd5-678">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="45bd5-678">Functional group version not supported</span></span>|  
|<span data-ttu-id="45bd5-679">3</span><span class="sxs-lookup"><span data-stu-id="45bd5-679">3</span></span>|<span data-ttu-id="45bd5-680">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="45bd5-680">Functional group trailer missing</span></span>|  
|<span data-ttu-id="45bd5-681">4</span><span class="sxs-lookup"><span data-stu-id="45bd5-681">4</span></span>|<span data-ttu-id="45bd5-682">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="45bd5-682">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="45bd5-683">5</span><span class="sxs-lookup"><span data-stu-id="45bd5-683">5</span></span>|<span data-ttu-id="45bd5-684">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="45bd5-684">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="45bd5-685">6-26</span><span class="sxs-lookup"><span data-stu-id="45bd5-685">6-26</span></span>|<span data-ttu-id="45bd5-686">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="45bd5-686">Other unsupported validation errors</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45bd5-687">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45bd5-687">See Also</span></span>  
 <span data-ttu-id="45bd5-688">[如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="45bd5-688">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="45bd5-689">如何为入站 EDI 消息存储数据</span><span class="sxs-lookup"><span data-stu-id="45bd5-689">How Data Is Stored for Inbound EDI Messages</span></span>](../core/how-data-is-stored-for-inbound-edi-messages.md)