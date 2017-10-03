---
title: "重写 EDI 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510a3817d0fd99d43b6da9462c74dd8bc7c1bdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overriding-edi-headers"></a><span data-ttu-id="9aaca-102">替代 EDI 标头</span><span class="sxs-lookup"><span data-stu-id="9aaca-102">Overriding EDI Headers</span></span>
<span data-ttu-id="9aaca-103">发送 EDI 编码的交换时，应用到消息的 EDI 信封通常基于接收协议的 EDI 属性，或基于后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="9aaca-103">When sending an EDI-encoded interchange, the EDI envelope applied to the message is normally based upon the EDI properties of the receiving agreement, or the fallback agreement properties.</span></span> <span data-ttu-id="9aaca-104">但是，基于运行时所生成的值来设置 EDI 信封属性通常很有用。</span><span class="sxs-lookup"><span data-stu-id="9aaca-104">However it is often useful to set the EDI envelope properties based on runtime generated values.</span></span>  
  
 <span data-ttu-id="9aaca-105">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，你可以使用 EdiOverride 上下文属性来指定用于在出站文档上生成 EDI 信封的值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use the EdiOverride context properties to specify the values used to generate the EDI envelope on outbound documents.</span></span>  
  
## <a name="using-edioverride-context-properties"></a><span data-ttu-id="9aaca-106">使用 EdiOverride 上下文属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-106">Using EdiOverride Context Properties</span></span>  
 <span data-ttu-id="9aaca-107">EdiOverride 上下文属性提供一种方法来重写全部或部分用于生成 EDI 信封的值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-107">The EdiOverride context properties provide a way to override all, or part, of the values used to generate the EDI envelope.</span></span> <span data-ttu-id="9aaca-108">EDI 发送管道将使用包含一个有效值的 EdiOverride 上下文属性来构造信封。</span><span class="sxs-lookup"><span data-stu-id="9aaca-108">The EDI send pipeline will use EdiOverride context property that contains a valid value to construct the envelope.</span></span> <span data-ttu-id="9aaca-109">如果未填充某个属性，则管道将使用协议属性中所指定的值；而如果还未定义协议，则将使用后备协议属性中所指定的值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-109">If a property is not populated, the pipeline will use the value specified in agreement properties or fallback agreement properties, if an agreement is not defined.</span></span> <span data-ttu-id="9aaca-110">如果某个属性包含无效值，则管道将挂起消息并报告一个验证错误。</span><span class="sxs-lookup"><span data-stu-id="9aaca-110">If a property contains an invalid value, the pipeline will suspend the message and report a validation error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aaca-111">仅在将 `EdiOverride.OverrideEdiHeader` 属性写入到消息的上下文，且包含一个“True”值时，才使用在 EdiOverride 集合中指定的值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-111">The values specified in the EdiOverride collection are only used if the `EdiOverride.OverrideEdiHeader` property is written into the context of a message and contains a value of “True”.</span></span>  
>   
>  <span data-ttu-id="9aaca-112">未设置默认值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-112">The default value is not set.</span></span>  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a><span data-ttu-id="9aaca-113">X12 信封值的 EdiOverride 属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-113">EdiOverride properties for X12 Envelope Values</span></span>  
 <span data-ttu-id="9aaca-114">下表显示了 EdiOverride 上下文属性以及相应的 X12 信封标头：</span><span class="sxs-lookup"><span data-stu-id="9aaca-114">The following table shows the EdiOverride context properties and the corresponding X12 envelope header:</span></span>  
  
|<span data-ttu-id="9aaca-115">标题</span><span class="sxs-lookup"><span data-stu-id="9aaca-115">Header</span></span>|<span data-ttu-id="9aaca-116">属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-116">Properties</span></span>|  
|------------|----------------|  
|<span data-ttu-id="9aaca-117">交换控制标头 (ISA)</span><span class="sxs-lookup"><span data-stu-id="9aaca-117">Interchange Control Header (ISA)</span></span>|<span data-ttu-id="9aaca-118">ISA01、ISA02、ISA03、ISA04、ISA05、ISA06、ISA07、ISA08、ISA09、ISA10、ISA11、ISA12、ISA13、ISA14、ISA15、ISA16</span><span class="sxs-lookup"><span data-stu-id="9aaca-118">ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16</span></span>|  
|<span data-ttu-id="9aaca-119">功能组标头 (GS)</span><span class="sxs-lookup"><span data-stu-id="9aaca-119">Functional Group Headers (GS)</span></span>|<span data-ttu-id="9aaca-120">GS01、GS02、GS03、GS04、GS05、GS06、GS07、GS08</span><span class="sxs-lookup"><span data-stu-id="9aaca-120">GS01, GS02, GS03, GS04, GS05, GS06, GS07, GS08</span></span>|  
|<span data-ttu-id="9aaca-121">事务将标头设置</span><span class="sxs-lookup"><span data-stu-id="9aaca-121">Transaction Set Header</span></span>|<span data-ttu-id="9aaca-122">ST02</span><span class="sxs-lookup"><span data-stu-id="9aaca-122">ST02</span></span>|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a><span data-ttu-id="9aaca-123">EDIFACT 信封值的 EdiOverride 属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-123">EdiOverride properties for EDIFACT Envelope Values</span></span>  
 <span data-ttu-id="9aaca-124">下表显示了 EdiOverride 上下文属性以及相应的 EDIFACT 信封段：</span><span class="sxs-lookup"><span data-stu-id="9aaca-124">The following table shows the EdiOverride context properties and the corresponding EDIFACT envelope segment:</span></span>  
  
|<span data-ttu-id="9aaca-125">段</span><span class="sxs-lookup"><span data-stu-id="9aaca-125">Segment</span></span>|<span data-ttu-id="9aaca-126">属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-126">Properties</span></span>|  
|-------------|----------------|  
|<span data-ttu-id="9aaca-127">服务字符串建议 (UNA)</span><span class="sxs-lookup"><span data-stu-id="9aaca-127">Service String Advice (UNA)</span></span>|<span data-ttu-id="9aaca-128">UNA1、UNA2、UNA3、UNA4、 UNA5、UNA6、UNA6Suffix</span><span class="sxs-lookup"><span data-stu-id="9aaca-128">UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix</span></span>|  
|<span data-ttu-id="9aaca-129">交换控制标头 (UNB)</span><span class="sxs-lookup"><span data-stu-id="9aaca-129">Interchange Control Header (UNB)</span></span>|<span data-ttu-id="9aaca-130">UNB1_1、UNB1_2、UNB2_1、UNB2_2、UNB2_3、UNB3_1、UNB3_2、UNB3_3、UNB4_1、UNB4_2、UNB5、UNB6_1、UNB7、UNB8、UNB9、UNB10、UNB11</span><span class="sxs-lookup"><span data-stu-id="9aaca-130">UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11</span></span>|  
|<span data-ttu-id="9aaca-131">功能组标头 (UNG)</span><span class="sxs-lookup"><span data-stu-id="9aaca-131">Functional Group Headers (UNG)</span></span>|<span data-ttu-id="9aaca-132">UNG1、UNG2_1、UNG2_2、UNG3_1、UNG3_2、UNG4_1、UNG4_2、UNG5、UNG6、UNG7_1、UNG7_2、UNG7_3、UNG8</span><span class="sxs-lookup"><span data-stu-id="9aaca-132">UNG1, UNG2_1, UNG2_2, UNG3_1, UNG3_2, UNG4_1, UNG4_2, UNG5, UNG6, UNG7_1, UNG7_2, UNG7_3, UNG8</span></span>|  
|<span data-ttu-id="9aaca-133">消息标头 (UNH)</span><span class="sxs-lookup"><span data-stu-id="9aaca-133">Message Header (UNH)</span></span>|<span data-ttu-id="9aaca-134">UNH1</span><span class="sxs-lookup"><span data-stu-id="9aaca-134">UNH1</span></span>|  
  
 <span data-ttu-id="9aaca-135">由于 UNA 和 UNG EDIFACT 段都是可选的可以使用 GenerateUNA 和 GenerateUNG 属性以确定这些标头是否生成，而不考虑**应用 UNA 段**协议设置。</span><span class="sxs-lookup"><span data-stu-id="9aaca-135">Since the UNA and UNG EDIFACT segments are optional, the GenerateUNA and GenerateUNG properties can be used to determine if these headers are generated, regardless of the **Apply UNA segment** agreement setting.</span></span> <span data-ttu-id="9aaca-136">下表显示了导致生成这些段的值：</span><span class="sxs-lookup"><span data-stu-id="9aaca-136">The following tables show the values that result in generation of these segments:</span></span>  
  
|<span data-ttu-id="9aaca-137">GenerateUNA 上下文属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-137">GenerateUNA context property</span></span>|<span data-ttu-id="9aaca-138">应用 UNA 段协议设置</span><span class="sxs-lookup"><span data-stu-id="9aaca-138">Apply UNA segment agreement setting</span></span>|<span data-ttu-id="9aaca-139">引擎行为</span><span class="sxs-lookup"><span data-stu-id="9aaca-139">Engine behavior</span></span>|  
|----------------------------------|-----------------------------------------|---------------------|  
|<span data-ttu-id="9aaca-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="9aaca-140">TRUE</span></span>|<span data-ttu-id="9aaca-141">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-141">CHECKED</span></span>|<span data-ttu-id="9aaca-142">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-142">Generate UNA</span></span>|  
|<span data-ttu-id="9aaca-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="9aaca-143">TRUE</span></span>|<span data-ttu-id="9aaca-144">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-144">UNCHECKED</span></span>|<span data-ttu-id="9aaca-145">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-145">Generate UNA</span></span>|  
|<span data-ttu-id="9aaca-146">FALSE</span><span class="sxs-lookup"><span data-stu-id="9aaca-146">FALSE</span></span>|<span data-ttu-id="9aaca-147">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-147">CHECKED</span></span>|<span data-ttu-id="9aaca-148">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-148">Do not generate UNA</span></span>|  
|<span data-ttu-id="9aaca-149">FALSE</span><span class="sxs-lookup"><span data-stu-id="9aaca-149">FALSE</span></span>|<span data-ttu-id="9aaca-150">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-150">UNCHECKED</span></span>|<span data-ttu-id="9aaca-151">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-151">Do not generate UNA</span></span>|  
|<span data-ttu-id="9aaca-152">不显示（OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="9aaca-152">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="9aaca-153">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-153">CHECKED</span></span>|<span data-ttu-id="9aaca-154">生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-154">Generate UNA</span></span>|  
|<span data-ttu-id="9aaca-155">不显示（OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="9aaca-155">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="9aaca-156">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-156">UNCHECKED</span></span>|<span data-ttu-id="9aaca-157">不生成 UNA</span><span class="sxs-lookup"><span data-stu-id="9aaca-157">Do not generate UNA</span></span>|  
  
|<span data-ttu-id="9aaca-158">GenerateUNG 上下文属性</span><span class="sxs-lookup"><span data-stu-id="9aaca-158">GenerateUNG context property</span></span>|<span data-ttu-id="9aaca-159">应用 UNG 段协议设置</span><span class="sxs-lookup"><span data-stu-id="9aaca-159">Apply UNG segments agreement setting</span></span>|<span data-ttu-id="9aaca-160">引擎行为</span><span class="sxs-lookup"><span data-stu-id="9aaca-160">Engine behavior</span></span>|  
|----------------------------------|------------------------------------------|---------------------|  
|<span data-ttu-id="9aaca-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="9aaca-161">TRUE</span></span>|<span data-ttu-id="9aaca-162">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-162">CHECKED</span></span>|<span data-ttu-id="9aaca-163">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-163">Generate UNG</span></span>|  
|<span data-ttu-id="9aaca-164">TRUE</span><span class="sxs-lookup"><span data-stu-id="9aaca-164">TRUE</span></span>|<span data-ttu-id="9aaca-165">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-165">UNCHECKED</span></span>|<span data-ttu-id="9aaca-166">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-166">Generate UNG</span></span>|  
|<span data-ttu-id="9aaca-167">FALSE</span><span class="sxs-lookup"><span data-stu-id="9aaca-167">FALSE</span></span>|<span data-ttu-id="9aaca-168">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-168">CHECKED</span></span>|<span data-ttu-id="9aaca-169">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-169">Do not generate UNG</span></span>|  
|<span data-ttu-id="9aaca-170">FALSE</span><span class="sxs-lookup"><span data-stu-id="9aaca-170">FALSE</span></span>|<span data-ttu-id="9aaca-171">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-171">UNCHECKED</span></span>|<span data-ttu-id="9aaca-172">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-172">Do not generate UNG</span></span>|  
|<span data-ttu-id="9aaca-173">不显示（OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="9aaca-173">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="9aaca-174">CHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-174">CHECKED</span></span>|<span data-ttu-id="9aaca-175">生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-175">Generate UNG</span></span>|  
|<span data-ttu-id="9aaca-176">不显示（OverrideEDIHeader 为 false）</span><span class="sxs-lookup"><span data-stu-id="9aaca-176">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="9aaca-177">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="9aaca-177">UNCHECKED</span></span>|<span data-ttu-id="9aaca-178">不生成 UNG</span><span class="sxs-lookup"><span data-stu-id="9aaca-178">Do not generate UNG</span></span>|  
  
### <a name="group-envelopes"></a><span data-ttu-id="9aaca-179">组信封</span><span class="sxs-lookup"><span data-stu-id="9aaca-179">Group envelopes</span></span>  
 <span data-ttu-id="9aaca-180">由于交换可显示多个组，因此，组信封带来了一个特殊的难题。</span><span class="sxs-lookup"><span data-stu-id="9aaca-180">Group envelopes present a special challenge, as the interchange can have more than one group present.</span></span> <span data-ttu-id="9aaca-181">为了解决这个难题，EDI 发送管道可将信封应用到交换中的所有组，或仅将信封应用到交换中的一个组。</span><span class="sxs-lookup"><span data-stu-id="9aaca-181">To address this, the EDI send pipeline can either apply the envelope to all groups in the interchange, or apply the envelope to the only group in the interchange.</span></span>  
  
 <span data-ttu-id="9aaca-182">对于单一事务，可重写所有 GS 或 UNG 字段，而对于成批交换，仅可重写以下字段：</span><span class="sxs-lookup"><span data-stu-id="9aaca-182">For single transactions, all GS or UNG fields can be overridden, for batch interchanges only the following fields can be overridden:</span></span>  
  
-   <span data-ttu-id="9aaca-183">GS04</span><span class="sxs-lookup"><span data-stu-id="9aaca-183">GS04</span></span>  
  
-   <span data-ttu-id="9aaca-184">GS05</span><span class="sxs-lookup"><span data-stu-id="9aaca-184">GS05</span></span>  
  
-   <span data-ttu-id="9aaca-185">UNG4_1</span><span class="sxs-lookup"><span data-stu-id="9aaca-185">UNG4_1</span></span>  
  
-   <span data-ttu-id="9aaca-186">UNG4_2</span><span class="sxs-lookup"><span data-stu-id="9aaca-186">UNG4_2</span></span>  
  
### <a name="batching"></a><span data-ttu-id="9aaca-187">批处理</span><span class="sxs-lookup"><span data-stu-id="9aaca-187">Batching</span></span>  
 <span data-ttu-id="9aaca-188">批处理消息的事务集控制编号的重写将由批处理业务流程来处理。</span><span class="sxs-lookup"><span data-stu-id="9aaca-188">Overriding the transaction set control number for batched messages is handled by the Batching orchestration.</span></span> <span data-ttu-id="9aaca-189">可通过将以下属性写入到将进行批处理的任何消息的上下文来重写事务集控制编号：</span><span class="sxs-lookup"><span data-stu-id="9aaca-189">The following properties can be written to the context of any message that will be batched to override the transaction set control number:</span></span>  
  
-   <span data-ttu-id="9aaca-190">ST02（适用于 X12 消息）</span><span class="sxs-lookup"><span data-stu-id="9aaca-190">ST02 (for X12 messages)</span></span>  
  
-   <span data-ttu-id="9aaca-191">UNH1（适用于 EDIFACT 消息）</span><span class="sxs-lookup"><span data-stu-id="9aaca-191">UNH1 (For EDIFACT messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aaca-192">如果相同组中的多个传入消息包含相同的控制编号，则具有重复编号的消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="9aaca-192">If multiple incoming messages contain the same control number in the same group, messages with duplicate numbers will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aaca-193">对于将进行批处理的消息，不要升级 EdiOverride 上下文属性 ISA、UNA、GS 或 UNG。</span><span class="sxs-lookup"><span data-stu-id="9aaca-193">Do not promote the EdiOverride context properties ISA, UNA, GS, or UNG for messages that are to be batched.</span></span> <span data-ttu-id="9aaca-194">如果你需要重写这些属性，则应首先在批处理业务流程的输出消息上升级这些属性，然后再将它们发送到 EDI 发送管道。</span><span class="sxs-lookup"><span data-stu-id="9aaca-194">If you need to override these properties, promote them on the output message of the batch orchestration before sending to the EDI send pipeline.</span></span>  
  
### <a name="delimiter-collision"></a><span data-ttu-id="9aaca-195">分隔符冲突</span><span class="sxs-lookup"><span data-stu-id="9aaca-195">Delimiter collision</span></span>  
 <span data-ttu-id="9aaca-196">对于每个字段，分隔符（例如，UNA 标头）必须包含一个唯一值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-196">Delimiters, such as the UNA headers, must contain a unique value for each field.</span></span> <span data-ttu-id="9aaca-197">重写分隔符（例如，UNA 标头）值时，必须确保每个分隔符的值不仅在你所重写的值中是唯一的，还应在协议或后备协议设置中所使用的任何分隔符中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9aaca-197">When overriding delimiter values, such as the UNA headers, you must ensure that each delimiter value is unique not only within the values you override, but also among any delimiter values used from the agreement or fallback agreement settings.</span></span>  
  
 <span data-ttu-id="9aaca-198">例如，如果你重写协议属性中的 UNA1、UNA2、UNA4、UNA3、UNA5、UNA6 和 UNA6Suffix，则每个属性必须包含与其他值不同的唯一值。</span><span class="sxs-lookup"><span data-stu-id="9aaca-198">For example, if you override UNA1, UNA2, and UNA4, and UNA3, UNA5, UNA6 and UNA6Suffix come from agreement properties, each property must contain a unique value compared to the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aaca-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aaca-199">See Also</span></span>  
 [<span data-ttu-id="9aaca-200">BizTalk Server 将 EDI 消息的发送</span><span class="sxs-lookup"><span data-stu-id="9aaca-200">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)