---
title: "MQSeries 上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27309379fac2c4821251f27fd2aa5a6e9d59418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-context-properties"></a><span data-ttu-id="3161c-102">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="3161c-102">MQSeries Context Properties</span></span>
<span data-ttu-id="3161c-103">MQSeries 适配器提供了一组特定于 MQSeries 的上下文属性以供您在应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="3161c-103">The MQSeries adapter provides a set of context properties, specific to MQSeries, for use in your applications.</span></span> <span data-ttu-id="3161c-104">您可以在筛选表达式和业务流程中使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="3161c-104">You can use these properties in filter expressions and in your orchestrations.</span></span>  
  
 <span data-ttu-id="3161c-105">对于以绑定到 MQSeries 适配器的发送端口为目标的消息，若要将 MQSeries 上下文属性分配给此类消息，请使用消息赋值运算符，并在 MQSeries 命名空间中指定可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="3161c-105">To assign MQSeries context properties to a message destined to a send port that is bound to the MQSeries adapter, use the message assignment operator and specify one of the available context properties in the MQSeries namespace.</span></span>  
  
 <span data-ttu-id="3161c-106">以下是一种设置 MQSeries **MQMD_UserIdentifier**属性：</span><span class="sxs-lookup"><span data-stu-id="3161c-106">The following is an example of setting the MQSeries **MQMD_UserIdentifier** property:</span></span>  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 <span data-ttu-id="3161c-107">必须从 IBM MQSeries SDK 所附带的 C 编程语言头文件中获得枚举值。</span><span class="sxs-lookup"><span data-stu-id="3161c-107">You must obtain enumerated values from the C programming language header files included with the IBM MQSeries SDK.</span></span> <span data-ttu-id="3161c-108">在 Program Files\IBM\WebSphere MQ\Tools\c\include 文件夹中可找到这些文件。</span><span class="sxs-lookup"><span data-stu-id="3161c-108">You can find these files in the Program Files\IBM\WebSphere MQ\Tools\c\include folder.</span></span> <span data-ttu-id="3161c-109">这些文件定义了在设置或读取 MQSeries 上下文属性值时要使用的值。</span><span class="sxs-lookup"><span data-stu-id="3161c-109">These files define the values to use when setting or reading MQSeries context property values.</span></span>  
  
 <span data-ttu-id="3161c-110">十六进制字符串值是表示二进制值的字符串。</span><span class="sxs-lookup"><span data-stu-id="3161c-110">Hexadecimal string values are character strings representing binary values.</span></span> <span data-ttu-id="3161c-111">这些值不具有诸如 0x 之类的前缀。</span><span class="sxs-lookup"><span data-stu-id="3161c-111">They do not have a prefix such as 0x.</span></span> <span data-ttu-id="3161c-112">它们包含从 0 到 9 的数字，以及从“a”到“f”或“A”到“F”的字母。</span><span class="sxs-lookup"><span data-stu-id="3161c-112">They contain digits from 0 through 9 and letters from "a" through "f" or "A" through "F".</span></span> <span data-ttu-id="3161c-113">适配器将忽略它们之间的空格。</span><span class="sxs-lookup"><span data-stu-id="3161c-113">The adapter ignores white space in them.</span></span>  
  
 <span data-ttu-id="3161c-114">有关这些属性的详细信息，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="3161c-114">For more information about these properties, see the IBM WebSphere MQ documentation.</span></span>  
  
 <span data-ttu-id="3161c-115">下表显示了可用的消息描述符（MQMD 结构）属性的完整集以及其对应的类型和值：</span><span class="sxs-lookup"><span data-stu-id="3161c-115">The following table shows the complete set of available Message Descriptor (MQMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="3161c-116">Name</span><span class="sxs-lookup"><span data-stu-id="3161c-116">Name</span></span>|<span data-ttu-id="3161c-117">类型</span><span class="sxs-lookup"><span data-stu-id="3161c-117">Type</span></span>|<span data-ttu-id="3161c-118">长度</span><span class="sxs-lookup"><span data-stu-id="3161c-118">Length</span></span>|<span data-ttu-id="3161c-119">值</span><span class="sxs-lookup"><span data-stu-id="3161c-119">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="3161c-120">**MQMD_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="3161c-120">**MQMD_AccountingToken**</span></span>|<span data-ttu-id="3161c-121">string</span><span class="sxs-lookup"><span data-stu-id="3161c-121">string</span></span>|<span data-ttu-id="3161c-122">64</span><span class="sxs-lookup"><span data-stu-id="3161c-122">64</span></span>|<span data-ttu-id="3161c-123">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-123">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-124">**MQMD_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="3161c-124">**MQMD_ApplIdentityData**</span></span>|<span data-ttu-id="3161c-125">string</span><span class="sxs-lookup"><span data-stu-id="3161c-125">string</span></span>|<span data-ttu-id="3161c-126">32</span><span class="sxs-lookup"><span data-stu-id="3161c-126">32</span></span>|<span data-ttu-id="3161c-127">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-127">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-128">**MQMD_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="3161c-128">**MQMD_ApplOriginData**</span></span>|<span data-ttu-id="3161c-129">string</span><span class="sxs-lookup"><span data-stu-id="3161c-129">string</span></span>|<span data-ttu-id="3161c-130">4</span><span class="sxs-lookup"><span data-stu-id="3161c-130">4</span></span>|<span data-ttu-id="3161c-131">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-131">String</span></span><br /><br /> <span data-ttu-id="3161c-132">**默认值：**空间</span><span class="sxs-lookup"><span data-stu-id="3161c-132">**Default:** space</span></span>|  
|<span data-ttu-id="3161c-133">**MQMD_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="3161c-133">**MQMD_BackoutCount**</span></span>|<span data-ttu-id="3161c-134">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-134">unsigned int</span></span>|<span data-ttu-id="3161c-135">4</span><span class="sxs-lookup"><span data-stu-id="3161c-135">4</span></span>|<span data-ttu-id="3161c-136">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-136">Number</span></span><br /><br /> <span data-ttu-id="3161c-137">只读</span><span class="sxs-lookup"><span data-stu-id="3161c-137">Read only</span></span><br /><br /> <span data-ttu-id="3161c-138">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-138">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-139">**MQMD_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="3161c-139">**MQMD_CodedCharSetId**</span></span>|<span data-ttu-id="3161c-140">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-140">unsigned int</span></span>|<span data-ttu-id="3161c-141">4</span><span class="sxs-lookup"><span data-stu-id="3161c-141">4</span></span>|<span data-ttu-id="3161c-142">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-142">Number</span></span><br /><br /> <span data-ttu-id="3161c-143">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-143">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-144">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="3161c-144">**MQMD_CorrelId**</span></span>|<span data-ttu-id="3161c-145">string</span><span class="sxs-lookup"><span data-stu-id="3161c-145">string</span></span>|<span data-ttu-id="3161c-146">48</span><span class="sxs-lookup"><span data-stu-id="3161c-146">48</span></span>|<span data-ttu-id="3161c-147">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-147">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-148">**MQMD_Encoding**</span><span class="sxs-lookup"><span data-stu-id="3161c-148">**MQMD_Encoding**</span></span>|<span data-ttu-id="3161c-149">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-149">unsigned int</span></span>|<span data-ttu-id="3161c-150">4</span><span class="sxs-lookup"><span data-stu-id="3161c-150">4</span></span>|<span data-ttu-id="3161c-151">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-151">Number</span></span><br /><br /> <span data-ttu-id="3161c-152">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-152">Use header file value.</span></span> <span data-ttu-id="3161c-153">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-153">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-154">**MQMD_Expiry**</span><span class="sxs-lookup"><span data-stu-id="3161c-154">**MQMD_Expiry**</span></span>|<span data-ttu-id="3161c-155">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-155">unsigned int</span></span>|<span data-ttu-id="3161c-156">4</span><span class="sxs-lookup"><span data-stu-id="3161c-156">4</span></span>|<span data-ttu-id="3161c-157">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-157">Number</span></span>|  
|<span data-ttu-id="3161c-158">**MQMD_Feedback**</span><span class="sxs-lookup"><span data-stu-id="3161c-158">**MQMD_Feedback**</span></span>|<span data-ttu-id="3161c-159">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-159">unsigned int</span></span>|<span data-ttu-id="3161c-160">4</span><span class="sxs-lookup"><span data-stu-id="3161c-160">4</span></span>|<span data-ttu-id="3161c-161">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-161">Number</span></span><br /><br /> <span data-ttu-id="3161c-162">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-162">Use header file value.</span></span> <span data-ttu-id="3161c-163">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-163">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-164">**MQMD_Format**</span><span class="sxs-lookup"><span data-stu-id="3161c-164">**MQMD_Format**</span></span>|<span data-ttu-id="3161c-165">string</span><span class="sxs-lookup"><span data-stu-id="3161c-165">string</span></span>|<span data-ttu-id="3161c-166">8</span><span class="sxs-lookup"><span data-stu-id="3161c-166">8</span></span>|<span data-ttu-id="3161c-167">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-167">String</span></span><br /><br /> <span data-ttu-id="3161c-168">如果此属性设置为 MQXMIT，则应确保 MQXQH 属性具有相应值。</span><span class="sxs-lookup"><span data-stu-id="3161c-168">If set to MQXMIT, makes sure that the MQXQH properties have values.</span></span>|  
|<span data-ttu-id="3161c-169">**MQMD_GroupID**</span><span class="sxs-lookup"><span data-stu-id="3161c-169">**MQMD_GroupID**</span></span>|<span data-ttu-id="3161c-170">string</span><span class="sxs-lookup"><span data-stu-id="3161c-170">string</span></span>|<span data-ttu-id="3161c-171">48</span><span class="sxs-lookup"><span data-stu-id="3161c-171">48</span></span>|<span data-ttu-id="3161c-172">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-172">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-173">**MQMD_MsgFlags**</span><span class="sxs-lookup"><span data-stu-id="3161c-173">**MQMD_MsgFlags**</span></span>|<span data-ttu-id="3161c-174">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-174">unsigned int</span></span>|<span data-ttu-id="3161c-175">4</span><span class="sxs-lookup"><span data-stu-id="3161c-175">4</span></span>|<span data-ttu-id="3161c-176">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-176">Number</span></span><br /><br /> <span data-ttu-id="3161c-177">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-177">Use header file value.</span></span> <span data-ttu-id="3161c-178">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-178">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-179">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="3161c-179">**MQMD_MsgId**</span></span>|<span data-ttu-id="3161c-180">string</span><span class="sxs-lookup"><span data-stu-id="3161c-180">string</span></span>|<span data-ttu-id="3161c-181">48</span><span class="sxs-lookup"><span data-stu-id="3161c-181">48</span></span>|<span data-ttu-id="3161c-182">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-182">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-183">**MQMD_MsgSeqNumber**</span><span class="sxs-lookup"><span data-stu-id="3161c-183">**MQMD_MsgSeqNumber**</span></span>|<span data-ttu-id="3161c-184">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-184">unsigned int</span></span>|<span data-ttu-id="3161c-185">4</span><span class="sxs-lookup"><span data-stu-id="3161c-185">4</span></span>||  
|<span data-ttu-id="3161c-186">**MQMD_MsgType**</span><span class="sxs-lookup"><span data-stu-id="3161c-186">**MQMD_MsgType**</span></span>|<span data-ttu-id="3161c-187">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-187">unsigned int</span></span>|<span data-ttu-id="3161c-188">4</span><span class="sxs-lookup"><span data-stu-id="3161c-188">4</span></span>|<span data-ttu-id="3161c-189">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-189">Number</span></span><br /><br /> <span data-ttu-id="3161c-190">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-190">Use header file value.</span></span>|  
|<span data-ttu-id="3161c-191">**MQMD_Offset**</span><span class="sxs-lookup"><span data-stu-id="3161c-191">**MQMD_Offset**</span></span>|<span data-ttu-id="3161c-192">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-192">unsigned int</span></span>|<span data-ttu-id="3161c-193">4</span><span class="sxs-lookup"><span data-stu-id="3161c-193">4</span></span>||  
|<span data-ttu-id="3161c-194">**MQMD_OriginalLength**</span><span class="sxs-lookup"><span data-stu-id="3161c-194">**MQMD_OriginalLength**</span></span>|<span data-ttu-id="3161c-195">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-195">unsigned int</span></span>|<span data-ttu-id="3161c-196">4</span><span class="sxs-lookup"><span data-stu-id="3161c-196">4</span></span>||  
|<span data-ttu-id="3161c-197">**MQMD_Persistence**</span><span class="sxs-lookup"><span data-stu-id="3161c-197">**MQMD_Persistence**</span></span>|<span data-ttu-id="3161c-198">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-198">unsigned int</span></span>|<span data-ttu-id="3161c-199">4</span><span class="sxs-lookup"><span data-stu-id="3161c-199">4</span></span>|<span data-ttu-id="3161c-200">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-200">Number</span></span><br /><br /> <span data-ttu-id="3161c-201">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-201">Use header file value.</span></span>|  
|<span data-ttu-id="3161c-202">**MQMD_Priority**</span><span class="sxs-lookup"><span data-stu-id="3161c-202">**MQMD_Priority**</span></span>|<span data-ttu-id="3161c-203">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-203">unsigned int</span></span>|<span data-ttu-id="3161c-204">4</span><span class="sxs-lookup"><span data-stu-id="3161c-204">4</span></span>|<span data-ttu-id="3161c-205">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-205">Number</span></span>|  
|<span data-ttu-id="3161c-206">**MQMD_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="3161c-206">**MQMD_PutApplName**</span></span>|<span data-ttu-id="3161c-207">string</span><span class="sxs-lookup"><span data-stu-id="3161c-207">string</span></span>|<span data-ttu-id="3161c-208">28</span><span class="sxs-lookup"><span data-stu-id="3161c-208">28</span></span>|<span data-ttu-id="3161c-209">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-209">String</span></span><br /><br /> <span data-ttu-id="3161c-210">**默认值：**空间</span><span class="sxs-lookup"><span data-stu-id="3161c-210">**Default:** space</span></span>|  
|<span data-ttu-id="3161c-211">**MQMD_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="3161c-211">**MQMD_PutApplType**</span></span>|<span data-ttu-id="3161c-212">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-212">unsigned int</span></span>|<span data-ttu-id="3161c-213">4</span><span class="sxs-lookup"><span data-stu-id="3161c-213">4</span></span>|<span data-ttu-id="3161c-214">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-214">Number</span></span><br /><br /> <span data-ttu-id="3161c-215">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-215">Use header file value.</span></span> <span data-ttu-id="3161c-216">**默认值：** 0</span><span class="sxs-lookup"><span data-stu-id="3161c-216">**Default:** 0</span></span>|  
|<span data-ttu-id="3161c-217">**MQMD_PutDate**</span><span class="sxs-lookup"><span data-stu-id="3161c-217">**MQMD_PutDate**</span></span>|<span data-ttu-id="3161c-218">string</span><span class="sxs-lookup"><span data-stu-id="3161c-218">string</span></span>|<span data-ttu-id="3161c-219">8</span><span class="sxs-lookup"><span data-stu-id="3161c-219">8</span></span>|<span data-ttu-id="3161c-220">日期</span><span class="sxs-lookup"><span data-stu-id="3161c-220">Date</span></span>|  
|<span data-ttu-id="3161c-221">**MQMD_PutTime**</span><span class="sxs-lookup"><span data-stu-id="3161c-221">**MQMD_PutTime**</span></span>|<span data-ttu-id="3161c-222">string</span><span class="sxs-lookup"><span data-stu-id="3161c-222">string</span></span>|<span data-ttu-id="3161c-223">8</span><span class="sxs-lookup"><span data-stu-id="3161c-223">8</span></span>|<span data-ttu-id="3161c-224">Time</span><span class="sxs-lookup"><span data-stu-id="3161c-224">Time</span></span>|  
|<span data-ttu-id="3161c-225">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="3161c-225">**MQMD_ReplyToQ**</span></span>|<span data-ttu-id="3161c-226">string</span><span class="sxs-lookup"><span data-stu-id="3161c-226">string</span></span>|<span data-ttu-id="3161c-227">48</span><span class="sxs-lookup"><span data-stu-id="3161c-227">48</span></span>|<span data-ttu-id="3161c-228">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-228">String</span></span><br /><br /> <span data-ttu-id="3161c-229">**默认值：**空间</span><span class="sxs-lookup"><span data-stu-id="3161c-229">**Default:** space</span></span>|  
|<span data-ttu-id="3161c-230">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="3161c-230">**MQMD_ReplyToQMgr**</span></span>|<span data-ttu-id="3161c-231">string</span><span class="sxs-lookup"><span data-stu-id="3161c-231">string</span></span>|<span data-ttu-id="3161c-232">48</span><span class="sxs-lookup"><span data-stu-id="3161c-232">48</span></span>|<span data-ttu-id="3161c-233">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-233">String</span></span><br /><br /> <span data-ttu-id="3161c-234">**默认值：**空间</span><span class="sxs-lookup"><span data-stu-id="3161c-234">**Default:** space</span></span>|  
|<span data-ttu-id="3161c-235">**MQMD_Report**</span><span class="sxs-lookup"><span data-stu-id="3161c-235">**MQMD_Report**</span></span>|<span data-ttu-id="3161c-236">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-236">unsigned int</span></span>|<span data-ttu-id="3161c-237">4</span><span class="sxs-lookup"><span data-stu-id="3161c-237">4</span></span>|<span data-ttu-id="3161c-238">Number</span><span class="sxs-lookup"><span data-stu-id="3161c-238">Number</span></span><br /><br /> <span data-ttu-id="3161c-239">使用头文件值。</span><span class="sxs-lookup"><span data-stu-id="3161c-239">Use header file value.</span></span>|  
|<span data-ttu-id="3161c-240">**MQMD_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="3161c-240">**MQMD_UserIdentifier**</span></span>|<span data-ttu-id="3161c-241">string</span><span class="sxs-lookup"><span data-stu-id="3161c-241">string</span></span>|<span data-ttu-id="3161c-242">12</span><span class="sxs-lookup"><span data-stu-id="3161c-242">12</span></span>|<span data-ttu-id="3161c-243">字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-243">String</span></span><br /><br /> <span data-ttu-id="3161c-244">当你使用包含用户标识符**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="3161c-244">Contains the user identifier when you use the **SSOAffiliateApplication** property.</span></span>|  
  
 <span data-ttu-id="3161c-245">在直接从 MQSeries 传输队列中接收消息时，MQSeries 适配器将设置该传输队列标头属性（MQXQH 数据结构）的格式，并将其放置在其对应的上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="3161c-245">When receiving messages directly from MQSeries transmission queues, the MQSeries adapter formats the transmission queue header properties (the MQXQH data structure) and places them in their corresponding context properties.</span></span> <span data-ttu-id="3161c-246">当直接向 MQSeries 传输队列发送消息，格式化和从相应的上下文属性仅当分配值的标头属性**MQMD_Format**属性具有 MQXMIT 的值。</span><span class="sxs-lookup"><span data-stu-id="3161c-246">When sending messages directly to MQSeries transmission queues, the header properties are formatted and assigned values from the corresponding context properties only if the **MQMD_Format** property has a value of MQXMIT.</span></span> <span data-ttu-id="3161c-247">下表介绍的属性。</span><span class="sxs-lookup"><span data-stu-id="3161c-247">The following table describes the properties.</span></span>  
  
|<span data-ttu-id="3161c-248">Name</span><span class="sxs-lookup"><span data-stu-id="3161c-248">Name</span></span>|<span data-ttu-id="3161c-249">类型</span><span class="sxs-lookup"><span data-stu-id="3161c-249">Type</span></span>|<span data-ttu-id="3161c-250">长度</span><span class="sxs-lookup"><span data-stu-id="3161c-250">Length</span></span>|<span data-ttu-id="3161c-251">值</span><span class="sxs-lookup"><span data-stu-id="3161c-251">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="3161c-252">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="3161c-252">**MQXQH_RemoteQMgrName**</span></span>|<span data-ttu-id="3161c-253">string</span><span class="sxs-lookup"><span data-stu-id="3161c-253">string</span></span>|<span data-ttu-id="3161c-254">48</span><span class="sxs-lookup"><span data-stu-id="3161c-254">48</span></span>|<span data-ttu-id="3161c-255">string</span><span class="sxs-lookup"><span data-stu-id="3161c-255">string</span></span>|  
|<span data-ttu-id="3161c-256">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="3161c-256">**MQXQH_RemoteQName**</span></span>|<span data-ttu-id="3161c-257">string</span><span class="sxs-lookup"><span data-stu-id="3161c-257">string</span></span>|<span data-ttu-id="3161c-258">48</span><span class="sxs-lookup"><span data-stu-id="3161c-258">48</span></span>|<span data-ttu-id="3161c-259">string</span><span class="sxs-lookup"><span data-stu-id="3161c-259">string</span></span>|  
  
 <span data-ttu-id="3161c-260">与本主题前面部分列出的属性一样，该适配器将按照相同的规则填充以下消息描述符值。</span><span class="sxs-lookup"><span data-stu-id="3161c-260">Together with the properties listed earlier in this topic, the adapter populates the following Message Descriptor values following the same rules.</span></span> <span data-ttu-id="3161c-261">该适配器使用 MQXQH_ 而不是 MQMD_ 作为这些属性名的前缀，否则这些属性将直接映射到在消息描述符表中定义的那些属性：</span><span class="sxs-lookup"><span data-stu-id="3161c-261">The adapter prefixes these property names with MQXQH_ instead of MQMD_, but otherwise they map directly to those properties defined in the Message Descriptor table:</span></span>  
  
-   <span data-ttu-id="3161c-262">**MQXQH_MsgDesc_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="3161c-262">**MQXQH_MsgDesc_AccountingToken**</span></span>  
  
-   <span data-ttu-id="3161c-263">**MQXQH_MsgDesc_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="3161c-263">**MQXQH_MsgDesc_ApplIdentityData**</span></span>  
  
-   <span data-ttu-id="3161c-264">**MQXQH_MsgDesc_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="3161c-264">**MQXQH_MsgDesc_ApplOriginData**</span></span>  
  
-   <span data-ttu-id="3161c-265">**MQXQH_MsgDesc_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="3161c-265">**MQXQH_MsgDesc_BackoutCount**</span></span>  
  
-   <span data-ttu-id="3161c-266">**MQXQH_MsgDesc_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="3161c-266">**MQXQH_MsgDesc_CodedCharSetId**</span></span>  
  
-   <span data-ttu-id="3161c-267">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="3161c-267">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="3161c-268">**MQXQH_MsgDesc_Encoding**</span><span class="sxs-lookup"><span data-stu-id="3161c-268">**MQXQH_MsgDesc_Encoding**</span></span>  
  
-   <span data-ttu-id="3161c-269">**MQXQH_MsgDesc_Expiry**</span><span class="sxs-lookup"><span data-stu-id="3161c-269">**MQXQH_MsgDesc_Expiry**</span></span>  
  
-   <span data-ttu-id="3161c-270">**MQXQH_MsgDesc_Feedback**</span><span class="sxs-lookup"><span data-stu-id="3161c-270">**MQXQH_MsgDesc_Feedback**</span></span>  
  
-   <span data-ttu-id="3161c-271">**MQXQH_MsgDesc_Format**</span><span class="sxs-lookup"><span data-stu-id="3161c-271">**MQXQH_MsgDesc_Format**</span></span>  
  
-   <span data-ttu-id="3161c-272">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="3161c-272">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="3161c-273">**MQXQH_MsgDesc_MsgType**</span><span class="sxs-lookup"><span data-stu-id="3161c-273">**MQXQH_MsgDesc_MsgType**</span></span>  
  
-   <span data-ttu-id="3161c-274">**MQXQH_MsgDesc_Persistence**</span><span class="sxs-lookup"><span data-stu-id="3161c-274">**MQXQH_MsgDesc_Persistence**</span></span>  
  
-   <span data-ttu-id="3161c-275">**MQXQH_MsgDesc_Priority**</span><span class="sxs-lookup"><span data-stu-id="3161c-275">**MQXQH_MsgDesc_Priority**</span></span>  
  
-   <span data-ttu-id="3161c-276">**MQXQH_MsgDesc_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="3161c-276">**MQXQH_MsgDesc_PutApplName**</span></span>  
  
-   <span data-ttu-id="3161c-277">**MQXQH_MsgDesc_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="3161c-277">**MQXQH_MsgDesc_PutApplType**</span></span>  
  
-   <span data-ttu-id="3161c-278">**MQXQH_MsgDesc_PutDate**</span><span class="sxs-lookup"><span data-stu-id="3161c-278">**MQXQH_MsgDesc_PutDate**</span></span>  
  
-   <span data-ttu-id="3161c-279">**MQXQH_MsgDesc_PutTime**</span><span class="sxs-lookup"><span data-stu-id="3161c-279">**MQXQH_MsgDesc_PutTime**</span></span>  
  
-   <span data-ttu-id="3161c-280">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="3161c-280">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="3161c-281">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="3161c-281">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="3161c-282">**MQXQH_MsgDesc_Report**</span><span class="sxs-lookup"><span data-stu-id="3161c-282">**MQXQH_MsgDesc_Report**</span></span>  
  
-   <span data-ttu-id="3161c-283">**MQXQH_MsgDesc_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="3161c-283">**MQXQH_MsgDesc_UserIdentifier**</span></span>  
  
 <span data-ttu-id="3161c-284">属性架构中还包含与 MQSeries 相关的其他属性，这些属性可在筛选表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="3161c-284">There are additional MQSeries-related properties included in the property schema and available for use in filtering expressions.</span></span> <span data-ttu-id="3161c-285">下表列出了这些属性：</span><span class="sxs-lookup"><span data-stu-id="3161c-285">The following table lists these properties.</span></span>  
  
|<span data-ttu-id="3161c-286">Name</span><span class="sxs-lookup"><span data-stu-id="3161c-286">Name</span></span>|<span data-ttu-id="3161c-287">类型</span><span class="sxs-lookup"><span data-stu-id="3161c-287">Type</span></span>|<span data-ttu-id="3161c-288">长度</span><span class="sxs-lookup"><span data-stu-id="3161c-288">Length</span></span>|<span data-ttu-id="3161c-289">值</span><span class="sxs-lookup"><span data-stu-id="3161c-289">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="3161c-290">**MQCIH_AbendCode**</span><span class="sxs-lookup"><span data-stu-id="3161c-290">**MQCIH_AbendCode**</span></span>|<span data-ttu-id="3161c-291">string</span><span class="sxs-lookup"><span data-stu-id="3161c-291">string</span></span>|<span data-ttu-id="3161c-292">4</span><span class="sxs-lookup"><span data-stu-id="3161c-292">4</span></span>||  
|<span data-ttu-id="3161c-293">**MQCIH_ADSDescriptor**</span><span class="sxs-lookup"><span data-stu-id="3161c-293">**MQCIH_ADSDescriptor**</span></span>|<span data-ttu-id="3161c-294">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-294">unsigned int</span></span>|<span data-ttu-id="3161c-295">4</span><span class="sxs-lookup"><span data-stu-id="3161c-295">4</span></span>||  
|<span data-ttu-id="3161c-296">**MQCIH_AttentionId**</span><span class="sxs-lookup"><span data-stu-id="3161c-296">**MQCIH_AttentionId**</span></span>|<span data-ttu-id="3161c-297">string</span><span class="sxs-lookup"><span data-stu-id="3161c-297">string</span></span>|<span data-ttu-id="3161c-298">4</span><span class="sxs-lookup"><span data-stu-id="3161c-298">4</span></span>||  
|<span data-ttu-id="3161c-299">**MQCIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="3161c-299">**MQCIH_Authenticator**</span></span>|<span data-ttu-id="3161c-300">string</span><span class="sxs-lookup"><span data-stu-id="3161c-300">string</span></span>|<span data-ttu-id="3161c-301">8</span><span class="sxs-lookup"><span data-stu-id="3161c-301">8</span></span>|<span data-ttu-id="3161c-302">当你使用设置为 SSO 的密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="3161c-302">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="3161c-303">**注意：**将设置此值为空 MQSeries 适配器 SSO 密码长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="3161c-303">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="3161c-304">**MQCIH_CancelCode**</span><span class="sxs-lookup"><span data-stu-id="3161c-304">**MQCIH_CancelCode**</span></span>|<span data-ttu-id="3161c-305">string</span><span class="sxs-lookup"><span data-stu-id="3161c-305">string</span></span>|<span data-ttu-id="3161c-306">4</span><span class="sxs-lookup"><span data-stu-id="3161c-306">4</span></span>||  
|<span data-ttu-id="3161c-307">**MQCIH_CompCode**</span><span class="sxs-lookup"><span data-stu-id="3161c-307">**MQCIH_CompCode**</span></span>|<span data-ttu-id="3161c-308">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-308">unsigned int</span></span>|<span data-ttu-id="3161c-309">4</span><span class="sxs-lookup"><span data-stu-id="3161c-309">4</span></span>||  
|<span data-ttu-id="3161c-310">**MQCIH_ConversationalTask**</span><span class="sxs-lookup"><span data-stu-id="3161c-310">**MQCIH_ConversationalTask**</span></span>|<span data-ttu-id="3161c-311">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-311">unsigned int</span></span>|<span data-ttu-id="3161c-312">4</span><span class="sxs-lookup"><span data-stu-id="3161c-312">4</span></span>||  
|<span data-ttu-id="3161c-313">**MQCIH_CursorPosition**</span><span class="sxs-lookup"><span data-stu-id="3161c-313">**MQCIH_CursorPosition**</span></span>|<span data-ttu-id="3161c-314">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-314">unsigned int</span></span>|<span data-ttu-id="3161c-315">4</span><span class="sxs-lookup"><span data-stu-id="3161c-315">4</span></span>||  
|<span data-ttu-id="3161c-316">**MQCIH_ErrorOffset**</span><span class="sxs-lookup"><span data-stu-id="3161c-316">**MQCIH_ErrorOffset**</span></span>|<span data-ttu-id="3161c-317">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-317">unsigned int</span></span>|<span data-ttu-id="3161c-318">4</span><span class="sxs-lookup"><span data-stu-id="3161c-318">4</span></span>||  
|<span data-ttu-id="3161c-319">**MQCIH_Facility**</span><span class="sxs-lookup"><span data-stu-id="3161c-319">**MQCIH_Facility**</span></span>|<span data-ttu-id="3161c-320">string</span><span class="sxs-lookup"><span data-stu-id="3161c-320">string</span></span>|<span data-ttu-id="3161c-321">16</span><span class="sxs-lookup"><span data-stu-id="3161c-321">16</span></span>|<span data-ttu-id="3161c-322">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-322">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-323">**MQCIH_FacilityKeepTime**</span><span class="sxs-lookup"><span data-stu-id="3161c-323">**MQCIH_FacilityKeepTime**</span></span>|<span data-ttu-id="3161c-324">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-324">unsigned int</span></span>|<span data-ttu-id="3161c-325">4</span><span class="sxs-lookup"><span data-stu-id="3161c-325">4</span></span>||  
|<span data-ttu-id="3161c-326">**MQCIH_FacilityLike**</span><span class="sxs-lookup"><span data-stu-id="3161c-326">**MQCIH_FacilityLike**</span></span>|<span data-ttu-id="3161c-327">string</span><span class="sxs-lookup"><span data-stu-id="3161c-327">string</span></span>|<span data-ttu-id="3161c-328">4</span><span class="sxs-lookup"><span data-stu-id="3161c-328">4</span></span>||  
|<span data-ttu-id="3161c-329">**MQCIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="3161c-329">**MQCIH_Flags**</span></span>|<span data-ttu-id="3161c-330">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-330">unsigned int</span></span>|<span data-ttu-id="3161c-331">4</span><span class="sxs-lookup"><span data-stu-id="3161c-331">4</span></span>||  
|<span data-ttu-id="3161c-332">**MQCIH_Format**</span><span class="sxs-lookup"><span data-stu-id="3161c-332">**MQCIH_Format**</span></span>|<span data-ttu-id="3161c-333">string</span><span class="sxs-lookup"><span data-stu-id="3161c-333">string</span></span>|||  
|<span data-ttu-id="3161c-334">**MQCIH_Function**</span><span class="sxs-lookup"><span data-stu-id="3161c-334">**MQCIH_Function**</span></span>|<span data-ttu-id="3161c-335">string</span><span class="sxs-lookup"><span data-stu-id="3161c-335">string</span></span>|<span data-ttu-id="3161c-336">4</span><span class="sxs-lookup"><span data-stu-id="3161c-336">4</span></span>||  
|<span data-ttu-id="3161c-337">**MQCIH_GetWaitInterval**</span><span class="sxs-lookup"><span data-stu-id="3161c-337">**MQCIH_GetWaitInterval**</span></span>|<span data-ttu-id="3161c-338">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-338">unsigned int</span></span>|<span data-ttu-id="3161c-339">4</span><span class="sxs-lookup"><span data-stu-id="3161c-339">4</span></span>||  
|<span data-ttu-id="3161c-340">**MQCIH_LinkType**</span><span class="sxs-lookup"><span data-stu-id="3161c-340">**MQCIH_LinkType**</span></span>|<span data-ttu-id="3161c-341">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-341">unsigned int</span></span>|<span data-ttu-id="3161c-342">4</span><span class="sxs-lookup"><span data-stu-id="3161c-342">4</span></span>||  
|<span data-ttu-id="3161c-343">**MQCIH_NextTransactionId**</span><span class="sxs-lookup"><span data-stu-id="3161c-343">**MQCIH_NextTransactionId**</span></span>|<span data-ttu-id="3161c-344">string</span><span class="sxs-lookup"><span data-stu-id="3161c-344">string</span></span>|<span data-ttu-id="3161c-345">4</span><span class="sxs-lookup"><span data-stu-id="3161c-345">4</span></span>||  
|<span data-ttu-id="3161c-346">**MQCIH_OutputDataLength**</span><span class="sxs-lookup"><span data-stu-id="3161c-346">**MQCIH_OutputDataLength**</span></span>|<span data-ttu-id="3161c-347">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-347">unsigned int</span></span>|<span data-ttu-id="3161c-348">4</span><span class="sxs-lookup"><span data-stu-id="3161c-348">4</span></span>||  
|<span data-ttu-id="3161c-349">**MQCIH_Reason**</span><span class="sxs-lookup"><span data-stu-id="3161c-349">**MQCIH_Reason**</span></span>|<span data-ttu-id="3161c-350">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-350">unsigned int</span></span>|<span data-ttu-id="3161c-351">4</span><span class="sxs-lookup"><span data-stu-id="3161c-351">4</span></span>||  
|<span data-ttu-id="3161c-352">**MQCIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="3161c-352">**MQCIH_ReplyToFormat**</span></span>|<span data-ttu-id="3161c-353">string</span><span class="sxs-lookup"><span data-stu-id="3161c-353">string</span></span>|||  
|<span data-ttu-id="3161c-354">**MQCIH_ReturnCode**</span><span class="sxs-lookup"><span data-stu-id="3161c-354">**MQCIH_ReturnCode**</span></span>|<span data-ttu-id="3161c-355">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-355">unsigned int</span></span>|<span data-ttu-id="3161c-356">4</span><span class="sxs-lookup"><span data-stu-id="3161c-356">4</span></span>||  
|<span data-ttu-id="3161c-357">**MQCIH_StartCode**</span><span class="sxs-lookup"><span data-stu-id="3161c-357">**MQCIH_StartCode**</span></span>|<span data-ttu-id="3161c-358">string</span><span class="sxs-lookup"><span data-stu-id="3161c-358">string</span></span>|<span data-ttu-id="3161c-359">4</span><span class="sxs-lookup"><span data-stu-id="3161c-359">4</span></span>||  
|<span data-ttu-id="3161c-360">**MQCIH_TaskEndStatus**</span><span class="sxs-lookup"><span data-stu-id="3161c-360">**MQCIH_TaskEndStatus**</span></span>|<span data-ttu-id="3161c-361">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-361">unsigned int</span></span>|<span data-ttu-id="3161c-362">4</span><span class="sxs-lookup"><span data-stu-id="3161c-362">4</span></span>||  
|<span data-ttu-id="3161c-363">**MQCIH_TransactionId**</span><span class="sxs-lookup"><span data-stu-id="3161c-363">**MQCIH_TransactionId**</span></span>|<span data-ttu-id="3161c-364">string</span><span class="sxs-lookup"><span data-stu-id="3161c-364">string</span></span>|<span data-ttu-id="3161c-365">4</span><span class="sxs-lookup"><span data-stu-id="3161c-365">4</span></span>||  
|<span data-ttu-id="3161c-366">**MQCIH_UOWControl**</span><span class="sxs-lookup"><span data-stu-id="3161c-366">**MQCIH_UOWControl**</span></span>|<span data-ttu-id="3161c-367">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-367">unsigned int</span></span>|<span data-ttu-id="3161c-368">4</span><span class="sxs-lookup"><span data-stu-id="3161c-368">4</span></span>||  
|<span data-ttu-id="3161c-369">**MQIIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="3161c-369">**MQIIH_Authenticator**</span></span>|<span data-ttu-id="3161c-370">string</span><span class="sxs-lookup"><span data-stu-id="3161c-370">string</span></span>|<span data-ttu-id="3161c-371">8</span><span class="sxs-lookup"><span data-stu-id="3161c-371">8</span></span>|<span data-ttu-id="3161c-372">当你使用设置为 SSO 的密码**SSOAffiliateApplication**属性。</span><span class="sxs-lookup"><span data-stu-id="3161c-372">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="3161c-373">**注意：**将设置此值为空 MQSeries 适配器 SSO 密码长度超过 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="3161c-373">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="3161c-374">**MQIIH_CommitMode**</span><span class="sxs-lookup"><span data-stu-id="3161c-374">**MQIIH_CommitMode**</span></span>|<span data-ttu-id="3161c-375">string</span><span class="sxs-lookup"><span data-stu-id="3161c-375">string</span></span>|||  
|<span data-ttu-id="3161c-376">**MQIIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="3161c-376">**MQIIH_Flags**</span></span>|<span data-ttu-id="3161c-377">unsigned int</span><span class="sxs-lookup"><span data-stu-id="3161c-377">unsigned int</span></span>|<span data-ttu-id="3161c-378">4</span><span class="sxs-lookup"><span data-stu-id="3161c-378">4</span></span>||  
|<span data-ttu-id="3161c-379">**MQIIH_Format**</span><span class="sxs-lookup"><span data-stu-id="3161c-379">**MQIIH_Format**</span></span>|<span data-ttu-id="3161c-380">string</span><span class="sxs-lookup"><span data-stu-id="3161c-380">string</span></span>|||  
|<span data-ttu-id="3161c-381">**MQIIH_LTermOverride**</span><span class="sxs-lookup"><span data-stu-id="3161c-381">**MQIIH_LTermOverride**</span></span>|<span data-ttu-id="3161c-382">string</span><span class="sxs-lookup"><span data-stu-id="3161c-382">string</span></span>|<span data-ttu-id="3161c-383">8</span><span class="sxs-lookup"><span data-stu-id="3161c-383">8</span></span>||  
|<span data-ttu-id="3161c-384">**MQIIH_MFSMapName**</span><span class="sxs-lookup"><span data-stu-id="3161c-384">**MQIIH_MFSMapName**</span></span>|<span data-ttu-id="3161c-385">string</span><span class="sxs-lookup"><span data-stu-id="3161c-385">string</span></span>|<span data-ttu-id="3161c-386">8</span><span class="sxs-lookup"><span data-stu-id="3161c-386">8</span></span>||  
|<span data-ttu-id="3161c-387">**MQIIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="3161c-387">**MQIIH_ReplyToFormat**</span></span>|<span data-ttu-id="3161c-388">string</span><span class="sxs-lookup"><span data-stu-id="3161c-388">string</span></span>|||  
|<span data-ttu-id="3161c-389">**MQIIH_SecurityScope**</span><span class="sxs-lookup"><span data-stu-id="3161c-389">**MQIIH_SecurityScope**</span></span>|<span data-ttu-id="3161c-390">string</span><span class="sxs-lookup"><span data-stu-id="3161c-390">string</span></span>|||  
|<span data-ttu-id="3161c-391">**MQIIH_TranInstanceId**</span><span class="sxs-lookup"><span data-stu-id="3161c-391">**MQIIH_TranInstanceId**</span></span>|<span data-ttu-id="3161c-392">string</span><span class="sxs-lookup"><span data-stu-id="3161c-392">string</span></span>|<span data-ttu-id="3161c-393">32</span><span class="sxs-lookup"><span data-stu-id="3161c-393">32</span></span>|<span data-ttu-id="3161c-394">十六进制字符串</span><span class="sxs-lookup"><span data-stu-id="3161c-394">Hexadecimal string</span></span>|  
|<span data-ttu-id="3161c-395">**MQIIH_TranState**</span><span class="sxs-lookup"><span data-stu-id="3161c-395">**MQIIH_TranState**</span></span>|<span data-ttu-id="3161c-396">string</span><span class="sxs-lookup"><span data-stu-id="3161c-396">string</span></span>|||  
  
## <a name="see-also"></a><span data-ttu-id="3161c-397">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3161c-397">See Also</span></span>  
 <span data-ttu-id="3161c-398">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3161c-398">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="3161c-399">[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="3161c-399">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="3161c-400">数据类型转换的属性</span><span class="sxs-lookup"><span data-stu-id="3161c-400">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)