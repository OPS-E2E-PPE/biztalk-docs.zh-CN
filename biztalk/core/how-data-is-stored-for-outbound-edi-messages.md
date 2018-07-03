---
title: 如何为出站 EDI 消息存储数据 |Microsoft Docs
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
ms.openlocfilehash: 3cb6768605c39eff857a5dda4ed523dd1b524b5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001414"
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a><span data-ttu-id="d6e05-102">出站 EDI 消息数据的存储方式</span><span class="sxs-lookup"><span data-stu-id="d6e05-102">How Data Is Stored for Outbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d6e05-103"> 执行以下操作生成的出站交换状态报告条目：</span><span class="sxs-lookup"><span data-stu-id="d6e05-103"> does the following to generate a status report entry for an outbound interchange:</span></span>  
  
1.  <span data-ttu-id="d6e05-104">当出站消息 XML 发送到 EDI 发送管道时，发送管道在状态报告具有以下值的数据存储区中创建一个条目：</span><span class="sxs-lookup"><span data-stu-id="d6e05-104">When outbound message XML is sent to the EDI send pipeline, the send pipeline creates an entry in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="d6e05-105">交换状态条目将设置为已处理</span><span class="sxs-lookup"><span data-stu-id="d6e05-105">Interchange status entry is set to Processed</span></span>  
  
    -   <span data-ttu-id="d6e05-106">交换确认状态条目 （一个每个交换） 设置为预期</span><span class="sxs-lookup"><span data-stu-id="d6e05-106">Interchange ACK status entry (one per interchange) is set to Expected</span></span>  
  
    -   <span data-ttu-id="d6e05-107">功能确认状态条目 （一个每个组在 X12 中，一个用于在 EDIFACT 中的所有组） 设置为预期</span><span class="sxs-lookup"><span data-stu-id="d6e05-107">Functional ACK status entries (one per group in X12, one for all groups in EDIFACT) are set to Expected</span></span>  
  
2.  <span data-ttu-id="d6e05-108">EDI 消息已发送到贸易合作伙伴，并从贸易合作伙伴返回确认后，EDI 接收管道接收确认更新交换状态、 交换 ACK 状态和功能ACK 状态条目为已接受/部分接受/拒绝，根据需要。</span><span class="sxs-lookup"><span data-stu-id="d6e05-108">After the EDI message has been sent to the trading partner, and the acknowledgment has been returned from the trading partner, the EDI receive pipeline that receives the acknowledgment updates the Interchange status, the Interchange ACK status, and the Functional ACK status entries to Accepted/Partially Accepted/Rejected, as appropriate.</span></span>  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a><span data-ttu-id="d6e05-109">发送管道为出站交换存储的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-109">Data Stored by the Send Pipeline for Outbound Interchanges</span></span>  
 <span data-ttu-id="d6e05-110">发送管道在发送每个交换状态报告数据存储区中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="d6e05-110">The send pipeline creates a record in the status report data store for each interchange that it sends.</span></span> <span data-ttu-id="d6e05-111">可从交换标头/尾部段 （ISA/IEA 或 UNB/UNZ） 最多的数据所需的条目。</span><span class="sxs-lookup"><span data-stu-id="d6e05-111">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="d6e05-112">可从发送端口的属性的其他数据。</span><span class="sxs-lookup"><span data-stu-id="d6e05-112">Other data is available from send port properties.</span></span> <span data-ttu-id="d6e05-113">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="d6e05-113">The data stored includes:</span></span>  
  
-   <span data-ttu-id="d6e05-114">记录类型 = 交换状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-114">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="d6e05-115">交换方向 = 更新数据 = 发送</span><span class="sxs-lookup"><span data-stu-id="d6e05-115">Interchange Direction = Update Data = Send</span></span>  
  
-   <span data-ttu-id="d6e05-116">交换接收方 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-116">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="d6e05-117">交换发送方 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-117">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="d6e05-118">交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-118">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="d6e05-119">交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-119">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="d6e05-120">交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-120">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="d6e05-121">交换状态： 处理/发送。</span><span class="sxs-lookup"><span data-stu-id="d6e05-121">Interchange Status: Processed/Sent.</span></span> <span data-ttu-id="d6e05-122">已处理状态指示已成功处理交换和其移交给交付的发送适配器发送管道。</span><span class="sxs-lookup"><span data-stu-id="d6e05-122">A status of Processed indicates that the send pipeline has successfully processed the interchange and handed it over to the send adapter for delivery.</span></span>  
  
-   <span data-ttu-id="d6e05-123">交换控制计数 (X12 中的组/消息分别) = 数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-123">Interchange Control Count (Groups/Messages in X12 respectively) = Data</span></span>  
  
-   <span data-ttu-id="d6e05-124">交换发送端口 ID = 数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-124">Interchange Send Port ID = Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="d6e05-125">接收管道为收到响应的出站交换中每个技术确认存储的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-125">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="d6e05-126">接收管道接收每个技术确认状态报告数据存储区创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="d6e05-126">The receive pipeline creates a record in the status report data store for each technical acknowledgment that it receives.</span></span> <span data-ttu-id="d6e05-127">接收管道创建每个接收的交换在状态报告数据存储区中的记录。</span><span class="sxs-lookup"><span data-stu-id="d6e05-127">The receive pipeline creates a record of each interchange received in the status report data store.</span></span> <span data-ttu-id="d6e05-128">每个技术确认作为响应的交换发送给贸易合作伙伴接收的数据存储区中创建一个技术确认状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="d6e05-128">creates one technical acknowledgment status report entry in the data store for each technical ACK received as a response to an interchange sent to a trading partner.</span></span> <span data-ttu-id="d6e05-129">只有 UCI 段对于 EDIFACT 具有用于 CONTRL 消息和 X12 TA1 技术确认。</span><span class="sxs-lookup"><span data-stu-id="d6e05-129">The technical acknowledge is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="d6e05-130">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="d6e05-130">The data stored includes:</span></span>  
  
- <span data-ttu-id="d6e05-131">记录类型 = 交换确认状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-131">Record Type = Interchange ACK Status</span></span>  
  
- <span data-ttu-id="d6e05-132">交换确认方向 = 发送-更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-132">Interchange ACK Direction = Send – Update Data</span></span>  
  
- <span data-ttu-id="d6e05-133">交换接收方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-133">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-134">交换发送方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-134">Interchange Sender = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-135">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="d6e05-135">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
- <span data-ttu-id="d6e05-136">交换控制 ID = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-136">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-137">交换确认状态 = 已生成或不适用\<引用注释 0&gt\> -更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-137">Interchange ACK Status = Generated or Not Applicable \<Refer Note 0\> - Update Data</span></span>  
  
- <span data-ttu-id="d6e05-138">交换确认控制 ID = 不赋值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-138">Interchange ACK Control ID= Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-139">交换确认日期 = 不赋值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-139">Interchange ACK Date = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-140">交换确认时间 = 不赋值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-140">Interchange ACK Time = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-141">确认/操作代码 = 更新数据\<，请参阅备注 1\> （来自 X12-TA104 或 EDIFACT-UCI4） \*</span><span class="sxs-lookup"><span data-stu-id="d6e05-141">ACK/Action Code = Update Data  \<refer note 1\> (from X12-TA104 or EDIFACT-UCI4)\*</span></span>  
  
- <span data-ttu-id="d6e05-142">确认注释代码 = 更新数据\<，请参阅备注 2\> （来自 X12-TA105，不适用于 EDIFACT) \*</span><span class="sxs-lookup"><span data-stu-id="d6e05-142">ACK Note Code = Update Data \<Refer Note 2\> (from X12-TA105, not applicable for EDIFACT)\*</span></span>  
  
  <span data-ttu-id="d6e05-143">使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-143">The following ACK/Action Codes are used:</span></span>  
  
|<span data-ttu-id="d6e05-144">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-144">Data in ACK/Action Code</span></span>|<span data-ttu-id="d6e05-145">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-145">Error description for Reporting</span></span>|<span data-ttu-id="d6e05-146">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="d6e05-146">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="d6e05-147">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="d6e05-147">A</span></span>|<span data-ttu-id="d6e05-148">已接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-148">Accepted</span></span>|<span data-ttu-id="d6e05-149">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-149">X12</span></span>|  
|<span data-ttu-id="d6e05-150">E</span><span class="sxs-lookup"><span data-stu-id="d6e05-150">E</span></span>|<span data-ttu-id="d6e05-151">记下已被接受，错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-151">Accepted, errors noted</span></span>|<span data-ttu-id="d6e05-152">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-152">X12</span></span>|  
|<span data-ttu-id="d6e05-153">P</span><span class="sxs-lookup"><span data-stu-id="d6e05-153">P</span></span>|<span data-ttu-id="d6e05-154">部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-154">Partially Accepted</span></span>|<span data-ttu-id="d6e05-155">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-155">X12</span></span>|  
|<span data-ttu-id="d6e05-156">R</span><span class="sxs-lookup"><span data-stu-id="d6e05-156">R</span></span>|<span data-ttu-id="d6e05-157">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-157">Rejected</span></span>|<span data-ttu-id="d6e05-158">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-158">X12</span></span>|  
|<span data-ttu-id="d6e05-159">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-159">4</span></span>|<span data-ttu-id="d6e05-160">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-160">Rejected</span></span>|<span data-ttu-id="d6e05-161">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-161">EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-162">8</span><span class="sxs-lookup"><span data-stu-id="d6e05-162">8</span></span>|<span data-ttu-id="d6e05-163">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-163">Accepted/Partially Accepted</span></span>|<span data-ttu-id="d6e05-164">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-164">EDIFACT</span></span>|  
  
 <span data-ttu-id="d6e05-165">使用以下 ACK 注释代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-165">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="d6e05-166">确认注释代码 （在 X12 中) 中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-166">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="d6e05-167">Description</span><span class="sxs-lookup"><span data-stu-id="d6e05-167">Description</span></span>|  
|--------------------------------------|-----------------|  
|<span data-ttu-id="d6e05-168">000</span><span class="sxs-lookup"><span data-stu-id="d6e05-168">000</span></span>|<span data-ttu-id="d6e05-169">成功</span><span class="sxs-lookup"><span data-stu-id="d6e05-169">Success</span></span>|  
|<span data-ttu-id="d6e05-170">001</span><span class="sxs-lookup"><span data-stu-id="d6e05-170">001</span></span>|<span data-ttu-id="d6e05-171">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-171">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="d6e05-172">002</span><span class="sxs-lookup"><span data-stu-id="d6e05-172">002</span></span>|<span data-ttu-id="d6e05-173">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="d6e05-173">Standard not supported</span></span>|  
|<span data-ttu-id="d6e05-174">003</span><span class="sxs-lookup"><span data-stu-id="d6e05-174">003</span></span>|<span data-ttu-id="d6e05-175">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="d6e05-175">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="d6e05-176">004</span><span class="sxs-lookup"><span data-stu-id="d6e05-176">004</span></span>|<span data-ttu-id="d6e05-177">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-177">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="d6e05-178">005</span><span class="sxs-lookup"><span data-stu-id="d6e05-178">005</span></span>|<span data-ttu-id="d6e05-179">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-179">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="d6e05-180">006</span><span class="sxs-lookup"><span data-stu-id="d6e05-180">006</span></span>|<span data-ttu-id="d6e05-181">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-181">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="d6e05-182">007</span><span class="sxs-lookup"><span data-stu-id="d6e05-182">007</span></span>|<span data-ttu-id="d6e05-183">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-183">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="d6e05-184">008</span><span class="sxs-lookup"><span data-stu-id="d6e05-184">008</span></span>|<span data-ttu-id="d6e05-185">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-185">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="d6e05-186">009</span><span class="sxs-lookup"><span data-stu-id="d6e05-186">009</span></span>|<span data-ttu-id="d6e05-187">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-187">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="d6e05-188">010</span><span class="sxs-lookup"><span data-stu-id="d6e05-188">010</span></span>|<span data-ttu-id="d6e05-189">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="d6e05-189">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="d6e05-190">011</span><span class="sxs-lookup"><span data-stu-id="d6e05-190">011</span></span>|<span data-ttu-id="d6e05-191">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="d6e05-191">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="d6e05-192">012</span><span class="sxs-lookup"><span data-stu-id="d6e05-192">012</span></span>|<span data-ttu-id="d6e05-193">安全信息限定符值无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-193">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="d6e05-194">013</span><span class="sxs-lookup"><span data-stu-id="d6e05-194">013</span></span>|<span data-ttu-id="d6e05-195">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="d6e05-195">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="d6e05-196">014</span><span class="sxs-lookup"><span data-stu-id="d6e05-196">014</span></span>|<span data-ttu-id="d6e05-197">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="d6e05-197">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="d6e05-198">015</span><span class="sxs-lookup"><span data-stu-id="d6e05-198">015</span></span>|<span data-ttu-id="d6e05-199">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="d6e05-199">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="d6e05-200">016</span><span class="sxs-lookup"><span data-stu-id="d6e05-200">016</span></span>|<span data-ttu-id="d6e05-201">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="d6e05-201">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="d6e05-202">017</span><span class="sxs-lookup"><span data-stu-id="d6e05-202">017</span></span>|<span data-ttu-id="d6e05-203">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="d6e05-203">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="d6e05-204">018</span><span class="sxs-lookup"><span data-stu-id="d6e05-204">018</span></span>|<span data-ttu-id="d6e05-205">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="d6e05-205">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="d6e05-206">019</span><span class="sxs-lookup"><span data-stu-id="d6e05-206">019</span></span>|<span data-ttu-id="d6e05-207">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="d6e05-207">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="d6e05-208">020</span><span class="sxs-lookup"><span data-stu-id="d6e05-208">020</span></span>|<span data-ttu-id="d6e05-209">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-209">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="d6e05-210">021</span><span class="sxs-lookup"><span data-stu-id="d6e05-210">021</span></span>|<span data-ttu-id="d6e05-211">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-211">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="d6e05-212">022</span><span class="sxs-lookup"><span data-stu-id="d6e05-212">022</span></span>|<span data-ttu-id="d6e05-213">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-213">Invalid Control Structure</span></span>|  
|<span data-ttu-id="d6e05-214">023</span><span class="sxs-lookup"><span data-stu-id="d6e05-214">023</span></span>|<span data-ttu-id="d6e05-215">文件结尾不正确</span><span class="sxs-lookup"><span data-stu-id="d6e05-215">Improper End-of-File</span></span>|  
|<span data-ttu-id="d6e05-216">024</span><span class="sxs-lookup"><span data-stu-id="d6e05-216">024</span></span>|<span data-ttu-id="d6e05-217">交换内容无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-217">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="d6e05-218">025</span><span class="sxs-lookup"><span data-stu-id="d6e05-218">025</span></span>|<span data-ttu-id="d6e05-219">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="d6e05-219">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="d6e05-220">026</span><span class="sxs-lookup"><span data-stu-id="d6e05-220">026</span></span>|<span data-ttu-id="d6e05-221">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-221">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="d6e05-222">027</span><span class="sxs-lookup"><span data-stu-id="d6e05-222">027</span></span>|<span data-ttu-id="d6e05-223">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-223">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="d6e05-224">028</span><span class="sxs-lookup"><span data-stu-id="d6e05-224">028</span></span>|<span data-ttu-id="d6e05-225">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-225">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="d6e05-226">029</span><span class="sxs-lookup"><span data-stu-id="d6e05-226">029</span></span>|<span data-ttu-id="d6e05-227">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-227">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="d6e05-228">030</span><span class="sxs-lookup"><span data-stu-id="d6e05-228">030</span></span>|<span data-ttu-id="d6e05-229">延迟的送达请求中的无效的送达时间代码</span><span class="sxs-lookup"><span data-stu-id="d6e05-229">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="d6e05-230">031</span><span class="sxs-lookup"><span data-stu-id="d6e05-230">031</span></span>|<span data-ttu-id="d6e05-231">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-231">Invalid Grade of Service</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="d6e05-232">接收管道为收到响应的出站交换中每个技术确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-232">Data Updated by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="d6e05-233">对于接收管道接收每个技术确认，它将更新发送相关交换状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="d6e05-233">For each technical acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="d6e05-234">EDI 拆装器定位在数据存储中使用的 UCI 和 TA1 段传入的确认中的数据，如下所示的记录：</span><span class="sxs-lookup"><span data-stu-id="d6e05-234">The EDI Disassembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="d6e05-235">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="d6e05-235">Fields in ACK</span></span>|<span data-ttu-id="d6e05-236">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="d6e05-236">Fields in Data store</span></span>|<span data-ttu-id="d6e05-237">注释</span><span class="sxs-lookup"><span data-stu-id="d6e05-237">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="d6e05-238">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-238">Interchange Sender ID</span></span>|<span data-ttu-id="d6e05-239">交换收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-239">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="d6e05-240">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-240">Interchange Receiver ID</span></span>|<span data-ttu-id="d6e05-241">交换发送方</span><span class="sxs-lookup"><span data-stu-id="d6e05-241">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="d6e05-242">交换日期</span><span class="sxs-lookup"><span data-stu-id="d6e05-242">Interchange Date</span></span>|-|  
|<span data-ttu-id="d6e05-243">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="d6e05-243">Interchange Control Number</span></span>|<span data-ttu-id="d6e05-244">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-244">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="d6e05-245">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="d6e05-245">Interchange Direction = Send</span></span>|<span data-ttu-id="d6e05-246">唯一性的保留的批方案中必需的</span><span class="sxs-lookup"><span data-stu-id="d6e05-246">Required in preserved batch scenario for uniqueness</span></span>|  
|<span data-ttu-id="d6e05-247">记录类型</span><span class="sxs-lookup"><span data-stu-id="d6e05-247">Record Type</span></span>|<span data-ttu-id="d6e05-248">交换状态和交换确认状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-248">Interchange Status and Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="d6e05-249">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="d6e05-249">The data stored includes:</span></span>  
  
- <span data-ttu-id="d6e05-250">交换确认方向 = 接收 – 的现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-250">Interchange ACK Direction = Receive – Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-251">交换确认状态 = 接收</span><span class="sxs-lookup"><span data-stu-id="d6e05-251">Interchange ACK Status = Received</span></span>  
  
- <span data-ttu-id="d6e05-252">交换接收方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-252">Interchange Receiver = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-253">交换发送方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-253">Interchange Sender = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-254">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-254">Interchange Date = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-255">交换控制 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-255">Interchange Control ID = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-256">交换确认控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-256">Interchange ACK Control ID= Update Data</span></span>  
  
- <span data-ttu-id="d6e05-257">交换确认日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-257">Interchange ACK Date = Update Data</span></span>  
  
- <span data-ttu-id="d6e05-258">交换确认时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-258">Interchange ACK Time = Update Data</span></span>  
  
- <span data-ttu-id="d6e05-259">确认/操作代码 = 更新数据 （来自 X12-TA104 或 EDIFACT-UCI4） \*\<引用注释 1\></span><span class="sxs-lookup"><span data-stu-id="d6e05-259">ACK/Action Code = Update Data (from X12-TA104 or EDIFACT-UCI4)\* \<Refer Note 1\></span></span>  
  
- <span data-ttu-id="d6e05-260">确认注释代码 2 = 更新数据 (来自 X12-TA105，未对 EDIFACT) \* \<，请参阅备注 2\></span><span class="sxs-lookup"><span data-stu-id="d6e05-260">ACK Note Code 2 = Update Data (from X12-TA105 and not valued for EDIFACT)\* \<Refer Note 2\></span></span>  
  
  <span data-ttu-id="d6e05-261">ACK X12 中的数据： TA1 104 或 EDIFACT UCI4 是按如下所示映射：</span><span class="sxs-lookup"><span data-stu-id="d6e05-261">The data from the ACK X12:TA1-104 or EDIFACT UCI4 is to be mapped as follows:</span></span>  
  
|<span data-ttu-id="d6e05-262">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-262">Data in ACK/Action Code</span></span>|<span data-ttu-id="d6e05-263">映射的状态报告</span><span class="sxs-lookup"><span data-stu-id="d6e05-263">Mapped for Status Reporting</span></span>|<span data-ttu-id="d6e05-264">注释</span><span class="sxs-lookup"><span data-stu-id="d6e05-264">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="d6e05-265">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="d6e05-265">A</span></span>|<span data-ttu-id="d6e05-266">已接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-266">Accepted</span></span>|<span data-ttu-id="d6e05-267">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-267">X12</span></span>|  
|<span data-ttu-id="d6e05-268">P</span><span class="sxs-lookup"><span data-stu-id="d6e05-268">P</span></span>|<span data-ttu-id="d6e05-269">部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-269">Partially Accepted</span></span>|<span data-ttu-id="d6e05-270">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-270">X12</span></span>|  
|<span data-ttu-id="d6e05-271">R、 M、 W、 X</span><span class="sxs-lookup"><span data-stu-id="d6e05-271">R, M, W, X</span></span>|<span data-ttu-id="d6e05-272">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-272">Rejected</span></span>|<span data-ttu-id="d6e05-273">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-273">X12</span></span>|  
|<span data-ttu-id="d6e05-274">E</span><span class="sxs-lookup"><span data-stu-id="d6e05-274">E</span></span>|<span data-ttu-id="d6e05-275">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-275">Accepted with errors</span></span>|<span data-ttu-id="d6e05-276">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-276">X12</span></span>|  
|<span data-ttu-id="d6e05-277">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-277">4</span></span>|<span data-ttu-id="d6e05-278">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-278">Rejected</span></span>|<span data-ttu-id="d6e05-279">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-279">EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-280">7, 8</span><span class="sxs-lookup"><span data-stu-id="d6e05-280">7, 8</span></span>|<span data-ttu-id="d6e05-281">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-281">Accepted/Partially Accepted</span></span>|<span data-ttu-id="d6e05-282">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-282">EDIFACT</span></span>|  
  
 <span data-ttu-id="d6e05-283">使用以下 ACK 注释代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-283">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="d6e05-284">确认注释代码 （在 X12 中) 中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-284">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="d6e05-285">映射的状态报告</span><span class="sxs-lookup"><span data-stu-id="d6e05-285">Mapped for Status Reporting</span></span>|  
|--------------------------------------|---------------------------------|  
|<span data-ttu-id="d6e05-286">000</span><span class="sxs-lookup"><span data-stu-id="d6e05-286">000</span></span>|<span data-ttu-id="d6e05-287">成功</span><span class="sxs-lookup"><span data-stu-id="d6e05-287">Success</span></span>|  
|<span data-ttu-id="d6e05-288">001</span><span class="sxs-lookup"><span data-stu-id="d6e05-288">001</span></span>|<span data-ttu-id="d6e05-289">交换控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-289">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="d6e05-290">002</span><span class="sxs-lookup"><span data-stu-id="d6e05-290">002</span></span>|<span data-ttu-id="d6e05-291">不支持的标准</span><span class="sxs-lookup"><span data-stu-id="d6e05-291">Standard not supported</span></span>|  
|<span data-ttu-id="d6e05-292">003</span><span class="sxs-lookup"><span data-stu-id="d6e05-292">003</span></span>|<span data-ttu-id="d6e05-293">版本不支持的控件</span><span class="sxs-lookup"><span data-stu-id="d6e05-293">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="d6e05-294">004</span><span class="sxs-lookup"><span data-stu-id="d6e05-294">004</span></span>|<span data-ttu-id="d6e05-295">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-295">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="d6e05-296">005</span><span class="sxs-lookup"><span data-stu-id="d6e05-296">005</span></span>|<span data-ttu-id="d6e05-297">发送方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-297">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="d6e05-298">006</span><span class="sxs-lookup"><span data-stu-id="d6e05-298">006</span></span>|<span data-ttu-id="d6e05-299">交换发送方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-299">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="d6e05-300">007</span><span class="sxs-lookup"><span data-stu-id="d6e05-300">007</span></span>|<span data-ttu-id="d6e05-301">接收方的交换 ID 限定符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-301">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="d6e05-302">008</span><span class="sxs-lookup"><span data-stu-id="d6e05-302">008</span></span>|<span data-ttu-id="d6e05-303">交换接收方 ID 无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-303">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="d6e05-304">009</span><span class="sxs-lookup"><span data-stu-id="d6e05-304">009</span></span>|<span data-ttu-id="d6e05-305">未知交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-305">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="d6e05-306">010</span><span class="sxs-lookup"><span data-stu-id="d6e05-306">010</span></span>|<span data-ttu-id="d6e05-307">无效的授权信息限定符值</span><span class="sxs-lookup"><span data-stu-id="d6e05-307">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="d6e05-308">011</span><span class="sxs-lookup"><span data-stu-id="d6e05-308">011</span></span>|<span data-ttu-id="d6e05-309">无效的授权信息值</span><span class="sxs-lookup"><span data-stu-id="d6e05-309">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="d6e05-310">012</span><span class="sxs-lookup"><span data-stu-id="d6e05-310">012</span></span>|<span data-ttu-id="d6e05-311">安全信息限定符值无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-311">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="d6e05-312">013</span><span class="sxs-lookup"><span data-stu-id="d6e05-312">013</span></span>|<span data-ttu-id="d6e05-313">无效的安全信息值</span><span class="sxs-lookup"><span data-stu-id="d6e05-313">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="d6e05-314">014</span><span class="sxs-lookup"><span data-stu-id="d6e05-314">014</span></span>|<span data-ttu-id="d6e05-315">无效的交换日期值</span><span class="sxs-lookup"><span data-stu-id="d6e05-315">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="d6e05-316">015</span><span class="sxs-lookup"><span data-stu-id="d6e05-316">015</span></span>|<span data-ttu-id="d6e05-317">无效的交换时间值</span><span class="sxs-lookup"><span data-stu-id="d6e05-317">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="d6e05-318">016</span><span class="sxs-lookup"><span data-stu-id="d6e05-318">016</span></span>|<span data-ttu-id="d6e05-319">无效的交换标准标识符值</span><span class="sxs-lookup"><span data-stu-id="d6e05-319">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="d6e05-320">017</span><span class="sxs-lookup"><span data-stu-id="d6e05-320">017</span></span>|<span data-ttu-id="d6e05-321">无效的交换版本 ID 值</span><span class="sxs-lookup"><span data-stu-id="d6e05-321">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="d6e05-322">018</span><span class="sxs-lookup"><span data-stu-id="d6e05-322">018</span></span>|<span data-ttu-id="d6e05-323">无效的交换控制编号值</span><span class="sxs-lookup"><span data-stu-id="d6e05-323">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="d6e05-324">019</span><span class="sxs-lookup"><span data-stu-id="d6e05-324">019</span></span>|<span data-ttu-id="d6e05-325">无效的确认请求值</span><span class="sxs-lookup"><span data-stu-id="d6e05-325">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="d6e05-326">020</span><span class="sxs-lookup"><span data-stu-id="d6e05-326">020</span></span>|<span data-ttu-id="d6e05-327">测试指示器值无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-327">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="d6e05-328">021</span><span class="sxs-lookup"><span data-stu-id="d6e05-328">021</span></span>|<span data-ttu-id="d6e05-329">包含的组值的数目无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-329">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="d6e05-330">022</span><span class="sxs-lookup"><span data-stu-id="d6e05-330">022</span></span>|<span data-ttu-id="d6e05-331">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-331">Invalid Control Structure</span></span>|  
|<span data-ttu-id="d6e05-332">023</span><span class="sxs-lookup"><span data-stu-id="d6e05-332">023</span></span>|<span data-ttu-id="d6e05-333">文件结尾不正确</span><span class="sxs-lookup"><span data-stu-id="d6e05-333">Improper End-of-File</span></span>|  
|<span data-ttu-id="d6e05-334">024</span><span class="sxs-lookup"><span data-stu-id="d6e05-334">024</span></span>|<span data-ttu-id="d6e05-335">交换内容无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-335">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="d6e05-336">025</span><span class="sxs-lookup"><span data-stu-id="d6e05-336">025</span></span>|<span data-ttu-id="d6e05-337">交换控制编号重复</span><span class="sxs-lookup"><span data-stu-id="d6e05-337">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="d6e05-338">026</span><span class="sxs-lookup"><span data-stu-id="d6e05-338">026</span></span>|<span data-ttu-id="d6e05-339">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-339">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="d6e05-340">027</span><span class="sxs-lookup"><span data-stu-id="d6e05-340">027</span></span>|<span data-ttu-id="d6e05-341">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-341">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="d6e05-342">028</span><span class="sxs-lookup"><span data-stu-id="d6e05-342">028</span></span>|<span data-ttu-id="d6e05-343">延迟送达请求中的送达日期无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-343">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="d6e05-344">029</span><span class="sxs-lookup"><span data-stu-id="d6e05-344">029</span></span>|<span data-ttu-id="d6e05-345">延迟送达请求中的送达时间无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-345">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="d6e05-346">030</span><span class="sxs-lookup"><span data-stu-id="d6e05-346">030</span></span>|<span data-ttu-id="d6e05-347">延迟的送达请求中的无效的送达时间代码</span><span class="sxs-lookup"><span data-stu-id="d6e05-347">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="d6e05-348">031</span><span class="sxs-lookup"><span data-stu-id="d6e05-348">031</span></span>|<span data-ttu-id="d6e05-349">服务的级别无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-349">Invalid Grade of Service</span></span>|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a><span data-ttu-id="d6e05-350">接收管道为每个功能确认以响应出站交换接收到存储的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-350">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outbound Interchanges</span></span>  
 <span data-ttu-id="d6e05-351">接收管道接收每个功能确认状态报告数据存储区创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="d6e05-351">The receive pipeline creates a record in the status report data store for each functional acknowledgment that it receives.</span></span>  <span data-ttu-id="d6e05-352">技术确认是 997 的 X12 和完整 CONTRL 消息的 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="d6e05-352">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="d6e05-353">每个组的一个条目将创建。</span><span class="sxs-lookup"><span data-stu-id="d6e05-353">One entry per group will to be created.</span></span> <span data-ttu-id="d6e05-354">此项时使用的交换和组标头中的数据。</span><span class="sxs-lookup"><span data-stu-id="d6e05-354">Data from the interchange and group headers is used while making this entry.</span></span> <span data-ttu-id="d6e05-355">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="d6e05-355">The data stored includes:</span></span>  
  
- <span data-ttu-id="d6e05-356">记录类型 = 功能确认状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-356">Record Type = Functional ACK Status</span></span>  
  
- <span data-ttu-id="d6e05-357">功能确认方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="d6e05-357">Functional ACK Direction = Send</span></span>  
  
- <span data-ttu-id="d6e05-358">功能确认状态 =\<生成或不适用，请参阅备注 1\></span><span class="sxs-lookup"><span data-stu-id="d6e05-358">Functional ACK Status = \<Generated or Not Applicable, refer note 1\></span></span>  
  
- <span data-ttu-id="d6e05-359">交换接收方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-359">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-360">交换发送方 = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-360">Interchange Sender = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-361">交换日期 = 更新数据 (所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="d6e05-361">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
- <span data-ttu-id="d6e05-362">交换控制 ID = 更新数据 （需要相关）</span><span class="sxs-lookup"><span data-stu-id="d6e05-362">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="d6e05-363">组控制编号 = 更新数据 (optional 对于 EDIFACT 和所需的 X12 相关)</span><span class="sxs-lookup"><span data-stu-id="d6e05-363">Group Control Number = Update Data (‘optional for EDIFACT’ and required for X12 correlation)</span></span>  
  
- <span data-ttu-id="d6e05-364">功能 ID 代码 = 更新数据 (GS01/UNG01)</span><span class="sxs-lookup"><span data-stu-id="d6e05-364">Functional ID Code = Update Data (GS01/UNG01)</span></span>  
  
- <span data-ttu-id="d6e05-365">事务集计数 = 更新数据 (UNE1/UNZ1)</span><span class="sxs-lookup"><span data-stu-id="d6e05-365">Count of Transaction Sets = Update Data (UNE1/UNZ1)</span></span>  
  
- <span data-ttu-id="d6e05-366">功能 ACK 交换控制 ID = 不是值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-366">Functional ACK Interchange Control ID= Not value – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-367">功能确认交换日期 = 不赋值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-367">Functional ACK Interchange Date = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-368">功能确认交换时间 = 不赋值 – 将由发送方应用</span><span class="sxs-lookup"><span data-stu-id="d6e05-368">Functional ACK Interchange Time = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="d6e05-369">计数的事务集收到 = 更新数据 (X12 AK903，并计算出用于 EDIFACT 编码的引擎)</span><span class="sxs-lookup"><span data-stu-id="d6e05-369">Count of Transaction Sets Received = Update Data (X12-AK903 and computed by Engine for EDIFACT encoding)</span></span>  
  
- <span data-ttu-id="d6e05-370">接受的事务计数集 = 更新数据 (X12 AK904 和计算引擎为 EDIFACT 引擎)</span><span class="sxs-lookup"><span data-stu-id="d6e05-370">Count of Transaction Sets Accepted = Update Data (X12-AK904 and computed by Engine for EDIFACT engine)</span></span>  
  
- <span data-ttu-id="d6e05-371">确认/操作代码 = 更新数据\<，请参阅备注 2\> （来自 X12-AK901 或 EDIFACT-UCI4） \*</span><span class="sxs-lookup"><span data-stu-id="d6e05-371">ACK/Action Code = Update Data  \<refer note 2\> (from X12-AK901 or EDIFACT-UCI4)\*</span></span>  
  
- <span data-ttu-id="d6e05-372">错误/语法错误代码 = 更新数据 (X12 AK905，EDIFACT UCI5) 请注意 3</span><span class="sxs-lookup"><span data-stu-id="d6e05-372">Error/Syntax Error Code  = Update Data (X12-AK905, EDIFACT UCI5) Note 3</span></span>  
  
- <span data-ttu-id="d6e05-373">附加 X12 确认错误代码 2 = 更新数据 (X12-AK906)</span><span class="sxs-lookup"><span data-stu-id="d6e05-373">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
- <span data-ttu-id="d6e05-374">附加 X12 确认错误代码 3 = 更新数据 (X12-AK907)</span><span class="sxs-lookup"><span data-stu-id="d6e05-374">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
- <span data-ttu-id="d6e05-375">附加 X12 确认错误代码 4 = 更新数据 (X12-AK908)</span><span class="sxs-lookup"><span data-stu-id="d6e05-375">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
- <span data-ttu-id="d6e05-376">附加 X12 确认错误代码 5 = 更新数据 (X12-AK909)</span><span class="sxs-lookup"><span data-stu-id="d6e05-376">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
  <span data-ttu-id="d6e05-377">将使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-377">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="d6e05-378">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-378">Data in ACK/Action Code</span></span>|<span data-ttu-id="d6e05-379">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-379">Error description for Reporting</span></span>|<span data-ttu-id="d6e05-380">注释 （适用性）</span><span class="sxs-lookup"><span data-stu-id="d6e05-380">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="d6e05-381">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="d6e05-381">A</span></span>|<span data-ttu-id="d6e05-382">已接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-382">Accepted</span></span>|<span data-ttu-id="d6e05-383">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-383">X12</span></span>|  
|<span data-ttu-id="d6e05-384">E</span><span class="sxs-lookup"><span data-stu-id="d6e05-384">E</span></span>|<span data-ttu-id="d6e05-385">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-385">Accepted  with errors</span></span>|<span data-ttu-id="d6e05-386">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-386">X12</span></span>|  
|<span data-ttu-id="d6e05-387">P</span><span class="sxs-lookup"><span data-stu-id="d6e05-387">P</span></span>|<span data-ttu-id="d6e05-388">部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-388">Partially Accepted</span></span>|<span data-ttu-id="d6e05-389">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-389">X12</span></span>|  
|<span data-ttu-id="d6e05-390">R</span><span class="sxs-lookup"><span data-stu-id="d6e05-390">R</span></span>|<span data-ttu-id="d6e05-391">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-391">Rejected</span></span>|<span data-ttu-id="d6e05-392">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-392">X12</span></span>|  
|<span data-ttu-id="d6e05-393">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-393">4</span></span>|<span data-ttu-id="d6e05-394">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-394">Rejected</span></span>|<span data-ttu-id="d6e05-395">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-395">EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-396">7</span><span class="sxs-lookup"><span data-stu-id="d6e05-396">7</span></span>|<span data-ttu-id="d6e05-397">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-397">Accepted/Partially Accepted</span></span>|<span data-ttu-id="d6e05-398">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-398">EDIFACT</span></span>|  
  
 <span data-ttu-id="d6e05-399">对于 EDIFACT，将使用以下的错误/语法错误代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-399">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="d6e05-400">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="d6e05-400">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="d6e05-401">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="d6e05-401">(applicable to EDIFACT)</span></span>|<span data-ttu-id="d6e05-402">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-402">Error Description for reporting</span></span>|  
|--------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="d6e05-403">2</span><span class="sxs-lookup"><span data-stu-id="d6e05-403">2</span></span>|<span data-ttu-id="d6e05-404">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="d6e05-404">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="d6e05-405">7</span><span class="sxs-lookup"><span data-stu-id="d6e05-405">7</span></span>|<span data-ttu-id="d6e05-406">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-406">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="d6e05-407">12</span><span class="sxs-lookup"><span data-stu-id="d6e05-407">12</span></span>|<span data-ttu-id="d6e05-408">无效的值</span><span class="sxs-lookup"><span data-stu-id="d6e05-408">Invalid value</span></span>|  
|<span data-ttu-id="d6e05-409">13</span><span class="sxs-lookup"><span data-stu-id="d6e05-409">13</span></span>|<span data-ttu-id="d6e05-410">Missing</span><span class="sxs-lookup"><span data-stu-id="d6e05-410">Missing</span></span>|  
|<span data-ttu-id="d6e05-411">14</span><span class="sxs-lookup"><span data-stu-id="d6e05-411">14</span></span>|<span data-ttu-id="d6e05-412">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="d6e05-412">Value not supported in this position</span></span>|  
|<span data-ttu-id="d6e05-413">15</span><span class="sxs-lookup"><span data-stu-id="d6e05-413">15</span></span>|<span data-ttu-id="d6e05-414">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="d6e05-414">Not supported in this position</span></span>|  
|<span data-ttu-id="d6e05-415">16</span><span class="sxs-lookup"><span data-stu-id="d6e05-415">16</span></span>|<span data-ttu-id="d6e05-416">组分过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-416">Too many constituents</span></span>|  
|<span data-ttu-id="d6e05-417">17</span><span class="sxs-lookup"><span data-stu-id="d6e05-417">17</span></span>|<span data-ttu-id="d6e05-418">无协议</span><span class="sxs-lookup"><span data-stu-id="d6e05-418">No agreement</span></span>|  
|<span data-ttu-id="d6e05-419">18</span><span class="sxs-lookup"><span data-stu-id="d6e05-419">18</span></span>|<span data-ttu-id="d6e05-420">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-420">Unspecified error</span></span>|  
|<span data-ttu-id="d6e05-421">19</span><span class="sxs-lookup"><span data-stu-id="d6e05-421">19</span></span>|<span data-ttu-id="d6e05-422">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-422">Invalid decimal notation</span></span>|  
|<span data-ttu-id="d6e05-423">20</span><span class="sxs-lookup"><span data-stu-id="d6e05-423">20</span></span>|<span data-ttu-id="d6e05-424">字符作为服务字符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-424">Character invalid as service character</span></span>|  
|<span data-ttu-id="d6e05-425">21</span><span class="sxs-lookup"><span data-stu-id="d6e05-425">21</span></span>|<span data-ttu-id="d6e05-426">无效字符</span><span class="sxs-lookup"><span data-stu-id="d6e05-426">Invalid character(s)</span></span>|  
|<span data-ttu-id="d6e05-427">22</span><span class="sxs-lookup"><span data-stu-id="d6e05-427">22</span></span>|<span data-ttu-id="d6e05-428">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="d6e05-428">Invalid service character(s)</span></span>|  
|<span data-ttu-id="d6e05-429">23</span><span class="sxs-lookup"><span data-stu-id="d6e05-429">23</span></span>|<span data-ttu-id="d6e05-430">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-430">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="d6e05-431">24</span><span class="sxs-lookup"><span data-stu-id="d6e05-431">24</span></span>|<span data-ttu-id="d6e05-432">太旧</span><span class="sxs-lookup"><span data-stu-id="d6e05-432">Too old</span></span>|  
|<span data-ttu-id="d6e05-433">25</span><span class="sxs-lookup"><span data-stu-id="d6e05-433">25</span></span>|<span data-ttu-id="d6e05-434">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="d6e05-434">Test indicator not supported</span></span>|  
|<span data-ttu-id="d6e05-435">26</span><span class="sxs-lookup"><span data-stu-id="d6e05-435">26</span></span>|<span data-ttu-id="d6e05-436">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="d6e05-436">Duplicate detected</span></span>|  
|<span data-ttu-id="d6e05-437">27</span><span class="sxs-lookup"><span data-stu-id="d6e05-437">27</span></span>|<span data-ttu-id="d6e05-438">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="d6e05-438">Security function not supported</span></span>|  
|<span data-ttu-id="d6e05-439">28</span><span class="sxs-lookup"><span data-stu-id="d6e05-439">28</span></span>|<span data-ttu-id="d6e05-440">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-440">References do not match</span></span>|  
|<span data-ttu-id="d6e05-441">29</span><span class="sxs-lookup"><span data-stu-id="d6e05-441">29</span></span>|<span data-ttu-id="d6e05-442">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-442">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="d6e05-443">30</span><span class="sxs-lookup"><span data-stu-id="d6e05-443">30</span></span>|<span data-ttu-id="d6e05-444">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="d6e05-444">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="d6e05-445">31</span><span class="sxs-lookup"><span data-stu-id="d6e05-445">31</span></span>|<span data-ttu-id="d6e05-446">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="d6e05-446">More than one message type in group</span></span>|  
|<span data-ttu-id="d6e05-447">32</span><span class="sxs-lookup"><span data-stu-id="d6e05-447">32</span></span>|<span data-ttu-id="d6e05-448">低级别为空</span><span class="sxs-lookup"><span data-stu-id="d6e05-448">Lower level empty</span></span>|  
|<span data-ttu-id="d6e05-449">33</span><span class="sxs-lookup"><span data-stu-id="d6e05-449">33</span></span>|<span data-ttu-id="d6e05-450">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="d6e05-450">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="d6e05-451">34</span><span class="sxs-lookup"><span data-stu-id="d6e05-451">34</span></span>|<span data-ttu-id="d6e05-452">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="d6e05-452">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="d6e05-453">35</span><span class="sxs-lookup"><span data-stu-id="d6e05-453">35</span></span>|<span data-ttu-id="d6e05-454">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-454">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="d6e05-455">36</span><span class="sxs-lookup"><span data-stu-id="d6e05-455">36</span></span>|<span data-ttu-id="d6e05-456">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-456">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="d6e05-457">37</span><span class="sxs-lookup"><span data-stu-id="d6e05-457">37</span></span>|<span data-ttu-id="d6e05-458">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-458">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="d6e05-459">38</span><span class="sxs-lookup"><span data-stu-id="d6e05-459">38</span></span>|<span data-ttu-id="d6e05-460">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="d6e05-460">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="d6e05-461">39</span><span class="sxs-lookup"><span data-stu-id="d6e05-461">39</span></span>|<span data-ttu-id="d6e05-462">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="d6e05-462">Data element too long</span></span>|  
|<span data-ttu-id="d6e05-463">40</span><span class="sxs-lookup"><span data-stu-id="d6e05-463">40</span></span>|<span data-ttu-id="d6e05-464">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="d6e05-464">Data element too short</span></span>|  
|<span data-ttu-id="d6e05-465">41</span><span class="sxs-lookup"><span data-stu-id="d6e05-465">41</span></span>|<span data-ttu-id="d6e05-466">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-466">Permanent communication network error</span></span>|  
|<span data-ttu-id="d6e05-467">42</span><span class="sxs-lookup"><span data-stu-id="d6e05-467">42</span></span>|<span data-ttu-id="d6e05-468">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-468">Temporary communication network error</span></span>|  
|<span data-ttu-id="d6e05-469">43</span><span class="sxs-lookup"><span data-stu-id="d6e05-469">43</span></span>|<span data-ttu-id="d6e05-470">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-470">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="d6e05-471">45</span><span class="sxs-lookup"><span data-stu-id="d6e05-471">45</span></span>|<span data-ttu-id="d6e05-472">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="d6e05-472">Trailing separator</span></span>|  
|<span data-ttu-id="d6e05-473">46</span><span class="sxs-lookup"><span data-stu-id="d6e05-473">46</span></span>|<span data-ttu-id="d6e05-474">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="d6e05-474">Character set not supported</span></span>|  
|<span data-ttu-id="d6e05-475">47</span><span class="sxs-lookup"><span data-stu-id="d6e05-475">47</span></span>|<span data-ttu-id="d6e05-476">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="d6e05-476">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="d6e05-477">48</span><span class="sxs-lookup"><span data-stu-id="d6e05-477">48</span></span>|<span data-ttu-id="d6e05-478">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="d6e05-478">Dependency condition violated</span></span>|  
|<span data-ttu-id="d6e05-479">70</span><span class="sxs-lookup"><span data-stu-id="d6e05-479">70</span></span>|<span data-ttu-id="d6e05-480">事务集缺失或无效事务集标识符</span><span class="sxs-lookup"><span data-stu-id="d6e05-480">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="d6e05-481">71</span><span class="sxs-lookup"><span data-stu-id="d6e05-481">71</span></span>|<span data-ttu-id="d6e05-482">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-482">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="d6e05-483">72</span><span class="sxs-lookup"><span data-stu-id="d6e05-483">72</span></span>|<span data-ttu-id="d6e05-484">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-484">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="d6e05-485">73</span><span class="sxs-lookup"><span data-stu-id="d6e05-485">73</span></span>|<span data-ttu-id="d6e05-486">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="d6e05-486">XML not at correct position</span></span>|  
|<span data-ttu-id="d6e05-487">74</span><span class="sxs-lookup"><span data-stu-id="d6e05-487">74</span></span>|<span data-ttu-id="d6e05-488">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-488">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="d6e05-489">75</span><span class="sxs-lookup"><span data-stu-id="d6e05-489">75</span></span>|<span data-ttu-id="d6e05-490">段重复过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-490">Too few segment repetitions</span></span>|  
|<span data-ttu-id="d6e05-491">76</span><span class="sxs-lookup"><span data-stu-id="d6e05-491">76</span></span>|<span data-ttu-id="d6e05-492">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-492">Too few data elements found</span></span>|  
  
 <span data-ttu-id="d6e05-493">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="d6e05-493">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="d6e05-494">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="d6e05-494">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="d6e05-495">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="d6e05-495">(applicable to X12)</span></span>|<span data-ttu-id="d6e05-496">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-496">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="d6e05-497">@shouldalert</span><span class="sxs-lookup"><span data-stu-id="d6e05-497">1</span></span>|<span data-ttu-id="d6e05-498">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="d6e05-498">Functional group not supported</span></span>|  
|<span data-ttu-id="d6e05-499">2</span><span class="sxs-lookup"><span data-stu-id="d6e05-499">2</span></span>|<span data-ttu-id="d6e05-500">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="d6e05-500">Functional group version not supported</span></span>|  
|<span data-ttu-id="d6e05-501">3</span><span class="sxs-lookup"><span data-stu-id="d6e05-501">3</span></span>|<span data-ttu-id="d6e05-502">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="d6e05-502">Functional group trailer missing</span></span>|  
|<span data-ttu-id="d6e05-503">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-503">4</span></span>|<span data-ttu-id="d6e05-504">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="d6e05-504">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="d6e05-505">5</span><span class="sxs-lookup"><span data-stu-id="d6e05-505">5</span></span>|<span data-ttu-id="d6e05-506">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-506">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="d6e05-507">6-26</span><span class="sxs-lookup"><span data-stu-id="d6e05-507">6-26</span></span>|<span data-ttu-id="d6e05-508">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-508">Other unsupported validation errors</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a><span data-ttu-id="d6e05-509">接收管道为每个为了响应传出交换而接收的功能确认更新的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-509">Data Updated by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outgoing Interchanges</span></span>  
 <span data-ttu-id="d6e05-510">对于接收管道接收的每个功能确认，发送管道会更新所发送相关交换的状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="d6e05-510">For each functional acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="d6e05-511">EDI 拆装器使用传入确认的交换和组标头段中的数据来定位数据存储区中的记录：</span><span class="sxs-lookup"><span data-stu-id="d6e05-511">The EDI Disassembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="d6e05-512">ACK 中的字段</span><span class="sxs-lookup"><span data-stu-id="d6e05-512">Fields in ACK</span></span>|<span data-ttu-id="d6e05-513">数据存储区中的字段</span><span class="sxs-lookup"><span data-stu-id="d6e05-513">Fields in Data store</span></span>|<span data-ttu-id="d6e05-514">注释</span><span class="sxs-lookup"><span data-stu-id="d6e05-514">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="d6e05-515">交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-515">Interchange Sender ID</span></span>|<span data-ttu-id="d6e05-516">交换收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-516">Interchange Receiver</span></span>|<span data-ttu-id="d6e05-517">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-517">Applicable to both X12 and EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-518">交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-518">Interchange Receiver ID</span></span>|<span data-ttu-id="d6e05-519">交换发送方</span><span class="sxs-lookup"><span data-stu-id="d6e05-519">Interchange Sender</span></span>|<span data-ttu-id="d6e05-520">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-520">Applicable to both X12 and EDIFACT</span></span>|  
|-|<span data-ttu-id="d6e05-521">交换日期</span><span class="sxs-lookup"><span data-stu-id="d6e05-521">Interchange Date</span></span>|-|  
|<span data-ttu-id="d6e05-522">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="d6e05-522">Interchange Control Number</span></span>|<span data-ttu-id="d6e05-523">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-523">Interchange Control ID</span></span>|<span data-ttu-id="d6e05-524">仅适用于 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-524">Applicable only to EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-525">组控制编号</span><span class="sxs-lookup"><span data-stu-id="d6e05-525">Group Control Number</span></span>|<span data-ttu-id="d6e05-526">组控制编号</span><span class="sxs-lookup"><span data-stu-id="d6e05-526">Group Control Number</span></span>|<span data-ttu-id="d6e05-527">仅适用于 X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-527">Applicable only to X12</span></span>|  
|-|<span data-ttu-id="d6e05-528">交换方向 = 发送</span><span class="sxs-lookup"><span data-stu-id="d6e05-528">Interchange Direction = Send</span></span>|<span data-ttu-id="d6e05-529">由于要在 BIBO 方案中实现唯一性，因此是必需</span><span class="sxs-lookup"><span data-stu-id="d6e05-529">Required since in BIBO Scenario for uniqueness</span></span>|  
|<span data-ttu-id="d6e05-530">记录类型</span><span class="sxs-lookup"><span data-stu-id="d6e05-530">Record Type</span></span>|<span data-ttu-id="d6e05-531">功能确认状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-531">Functional ACK Status</span></span>|<span data-ttu-id="d6e05-532">适用于 X12 和 EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-532">Applicable to both X12 and EDIFACT</span></span>|  
  
 <span data-ttu-id="d6e05-533">存储的数据包括：</span><span class="sxs-lookup"><span data-stu-id="d6e05-533">The data stored includes:</span></span>  
  
- <span data-ttu-id="d6e05-534">记录类型 = 功能确认状态</span><span class="sxs-lookup"><span data-stu-id="d6e05-534">Record Type = Functional ACK Status</span></span>  
  
- <span data-ttu-id="d6e05-535">功能确认方向 = 接收</span><span class="sxs-lookup"><span data-stu-id="d6e05-535">Functional ACK Direction = Receive</span></span>  
  
- <span data-ttu-id="d6e05-536">功能确认状态 = 按照接收来更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-536">Functional ACK Status =Update Data as Received</span></span>  
  
- <span data-ttu-id="d6e05-537">交换接收方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-537">Interchange Receiver = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-538">交换发送方 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-538">Interchange Sender = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-539">交换日期 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-539">Interchange Date = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-540">交换控制 ID = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-540">Interchange Control ID = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-541">组控制编号 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-541">Group Control Number = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-542">功能 ID 代码 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-542">Functional ID Code = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-543">事务集计数 = 现有数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-543">Count of Transaction Sets = Existing Data</span></span>  
  
- <span data-ttu-id="d6e05-544">功能确认交换控制 ID = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-544">Functional ACK Interchange Control ID= Update Data</span></span>  
  
- <span data-ttu-id="d6e05-545">功能确认交换日期 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-545">Functional ACK Interchange Date = Update Data</span></span>  
  
- <span data-ttu-id="d6e05-546">功能确认交换时间 = 更新数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-546">Functional ACK Interchange Time = Update Data</span></span>  
  
- <span data-ttu-id="d6e05-547">传送的事务集的计数 = 更新数据（X12 AK903，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="d6e05-547">Count of Transaction Sets Delivered = Update Data (X12 AK903 and not applicable for EDIFACT)</span></span>  
  
- <span data-ttu-id="d6e05-548">接受的事务集的计数 = 更新数据（X12 AK904，不适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="d6e05-548">Count of Transaction Sets Accepted = Update Data (X12 AK904 and not applicable for EDIFACT)</span></span>  
  
- <span data-ttu-id="d6e05-549">确认/操作代码 = 更新数据（X12 AK901 和 UCI4）引用注释 1</span><span class="sxs-lookup"><span data-stu-id="d6e05-549">ACK/Action Code = Update Data (X12 AK901 and UCI4) Refer Note 1</span></span>  
  
- <span data-ttu-id="d6e05-550">错误/语法错误代码 =（X12 AK905 和 UCI5）引用注释 2</span><span class="sxs-lookup"><span data-stu-id="d6e05-550">Error/Syntax Error Code  = (X12 AK905 and UCI5) Refer Note 2</span></span>  
  
- <span data-ttu-id="d6e05-551">附加 X12 确认错误代码 2 = 更新数据 (X12-AK906)</span><span class="sxs-lookup"><span data-stu-id="d6e05-551">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
- <span data-ttu-id="d6e05-552">附加 X12 确认错误代码 3 = 更新数据 (X12-AK907)</span><span class="sxs-lookup"><span data-stu-id="d6e05-552">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
- <span data-ttu-id="d6e05-553">附加 X12 确认错误代码 4 = 更新数据 (X12-AK908)</span><span class="sxs-lookup"><span data-stu-id="d6e05-553">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
- <span data-ttu-id="d6e05-554">附加 X12 确认错误代码 5 = 更新数据 (X12-AK909)</span><span class="sxs-lookup"><span data-stu-id="d6e05-554">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
  <span data-ttu-id="d6e05-555">将使用以下确认/操作代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-555">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="d6e05-556">确认/操作代码中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-556">Data in ACK/Action Code</span></span>|<span data-ttu-id="d6e05-557">映射的状态报告</span><span class="sxs-lookup"><span data-stu-id="d6e05-557">Mapped for Status Reporting</span></span>|<span data-ttu-id="d6e05-558">注释</span><span class="sxs-lookup"><span data-stu-id="d6e05-558">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="d6e05-559">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="d6e05-559">A</span></span>|<span data-ttu-id="d6e05-560">已接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-560">Accepted</span></span>|<span data-ttu-id="d6e05-561">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-561">X12</span></span>|  
|<span data-ttu-id="d6e05-562">P</span><span class="sxs-lookup"><span data-stu-id="d6e05-562">P</span></span>|<span data-ttu-id="d6e05-563">部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-563">Partially Accepted</span></span>|<span data-ttu-id="d6e05-564">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-564">X12</span></span>|  
|<span data-ttu-id="d6e05-565">R、 M、 W、 X</span><span class="sxs-lookup"><span data-stu-id="d6e05-565">R, M, W, X</span></span>|<span data-ttu-id="d6e05-566">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-566">Rejected</span></span>|<span data-ttu-id="d6e05-567">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-567">X12</span></span>|  
|<span data-ttu-id="d6e05-568">E</span><span class="sxs-lookup"><span data-stu-id="d6e05-568">E</span></span>|<span data-ttu-id="d6e05-569">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-569">Accepted with errors</span></span>|<span data-ttu-id="d6e05-570">X12</span><span class="sxs-lookup"><span data-stu-id="d6e05-570">X12</span></span>|  
|<span data-ttu-id="d6e05-571">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-571">4</span></span>|<span data-ttu-id="d6e05-572">已拒绝</span><span class="sxs-lookup"><span data-stu-id="d6e05-572">Rejected</span></span>|<span data-ttu-id="d6e05-573">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-573">EDIFACT</span></span>|  
|<span data-ttu-id="d6e05-574">7, 8</span><span class="sxs-lookup"><span data-stu-id="d6e05-574">7, 8</span></span>|<span data-ttu-id="d6e05-575">接受/部分接受</span><span class="sxs-lookup"><span data-stu-id="d6e05-575">Accepted/Partially Accepted</span></span>|<span data-ttu-id="d6e05-576">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d6e05-576">EDIFACT</span></span>|  
  
 <span data-ttu-id="d6e05-577">对于 EDIFACT，将使用以下的错误/语法错误代码：</span><span class="sxs-lookup"><span data-stu-id="d6e05-577">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="d6e05-578">错误/语法错误 Cod 中的数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-578">Data in Error/Syntax Error Cod</span></span><br /><br /> <span data-ttu-id="d6e05-579">（适用于 EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="d6e05-579">(applicable to EDIFACT)</span></span>|<span data-ttu-id="d6e05-580">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-580">Error Description for reporting</span></span>|  
|-------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="d6e05-581">2</span><span class="sxs-lookup"><span data-stu-id="d6e05-581">2</span></span>|<span data-ttu-id="d6e05-582">不支持语法版本或级别</span><span class="sxs-lookup"><span data-stu-id="d6e05-582">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="d6e05-583">7</span><span class="sxs-lookup"><span data-stu-id="d6e05-583">7</span></span>|<span data-ttu-id="d6e05-584">交换收件人不是实际的收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-584">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="d6e05-585">12</span><span class="sxs-lookup"><span data-stu-id="d6e05-585">12</span></span>|<span data-ttu-id="d6e05-586">无效的值</span><span class="sxs-lookup"><span data-stu-id="d6e05-586">Invalid value</span></span>|  
|<span data-ttu-id="d6e05-587">13</span><span class="sxs-lookup"><span data-stu-id="d6e05-587">13</span></span>|<span data-ttu-id="d6e05-588">Missing</span><span class="sxs-lookup"><span data-stu-id="d6e05-588">Missing</span></span>|  
|<span data-ttu-id="d6e05-589">14</span><span class="sxs-lookup"><span data-stu-id="d6e05-589">14</span></span>|<span data-ttu-id="d6e05-590">在此位置不支持该值</span><span class="sxs-lookup"><span data-stu-id="d6e05-590">Value not supported in this position</span></span>|  
|<span data-ttu-id="d6e05-591">15</span><span class="sxs-lookup"><span data-stu-id="d6e05-591">15</span></span>|<span data-ttu-id="d6e05-592">在此位置不支持</span><span class="sxs-lookup"><span data-stu-id="d6e05-592">Not supported in this position</span></span>|  
|<span data-ttu-id="d6e05-593">16</span><span class="sxs-lookup"><span data-stu-id="d6e05-593">16</span></span>|<span data-ttu-id="d6e05-594">组分过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-594">Too many constituents</span></span>|  
|<span data-ttu-id="d6e05-595">17</span><span class="sxs-lookup"><span data-stu-id="d6e05-595">17</span></span>|<span data-ttu-id="d6e05-596">无协议</span><span class="sxs-lookup"><span data-stu-id="d6e05-596">No agreement</span></span>|  
|<span data-ttu-id="d6e05-597">18</span><span class="sxs-lookup"><span data-stu-id="d6e05-597">18</span></span>|<span data-ttu-id="d6e05-598">未指定的错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-598">Unspecified error</span></span>|  
|<span data-ttu-id="d6e05-599">19</span><span class="sxs-lookup"><span data-stu-id="d6e05-599">19</span></span>|<span data-ttu-id="d6e05-600">十进制符号无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-600">Invalid decimal notation</span></span>|  
|<span data-ttu-id="d6e05-601">20</span><span class="sxs-lookup"><span data-stu-id="d6e05-601">20</span></span>|<span data-ttu-id="d6e05-602">字符作为服务字符无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-602">Character invalid as service character</span></span>|  
|<span data-ttu-id="d6e05-603">21</span><span class="sxs-lookup"><span data-stu-id="d6e05-603">21</span></span>|<span data-ttu-id="d6e05-604">无效字符</span><span class="sxs-lookup"><span data-stu-id="d6e05-604">Invalid character(s)</span></span>|  
|<span data-ttu-id="d6e05-605">22</span><span class="sxs-lookup"><span data-stu-id="d6e05-605">22</span></span>|<span data-ttu-id="d6e05-606">无效服务字符</span><span class="sxs-lookup"><span data-stu-id="d6e05-606">Invalid service character(s)</span></span>|  
|<span data-ttu-id="d6e05-607">23</span><span class="sxs-lookup"><span data-stu-id="d6e05-607">23</span></span>|<span data-ttu-id="d6e05-608">未知交换发件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-608">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="d6e05-609">24</span><span class="sxs-lookup"><span data-stu-id="d6e05-609">24</span></span>|<span data-ttu-id="d6e05-610">太旧</span><span class="sxs-lookup"><span data-stu-id="d6e05-610">Too old</span></span>|  
|<span data-ttu-id="d6e05-611">25</span><span class="sxs-lookup"><span data-stu-id="d6e05-611">25</span></span>|<span data-ttu-id="d6e05-612">不支持测试指示器</span><span class="sxs-lookup"><span data-stu-id="d6e05-612">Test indicator not supported</span></span>|  
|<span data-ttu-id="d6e05-613">26</span><span class="sxs-lookup"><span data-stu-id="d6e05-613">26</span></span>|<span data-ttu-id="d6e05-614">检测到重复内容</span><span class="sxs-lookup"><span data-stu-id="d6e05-614">Duplicate detected</span></span>|  
|<span data-ttu-id="d6e05-615">27</span><span class="sxs-lookup"><span data-stu-id="d6e05-615">27</span></span>|<span data-ttu-id="d6e05-616">不支持安全功能</span><span class="sxs-lookup"><span data-stu-id="d6e05-616">Security function not supported</span></span>|  
|<span data-ttu-id="d6e05-617">28</span><span class="sxs-lookup"><span data-stu-id="d6e05-617">28</span></span>|<span data-ttu-id="d6e05-618">参考不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-618">References do not match</span></span>|  
|<span data-ttu-id="d6e05-619">29</span><span class="sxs-lookup"><span data-stu-id="d6e05-619">29</span></span>|<span data-ttu-id="d6e05-620">控制数与接收到的实例数不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-620">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="d6e05-621">30</span><span class="sxs-lookup"><span data-stu-id="d6e05-621">30</span></span>|<span data-ttu-id="d6e05-622">组和消息/包混合</span><span class="sxs-lookup"><span data-stu-id="d6e05-622">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="d6e05-623">31</span><span class="sxs-lookup"><span data-stu-id="d6e05-623">31</span></span>|<span data-ttu-id="d6e05-624">在组中有一种以上的消息类型</span><span class="sxs-lookup"><span data-stu-id="d6e05-624">More than one message type in group</span></span>|  
|<span data-ttu-id="d6e05-625">32</span><span class="sxs-lookup"><span data-stu-id="d6e05-625">32</span></span>|<span data-ttu-id="d6e05-626">低级别为空</span><span class="sxs-lookup"><span data-stu-id="d6e05-626">Lower level empty</span></span>|  
|<span data-ttu-id="d6e05-627">33</span><span class="sxs-lookup"><span data-stu-id="d6e05-627">33</span></span>|<span data-ttu-id="d6e05-628">在消息、包或组外出现无效内容</span><span class="sxs-lookup"><span data-stu-id="d6e05-628">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="d6e05-629">34</span><span class="sxs-lookup"><span data-stu-id="d6e05-629">34</span></span>|<span data-ttu-id="d6e05-630">不允许嵌套指示器</span><span class="sxs-lookup"><span data-stu-id="d6e05-630">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="d6e05-631">35</span><span class="sxs-lookup"><span data-stu-id="d6e05-631">35</span></span>|<span data-ttu-id="d6e05-632">数据元素或段重复过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-632">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="d6e05-633">36</span><span class="sxs-lookup"><span data-stu-id="d6e05-633">36</span></span>|<span data-ttu-id="d6e05-634">段组重复过多</span><span class="sxs-lookup"><span data-stu-id="d6e05-634">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="d6e05-635">37</span><span class="sxs-lookup"><span data-stu-id="d6e05-635">37</span></span>|<span data-ttu-id="d6e05-636">字符类型无效</span><span class="sxs-lookup"><span data-stu-id="d6e05-636">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="d6e05-637">38</span><span class="sxs-lookup"><span data-stu-id="d6e05-637">38</span></span>|<span data-ttu-id="d6e05-638">在小数点前缺少数字</span><span class="sxs-lookup"><span data-stu-id="d6e05-638">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="d6e05-639">39</span><span class="sxs-lookup"><span data-stu-id="d6e05-639">39</span></span>|<span data-ttu-id="d6e05-640">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="d6e05-640">Data element too long</span></span>|  
|<span data-ttu-id="d6e05-641">40</span><span class="sxs-lookup"><span data-stu-id="d6e05-641">40</span></span>|<span data-ttu-id="d6e05-642">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="d6e05-642">Data element too short</span></span>|  
|<span data-ttu-id="d6e05-643">41</span><span class="sxs-lookup"><span data-stu-id="d6e05-643">41</span></span>|<span data-ttu-id="d6e05-644">永久性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-644">Permanent communication network error</span></span>|  
|<span data-ttu-id="d6e05-645">42</span><span class="sxs-lookup"><span data-stu-id="d6e05-645">42</span></span>|<span data-ttu-id="d6e05-646">临时性通信网络错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-646">Temporary communication network error</span></span>|  
|<span data-ttu-id="d6e05-647">43</span><span class="sxs-lookup"><span data-stu-id="d6e05-647">43</span></span>|<span data-ttu-id="d6e05-648">未知交换收件人</span><span class="sxs-lookup"><span data-stu-id="d6e05-648">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="d6e05-649">45</span><span class="sxs-lookup"><span data-stu-id="d6e05-649">45</span></span>|<span data-ttu-id="d6e05-650">尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="d6e05-650">Trailing separator</span></span>|  
|<span data-ttu-id="d6e05-651">46</span><span class="sxs-lookup"><span data-stu-id="d6e05-651">46</span></span>|<span data-ttu-id="d6e05-652">不支持的字符集</span><span class="sxs-lookup"><span data-stu-id="d6e05-652">Character set not supported</span></span>|  
|<span data-ttu-id="d6e05-653">47</span><span class="sxs-lookup"><span data-stu-id="d6e05-653">47</span></span>|<span data-ttu-id="d6e05-654">不支持信封功能</span><span class="sxs-lookup"><span data-stu-id="d6e05-654">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="d6e05-655">48</span><span class="sxs-lookup"><span data-stu-id="d6e05-655">48</span></span>|<span data-ttu-id="d6e05-656">违反了依存关系条件</span><span class="sxs-lookup"><span data-stu-id="d6e05-656">Dependency condition violated</span></span>|  
|<span data-ttu-id="d6e05-657">70</span><span class="sxs-lookup"><span data-stu-id="d6e05-657">70</span></span>|<span data-ttu-id="d6e05-658">事务集缺失或无效事务集标识符</span><span class="sxs-lookup"><span data-stu-id="d6e05-658">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="d6e05-659">71</span><span class="sxs-lookup"><span data-stu-id="d6e05-659">71</span></span>|<span data-ttu-id="d6e05-660">事务集或组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-660">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="d6e05-661">72</span><span class="sxs-lookup"><span data-stu-id="d6e05-661">72</span></span>|<span data-ttu-id="d6e05-662">无法识别的段 ID</span><span class="sxs-lookup"><span data-stu-id="d6e05-662">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="d6e05-663">73</span><span class="sxs-lookup"><span data-stu-id="d6e05-663">73</span></span>|<span data-ttu-id="d6e05-664">XML 的位置不正确</span><span class="sxs-lookup"><span data-stu-id="d6e05-664">XML not at correct position</span></span>|  
|<span data-ttu-id="d6e05-665">74</span><span class="sxs-lookup"><span data-stu-id="d6e05-665">74</span></span>|<span data-ttu-id="d6e05-666">段组重复过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-666">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="d6e05-667">75</span><span class="sxs-lookup"><span data-stu-id="d6e05-667">75</span></span>|<span data-ttu-id="d6e05-668">段重复过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-668">Too few segment repetitions</span></span>|  
|<span data-ttu-id="d6e05-669">76</span><span class="sxs-lookup"><span data-stu-id="d6e05-669">76</span></span>|<span data-ttu-id="d6e05-670">找到的数据元素过少</span><span class="sxs-lookup"><span data-stu-id="d6e05-670">Too few data elements found</span></span>|  
  
 <span data-ttu-id="d6e05-671">以下错误/语法错误代码将用于 X12：</span><span class="sxs-lookup"><span data-stu-id="d6e05-671">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="d6e05-672">错误/语法错误代码</span><span class="sxs-lookup"><span data-stu-id="d6e05-672">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="d6e05-673">（适用于 X12）</span><span class="sxs-lookup"><span data-stu-id="d6e05-673">(applicable to X12)</span></span>|<span data-ttu-id="d6e05-674">用于报告的错误说明</span><span class="sxs-lookup"><span data-stu-id="d6e05-674">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="d6e05-675">@shouldalert</span><span class="sxs-lookup"><span data-stu-id="d6e05-675">1</span></span>|<span data-ttu-id="d6e05-676">不支持功能组</span><span class="sxs-lookup"><span data-stu-id="d6e05-676">Functional group not supported</span></span>|  
|<span data-ttu-id="d6e05-677">2</span><span class="sxs-lookup"><span data-stu-id="d6e05-677">2</span></span>|<span data-ttu-id="d6e05-678">不支持的功能组版本</span><span class="sxs-lookup"><span data-stu-id="d6e05-678">Functional group version not supported</span></span>|  
|<span data-ttu-id="d6e05-679">3</span><span class="sxs-lookup"><span data-stu-id="d6e05-679">3</span></span>|<span data-ttu-id="d6e05-680">功能组尾部缺失</span><span class="sxs-lookup"><span data-stu-id="d6e05-680">Functional group trailer missing</span></span>|  
|<span data-ttu-id="d6e05-681">4</span><span class="sxs-lookup"><span data-stu-id="d6e05-681">4</span></span>|<span data-ttu-id="d6e05-682">功能组标头和尾部中的组控制编号不一致</span><span class="sxs-lookup"><span data-stu-id="d6e05-682">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="d6e05-683">5</span><span class="sxs-lookup"><span data-stu-id="d6e05-683">5</span></span>|<span data-ttu-id="d6e05-684">包含的事务集数与实际计数不匹配</span><span class="sxs-lookup"><span data-stu-id="d6e05-684">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="d6e05-685">6-26</span><span class="sxs-lookup"><span data-stu-id="d6e05-685">6-26</span></span>|<span data-ttu-id="d6e05-686">其他不支持的验证错误</span><span class="sxs-lookup"><span data-stu-id="d6e05-686">Other unsupported validation errors</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6e05-687">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6e05-687">See Also</span></span>  
 <span data-ttu-id="d6e05-688">[如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d6e05-688">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="d6e05-689">如何为入站 EDI 消息存储数据</span><span class="sxs-lookup"><span data-stu-id="d6e05-689">How Data Is Stored for Inbound EDI Messages</span></span>](../core/how-data-is-stored-for-inbound-edi-messages.md)