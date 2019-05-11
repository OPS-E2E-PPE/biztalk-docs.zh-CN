---
title: 替代 EDI 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e768bb992497651a14558895e4bedf2dbff692fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393370"
---
# <a name="overriding-edi-headers"></a><span data-ttu-id="3a9a9-102">替代 EDI 标头</span><span class="sxs-lookup"><span data-stu-id="3a9a9-102">Overriding EDI Headers</span></span>
<span data-ttu-id="3a9a9-103">将发送的 EDI 编码的交换时，应用于消息的 EDI 信封通常基于接收协议的 EDI 属性或后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-103">When sending an EDI-encoded interchange, the EDI envelope applied to the message is normally based upon the EDI properties of the receiving agreement, or the fallback agreement properties.</span></span> <span data-ttu-id="3a9a9-104">但是通常很有用，若要设置 EDI 信封属性基于运行时生成的值。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-104">However it is often useful to set the EDI envelope properties based on runtime generated values.</span></span>  
  
 <span data-ttu-id="3a9a9-105">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用 EdiOverride 上下文属性以指定用于生成出站文档的 EDI 信封的值。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use the EdiOverride context properties to specify the values used to generate the EDI envelope on outbound documents.</span></span>  
  
## <a name="using-edioverride-context-properties"></a><span data-ttu-id="3a9a9-106">使用 EdiOverride 上下文属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-106">Using EdiOverride Context Properties</span></span>  
 <span data-ttu-id="3a9a9-107">EdiOverride 上下文属性提供对重写全部或部分，用来生成 EDI 信封的值的一种方法。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-107">The EdiOverride context properties provide a way to override all, or part, of the values used to generate the EDI envelope.</span></span> <span data-ttu-id="3a9a9-108">EDI 发送管道将使用 EdiOverride 上下文属性，其中包含有效的值来构造信封。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-108">The EDI send pipeline will use EdiOverride context property that contains a valid value to construct the envelope.</span></span> <span data-ttu-id="3a9a9-109">如果不填充属性，则管道将使用在协议属性或后备协议属性中指定的值，如果未定义协议。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-109">If a property is not populated, the pipeline will use the value specified in agreement properties or fallback agreement properties, if an agreement is not defined.</span></span> <span data-ttu-id="3a9a9-110">如果某个属性包含无效的值，则管道将挂起消息并报告验证错误。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-110">If a property contains an invalid value, the pipeline will suspend the message and report a validation error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a9a9-111">如果仅使用在 EdiOverride 集合中指定的值`EdiOverride.OverrideEdiHeader`属性写入到消息的上下文的且包含值为"True"。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-111">The values specified in the EdiOverride collection are only used if the `EdiOverride.OverrideEdiHeader` property is written into the context of a message and contains a value of “True”.</span></span>  
>   
>  <span data-ttu-id="3a9a9-112">未设置默认值。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-112">The default value is not set.</span></span>  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a><span data-ttu-id="3a9a9-113">EdiOverride 属性适用于 X12 信封值</span><span class="sxs-lookup"><span data-stu-id="3a9a9-113">EdiOverride properties for X12 Envelope Values</span></span>  
 <span data-ttu-id="3a9a9-114">下表显示了 EdiOverride 上下文属性以及相应的 X12 信封标头：</span><span class="sxs-lookup"><span data-stu-id="3a9a9-114">The following table shows the EdiOverride context properties and the corresponding X12 envelope header:</span></span>  
  
|<span data-ttu-id="3a9a9-115">Header</span><span class="sxs-lookup"><span data-stu-id="3a9a9-115">Header</span></span>|<span data-ttu-id="3a9a9-116">属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-116">Properties</span></span>|  
|------------|----------------|  
|<span data-ttu-id="3a9a9-117">交换控制标头 (ISA)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-117">Interchange Control Header (ISA)</span></span>|<span data-ttu-id="3a9a9-118">ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16</span><span class="sxs-lookup"><span data-stu-id="3a9a9-118">ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16</span></span>|  
|<span data-ttu-id="3a9a9-119">功能组标头 (GS)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-119">Functional Group Headers (GS)</span></span>|<span data-ttu-id="3a9a9-120">GS01、 GS02、 GS03、 GS04、 GS05、 GS06、 GS07、 GS08</span><span class="sxs-lookup"><span data-stu-id="3a9a9-120">GS01, GS02, GS03, GS04, GS05, GS06, GS07, GS08</span></span>|  
|<span data-ttu-id="3a9a9-121">事务集标头</span><span class="sxs-lookup"><span data-stu-id="3a9a9-121">Transaction Set Header</span></span>|<span data-ttu-id="3a9a9-122">ST02</span><span class="sxs-lookup"><span data-stu-id="3a9a9-122">ST02</span></span>|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a><span data-ttu-id="3a9a9-123">EDIFACT 信封值的 EdiOverride 属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-123">EdiOverride properties for EDIFACT Envelope Values</span></span>  
 <span data-ttu-id="3a9a9-124">下表显示了 EdiOverride 上下文属性以及相应的 EDIFACT 信封段：</span><span class="sxs-lookup"><span data-stu-id="3a9a9-124">The following table shows the EdiOverride context properties and the corresponding EDIFACT envelope segment:</span></span>  
  
|<span data-ttu-id="3a9a9-125">段</span><span class="sxs-lookup"><span data-stu-id="3a9a9-125">Segment</span></span>|<span data-ttu-id="3a9a9-126">属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-126">Properties</span></span>|  
|-------------|----------------|  
|<span data-ttu-id="3a9a9-127">服务字符串建议 (UNA)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-127">Service String Advice (UNA)</span></span>|<span data-ttu-id="3a9a9-128">UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix</span><span class="sxs-lookup"><span data-stu-id="3a9a9-128">UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix</span></span>|  
|<span data-ttu-id="3a9a9-129">交换控制标头 (UNB)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-129">Interchange Control Header (UNB)</span></span>|<span data-ttu-id="3a9a9-130">UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11</span><span class="sxs-lookup"><span data-stu-id="3a9a9-130">UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11</span></span>|  
|<span data-ttu-id="3a9a9-131">功能组标头 (UNG)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-131">Functional Group Headers (UNG)</span></span>|<span data-ttu-id="3a9a9-132">UNG1、 UNG2_1、 UNG2_2、 UNG3_1、 UNG3_2、 UNG4_1、 UNG4_2、 UNG5、 UNG6、 UNG7_1、 UNG7_2、 UNG7_3、 UNG8</span><span class="sxs-lookup"><span data-stu-id="3a9a9-132">UNG1, UNG2_1, UNG2_2, UNG3_1, UNG3_2, UNG4_1, UNG4_2, UNG5, UNG6, UNG7_1, UNG7_2, UNG7_3, UNG8</span></span>|  
|<span data-ttu-id="3a9a9-133">消息标头 (UNH)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-133">Message Header (UNH)</span></span>|<span data-ttu-id="3a9a9-134">UNH1</span><span class="sxs-lookup"><span data-stu-id="3a9a9-134">UNH1</span></span>|  
  
 <span data-ttu-id="3a9a9-135">因为 UNA 和 UNG EDIFACT 段是可选的可使用 GenerateUNA 和 GenerateUNG 属性来确定这些标头就生成了，而不考虑**应用 UNA 段**协议设置。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-135">Since the UNA and UNG EDIFACT segments are optional, the GenerateUNA and GenerateUNG properties can be used to determine if these headers are generated, regardless of the **Apply UNA segment** agreement setting.</span></span> <span data-ttu-id="3a9a9-136">下表显示导致生成这些段的值：</span><span class="sxs-lookup"><span data-stu-id="3a9a9-136">The following tables show the values that result in generation of these segments:</span></span>  
  
|<span data-ttu-id="3a9a9-137">GenerateUNA 上下文属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-137">GenerateUNA context property</span></span>|<span data-ttu-id="3a9a9-138">应用 UNA 段协议设置</span><span class="sxs-lookup"><span data-stu-id="3a9a9-138">Apply UNA segment agreement setting</span></span>|<span data-ttu-id="3a9a9-139">引擎行为</span><span class="sxs-lookup"><span data-stu-id="3a9a9-139">Engine behavior</span></span>|  
|----------------------------------|-----------------------------------------|---------------------|  
|<span data-ttu-id="3a9a9-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-140">TRUE</span></span>|<span data-ttu-id="3a9a9-141">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-141">CHECKED</span></span>|<span data-ttu-id="3a9a9-142">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-142">Generate UNA</span></span>|  
|<span data-ttu-id="3a9a9-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-143">TRUE</span></span>|<span data-ttu-id="3a9a9-144">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-144">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-145">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-145">Generate UNA</span></span>|  
|<span data-ttu-id="3a9a9-146">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-146">FALSE</span></span>|<span data-ttu-id="3a9a9-147">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-147">CHECKED</span></span>|<span data-ttu-id="3a9a9-148">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-148">Do not generate UNA</span></span>|  
|<span data-ttu-id="3a9a9-149">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-149">FALSE</span></span>|<span data-ttu-id="3a9a9-150">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-150">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-151">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-151">Do not generate UNA</span></span>|  
|<span data-ttu-id="3a9a9-152">不显示 （OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="3a9a9-152">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="3a9a9-153">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-153">CHECKED</span></span>|<span data-ttu-id="3a9a9-154">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-154">Generate UNA</span></span>|  
|<span data-ttu-id="3a9a9-155">不显示 （OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="3a9a9-155">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="3a9a9-156">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-156">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-157">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="3a9a9-157">Do not generate UNA</span></span>|  
  
|<span data-ttu-id="3a9a9-158">GenerateUNG 上下文属性</span><span class="sxs-lookup"><span data-stu-id="3a9a9-158">GenerateUNG context property</span></span>|<span data-ttu-id="3a9a9-159">应用 UNG 段协议设置</span><span class="sxs-lookup"><span data-stu-id="3a9a9-159">Apply UNG segments agreement setting</span></span>|<span data-ttu-id="3a9a9-160">引擎行为</span><span class="sxs-lookup"><span data-stu-id="3a9a9-160">Engine behavior</span></span>|  
|----------------------------------|------------------------------------------|---------------------|  
|<span data-ttu-id="3a9a9-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-161">TRUE</span></span>|<span data-ttu-id="3a9a9-162">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-162">CHECKED</span></span>|<span data-ttu-id="3a9a9-163">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-163">Generate UNG</span></span>|  
|<span data-ttu-id="3a9a9-164">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-164">TRUE</span></span>|<span data-ttu-id="3a9a9-165">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-165">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-166">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-166">Generate UNG</span></span>|  
|<span data-ttu-id="3a9a9-167">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-167">FALSE</span></span>|<span data-ttu-id="3a9a9-168">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-168">CHECKED</span></span>|<span data-ttu-id="3a9a9-169">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-169">Do not generate UNG</span></span>|  
|<span data-ttu-id="3a9a9-170">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a9a9-170">FALSE</span></span>|<span data-ttu-id="3a9a9-171">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-171">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-172">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-172">Do not generate UNG</span></span>|  
|<span data-ttu-id="3a9a9-173">不显示 （OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="3a9a9-173">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="3a9a9-174">检查</span><span class="sxs-lookup"><span data-stu-id="3a9a9-174">CHECKED</span></span>|<span data-ttu-id="3a9a9-175">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-175">Generate UNG</span></span>|  
|<span data-ttu-id="3a9a9-176">不显示 （OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="3a9a9-176">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="3a9a9-177">未选中状态</span><span class="sxs-lookup"><span data-stu-id="3a9a9-177">UNCHECKED</span></span>|<span data-ttu-id="3a9a9-178">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="3a9a9-178">Do not generate UNG</span></span>|  
  
### <a name="group-envelopes"></a><span data-ttu-id="3a9a9-179">组信封</span><span class="sxs-lookup"><span data-stu-id="3a9a9-179">Group envelopes</span></span>  
 <span data-ttu-id="3a9a9-180">组信封带来一个特殊的难题，因为交换中可以有多个组存在。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-180">Group envelopes present a special challenge, as the interchange can have more than one group present.</span></span> <span data-ttu-id="3a9a9-181">若要解决此问题，EDI 发送管道可以将信封应用到交换中的所有组或将信封应用到交换中的唯一组。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-181">To address this, the EDI send pipeline can either apply the envelope to all groups in the interchange, or apply the envelope to the only group in the interchange.</span></span>  
  
 <span data-ttu-id="3a9a9-182">对于单个事务，所有 GS 或 UNG 字段可以重都写，对于成批交换，可以重都写仅以下字段：</span><span class="sxs-lookup"><span data-stu-id="3a9a9-182">For single transactions, all GS or UNG fields can be overridden, for batch interchanges only the following fields can be overridden:</span></span>  
  
-   <span data-ttu-id="3a9a9-183">GS04</span><span class="sxs-lookup"><span data-stu-id="3a9a9-183">GS04</span></span>  
  
-   <span data-ttu-id="3a9a9-184">GS05</span><span class="sxs-lookup"><span data-stu-id="3a9a9-184">GS05</span></span>  
  
-   <span data-ttu-id="3a9a9-185">UNG4_1</span><span class="sxs-lookup"><span data-stu-id="3a9a9-185">UNG4_1</span></span>  
  
-   <span data-ttu-id="3a9a9-186">UNG4_2</span><span class="sxs-lookup"><span data-stu-id="3a9a9-186">UNG4_2</span></span>  
  
### <a name="batching"></a><span data-ttu-id="3a9a9-187">批处理</span><span class="sxs-lookup"><span data-stu-id="3a9a9-187">Batching</span></span>  
 <span data-ttu-id="3a9a9-188">由批处理业务流程处理批处理消息的事务集控制编号重写。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-188">Overriding the transaction set control number for batched messages is handled by the Batching orchestration.</span></span> <span data-ttu-id="3a9a9-189">以下属性可写入到将进行批处理以重写任何消息的上下文的事务集控制编号：</span><span class="sxs-lookup"><span data-stu-id="3a9a9-189">The following properties can be written to the context of any message that will be batched to override the transaction set control number:</span></span>  
  
-   <span data-ttu-id="3a9a9-190">ST02 (对于 X12 消息)</span><span class="sxs-lookup"><span data-stu-id="3a9a9-190">ST02 (for X12 messages)</span></span>  
  
-   <span data-ttu-id="3a9a9-191">UNH1 （适用于 EDIFACT 消息</span><span class="sxs-lookup"><span data-stu-id="3a9a9-191">UNH1 (For EDIFACT messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a9a9-192">如果多个传入消息包含相同的控制编号相同的组中，具有重复编号的消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-192">If multiple incoming messages contain the same control number in the same group, messages with duplicate numbers will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a9a9-193">不要升级 EdiOverride 上下文属性 ISA、 UNA、 GS 或 UNG 是要进行批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-193">Do not promote the EdiOverride context properties ISA, UNA, GS, or UNG for messages that are to be batched.</span></span> <span data-ttu-id="3a9a9-194">如果你需要重写这些属性，将它们提升对输出消息之前发送到 EDI 批处理业务流程的发送管道。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-194">If you need to override these properties, promote them on the output message of the batch orchestration before sending to the EDI send pipeline.</span></span>  
  
### <a name="delimiter-collision"></a><span data-ttu-id="3a9a9-195">分隔符冲突</span><span class="sxs-lookup"><span data-stu-id="3a9a9-195">Delimiter collision</span></span>  
 <span data-ttu-id="3a9a9-196">分隔符，例如，UNA 标头中，必须包含每个字段的唯一值。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-196">Delimiters, such as the UNA headers, must contain a unique value for each field.</span></span> <span data-ttu-id="3a9a9-197">当重写分隔符的值，例如，UNA 标头中，必须确保每个分隔符值不仅中重写，而且还在协议或后备协议设置中使用任何分隔符值之间的值唯一。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-197">When overriding delimiter values, such as the UNA headers, you must ensure that each delimiter value is unique not only within the values you override, but also among any delimiter values used from the agreement or fallback agreement settings.</span></span>  
  
 <span data-ttu-id="3a9a9-198">例如，如果您重写 UNA1、 UNA2 和 UNA4，并且 UNA3、 UNA5、 UNA6 和 UNA6Suffix 来自协议属性，每个属性必须包含与其他的唯一值。</span><span class="sxs-lookup"><span data-stu-id="3a9a9-198">For example, if you override UNA1, UNA2, and UNA4, and UNA3, UNA5, UNA6 and UNA6Suffix come from agreement properties, each property must contain a unique value compared to the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9a9-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a9a9-199">See Also</span></span>  
 [<span data-ttu-id="3a9a9-200">BizTalk Server 如何发送 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="3a9a9-200">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)