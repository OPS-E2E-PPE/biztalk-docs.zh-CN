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
ms.openlocfilehash: 684fad8e1a417e9faf7127a81a4e8f7d6f10e630
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976590"
---
# <a name="mqseries-context-properties"></a><span data-ttu-id="e1008-102">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="e1008-102">MQSeries Context Properties</span></span>
<span data-ttu-id="e1008-103">MQSeries 适配器提供了一组特定于 MQSeries 的上下文属性以供您在应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="e1008-103">The MQSeries adapter provides a set of context properties, specific to MQSeries, for use in your applications.</span></span> <span data-ttu-id="e1008-104">您可以在筛选表达式和业务流程中使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="e1008-104">You can use these properties in filter expressions and in your orchestrations.</span></span>  
  
 <span data-ttu-id="e1008-105">对于以绑定到 MQSeries 适配器的发送端口为目标的消息，若要将 MQSeries 上下文属性分配给此类消息，请使用消息赋值运算符，并在 MQSeries 命名空间中指定可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="e1008-105">To assign MQSeries context properties to a message destined to a send port that is bound to the MQSeries adapter, use the message assignment operator and specify one of the available context properties in the MQSeries namespace.</span></span>  
  
 <span data-ttu-id="e1008-106">下面是设置 MQSeries 的示例**MQMD_UserIdentifier**属性：</span><span class="sxs-lookup"><span data-stu-id="e1008-106">The following is an example of setting the MQSeries **MQMD_UserIdentifier** property:</span></span>  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 <span data-ttu-id="e1008-107">必须从 IBM MQSeries SDK 所附带的 C 编程语言头文件中获得枚举值。</span><span class="sxs-lookup"><span data-stu-id="e1008-107">You must obtain enumerated values from the C programming language header files included with the IBM MQSeries SDK.</span></span> <span data-ttu-id="e1008-108">在 Program Files\IBM\WebSphere MQ\Tools\c\include 文件夹中可找到这些文件。</span><span class="sxs-lookup"><span data-stu-id="e1008-108">You can find these files in the Program Files\IBM\WebSphere MQ\Tools\c\include folder.</span></span> <span data-ttu-id="e1008-109">这些文件定义了在设置或读取 MQSeries 上下文属性值时要使用的值。</span><span class="sxs-lookup"><span data-stu-id="e1008-109">These files define the values to use when setting or reading MQSeries context property values.</span></span>  
  
 <span data-ttu-id="e1008-110">十六进制字符串值是表示二进制值的字符串。</span><span class="sxs-lookup"><span data-stu-id="e1008-110">Hexadecimal string values are character strings representing binary values.</span></span> <span data-ttu-id="e1008-111">这些值不具有诸如 0x 之类的前缀。</span><span class="sxs-lookup"><span data-stu-id="e1008-111">They do not have a prefix such as 0x.</span></span> <span data-ttu-id="e1008-112">它们包含从 0 到 9 的数字，以及从“a”到“f”或“A”到“F”的字母。</span><span class="sxs-lookup"><span data-stu-id="e1008-112">They contain digits from 0 through 9 and letters from "a" through "f" or "A" through "F".</span></span> <span data-ttu-id="e1008-113">适配器将忽略它们之间的空格。</span><span class="sxs-lookup"><span data-stu-id="e1008-113">The adapter ignores white space in them.</span></span>  
  
 <span data-ttu-id="e1008-114">有关这些属性的详细信息，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="e1008-114">For more information about these properties, see the IBM WebSphere MQ documentation.</span></span>  
  
 <span data-ttu-id="e1008-115">下表显示了可用的消息描述符（MQMD 结构）属性的完整集以及其对应的类型和值：</span><span class="sxs-lookup"><span data-stu-id="e1008-115">The following table shows the complete set of available Message Descriptor (MQMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="e1008-116">“属性”</span><span class="sxs-lookup"><span data-stu-id="e1008-116">Name</span></span>|<span data-ttu-id="e1008-117">类型</span><span class="sxs-lookup"><span data-stu-id="e1008-117">Type</span></span>|<span data-ttu-id="e1008-118">长度</span><span class="sxs-lookup"><span data-stu-id="e1008-118">Length</span></span>|<span data-ttu-id="e1008-119">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e1008-119">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="e1008-120">**MQMD_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="e1008-120">**MQMD_AccountingToken**</span></span>|<span data-ttu-id="e1008-121">string</span><span class="sxs-lookup"><span data-stu-id="e1008-121">string</span></span>|<span data-ttu-id="e1008-122">64</span><span class="sxs-lookup"><span data-stu-id="e1008-122">64</span></span>|<span data-ttu-id="e1008-123">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-123">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-124">**MQMD_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="e1008-124">**MQMD_ApplIdentityData**</span></span>|<span data-ttu-id="e1008-125">string</span><span class="sxs-lookup"><span data-stu-id="e1008-125">string</span></span>|<span data-ttu-id="e1008-126">32</span><span class="sxs-lookup"><span data-stu-id="e1008-126">32</span></span>|<span data-ttu-id="e1008-127">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-127">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-128">**MQMD_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="e1008-128">**MQMD_ApplOriginData**</span></span>|<span data-ttu-id="e1008-129">string</span><span class="sxs-lookup"><span data-stu-id="e1008-129">string</span></span>|<span data-ttu-id="e1008-130">4</span><span class="sxs-lookup"><span data-stu-id="e1008-130">4</span></span>|<span data-ttu-id="e1008-131">String</span><span class="sxs-lookup"><span data-stu-id="e1008-131">String</span></span><br /><br /> <span data-ttu-id="e1008-132">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="e1008-132">**Default:** space</span></span>|  
|<span data-ttu-id="e1008-133">**MQMD_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="e1008-133">**MQMD_BackoutCount**</span></span>|<span data-ttu-id="e1008-134">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-134">unsigned int</span></span>|<span data-ttu-id="e1008-135">4</span><span class="sxs-lookup"><span data-stu-id="e1008-135">4</span></span>|<span data-ttu-id="e1008-136">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-136">Number</span></span><br /><br /> <span data-ttu-id="e1008-137">只读</span><span class="sxs-lookup"><span data-stu-id="e1008-137">Read only</span></span><br /><br /> <span data-ttu-id="e1008-138">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-138">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-139">**MQMD_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="e1008-139">**MQMD_CodedCharSetId**</span></span>|<span data-ttu-id="e1008-140">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-140">unsigned int</span></span>|<span data-ttu-id="e1008-141">4</span><span class="sxs-lookup"><span data-stu-id="e1008-141">4</span></span>|<span data-ttu-id="e1008-142">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-142">Number</span></span><br /><br /> <span data-ttu-id="e1008-143">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-143">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-144">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="e1008-144">**MQMD_CorrelId**</span></span>|<span data-ttu-id="e1008-145">string</span><span class="sxs-lookup"><span data-stu-id="e1008-145">string</span></span>|<span data-ttu-id="e1008-146">48</span><span class="sxs-lookup"><span data-stu-id="e1008-146">48</span></span>|<span data-ttu-id="e1008-147">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-147">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-148">**MQMD_Encoding**</span><span class="sxs-lookup"><span data-stu-id="e1008-148">**MQMD_Encoding**</span></span>|<span data-ttu-id="e1008-149">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-149">unsigned int</span></span>|<span data-ttu-id="e1008-150">4</span><span class="sxs-lookup"><span data-stu-id="e1008-150">4</span></span>|<span data-ttu-id="e1008-151">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-151">Number</span></span><br /><br /> <span data-ttu-id="e1008-152">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-152">Use header file value.</span></span> <span data-ttu-id="e1008-153">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-153">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-154">**MQMD_Expiry**</span><span class="sxs-lookup"><span data-stu-id="e1008-154">**MQMD_Expiry**</span></span>|<span data-ttu-id="e1008-155">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-155">unsigned int</span></span>|<span data-ttu-id="e1008-156">4</span><span class="sxs-lookup"><span data-stu-id="e1008-156">4</span></span>|<span data-ttu-id="e1008-157">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-157">Number</span></span>|  
|<span data-ttu-id="e1008-158">**MQMD_Feedback**</span><span class="sxs-lookup"><span data-stu-id="e1008-158">**MQMD_Feedback**</span></span>|<span data-ttu-id="e1008-159">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-159">unsigned int</span></span>|<span data-ttu-id="e1008-160">4</span><span class="sxs-lookup"><span data-stu-id="e1008-160">4</span></span>|<span data-ttu-id="e1008-161">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-161">Number</span></span><br /><br /> <span data-ttu-id="e1008-162">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-162">Use header file value.</span></span> <span data-ttu-id="e1008-163">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-163">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-164">**MQMD_Format**</span><span class="sxs-lookup"><span data-stu-id="e1008-164">**MQMD_Format**</span></span>|<span data-ttu-id="e1008-165">string</span><span class="sxs-lookup"><span data-stu-id="e1008-165">string</span></span>|<span data-ttu-id="e1008-166">8</span><span class="sxs-lookup"><span data-stu-id="e1008-166">8</span></span>|<span data-ttu-id="e1008-167">String</span><span class="sxs-lookup"><span data-stu-id="e1008-167">String</span></span><br /><br /> <span data-ttu-id="e1008-168">如果此属性设置为 MQXMIT，则应确保 MQXQH 属性具有相应值。</span><span class="sxs-lookup"><span data-stu-id="e1008-168">If set to MQXMIT, makes sure that the MQXQH properties have values.</span></span>|  
|<span data-ttu-id="e1008-169">**MQMD_GroupID**</span><span class="sxs-lookup"><span data-stu-id="e1008-169">**MQMD_GroupID**</span></span>|<span data-ttu-id="e1008-170">string</span><span class="sxs-lookup"><span data-stu-id="e1008-170">string</span></span>|<span data-ttu-id="e1008-171">48</span><span class="sxs-lookup"><span data-stu-id="e1008-171">48</span></span>|<span data-ttu-id="e1008-172">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-172">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-173">**MQMD_MsgFlags**</span><span class="sxs-lookup"><span data-stu-id="e1008-173">**MQMD_MsgFlags**</span></span>|<span data-ttu-id="e1008-174">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-174">unsigned int</span></span>|<span data-ttu-id="e1008-175">4</span><span class="sxs-lookup"><span data-stu-id="e1008-175">4</span></span>|<span data-ttu-id="e1008-176">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-176">Number</span></span><br /><br /> <span data-ttu-id="e1008-177">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-177">Use header file value.</span></span> <span data-ttu-id="e1008-178">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-178">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-179">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="e1008-179">**MQMD_MsgId**</span></span>|<span data-ttu-id="e1008-180">string</span><span class="sxs-lookup"><span data-stu-id="e1008-180">string</span></span>|<span data-ttu-id="e1008-181">48</span><span class="sxs-lookup"><span data-stu-id="e1008-181">48</span></span>|<span data-ttu-id="e1008-182">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-182">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-183">**MQMD_MsgSeqNumber**</span><span class="sxs-lookup"><span data-stu-id="e1008-183">**MQMD_MsgSeqNumber**</span></span>|<span data-ttu-id="e1008-184">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-184">unsigned int</span></span>|<span data-ttu-id="e1008-185">4</span><span class="sxs-lookup"><span data-stu-id="e1008-185">4</span></span>||  
|<span data-ttu-id="e1008-186">**MQMD_MsgType**</span><span class="sxs-lookup"><span data-stu-id="e1008-186">**MQMD_MsgType**</span></span>|<span data-ttu-id="e1008-187">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-187">unsigned int</span></span>|<span data-ttu-id="e1008-188">4</span><span class="sxs-lookup"><span data-stu-id="e1008-188">4</span></span>|<span data-ttu-id="e1008-189">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-189">Number</span></span><br /><br /> <span data-ttu-id="e1008-190">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-190">Use header file value.</span></span>|  
|<span data-ttu-id="e1008-191">**MQMD_Offset**</span><span class="sxs-lookup"><span data-stu-id="e1008-191">**MQMD_Offset**</span></span>|<span data-ttu-id="e1008-192">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-192">unsigned int</span></span>|<span data-ttu-id="e1008-193">4</span><span class="sxs-lookup"><span data-stu-id="e1008-193">4</span></span>||  
|<span data-ttu-id="e1008-194">**MQMD_OriginalLength**</span><span class="sxs-lookup"><span data-stu-id="e1008-194">**MQMD_OriginalLength**</span></span>|<span data-ttu-id="e1008-195">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-195">unsigned int</span></span>|<span data-ttu-id="e1008-196">4</span><span class="sxs-lookup"><span data-stu-id="e1008-196">4</span></span>||  
|<span data-ttu-id="e1008-197">**MQMD_Persistence**</span><span class="sxs-lookup"><span data-stu-id="e1008-197">**MQMD_Persistence**</span></span>|<span data-ttu-id="e1008-198">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-198">unsigned int</span></span>|<span data-ttu-id="e1008-199">4</span><span class="sxs-lookup"><span data-stu-id="e1008-199">4</span></span>|<span data-ttu-id="e1008-200">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-200">Number</span></span><br /><br /> <span data-ttu-id="e1008-201">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-201">Use header file value.</span></span>|  
|<span data-ttu-id="e1008-202">**MQMD_Priority**</span><span class="sxs-lookup"><span data-stu-id="e1008-202">**MQMD_Priority**</span></span>|<span data-ttu-id="e1008-203">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-203">unsigned int</span></span>|<span data-ttu-id="e1008-204">4</span><span class="sxs-lookup"><span data-stu-id="e1008-204">4</span></span>|<span data-ttu-id="e1008-205">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-205">Number</span></span>|  
|<span data-ttu-id="e1008-206">**MQMD_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="e1008-206">**MQMD_PutApplName**</span></span>|<span data-ttu-id="e1008-207">string</span><span class="sxs-lookup"><span data-stu-id="e1008-207">string</span></span>|<span data-ttu-id="e1008-208">28</span><span class="sxs-lookup"><span data-stu-id="e1008-208">28</span></span>|<span data-ttu-id="e1008-209">String</span><span class="sxs-lookup"><span data-stu-id="e1008-209">String</span></span><br /><br /> <span data-ttu-id="e1008-210">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="e1008-210">**Default:** space</span></span>|  
|<span data-ttu-id="e1008-211">**MQMD_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="e1008-211">**MQMD_PutApplType**</span></span>|<span data-ttu-id="e1008-212">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-212">unsigned int</span></span>|<span data-ttu-id="e1008-213">4</span><span class="sxs-lookup"><span data-stu-id="e1008-213">4</span></span>|<span data-ttu-id="e1008-214">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-214">Number</span></span><br /><br /> <span data-ttu-id="e1008-215">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-215">Use header file value.</span></span> <span data-ttu-id="e1008-216">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="e1008-216">**Default:** 0</span></span>|  
|<span data-ttu-id="e1008-217">**MQMD_PutDate**</span><span class="sxs-lookup"><span data-stu-id="e1008-217">**MQMD_PutDate**</span></span>|<span data-ttu-id="e1008-218">string</span><span class="sxs-lookup"><span data-stu-id="e1008-218">string</span></span>|<span data-ttu-id="e1008-219">8</span><span class="sxs-lookup"><span data-stu-id="e1008-219">8</span></span>|<span data-ttu-id="e1008-220">date</span><span class="sxs-lookup"><span data-stu-id="e1008-220">Date</span></span>|  
|<span data-ttu-id="e1008-221">**MQMD_PutTime**</span><span class="sxs-lookup"><span data-stu-id="e1008-221">**MQMD_PutTime**</span></span>|<span data-ttu-id="e1008-222">string</span><span class="sxs-lookup"><span data-stu-id="e1008-222">string</span></span>|<span data-ttu-id="e1008-223">8</span><span class="sxs-lookup"><span data-stu-id="e1008-223">8</span></span>|<span data-ttu-id="e1008-224">Time</span><span class="sxs-lookup"><span data-stu-id="e1008-224">Time</span></span>|  
|<span data-ttu-id="e1008-225">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="e1008-225">**MQMD_ReplyToQ**</span></span>|<span data-ttu-id="e1008-226">string</span><span class="sxs-lookup"><span data-stu-id="e1008-226">string</span></span>|<span data-ttu-id="e1008-227">48</span><span class="sxs-lookup"><span data-stu-id="e1008-227">48</span></span>|<span data-ttu-id="e1008-228">String</span><span class="sxs-lookup"><span data-stu-id="e1008-228">String</span></span><br /><br /> <span data-ttu-id="e1008-229">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="e1008-229">**Default:** space</span></span>|  
|<span data-ttu-id="e1008-230">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="e1008-230">**MQMD_ReplyToQMgr**</span></span>|<span data-ttu-id="e1008-231">string</span><span class="sxs-lookup"><span data-stu-id="e1008-231">string</span></span>|<span data-ttu-id="e1008-232">48</span><span class="sxs-lookup"><span data-stu-id="e1008-232">48</span></span>|<span data-ttu-id="e1008-233">String</span><span class="sxs-lookup"><span data-stu-id="e1008-233">String</span></span><br /><br /> <span data-ttu-id="e1008-234">**默认值：** 空间</span><span class="sxs-lookup"><span data-stu-id="e1008-234">**Default:** space</span></span>|  
|<span data-ttu-id="e1008-235">**MQMD_Report**</span><span class="sxs-lookup"><span data-stu-id="e1008-235">**MQMD_Report**</span></span>|<span data-ttu-id="e1008-236">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-236">unsigned int</span></span>|<span data-ttu-id="e1008-237">4</span><span class="sxs-lookup"><span data-stu-id="e1008-237">4</span></span>|<span data-ttu-id="e1008-238">Number</span><span class="sxs-lookup"><span data-stu-id="e1008-238">Number</span></span><br /><br /> <span data-ttu-id="e1008-239">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="e1008-239">Use header file value.</span></span>|  
|<span data-ttu-id="e1008-240">**MQMD_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="e1008-240">**MQMD_UserIdentifier**</span></span>|<span data-ttu-id="e1008-241">string</span><span class="sxs-lookup"><span data-stu-id="e1008-241">string</span></span>|<span data-ttu-id="e1008-242">12</span><span class="sxs-lookup"><span data-stu-id="e1008-242">12</span></span>|<span data-ttu-id="e1008-243">String</span><span class="sxs-lookup"><span data-stu-id="e1008-243">String</span></span><br /><br /> <span data-ttu-id="e1008-244">当你使用时，包含用户标识符**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="e1008-244">Contains the user identifier when you use the **SSOAffiliateApplication** property.</span></span>|  
  
 <span data-ttu-id="e1008-245">在直接从 MQSeries 传输队列中接收消息时，MQSeries 适配器将设置该传输队列标头属性（MQXQH 数据结构）的格式，并将其放置在其对应的上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="e1008-245">When receiving messages directly from MQSeries transmission queues, the MQSeries adapter formats the transmission queue header properties (the MQXQH data structure) and places them in their corresponding context properties.</span></span> <span data-ttu-id="e1008-246">当直接向 MQSeries 传输队列发送消息，标头属性被格式化，并从相应的上下文属性仅当分配值**MQMD_Format**属性具有值为 mqxmit 时。</span><span class="sxs-lookup"><span data-stu-id="e1008-246">When sending messages directly to MQSeries transmission queues, the header properties are formatted and assigned values from the corresponding context properties only if the **MQMD_Format** property has a value of MQXMIT.</span></span> <span data-ttu-id="e1008-247">下表介绍的属性。</span><span class="sxs-lookup"><span data-stu-id="e1008-247">The following table describes the properties.</span></span>  
  
|<span data-ttu-id="e1008-248">“属性”</span><span class="sxs-lookup"><span data-stu-id="e1008-248">Name</span></span>|<span data-ttu-id="e1008-249">类型</span><span class="sxs-lookup"><span data-stu-id="e1008-249">Type</span></span>|<span data-ttu-id="e1008-250">长度</span><span class="sxs-lookup"><span data-stu-id="e1008-250">Length</span></span>|<span data-ttu-id="e1008-251">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e1008-251">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="e1008-252">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="e1008-252">**MQXQH_RemoteQMgrName**</span></span>|<span data-ttu-id="e1008-253">string</span><span class="sxs-lookup"><span data-stu-id="e1008-253">string</span></span>|<span data-ttu-id="e1008-254">48</span><span class="sxs-lookup"><span data-stu-id="e1008-254">48</span></span>|<span data-ttu-id="e1008-255">string</span><span class="sxs-lookup"><span data-stu-id="e1008-255">string</span></span>|  
|<span data-ttu-id="e1008-256">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="e1008-256">**MQXQH_RemoteQName**</span></span>|<span data-ttu-id="e1008-257">string</span><span class="sxs-lookup"><span data-stu-id="e1008-257">string</span></span>|<span data-ttu-id="e1008-258">48</span><span class="sxs-lookup"><span data-stu-id="e1008-258">48</span></span>|<span data-ttu-id="e1008-259">string</span><span class="sxs-lookup"><span data-stu-id="e1008-259">string</span></span>|  
  
 <span data-ttu-id="e1008-260">与本主题前面部分列出的属性一样，该适配器将按照相同的规则填充以下消息描述符值。</span><span class="sxs-lookup"><span data-stu-id="e1008-260">Together with the properties listed earlier in this topic, the adapter populates the following Message Descriptor values following the same rules.</span></span> <span data-ttu-id="e1008-261">该适配器使用 MQXQH_ 而不是 MQMD_ 作为这些属性名的前缀，否则这些属性将直接映射到在消息描述符表中定义的那些属性：</span><span class="sxs-lookup"><span data-stu-id="e1008-261">The adapter prefixes these property names with MQXQH_ instead of MQMD_, but otherwise they map directly to those properties defined in the Message Descriptor table:</span></span>  
  
- <span data-ttu-id="e1008-262">**MQXQH_MsgDesc_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="e1008-262">**MQXQH_MsgDesc_AccountingToken**</span></span>  
  
- <span data-ttu-id="e1008-263">**MQXQH_MsgDesc_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="e1008-263">**MQXQH_MsgDesc_ApplIdentityData**</span></span>  
  
- <span data-ttu-id="e1008-264">**MQXQH_MsgDesc_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="e1008-264">**MQXQH_MsgDesc_ApplOriginData**</span></span>  
  
- <span data-ttu-id="e1008-265">**MQXQH_MsgDesc_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="e1008-265">**MQXQH_MsgDesc_BackoutCount**</span></span>  
  
- <span data-ttu-id="e1008-266">**MQXQH_MsgDesc_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="e1008-266">**MQXQH_MsgDesc_CodedCharSetId**</span></span>  
  
- <span data-ttu-id="e1008-267">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="e1008-267">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
- <span data-ttu-id="e1008-268">**MQXQH_MsgDesc_Encoding**</span><span class="sxs-lookup"><span data-stu-id="e1008-268">**MQXQH_MsgDesc_Encoding**</span></span>  
  
- <span data-ttu-id="e1008-269">**MQXQH_MsgDesc_Expiry**</span><span class="sxs-lookup"><span data-stu-id="e1008-269">**MQXQH_MsgDesc_Expiry**</span></span>  
  
- <span data-ttu-id="e1008-270">**MQXQH_MsgDesc_Feedback**</span><span class="sxs-lookup"><span data-stu-id="e1008-270">**MQXQH_MsgDesc_Feedback**</span></span>  
  
- <span data-ttu-id="e1008-271">**MQXQH_MsgDesc_Format**</span><span class="sxs-lookup"><span data-stu-id="e1008-271">**MQXQH_MsgDesc_Format**</span></span>  
  
- <span data-ttu-id="e1008-272">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="e1008-272">**MQXQH_MsgDesc_MsgId**</span></span>  
  
- <span data-ttu-id="e1008-273">**MQXQH_MsgDesc_MsgType**</span><span class="sxs-lookup"><span data-stu-id="e1008-273">**MQXQH_MsgDesc_MsgType**</span></span>  
  
- <span data-ttu-id="e1008-274">**MQXQH_MsgDesc_Persistence**</span><span class="sxs-lookup"><span data-stu-id="e1008-274">**MQXQH_MsgDesc_Persistence**</span></span>  
  
- <span data-ttu-id="e1008-275">**MQXQH_MsgDesc_Priority**</span><span class="sxs-lookup"><span data-stu-id="e1008-275">**MQXQH_MsgDesc_Priority**</span></span>  
  
- <span data-ttu-id="e1008-276">**MQXQH_MsgDesc_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="e1008-276">**MQXQH_MsgDesc_PutApplName**</span></span>  
  
- <span data-ttu-id="e1008-277">**MQXQH_MsgDesc_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="e1008-277">**MQXQH_MsgDesc_PutApplType**</span></span>  
  
- <span data-ttu-id="e1008-278">**MQXQH_MsgDesc_PutDate**</span><span class="sxs-lookup"><span data-stu-id="e1008-278">**MQXQH_MsgDesc_PutDate**</span></span>  
  
- <span data-ttu-id="e1008-279">**MQXQH_MsgDesc_PutTime**</span><span class="sxs-lookup"><span data-stu-id="e1008-279">**MQXQH_MsgDesc_PutTime**</span></span>  
  
- <span data-ttu-id="e1008-280">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="e1008-280">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
- <span data-ttu-id="e1008-281">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="e1008-281">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
- <span data-ttu-id="e1008-282">**MQXQH_MsgDesc_Report**</span><span class="sxs-lookup"><span data-stu-id="e1008-282">**MQXQH_MsgDesc_Report**</span></span>  
  
- <span data-ttu-id="e1008-283">**MQXQH_MsgDesc_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="e1008-283">**MQXQH_MsgDesc_UserIdentifier**</span></span>  
  
  <span data-ttu-id="e1008-284">属性架构中还包含与 MQSeries 相关的其他属性，这些属性可在筛选表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="e1008-284">There are additional MQSeries-related properties included in the property schema and available for use in filtering expressions.</span></span> <span data-ttu-id="e1008-285">下表列出了这些属性：</span><span class="sxs-lookup"><span data-stu-id="e1008-285">The following table lists these properties.</span></span>  
  
|<span data-ttu-id="e1008-286">“属性”</span><span class="sxs-lookup"><span data-stu-id="e1008-286">Name</span></span>|<span data-ttu-id="e1008-287">类型</span><span class="sxs-lookup"><span data-stu-id="e1008-287">Type</span></span>|<span data-ttu-id="e1008-288">长度</span><span class="sxs-lookup"><span data-stu-id="e1008-288">Length</span></span>|<span data-ttu-id="e1008-289">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e1008-289">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="e1008-290">**MQCIH_AbendCode**</span><span class="sxs-lookup"><span data-stu-id="e1008-290">**MQCIH_AbendCode**</span></span>|<span data-ttu-id="e1008-291">string</span><span class="sxs-lookup"><span data-stu-id="e1008-291">string</span></span>|<span data-ttu-id="e1008-292">4</span><span class="sxs-lookup"><span data-stu-id="e1008-292">4</span></span>||  
|<span data-ttu-id="e1008-293">**MQCIH_ADSDescriptor**</span><span class="sxs-lookup"><span data-stu-id="e1008-293">**MQCIH_ADSDescriptor**</span></span>|<span data-ttu-id="e1008-294">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-294">unsigned int</span></span>|<span data-ttu-id="e1008-295">4</span><span class="sxs-lookup"><span data-stu-id="e1008-295">4</span></span>||  
|<span data-ttu-id="e1008-296">**MQCIH_AttentionId**</span><span class="sxs-lookup"><span data-stu-id="e1008-296">**MQCIH_AttentionId**</span></span>|<span data-ttu-id="e1008-297">string</span><span class="sxs-lookup"><span data-stu-id="e1008-297">string</span></span>|<span data-ttu-id="e1008-298">4</span><span class="sxs-lookup"><span data-stu-id="e1008-298">4</span></span>||  
|<span data-ttu-id="e1008-299">**MQCIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="e1008-299">**MQCIH_Authenticator**</span></span>|<span data-ttu-id="e1008-300">string</span><span class="sxs-lookup"><span data-stu-id="e1008-300">string</span></span>|<span data-ttu-id="e1008-301">8</span><span class="sxs-lookup"><span data-stu-id="e1008-301">8</span></span>|<span data-ttu-id="e1008-302">当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="e1008-302">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="e1008-303">**注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="e1008-303">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="e1008-304">**MQCIH_CancelCode**</span><span class="sxs-lookup"><span data-stu-id="e1008-304">**MQCIH_CancelCode**</span></span>|<span data-ttu-id="e1008-305">string</span><span class="sxs-lookup"><span data-stu-id="e1008-305">string</span></span>|<span data-ttu-id="e1008-306">4</span><span class="sxs-lookup"><span data-stu-id="e1008-306">4</span></span>||  
|<span data-ttu-id="e1008-307">**MQCIH_CompCode**</span><span class="sxs-lookup"><span data-stu-id="e1008-307">**MQCIH_CompCode**</span></span>|<span data-ttu-id="e1008-308">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-308">unsigned int</span></span>|<span data-ttu-id="e1008-309">4</span><span class="sxs-lookup"><span data-stu-id="e1008-309">4</span></span>||  
|<span data-ttu-id="e1008-310">**MQCIH_ConversationalTask**</span><span class="sxs-lookup"><span data-stu-id="e1008-310">**MQCIH_ConversationalTask**</span></span>|<span data-ttu-id="e1008-311">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-311">unsigned int</span></span>|<span data-ttu-id="e1008-312">4</span><span class="sxs-lookup"><span data-stu-id="e1008-312">4</span></span>||  
|<span data-ttu-id="e1008-313">**MQCIH_CursorPosition**</span><span class="sxs-lookup"><span data-stu-id="e1008-313">**MQCIH_CursorPosition**</span></span>|<span data-ttu-id="e1008-314">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-314">unsigned int</span></span>|<span data-ttu-id="e1008-315">4</span><span class="sxs-lookup"><span data-stu-id="e1008-315">4</span></span>||  
|<span data-ttu-id="e1008-316">**MQCIH_ErrorOffset**</span><span class="sxs-lookup"><span data-stu-id="e1008-316">**MQCIH_ErrorOffset**</span></span>|<span data-ttu-id="e1008-317">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-317">unsigned int</span></span>|<span data-ttu-id="e1008-318">4</span><span class="sxs-lookup"><span data-stu-id="e1008-318">4</span></span>||  
|<span data-ttu-id="e1008-319">**MQCIH_Facility**</span><span class="sxs-lookup"><span data-stu-id="e1008-319">**MQCIH_Facility**</span></span>|<span data-ttu-id="e1008-320">string</span><span class="sxs-lookup"><span data-stu-id="e1008-320">string</span></span>|<span data-ttu-id="e1008-321">16</span><span class="sxs-lookup"><span data-stu-id="e1008-321">16</span></span>|<span data-ttu-id="e1008-322">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-322">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-323">**MQCIH_FacilityKeepTime**</span><span class="sxs-lookup"><span data-stu-id="e1008-323">**MQCIH_FacilityKeepTime**</span></span>|<span data-ttu-id="e1008-324">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-324">unsigned int</span></span>|<span data-ttu-id="e1008-325">4</span><span class="sxs-lookup"><span data-stu-id="e1008-325">4</span></span>||  
|<span data-ttu-id="e1008-326">**MQCIH_FacilityLike**</span><span class="sxs-lookup"><span data-stu-id="e1008-326">**MQCIH_FacilityLike**</span></span>|<span data-ttu-id="e1008-327">string</span><span class="sxs-lookup"><span data-stu-id="e1008-327">string</span></span>|<span data-ttu-id="e1008-328">4</span><span class="sxs-lookup"><span data-stu-id="e1008-328">4</span></span>||  
|<span data-ttu-id="e1008-329">**MQCIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="e1008-329">**MQCIH_Flags**</span></span>|<span data-ttu-id="e1008-330">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-330">unsigned int</span></span>|<span data-ttu-id="e1008-331">4</span><span class="sxs-lookup"><span data-stu-id="e1008-331">4</span></span>||  
|<span data-ttu-id="e1008-332">**MQCIH_Format**</span><span class="sxs-lookup"><span data-stu-id="e1008-332">**MQCIH_Format**</span></span>|<span data-ttu-id="e1008-333">string</span><span class="sxs-lookup"><span data-stu-id="e1008-333">string</span></span>|||  
|<span data-ttu-id="e1008-334">**MQCIH_Function**</span><span class="sxs-lookup"><span data-stu-id="e1008-334">**MQCIH_Function**</span></span>|<span data-ttu-id="e1008-335">string</span><span class="sxs-lookup"><span data-stu-id="e1008-335">string</span></span>|<span data-ttu-id="e1008-336">4</span><span class="sxs-lookup"><span data-stu-id="e1008-336">4</span></span>||  
|<span data-ttu-id="e1008-337">**MQCIH_GetWaitInterval**</span><span class="sxs-lookup"><span data-stu-id="e1008-337">**MQCIH_GetWaitInterval**</span></span>|<span data-ttu-id="e1008-338">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-338">unsigned int</span></span>|<span data-ttu-id="e1008-339">4</span><span class="sxs-lookup"><span data-stu-id="e1008-339">4</span></span>||  
|<span data-ttu-id="e1008-340">**MQCIH_LinkType**</span><span class="sxs-lookup"><span data-stu-id="e1008-340">**MQCIH_LinkType**</span></span>|<span data-ttu-id="e1008-341">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-341">unsigned int</span></span>|<span data-ttu-id="e1008-342">4</span><span class="sxs-lookup"><span data-stu-id="e1008-342">4</span></span>||  
|<span data-ttu-id="e1008-343">**MQCIH_NextTransactionId**</span><span class="sxs-lookup"><span data-stu-id="e1008-343">**MQCIH_NextTransactionId**</span></span>|<span data-ttu-id="e1008-344">string</span><span class="sxs-lookup"><span data-stu-id="e1008-344">string</span></span>|<span data-ttu-id="e1008-345">4</span><span class="sxs-lookup"><span data-stu-id="e1008-345">4</span></span>||  
|<span data-ttu-id="e1008-346">**MQCIH_OutputDataLength**</span><span class="sxs-lookup"><span data-stu-id="e1008-346">**MQCIH_OutputDataLength**</span></span>|<span data-ttu-id="e1008-347">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-347">unsigned int</span></span>|<span data-ttu-id="e1008-348">4</span><span class="sxs-lookup"><span data-stu-id="e1008-348">4</span></span>||  
|<span data-ttu-id="e1008-349">**MQCIH_Reason**</span><span class="sxs-lookup"><span data-stu-id="e1008-349">**MQCIH_Reason**</span></span>|<span data-ttu-id="e1008-350">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-350">unsigned int</span></span>|<span data-ttu-id="e1008-351">4</span><span class="sxs-lookup"><span data-stu-id="e1008-351">4</span></span>||  
|<span data-ttu-id="e1008-352">**MQCIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="e1008-352">**MQCIH_ReplyToFormat**</span></span>|<span data-ttu-id="e1008-353">string</span><span class="sxs-lookup"><span data-stu-id="e1008-353">string</span></span>|||  
|<span data-ttu-id="e1008-354">**MQCIH_ReturnCode**</span><span class="sxs-lookup"><span data-stu-id="e1008-354">**MQCIH_ReturnCode**</span></span>|<span data-ttu-id="e1008-355">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-355">unsigned int</span></span>|<span data-ttu-id="e1008-356">4</span><span class="sxs-lookup"><span data-stu-id="e1008-356">4</span></span>||  
|<span data-ttu-id="e1008-357">**MQCIH_StartCode**</span><span class="sxs-lookup"><span data-stu-id="e1008-357">**MQCIH_StartCode**</span></span>|<span data-ttu-id="e1008-358">string</span><span class="sxs-lookup"><span data-stu-id="e1008-358">string</span></span>|<span data-ttu-id="e1008-359">4</span><span class="sxs-lookup"><span data-stu-id="e1008-359">4</span></span>||  
|<span data-ttu-id="e1008-360">**MQCIH_TaskEndStatus**</span><span class="sxs-lookup"><span data-stu-id="e1008-360">**MQCIH_TaskEndStatus**</span></span>|<span data-ttu-id="e1008-361">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-361">unsigned int</span></span>|<span data-ttu-id="e1008-362">4</span><span class="sxs-lookup"><span data-stu-id="e1008-362">4</span></span>||  
|<span data-ttu-id="e1008-363">**MQCIH_TransactionId**</span><span class="sxs-lookup"><span data-stu-id="e1008-363">**MQCIH_TransactionId**</span></span>|<span data-ttu-id="e1008-364">string</span><span class="sxs-lookup"><span data-stu-id="e1008-364">string</span></span>|<span data-ttu-id="e1008-365">4</span><span class="sxs-lookup"><span data-stu-id="e1008-365">4</span></span>||  
|<span data-ttu-id="e1008-366">**MQCIH_UOWControl**</span><span class="sxs-lookup"><span data-stu-id="e1008-366">**MQCIH_UOWControl**</span></span>|<span data-ttu-id="e1008-367">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-367">unsigned int</span></span>|<span data-ttu-id="e1008-368">4</span><span class="sxs-lookup"><span data-stu-id="e1008-368">4</span></span>||  
|<span data-ttu-id="e1008-369">**MQIIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="e1008-369">**MQIIH_Authenticator**</span></span>|<span data-ttu-id="e1008-370">string</span><span class="sxs-lookup"><span data-stu-id="e1008-370">string</span></span>|<span data-ttu-id="e1008-371">8</span><span class="sxs-lookup"><span data-stu-id="e1008-371">8</span></span>|<span data-ttu-id="e1008-372">当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="e1008-372">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="e1008-373">**注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="e1008-373">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="e1008-374">**MQIIH_CommitMode**</span><span class="sxs-lookup"><span data-stu-id="e1008-374">**MQIIH_CommitMode**</span></span>|<span data-ttu-id="e1008-375">string</span><span class="sxs-lookup"><span data-stu-id="e1008-375">string</span></span>|||  
|<span data-ttu-id="e1008-376">**MQIIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="e1008-376">**MQIIH_Flags**</span></span>|<span data-ttu-id="e1008-377">unsigned int</span><span class="sxs-lookup"><span data-stu-id="e1008-377">unsigned int</span></span>|<span data-ttu-id="e1008-378">4</span><span class="sxs-lookup"><span data-stu-id="e1008-378">4</span></span>||  
|<span data-ttu-id="e1008-379">**MQIIH_Format**</span><span class="sxs-lookup"><span data-stu-id="e1008-379">**MQIIH_Format**</span></span>|<span data-ttu-id="e1008-380">string</span><span class="sxs-lookup"><span data-stu-id="e1008-380">string</span></span>|||  
|<span data-ttu-id="e1008-381">**MQIIH_LTermOverride**</span><span class="sxs-lookup"><span data-stu-id="e1008-381">**MQIIH_LTermOverride**</span></span>|<span data-ttu-id="e1008-382">string</span><span class="sxs-lookup"><span data-stu-id="e1008-382">string</span></span>|<span data-ttu-id="e1008-383">8</span><span class="sxs-lookup"><span data-stu-id="e1008-383">8</span></span>||  
|<span data-ttu-id="e1008-384">**MQIIH_MFSMapName**</span><span class="sxs-lookup"><span data-stu-id="e1008-384">**MQIIH_MFSMapName**</span></span>|<span data-ttu-id="e1008-385">string</span><span class="sxs-lookup"><span data-stu-id="e1008-385">string</span></span>|<span data-ttu-id="e1008-386">8</span><span class="sxs-lookup"><span data-stu-id="e1008-386">8</span></span>||  
|<span data-ttu-id="e1008-387">**MQIIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="e1008-387">**MQIIH_ReplyToFormat**</span></span>|<span data-ttu-id="e1008-388">string</span><span class="sxs-lookup"><span data-stu-id="e1008-388">string</span></span>|||  
|<span data-ttu-id="e1008-389">**MQIIH_SecurityScope**</span><span class="sxs-lookup"><span data-stu-id="e1008-389">**MQIIH_SecurityScope**</span></span>|<span data-ttu-id="e1008-390">string</span><span class="sxs-lookup"><span data-stu-id="e1008-390">string</span></span>|||  
|<span data-ttu-id="e1008-391">**MQIIH_TranInstanceId**</span><span class="sxs-lookup"><span data-stu-id="e1008-391">**MQIIH_TranInstanceId**</span></span>|<span data-ttu-id="e1008-392">string</span><span class="sxs-lookup"><span data-stu-id="e1008-392">string</span></span>|<span data-ttu-id="e1008-393">32</span><span class="sxs-lookup"><span data-stu-id="e1008-393">32</span></span>|<span data-ttu-id="e1008-394">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="e1008-394">Hexadecimal string</span></span>|  
|<span data-ttu-id="e1008-395">**MQIIH_TranState**</span><span class="sxs-lookup"><span data-stu-id="e1008-395">**MQIIH_TranState**</span></span>|<span data-ttu-id="e1008-396">string</span><span class="sxs-lookup"><span data-stu-id="e1008-396">string</span></span>|||  
  
## <a name="see-also"></a><span data-ttu-id="e1008-397">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1008-397">See Also</span></span>  
 <span data-ttu-id="e1008-398">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e1008-398">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="e1008-399">[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1008-399">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="e1008-400">属性的数据类型转换</span><span class="sxs-lookup"><span data-stu-id="e1008-400">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)