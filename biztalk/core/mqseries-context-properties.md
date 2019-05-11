---
title: MQSeries 上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQCIH_TaskEndStatus property [MQSeries adapters]
- MQIIH_SecurityScope property [MQSeries adapters]
- MQCIH_AbendCode property [MQSeries adapters]
- filters, MQSeries adapters
- MQCIH_ReturnCode property [MQSeries adapters]
- MQCIH_TransactionId property [MQSeries adapters]
- MQCIH_ReplyToFormat property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- MQMD_PutTime property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQMD_PutApplName property [MQSeries adapters]
- configuring [MQSeries adapters], filtering
- MQCIH_UOWControl property [MQSeries adapters]
- MQCIH_ErrorOffset property [MQSeries adapters]
- MQMD_Priority property [MQSeries adapters]
- MQMD_MsgSeqNumber property [MQSeries adapters]
- MQMD_Format property [MQSeries adapters]
- MQCIH_ConversationalTask property [MQSeries adapters]
- Message Descriptor table [MQSeries adapters]
- MQMD_Feedback property [MQSeries adapters]
- MQCIH_Authenticator property [MQSeries adapters]
- MQIIH_TranState property [MQSeries adapters]
- MQCIH_AttentionId property [MQSeries adapters]
- MQMD_UserIdentifier property [MQSeries adapters]
- MQCIH_Flags property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQIIH_Format property [MQSeries adapters]
- MQMD_Offset property [MQSeries adapters]
- MQMD_BackoutCount property [MQSeries adapters]
- MQMD_Report property [MQSeries adapters]
- MQMD_MsgFlags property [MQSeries adapters]
- MQSeries adapters, filtering
- MQMD_ApplIdentityData property [MQSeries adapters]
- MQIIH_Authenticator property [MQSeries adapters]
- MQIIH_MFSMapName property [MQSeries adapters]
- MQCIH_LinkType property [MQSeries adapters]
- MQMD_Persistence property [MQSeries adapters]
- MQCIH_CursorPosition property [MQSeries adapters]
- MQCIH_Format property [MQSeries adapters]
- MQCIH_Facility property [MQSeries adapters]
- MQCIH_CancelCode property [MQSeries adapters]
- MQMD_PutDate property [MQSeries adapters]
- MQCIH_NextTransactionId property [MQSeries adapters]
- MQIIH_CommitMode property [MQSeries adapters]
- MQIIH_ReplyToFormat property [MQSeries adapters]
- MQCIH_Function property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- MQCIH_StartCode property [MQSeries adapters]
- MQMD_Expiry property [MQSeries adapters]
- MQMD_PutApplType property [MQSeries adapters]
- MQCIH_FacilityLike property [MQSeries adapters]
- MQIIH_Flags property [MQSeries adapters]
- MQCIH_CompCode property [MQSeries adapters]
- MQSeries adapters, properties
- MQCIH_FacilityKeepTime property [MQSeries adapters]
- MQMD_ApplOriginData property [MQSeries adapters]
- MQCIH_Reason property [MQSeries adapters]
- MQIIH_LTermOverride property [MQSeries adapters]
- MQMD_CodedCharSetId property [MQSeries adapters]
- MQMD_GroupID property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgType property [MQSeries adapters]
- MQMD_OriginalLength property [MQSeries adapters]
- MQMD_Encoding property [MQSeries adapters]
- MQMD_AccountingToken property [MQSeries adapters]
- MQCIH_OutputDataLength property [MQSeries adapters]
- MQIIH_TranInstanceId property [MQSeries adapters]
- MQCIH_GetWaitInterval property [MQSeries adapters]
- MQCIH_ADSDescriptor property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: 1b22b7d7-432b-4ec5-938c-c43077ce3e0f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 586897eb36f0c5b68ad58c79be865bc92ebd2087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326489"
---
# <a name="mqseries-context-properties"></a><span data-ttu-id="b80ec-102">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="b80ec-102">MQSeries Context Properties</span></span>
<span data-ttu-id="b80ec-103">MQSeries 适配器提供了一组特定于 MQSeries，以便在你的应用程序中使用的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-103">The MQSeries adapter provides a set of context properties, specific to MQSeries, for use in your applications.</span></span> <span data-ttu-id="b80ec-104">在筛选器表达式和您的业务流程中，可以使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-104">You can use these properties in filter expressions and in your orchestrations.</span></span>  
  
 <span data-ttu-id="b80ec-105">若要将 MQSeries 上下文属性分配到发往绑定到 MQSeries 适配器的发送端口的消息，请使用消息赋值运算符，并在 MQSeries 命名空间中指定一个可用上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-105">To assign MQSeries context properties to a message destined to a send port that is bound to the MQSeries adapter, use the message assignment operator and specify one of the available context properties in the MQSeries namespace.</span></span>  
  
 <span data-ttu-id="b80ec-106">下面是设置 MQSeries 的示例**MQMD_UserIdentifier**属性：</span><span class="sxs-lookup"><span data-stu-id="b80ec-106">The following is an example of setting the MQSeries **MQMD_UserIdentifier** property:</span></span>  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 <span data-ttu-id="b80ec-107">你必须获取枚举的值从 C 编程语言头文件包含在 IBM MQSeries SDK。</span><span class="sxs-lookup"><span data-stu-id="b80ec-107">You must obtain enumerated values from the C programming language header files included with the IBM MQSeries SDK.</span></span> <span data-ttu-id="b80ec-108">可以在 Program Files\IBM\WebSphere MQ\Tools\c\include 文件夹中找到这些文件。</span><span class="sxs-lookup"><span data-stu-id="b80ec-108">You can find these files in the Program Files\IBM\WebSphere MQ\Tools\c\include folder.</span></span> <span data-ttu-id="b80ec-109">这些文件定义设置或读取 MQSeries 上下文属性值时要使用的值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-109">These files define the values to use when setting or reading MQSeries context property values.</span></span>  
  
 <span data-ttu-id="b80ec-110">十六进制字符串值是表示二进制值的字符串。</span><span class="sxs-lookup"><span data-stu-id="b80ec-110">Hexadecimal string values are character strings representing binary values.</span></span> <span data-ttu-id="b80ec-111">它们不具有诸如 0x 之类的前缀。</span><span class="sxs-lookup"><span data-stu-id="b80ec-111">They do not have a prefix such as 0x.</span></span> <span data-ttu-id="b80ec-112">它们包含从 0 到 9 的数字和字母"a"到"f"或"A"到"F"。</span><span class="sxs-lookup"><span data-stu-id="b80ec-112">They contain digits from 0 through 9 and letters from "a" through "f" or "A" through "F".</span></span> <span data-ttu-id="b80ec-113">适配器将忽略它们中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="b80ec-113">The adapter ignores white space in them.</span></span>  
  
 <span data-ttu-id="b80ec-114">有关这些属性的详细信息，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="b80ec-114">For more information about these properties, see the IBM WebSphere MQ documentation.</span></span>  
  
 <span data-ttu-id="b80ec-115">下表显示了可用的消息描述符 （MQMD 结构） 属性及其相应的类型和值的完整集。</span><span class="sxs-lookup"><span data-stu-id="b80ec-115">The following table shows the complete set of available Message Descriptor (MQMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="b80ec-116">“属性”</span><span class="sxs-lookup"><span data-stu-id="b80ec-116">Name</span></span>|<span data-ttu-id="b80ec-117">类型</span><span class="sxs-lookup"><span data-stu-id="b80ec-117">Type</span></span>|<span data-ttu-id="b80ec-118">长度</span><span class="sxs-lookup"><span data-stu-id="b80ec-118">Length</span></span>|<span data-ttu-id="b80ec-119">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b80ec-119">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="b80ec-120">**MQMD_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="b80ec-120">**MQMD_AccountingToken**</span></span>|<span data-ttu-id="b80ec-121">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-121">string</span></span>|<span data-ttu-id="b80ec-122">64</span><span class="sxs-lookup"><span data-stu-id="b80ec-122">64</span></span>|<span data-ttu-id="b80ec-123">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-123">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-124">**MQMD_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="b80ec-124">**MQMD_ApplIdentityData**</span></span>|<span data-ttu-id="b80ec-125">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-125">string</span></span>|<span data-ttu-id="b80ec-126">32</span><span class="sxs-lookup"><span data-stu-id="b80ec-126">32</span></span>|<span data-ttu-id="b80ec-127">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-127">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-128">**MQMD_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="b80ec-128">**MQMD_ApplOriginData**</span></span>|<span data-ttu-id="b80ec-129">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-129">string</span></span>|<span data-ttu-id="b80ec-130">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-130">4</span></span>|<span data-ttu-id="b80ec-131">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-131">String</span></span><br /><br /> <span data-ttu-id="b80ec-132">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="b80ec-132">**Default:** space</span></span>|  
|<span data-ttu-id="b80ec-133">**MQMD_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="b80ec-133">**MQMD_BackoutCount**</span></span>|<span data-ttu-id="b80ec-134">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-134">unsigned int</span></span>|<span data-ttu-id="b80ec-135">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-135">4</span></span>|<span data-ttu-id="b80ec-136">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-136">Number</span></span><br /><br /> <span data-ttu-id="b80ec-137">只读</span><span class="sxs-lookup"><span data-stu-id="b80ec-137">Read only</span></span><br /><br /> <span data-ttu-id="b80ec-138">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-138">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-139">**MQMD_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-139">**MQMD_CodedCharSetId**</span></span>|<span data-ttu-id="b80ec-140">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-140">unsigned int</span></span>|<span data-ttu-id="b80ec-141">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-141">4</span></span>|<span data-ttu-id="b80ec-142">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-142">Number</span></span><br /><br /> <span data-ttu-id="b80ec-143">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-143">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-144">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-144">**MQMD_CorrelId**</span></span>|<span data-ttu-id="b80ec-145">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-145">string</span></span>|<span data-ttu-id="b80ec-146">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-146">48</span></span>|<span data-ttu-id="b80ec-147">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-147">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-148">**MQMD_Encoding**</span><span class="sxs-lookup"><span data-stu-id="b80ec-148">**MQMD_Encoding**</span></span>|<span data-ttu-id="b80ec-149">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-149">unsigned int</span></span>|<span data-ttu-id="b80ec-150">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-150">4</span></span>|<span data-ttu-id="b80ec-151">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-151">Number</span></span><br /><br /> <span data-ttu-id="b80ec-152">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-152">Use header file value.</span></span> <span data-ttu-id="b80ec-153">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-153">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-154">**MQMD_Expiry**</span><span class="sxs-lookup"><span data-stu-id="b80ec-154">**MQMD_Expiry**</span></span>|<span data-ttu-id="b80ec-155">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-155">unsigned int</span></span>|<span data-ttu-id="b80ec-156">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-156">4</span></span>|<span data-ttu-id="b80ec-157">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-157">Number</span></span>|  
|<span data-ttu-id="b80ec-158">**MQMD_Feedback**</span><span class="sxs-lookup"><span data-stu-id="b80ec-158">**MQMD_Feedback**</span></span>|<span data-ttu-id="b80ec-159">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-159">unsigned int</span></span>|<span data-ttu-id="b80ec-160">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-160">4</span></span>|<span data-ttu-id="b80ec-161">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-161">Number</span></span><br /><br /> <span data-ttu-id="b80ec-162">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-162">Use header file value.</span></span> <span data-ttu-id="b80ec-163">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-163">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-164">**MQMD_Format**</span><span class="sxs-lookup"><span data-stu-id="b80ec-164">**MQMD_Format**</span></span>|<span data-ttu-id="b80ec-165">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-165">string</span></span>|<span data-ttu-id="b80ec-166">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-166">8</span></span>|<span data-ttu-id="b80ec-167">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-167">String</span></span><br /><br /> <span data-ttu-id="b80ec-168">如果设置为 MQXMIT，可确保 MQXQH 属性具有值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-168">If set to MQXMIT, makes sure that the MQXQH properties have values.</span></span>|  
|<span data-ttu-id="b80ec-169">**MQMD_GroupID**</span><span class="sxs-lookup"><span data-stu-id="b80ec-169">**MQMD_GroupID**</span></span>|<span data-ttu-id="b80ec-170">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-170">string</span></span>|<span data-ttu-id="b80ec-171">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-171">48</span></span>|<span data-ttu-id="b80ec-172">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-172">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-173">**MQMD_MsgFlags**</span><span class="sxs-lookup"><span data-stu-id="b80ec-173">**MQMD_MsgFlags**</span></span>|<span data-ttu-id="b80ec-174">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-174">unsigned int</span></span>|<span data-ttu-id="b80ec-175">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-175">4</span></span>|<span data-ttu-id="b80ec-176">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-176">Number</span></span><br /><br /> <span data-ttu-id="b80ec-177">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-177">Use header file value.</span></span> <span data-ttu-id="b80ec-178">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-178">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-179">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-179">**MQMD_MsgId**</span></span>|<span data-ttu-id="b80ec-180">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-180">string</span></span>|<span data-ttu-id="b80ec-181">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-181">48</span></span>|<span data-ttu-id="b80ec-182">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-182">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-183">**MQMD_MsgSeqNumber**</span><span class="sxs-lookup"><span data-stu-id="b80ec-183">**MQMD_MsgSeqNumber**</span></span>|<span data-ttu-id="b80ec-184">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-184">unsigned int</span></span>|<span data-ttu-id="b80ec-185">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-185">4</span></span>||  
|<span data-ttu-id="b80ec-186">**MQMD_MsgType**</span><span class="sxs-lookup"><span data-stu-id="b80ec-186">**MQMD_MsgType**</span></span>|<span data-ttu-id="b80ec-187">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-187">unsigned int</span></span>|<span data-ttu-id="b80ec-188">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-188">4</span></span>|<span data-ttu-id="b80ec-189">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-189">Number</span></span><br /><br /> <span data-ttu-id="b80ec-190">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-190">Use header file value.</span></span>|  
|<span data-ttu-id="b80ec-191">**MQMD_Offset**</span><span class="sxs-lookup"><span data-stu-id="b80ec-191">**MQMD_Offset**</span></span>|<span data-ttu-id="b80ec-192">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-192">unsigned int</span></span>|<span data-ttu-id="b80ec-193">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-193">4</span></span>||  
|<span data-ttu-id="b80ec-194">**MQMD_OriginalLength**</span><span class="sxs-lookup"><span data-stu-id="b80ec-194">**MQMD_OriginalLength**</span></span>|<span data-ttu-id="b80ec-195">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-195">unsigned int</span></span>|<span data-ttu-id="b80ec-196">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-196">4</span></span>||  
|<span data-ttu-id="b80ec-197">**MQMD_Persistence**</span><span class="sxs-lookup"><span data-stu-id="b80ec-197">**MQMD_Persistence**</span></span>|<span data-ttu-id="b80ec-198">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-198">unsigned int</span></span>|<span data-ttu-id="b80ec-199">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-199">4</span></span>|<span data-ttu-id="b80ec-200">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-200">Number</span></span><br /><br /> <span data-ttu-id="b80ec-201">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-201">Use header file value.</span></span>|  
|<span data-ttu-id="b80ec-202">**MQMD_Priority**</span><span class="sxs-lookup"><span data-stu-id="b80ec-202">**MQMD_Priority**</span></span>|<span data-ttu-id="b80ec-203">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-203">unsigned int</span></span>|<span data-ttu-id="b80ec-204">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-204">4</span></span>|<span data-ttu-id="b80ec-205">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-205">Number</span></span>|  
|<span data-ttu-id="b80ec-206">**MQMD_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="b80ec-206">**MQMD_PutApplName**</span></span>|<span data-ttu-id="b80ec-207">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-207">string</span></span>|<span data-ttu-id="b80ec-208">28</span><span class="sxs-lookup"><span data-stu-id="b80ec-208">28</span></span>|<span data-ttu-id="b80ec-209">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-209">String</span></span><br /><br /> <span data-ttu-id="b80ec-210">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="b80ec-210">**Default:** space</span></span>|  
|<span data-ttu-id="b80ec-211">**MQMD_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="b80ec-211">**MQMD_PutApplType**</span></span>|<span data-ttu-id="b80ec-212">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-212">unsigned int</span></span>|<span data-ttu-id="b80ec-213">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-213">4</span></span>|<span data-ttu-id="b80ec-214">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-214">Number</span></span><br /><br /> <span data-ttu-id="b80ec-215">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-215">Use header file value.</span></span> <span data-ttu-id="b80ec-216">默认值：0</span><span class="sxs-lookup"><span data-stu-id="b80ec-216">**Default:** 0</span></span>|  
|<span data-ttu-id="b80ec-217">**MQMD_PutDate**</span><span class="sxs-lookup"><span data-stu-id="b80ec-217">**MQMD_PutDate**</span></span>|<span data-ttu-id="b80ec-218">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-218">string</span></span>|<span data-ttu-id="b80ec-219">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-219">8</span></span>|<span data-ttu-id="b80ec-220">Date</span><span class="sxs-lookup"><span data-stu-id="b80ec-220">Date</span></span>|  
|<span data-ttu-id="b80ec-221">**MQMD_PutTime**</span><span class="sxs-lookup"><span data-stu-id="b80ec-221">**MQMD_PutTime**</span></span>|<span data-ttu-id="b80ec-222">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-222">string</span></span>|<span data-ttu-id="b80ec-223">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-223">8</span></span>|<span data-ttu-id="b80ec-224">Time</span><span class="sxs-lookup"><span data-stu-id="b80ec-224">Time</span></span>|  
|<span data-ttu-id="b80ec-225">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="b80ec-225">**MQMD_ReplyToQ**</span></span>|<span data-ttu-id="b80ec-226">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-226">string</span></span>|<span data-ttu-id="b80ec-227">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-227">48</span></span>|<span data-ttu-id="b80ec-228">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-228">String</span></span><br /><br /> <span data-ttu-id="b80ec-229">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="b80ec-229">**Default:** space</span></span>|  
|<span data-ttu-id="b80ec-230">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="b80ec-230">**MQMD_ReplyToQMgr**</span></span>|<span data-ttu-id="b80ec-231">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-231">string</span></span>|<span data-ttu-id="b80ec-232">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-232">48</span></span>|<span data-ttu-id="b80ec-233">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-233">String</span></span><br /><br /> <span data-ttu-id="b80ec-234">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="b80ec-234">**Default:** space</span></span>|  
|<span data-ttu-id="b80ec-235">**MQMD_Report**</span><span class="sxs-lookup"><span data-stu-id="b80ec-235">**MQMD_Report**</span></span>|<span data-ttu-id="b80ec-236">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-236">unsigned int</span></span>|<span data-ttu-id="b80ec-237">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-237">4</span></span>|<span data-ttu-id="b80ec-238">Number</span><span class="sxs-lookup"><span data-stu-id="b80ec-238">Number</span></span><br /><br /> <span data-ttu-id="b80ec-239">使用标头文件值。</span><span class="sxs-lookup"><span data-stu-id="b80ec-239">Use header file value.</span></span>|  
|<span data-ttu-id="b80ec-240">**MQMD_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="b80ec-240">**MQMD_UserIdentifier**</span></span>|<span data-ttu-id="b80ec-241">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-241">string</span></span>|<span data-ttu-id="b80ec-242">12</span><span class="sxs-lookup"><span data-stu-id="b80ec-242">12</span></span>|<span data-ttu-id="b80ec-243">String</span><span class="sxs-lookup"><span data-stu-id="b80ec-243">String</span></span><br /><br /> <span data-ttu-id="b80ec-244">当你使用时，包含用户标识符**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-244">Contains the user identifier when you use the **SSOAffiliateApplication** property.</span></span>|  
  
 <span data-ttu-id="b80ec-245">当直接从 MQSeries 传输队列接收消息，MQSeries 适配器格式传输队列标头属性 （MQXQH 数据结构），并将其置于其对应的上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="b80ec-245">When receiving messages directly from MQSeries transmission queues, the MQSeries adapter formats the transmission queue header properties (the MQXQH data structure) and places them in their corresponding context properties.</span></span> <span data-ttu-id="b80ec-246">当直接向 MQSeries 传输队列发送消息，标头属性被格式化，并从相应的上下文属性仅当分配值**MQMD_Format**属性具有值为 mqxmit 时。</span><span class="sxs-lookup"><span data-stu-id="b80ec-246">When sending messages directly to MQSeries transmission queues, the header properties are formatted and assigned values from the corresponding context properties only if the **MQMD_Format** property has a value of MQXMIT.</span></span> <span data-ttu-id="b80ec-247">下表介绍的属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-247">The following table describes the properties.</span></span>  
  
|<span data-ttu-id="b80ec-248">“属性”</span><span class="sxs-lookup"><span data-stu-id="b80ec-248">Name</span></span>|<span data-ttu-id="b80ec-249">类型</span><span class="sxs-lookup"><span data-stu-id="b80ec-249">Type</span></span>|<span data-ttu-id="b80ec-250">长度</span><span class="sxs-lookup"><span data-stu-id="b80ec-250">Length</span></span>|<span data-ttu-id="b80ec-251">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b80ec-251">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="b80ec-252">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="b80ec-252">**MQXQH_RemoteQMgrName**</span></span>|<span data-ttu-id="b80ec-253">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-253">string</span></span>|<span data-ttu-id="b80ec-254">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-254">48</span></span>|<span data-ttu-id="b80ec-255">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-255">string</span></span>|  
|<span data-ttu-id="b80ec-256">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="b80ec-256">**MQXQH_RemoteQName**</span></span>|<span data-ttu-id="b80ec-257">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-257">string</span></span>|<span data-ttu-id="b80ec-258">48</span><span class="sxs-lookup"><span data-stu-id="b80ec-258">48</span></span>|<span data-ttu-id="b80ec-259">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-259">string</span></span>|  
  
 <span data-ttu-id="b80ec-260">本主题中前面列出的属性，以及适配器将填充以下消息描述符值遵循的规则相同。</span><span class="sxs-lookup"><span data-stu-id="b80ec-260">Together with the properties listed earlier in this topic, the adapter populates the following Message Descriptor values following the same rules.</span></span> <span data-ttu-id="b80ec-261">适配器使用 MQXQH_ 而不是 MQMD_，这些属性名称添加前缀，但否则它们直接映射到消息描述符表中定义的那些属性：</span><span class="sxs-lookup"><span data-stu-id="b80ec-261">The adapter prefixes these property names with MQXQH_ instead of MQMD_, but otherwise they map directly to those properties defined in the Message Descriptor table:</span></span>  
  
- <span data-ttu-id="b80ec-262">**MQXQH_MsgDesc_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="b80ec-262">**MQXQH_MsgDesc_AccountingToken**</span></span>  
  
- <span data-ttu-id="b80ec-263">**MQXQH_MsgDesc_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="b80ec-263">**MQXQH_MsgDesc_ApplIdentityData**</span></span>  
  
- <span data-ttu-id="b80ec-264">**MQXQH_MsgDesc_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="b80ec-264">**MQXQH_MsgDesc_ApplOriginData**</span></span>  
  
- <span data-ttu-id="b80ec-265">**MQXQH_MsgDesc_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="b80ec-265">**MQXQH_MsgDesc_BackoutCount**</span></span>  
  
- <span data-ttu-id="b80ec-266">**MQXQH_MsgDesc_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-266">**MQXQH_MsgDesc_CodedCharSetId**</span></span>  
  
- <span data-ttu-id="b80ec-267">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-267">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
- <span data-ttu-id="b80ec-268">**MQXQH_MsgDesc_Encoding**</span><span class="sxs-lookup"><span data-stu-id="b80ec-268">**MQXQH_MsgDesc_Encoding**</span></span>  
  
- <span data-ttu-id="b80ec-269">**MQXQH_MsgDesc_Expiry**</span><span class="sxs-lookup"><span data-stu-id="b80ec-269">**MQXQH_MsgDesc_Expiry**</span></span>  
  
- <span data-ttu-id="b80ec-270">**MQXQH_MsgDesc_Feedback**</span><span class="sxs-lookup"><span data-stu-id="b80ec-270">**MQXQH_MsgDesc_Feedback**</span></span>  
  
- <span data-ttu-id="b80ec-271">**MQXQH_MsgDesc_Format**</span><span class="sxs-lookup"><span data-stu-id="b80ec-271">**MQXQH_MsgDesc_Format**</span></span>  
  
- <span data-ttu-id="b80ec-272">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-272">**MQXQH_MsgDesc_MsgId**</span></span>  
  
- <span data-ttu-id="b80ec-273">**MQXQH_MsgDesc_MsgType**</span><span class="sxs-lookup"><span data-stu-id="b80ec-273">**MQXQH_MsgDesc_MsgType**</span></span>  
  
- <span data-ttu-id="b80ec-274">**MQXQH_MsgDesc_Persistence**</span><span class="sxs-lookup"><span data-stu-id="b80ec-274">**MQXQH_MsgDesc_Persistence**</span></span>  
  
- <span data-ttu-id="b80ec-275">**MQXQH_MsgDesc_Priority**</span><span class="sxs-lookup"><span data-stu-id="b80ec-275">**MQXQH_MsgDesc_Priority**</span></span>  
  
- <span data-ttu-id="b80ec-276">**MQXQH_MsgDesc_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="b80ec-276">**MQXQH_MsgDesc_PutApplName**</span></span>  
  
- <span data-ttu-id="b80ec-277">**MQXQH_MsgDesc_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="b80ec-277">**MQXQH_MsgDesc_PutApplType**</span></span>  
  
- <span data-ttu-id="b80ec-278">**MQXQH_MsgDesc_PutDate**</span><span class="sxs-lookup"><span data-stu-id="b80ec-278">**MQXQH_MsgDesc_PutDate**</span></span>  
  
- <span data-ttu-id="b80ec-279">**MQXQH_MsgDesc_PutTime**</span><span class="sxs-lookup"><span data-stu-id="b80ec-279">**MQXQH_MsgDesc_PutTime**</span></span>  
  
- <span data-ttu-id="b80ec-280">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="b80ec-280">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
- <span data-ttu-id="b80ec-281">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="b80ec-281">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
- <span data-ttu-id="b80ec-282">**MQXQH_MsgDesc_Report**</span><span class="sxs-lookup"><span data-stu-id="b80ec-282">**MQXQH_MsgDesc_Report**</span></span>  
  
- <span data-ttu-id="b80ec-283">**MQXQH_MsgDesc_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="b80ec-283">**MQXQH_MsgDesc_UserIdentifier**</span></span>  
  
  <span data-ttu-id="b80ec-284">有其他与 MQSeries 相关属性包含属性架构中并且可以在筛选表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="b80ec-284">There are additional MQSeries-related properties included in the property schema and available for use in filtering expressions.</span></span> <span data-ttu-id="b80ec-285">下表列出了这些属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-285">The following table lists these properties.</span></span>  
  
|<span data-ttu-id="b80ec-286">“属性”</span><span class="sxs-lookup"><span data-stu-id="b80ec-286">Name</span></span>|<span data-ttu-id="b80ec-287">类型</span><span class="sxs-lookup"><span data-stu-id="b80ec-287">Type</span></span>|<span data-ttu-id="b80ec-288">长度</span><span class="sxs-lookup"><span data-stu-id="b80ec-288">Length</span></span>|<span data-ttu-id="b80ec-289">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b80ec-289">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="b80ec-290">**MQCIH_AbendCode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-290">**MQCIH_AbendCode**</span></span>|<span data-ttu-id="b80ec-291">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-291">string</span></span>|<span data-ttu-id="b80ec-292">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-292">4</span></span>||  
|<span data-ttu-id="b80ec-293">**MQCIH_ADSDescriptor**</span><span class="sxs-lookup"><span data-stu-id="b80ec-293">**MQCIH_ADSDescriptor**</span></span>|<span data-ttu-id="b80ec-294">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-294">unsigned int</span></span>|<span data-ttu-id="b80ec-295">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-295">4</span></span>||  
|<span data-ttu-id="b80ec-296">**MQCIH_AttentionId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-296">**MQCIH_AttentionId**</span></span>|<span data-ttu-id="b80ec-297">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-297">string</span></span>|<span data-ttu-id="b80ec-298">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-298">4</span></span>||  
|<span data-ttu-id="b80ec-299">**MQCIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="b80ec-299">**MQCIH_Authenticator**</span></span>|<span data-ttu-id="b80ec-300">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-300">string</span></span>|<span data-ttu-id="b80ec-301">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-301">8</span></span>|<span data-ttu-id="b80ec-302">当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-302">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="b80ec-303">**注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="b80ec-303">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="b80ec-304">**MQCIH_CancelCode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-304">**MQCIH_CancelCode**</span></span>|<span data-ttu-id="b80ec-305">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-305">string</span></span>|<span data-ttu-id="b80ec-306">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-306">4</span></span>||  
|<span data-ttu-id="b80ec-307">**MQCIH_CompCode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-307">**MQCIH_CompCode**</span></span>|<span data-ttu-id="b80ec-308">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-308">unsigned int</span></span>|<span data-ttu-id="b80ec-309">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-309">4</span></span>||  
|<span data-ttu-id="b80ec-310">**MQCIH_ConversationalTask**</span><span class="sxs-lookup"><span data-stu-id="b80ec-310">**MQCIH_ConversationalTask**</span></span>|<span data-ttu-id="b80ec-311">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-311">unsigned int</span></span>|<span data-ttu-id="b80ec-312">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-312">4</span></span>||  
|<span data-ttu-id="b80ec-313">**MQCIH_CursorPosition**</span><span class="sxs-lookup"><span data-stu-id="b80ec-313">**MQCIH_CursorPosition**</span></span>|<span data-ttu-id="b80ec-314">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-314">unsigned int</span></span>|<span data-ttu-id="b80ec-315">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-315">4</span></span>||  
|<span data-ttu-id="b80ec-316">**MQCIH_ErrorOffset**</span><span class="sxs-lookup"><span data-stu-id="b80ec-316">**MQCIH_ErrorOffset**</span></span>|<span data-ttu-id="b80ec-317">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-317">unsigned int</span></span>|<span data-ttu-id="b80ec-318">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-318">4</span></span>||  
|<span data-ttu-id="b80ec-319">**MQCIH_Facility**</span><span class="sxs-lookup"><span data-stu-id="b80ec-319">**MQCIH_Facility**</span></span>|<span data-ttu-id="b80ec-320">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-320">string</span></span>|<span data-ttu-id="b80ec-321">16</span><span class="sxs-lookup"><span data-stu-id="b80ec-321">16</span></span>|<span data-ttu-id="b80ec-322">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-322">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-323">**MQCIH_FacilityKeepTime**</span><span class="sxs-lookup"><span data-stu-id="b80ec-323">**MQCIH_FacilityKeepTime**</span></span>|<span data-ttu-id="b80ec-324">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-324">unsigned int</span></span>|<span data-ttu-id="b80ec-325">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-325">4</span></span>||  
|<span data-ttu-id="b80ec-326">**MQCIH_FacilityLike**</span><span class="sxs-lookup"><span data-stu-id="b80ec-326">**MQCIH_FacilityLike**</span></span>|<span data-ttu-id="b80ec-327">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-327">string</span></span>|<span data-ttu-id="b80ec-328">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-328">4</span></span>||  
|<span data-ttu-id="b80ec-329">**MQCIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="b80ec-329">**MQCIH_Flags**</span></span>|<span data-ttu-id="b80ec-330">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-330">unsigned int</span></span>|<span data-ttu-id="b80ec-331">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-331">4</span></span>||  
|<span data-ttu-id="b80ec-332">**MQCIH_Format**</span><span class="sxs-lookup"><span data-stu-id="b80ec-332">**MQCIH_Format**</span></span>|<span data-ttu-id="b80ec-333">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-333">string</span></span>|||  
|<span data-ttu-id="b80ec-334">**MQCIH_Function**</span><span class="sxs-lookup"><span data-stu-id="b80ec-334">**MQCIH_Function**</span></span>|<span data-ttu-id="b80ec-335">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-335">string</span></span>|<span data-ttu-id="b80ec-336">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-336">4</span></span>||  
|<span data-ttu-id="b80ec-337">**MQCIH_GetWaitInterval**</span><span class="sxs-lookup"><span data-stu-id="b80ec-337">**MQCIH_GetWaitInterval**</span></span>|<span data-ttu-id="b80ec-338">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-338">unsigned int</span></span>|<span data-ttu-id="b80ec-339">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-339">4</span></span>||  
|<span data-ttu-id="b80ec-340">**MQCIH_LinkType**</span><span class="sxs-lookup"><span data-stu-id="b80ec-340">**MQCIH_LinkType**</span></span>|<span data-ttu-id="b80ec-341">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-341">unsigned int</span></span>|<span data-ttu-id="b80ec-342">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-342">4</span></span>||  
|<span data-ttu-id="b80ec-343">**MQCIH_NextTransactionId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-343">**MQCIH_NextTransactionId**</span></span>|<span data-ttu-id="b80ec-344">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-344">string</span></span>|<span data-ttu-id="b80ec-345">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-345">4</span></span>||  
|<span data-ttu-id="b80ec-346">**MQCIH_OutputDataLength**</span><span class="sxs-lookup"><span data-stu-id="b80ec-346">**MQCIH_OutputDataLength**</span></span>|<span data-ttu-id="b80ec-347">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-347">unsigned int</span></span>|<span data-ttu-id="b80ec-348">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-348">4</span></span>||  
|<span data-ttu-id="b80ec-349">**MQCIH_Reason**</span><span class="sxs-lookup"><span data-stu-id="b80ec-349">**MQCIH_Reason**</span></span>|<span data-ttu-id="b80ec-350">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-350">unsigned int</span></span>|<span data-ttu-id="b80ec-351">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-351">4</span></span>||  
|<span data-ttu-id="b80ec-352">**MQCIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="b80ec-352">**MQCIH_ReplyToFormat**</span></span>|<span data-ttu-id="b80ec-353">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-353">string</span></span>|||  
|<span data-ttu-id="b80ec-354">**MQCIH_ReturnCode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-354">**MQCIH_ReturnCode**</span></span>|<span data-ttu-id="b80ec-355">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-355">unsigned int</span></span>|<span data-ttu-id="b80ec-356">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-356">4</span></span>||  
|<span data-ttu-id="b80ec-357">**MQCIH_StartCode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-357">**MQCIH_StartCode**</span></span>|<span data-ttu-id="b80ec-358">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-358">string</span></span>|<span data-ttu-id="b80ec-359">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-359">4</span></span>||  
|<span data-ttu-id="b80ec-360">**MQCIH_TaskEndStatus**</span><span class="sxs-lookup"><span data-stu-id="b80ec-360">**MQCIH_TaskEndStatus**</span></span>|<span data-ttu-id="b80ec-361">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-361">unsigned int</span></span>|<span data-ttu-id="b80ec-362">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-362">4</span></span>||  
|<span data-ttu-id="b80ec-363">**MQCIH_TransactionId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-363">**MQCIH_TransactionId**</span></span>|<span data-ttu-id="b80ec-364">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-364">string</span></span>|<span data-ttu-id="b80ec-365">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-365">4</span></span>||  
|<span data-ttu-id="b80ec-366">**MQCIH_UOWControl**</span><span class="sxs-lookup"><span data-stu-id="b80ec-366">**MQCIH_UOWControl**</span></span>|<span data-ttu-id="b80ec-367">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-367">unsigned int</span></span>|<span data-ttu-id="b80ec-368">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-368">4</span></span>||  
|<span data-ttu-id="b80ec-369">**MQIIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="b80ec-369">**MQIIH_Authenticator**</span></span>|<span data-ttu-id="b80ec-370">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-370">string</span></span>|<span data-ttu-id="b80ec-371">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-371">8</span></span>|<span data-ttu-id="b80ec-372">当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="b80ec-372">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="b80ec-373">**注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="b80ec-373">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="b80ec-374">**MQIIH_CommitMode**</span><span class="sxs-lookup"><span data-stu-id="b80ec-374">**MQIIH_CommitMode**</span></span>|<span data-ttu-id="b80ec-375">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-375">string</span></span>|||  
|<span data-ttu-id="b80ec-376">**MQIIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="b80ec-376">**MQIIH_Flags**</span></span>|<span data-ttu-id="b80ec-377">unsigned int</span><span class="sxs-lookup"><span data-stu-id="b80ec-377">unsigned int</span></span>|<span data-ttu-id="b80ec-378">4</span><span class="sxs-lookup"><span data-stu-id="b80ec-378">4</span></span>||  
|<span data-ttu-id="b80ec-379">**MQIIH_Format**</span><span class="sxs-lookup"><span data-stu-id="b80ec-379">**MQIIH_Format**</span></span>|<span data-ttu-id="b80ec-380">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-380">string</span></span>|||  
|<span data-ttu-id="b80ec-381">**MQIIH_LTermOverride**</span><span class="sxs-lookup"><span data-stu-id="b80ec-381">**MQIIH_LTermOverride**</span></span>|<span data-ttu-id="b80ec-382">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-382">string</span></span>|<span data-ttu-id="b80ec-383">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-383">8</span></span>||  
|<span data-ttu-id="b80ec-384">**MQIIH_MFSMapName**</span><span class="sxs-lookup"><span data-stu-id="b80ec-384">**MQIIH_MFSMapName**</span></span>|<span data-ttu-id="b80ec-385">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-385">string</span></span>|<span data-ttu-id="b80ec-386">8</span><span class="sxs-lookup"><span data-stu-id="b80ec-386">8</span></span>||  
|<span data-ttu-id="b80ec-387">**MQIIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="b80ec-387">**MQIIH_ReplyToFormat**</span></span>|<span data-ttu-id="b80ec-388">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-388">string</span></span>|||  
|<span data-ttu-id="b80ec-389">**MQIIH_SecurityScope**</span><span class="sxs-lookup"><span data-stu-id="b80ec-389">**MQIIH_SecurityScope**</span></span>|<span data-ttu-id="b80ec-390">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-390">string</span></span>|||  
|<span data-ttu-id="b80ec-391">**MQIIH_TranInstanceId**</span><span class="sxs-lookup"><span data-stu-id="b80ec-391">**MQIIH_TranInstanceId**</span></span>|<span data-ttu-id="b80ec-392">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-392">string</span></span>|<span data-ttu-id="b80ec-393">32</span><span class="sxs-lookup"><span data-stu-id="b80ec-393">32</span></span>|<span data-ttu-id="b80ec-394">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="b80ec-394">Hexadecimal string</span></span>|  
|<span data-ttu-id="b80ec-395">**MQIIH_TranState**</span><span class="sxs-lookup"><span data-stu-id="b80ec-395">**MQIIH_TranState**</span></span>|<span data-ttu-id="b80ec-396">string</span><span class="sxs-lookup"><span data-stu-id="b80ec-396">string</span></span>|||  
  
## <a name="see-also"></a><span data-ttu-id="b80ec-397">请参阅</span><span class="sxs-lookup"><span data-stu-id="b80ec-397">See Also</span></span>  
 <span data-ttu-id="b80ec-398">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b80ec-398">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="b80ec-399">[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b80ec-399">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b80ec-400">属性的数据类型转换</span><span class="sxs-lookup"><span data-stu-id="b80ec-400">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)