---
title: HL7 消息结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- trigger events
- messages, trigger events
- segments, messages
- messages, message structure
ms.assetid: 4dbef56d-97ae-466d-bc8a-dc96c40896f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a298a21b7df2605cdb8dc181898808c94cf40b33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996950"
---
# <a name="hl7-message-structure"></a><span data-ttu-id="a6aeb-102">HL7 消息结构</span><span class="sxs-lookup"><span data-stu-id="a6aeb-102">HL7 Message Structure</span></span>
<span data-ttu-id="a6aeb-103">HL7 消息是与触发器事件相关联的层次结构。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-103">An HL7 message is a hierarchical structure associated with a trigger event.</span></span> <span data-ttu-id="a6aeb-104">HL7 标准定义为"卫生保健 （，），所以需要在系统之间流动的数据的真实世界中的事件"的触发器事件。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-104">The HL7 standard defines trigger event as "an event in the real world of health care (that) creates the need for data to flow among systems".</span></span> <span data-ttu-id="a6aeb-105">每个触发器事件都与定义的消息需要支持的触发器事件的数据类型的抽象消息相关联。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-105">Each trigger event is associated with an abstract message that defines the type of data that the message needs to support the trigger event.</span></span> <span data-ttu-id="a6aeb-106">抽象的消息是一系列段，并将重复和有关这些段包含的规则。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-106">The abstract message is a collection of segments, and includes the rules of repetition and inclusion for those segments.</span></span> <span data-ttu-id="a6aeb-107">下表显示了与触发器事件 A04 – 注册患者相关联的抽象消息的示例。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-107">The following table shows an example of an abstract message associated with the trigger event A04 – Register Patient.</span></span>  
  
|<span data-ttu-id="a6aeb-108">触发器事件</span><span class="sxs-lookup"><span data-stu-id="a6aeb-108">Trigger event</span></span>|<span data-ttu-id="a6aeb-109">抽象的消息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-109">Abstract message</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="a6aeb-110">ADT ^ A04 ^ ADT_A01</span><span class="sxs-lookup"><span data-stu-id="a6aeb-110">ADT^A04^ADT_A01</span></span>|<span data-ttu-id="a6aeb-111">病人入院、 放电装置和传输</span><span class="sxs-lookup"><span data-stu-id="a6aeb-111">Admissions, Discharge, and Transfer</span></span>|  
|<span data-ttu-id="a6aeb-112">MSH</span><span class="sxs-lookup"><span data-stu-id="a6aeb-112">MSH</span></span>|<span data-ttu-id="a6aeb-113">消息标头</span><span class="sxs-lookup"><span data-stu-id="a6aeb-113">Message Header</span></span>|  
|<span data-ttu-id="a6aeb-114">EVN</span><span class="sxs-lookup"><span data-stu-id="a6aeb-114">EVN</span></span>|<span data-ttu-id="a6aeb-115">事件类型</span><span class="sxs-lookup"><span data-stu-id="a6aeb-115">Event Type</span></span>|  
|<span data-ttu-id="a6aeb-116">PID</span><span class="sxs-lookup"><span data-stu-id="a6aeb-116">PID</span></span>|<span data-ttu-id="a6aeb-117">患者识别</span><span class="sxs-lookup"><span data-stu-id="a6aeb-117">Patient Identification</span></span>|  
|<span data-ttu-id="a6aeb-118">[PD1]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-118">[  PD1  ]</span></span>|<span data-ttu-id="a6aeb-119">其他人口统计信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-119">Additional Demographics</span></span>|  
|<span data-ttu-id="a6aeb-120">[{ROL}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-120">[{ ROL }]</span></span>|<span data-ttu-id="a6aeb-121">角色</span><span class="sxs-lookup"><span data-stu-id="a6aeb-121">Role</span></span>|  
|<span data-ttu-id="a6aeb-122">[{NK1}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-122">[{ NK1 }]</span></span>|<span data-ttu-id="a6aeb-123">下一步的系列: / 相关联的参与方</span><span class="sxs-lookup"><span data-stu-id="a6aeb-123">Next of Kin / Associated Parties</span></span>|  
|<span data-ttu-id="a6aeb-124">PV1</span><span class="sxs-lookup"><span data-stu-id="a6aeb-124">PV1</span></span>|<span data-ttu-id="a6aeb-125">患者，请访问</span><span class="sxs-lookup"><span data-stu-id="a6aeb-125">Patient Visit</span></span>|  
|<span data-ttu-id="a6aeb-126">[PV2]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-126">[  PV2  ]</span></span>|<span data-ttu-id="a6aeb-127">患者访问的其他信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-127">Patient Visit - Additional Information</span></span>|  
|<span data-ttu-id="a6aeb-128">[{ROL}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-128">[{ ROL }]</span></span>|<span data-ttu-id="a6aeb-129">角色</span><span class="sxs-lookup"><span data-stu-id="a6aeb-129">Role</span></span>|  
|<span data-ttu-id="a6aeb-130">[{DB1}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-130">[{ DB1 }]</span></span>|<span data-ttu-id="a6aeb-131">伤残信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-131">Disability Information</span></span>|  
|<span data-ttu-id="a6aeb-132">[{OBX}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-132">[{ OBX }]</span></span>|<span data-ttu-id="a6aeb-133">观察/结果</span><span class="sxs-lookup"><span data-stu-id="a6aeb-133">Observation/Result</span></span>|  
|<span data-ttu-id="a6aeb-134">[{AL1}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-134">[{ AL1 }]</span></span>|<span data-ttu-id="a6aeb-135">过敏信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-135">Allergy Information</span></span>|  
|<span data-ttu-id="a6aeb-136">[{DG1}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-136">[{ DG1 }]</span></span>|<span data-ttu-id="a6aeb-137">诊断信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-137">Diagnosis Information</span></span>|  
|<span data-ttu-id="a6aeb-138">[DRG]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-138">[  DRG  ]</span></span>|<span data-ttu-id="a6aeb-139">诊断相关的组</span><span class="sxs-lookup"><span data-stu-id="a6aeb-139">Diagnosis Related Group</span></span>|  
|<span data-ttu-id="a6aeb-140">[{</span><span class="sxs-lookup"><span data-stu-id="a6aeb-140">[{</span></span>||  
|<span data-ttu-id="a6aeb-141">PR1</span><span class="sxs-lookup"><span data-stu-id="a6aeb-141">PR1</span></span>|<span data-ttu-id="a6aeb-142">过程</span><span class="sxs-lookup"><span data-stu-id="a6aeb-142">Procedures</span></span>|  
|<span data-ttu-id="a6aeb-143">[{ROL}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-143">[{ ROL }]</span></span>|<span data-ttu-id="a6aeb-144">角色</span><span class="sxs-lookup"><span data-stu-id="a6aeb-144">Role</span></span>|  
|<span data-ttu-id="a6aeb-145">}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-145">}]</span></span>||  
|<span data-ttu-id="a6aeb-146">[{GT1}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-146">[{ GT1 } ]</span></span>|<span data-ttu-id="a6aeb-147">担保人担保</span><span class="sxs-lookup"><span data-stu-id="a6aeb-147">Guarantor</span></span>|  
|<span data-ttu-id="a6aeb-148">[{</span><span class="sxs-lookup"><span data-stu-id="a6aeb-148">[{</span></span>||  
|<span data-ttu-id="a6aeb-149">IN1</span><span class="sxs-lookup"><span data-stu-id="a6aeb-149">IN1</span></span>|<span data-ttu-id="a6aeb-150">保险</span><span class="sxs-lookup"><span data-stu-id="a6aeb-150">Insurance</span></span>|  
|<span data-ttu-id="a6aeb-151">输入 [2]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-151">[  IN2 ]</span></span>|<span data-ttu-id="a6aeb-152">保险的其他信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-152">Insurance Additional Information</span></span>|  
|<span data-ttu-id="a6aeb-153">[{IN3}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-153">[{ IN3 }]</span></span>|<span data-ttu-id="a6aeb-154">保险的其他信息的证书。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-154">Insurance Additional Information - Cert.</span></span>|  
|<span data-ttu-id="a6aeb-155">[{ROL}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-155">[{ ROL }]</span></span>|<span data-ttu-id="a6aeb-156">角色</span><span class="sxs-lookup"><span data-stu-id="a6aeb-156">Role</span></span>|  
|<span data-ttu-id="a6aeb-157">}]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-157">}]</span></span>||  
|<span data-ttu-id="a6aeb-158">[访问排序]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-158">[  ACC  ]</span></span>|<span data-ttu-id="a6aeb-159">意外的信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-159">Accident Information</span></span>|  
|<span data-ttu-id="a6aeb-160">[UB1]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-160">[  UB1  ]</span></span>|<span data-ttu-id="a6aeb-161">通用的帐单信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-161">Universal Bill Information</span></span>|  
|<span data-ttu-id="a6aeb-162">[UB2]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-162">[  UB2  ]</span></span>|<span data-ttu-id="a6aeb-163">通用帐单 92年信息</span><span class="sxs-lookup"><span data-stu-id="a6aeb-163">Universal Bill 92 Information</span></span>|  
|<span data-ttu-id="a6aeb-164">[PDA]</span><span class="sxs-lookup"><span data-stu-id="a6aeb-164">[  PDA  ]</span></span>|<span data-ttu-id="a6aeb-165">患者死亡和检查</span><span class="sxs-lookup"><span data-stu-id="a6aeb-165">Patient Death and Autopsy</span></span>|  
  
 <span data-ttu-id="a6aeb-166">上面的方括号"["，"]"指示一段或一组段是可选的而大括号"{"，"}"指示段或段重复的组。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-166">The brackets above "[", "]" indicate that a segment or group of segments is optional, while braces "{", "}" indicate the segment or group of segments repeat.</span></span>  
  
 <span data-ttu-id="a6aeb-167">段是一组字段其中每个符合特定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-167">A segment is a group of fields each of which conforms to a particular data type.</span></span> <span data-ttu-id="a6aeb-168">字段可以具有简单或复杂的结构。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-168">Fields can have a simple or complex structure.</span></span> <span data-ttu-id="a6aeb-169">它们包含的组件根据其数据类型定义中定义的规则。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-169">They consist of components according to the rules defined in their data-type definition.</span></span> <span data-ttu-id="a6aeb-170">为了支持更复杂的数据类型，某些组件可能会包含子组件。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-170">In order to support the more complex data types, some components may consist of subcomponents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6aeb-171">HL7 消息编码使用指定的分隔符的事实限制一名开发人员能够引入新的细分数据的方法。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-171">The fact that HL7 message encoding uses specified delimiters limits the ability of a developer to introduce new ways of subdividing the data.</span></span> <span data-ttu-id="a6aeb-172">可以是任何子子组件，因为这需要发明的新的分隔符类型。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-172">There can be no sub-subcomponent, since this would require invention of a new delimiter type.</span></span>  
  
 <span data-ttu-id="a6aeb-173">第一个 HL7 规范未定义抽象的消息。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-173">The first HL7 specifications did not define the abstract message.</span></span> <span data-ttu-id="a6aeb-174">抽象的消息是与触发器事件相关联的段的模式。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-174">The abstract message is the pattern of segments associated with a trigger event.</span></span> <span data-ttu-id="a6aeb-175">同样，HL7 消息包含在一起，重复或分段组的段的集合。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-175">Similarly, HL7 messages contain collections of segments that repeat together, or segment groups.</span></span> <span data-ttu-id="a6aeb-176">第一个 HL7 规范未定义段组。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-176">The first HL7 specifications did not define segment groups.</span></span> <span data-ttu-id="a6aeb-177">使用适用于版本 V2.3.1，开始，一直在后续版本中，这将更改由于需要支持 XML 编码。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-177">Starting with V2.3.1, and continuing in the subsequent versions, this changed due to the need to support XML encoding.</span></span> <span data-ttu-id="a6aeb-178">例如，上面的触发器事件表中的消息结构的名称是"ADT_A01"。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-178">For example, in the Trigger Event table above, the name of the message structure is "ADT_A01".</span></span> <span data-ttu-id="a6aeb-179">这是相同的模式用于支持 A01 – 承认患者的线段。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-179">This is the same pattern of segments used to support A01 – Admit Patient.</span></span> <span data-ttu-id="a6aeb-180">为方便起见，对应于消息结构的名称 （在方面 HL7 文档内的位置） 的第一个触发事件，使用它们。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-180">For convenience, the names of message structures correspond to the first (in terms of placement within the HL7 document) trigger event that uses them.</span></span> <span data-ttu-id="a6aeb-181">同样，触发器事件上表开头 IN1，包括输入 2、 IN3 和 ROL 中的段组重复作为一个组。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-181">Similarly, the group of segments in the Trigger Event table above that starts with IN1, including IN2, IN3, and ROL, repeats as a group.</span></span> <span data-ttu-id="a6aeb-182">其名称，从版本 2.5 开始是"保险"组。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-182">Its name—starting with Version 2.5 is "Insurance" group.</span></span>  
  
 <span data-ttu-id="a6aeb-183">在版本 2 中，版本间的兼容性规则通过要求标准的后续版本，不包括以前的版本使之无效的结构支持的接口的演变。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-183">In Version 2, the inter-version compatibility rules support evolution of interfaces by requiring that subsequent versions of the standard not include structures that invalidate prior versions.</span></span> <span data-ttu-id="a6aeb-184">这需要你未删除的触发器事件和执行不使用的触发器事件用于其他目的或使用不同的抽象消息比最初预期。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-184">This requires that you do not remove a trigger event and that you do not use a trigger event for a different purpose or with a different abstract message than originally intended.</span></span> <span data-ttu-id="a6aeb-185">对于抽象的消息，这意味着，不能删除一个段从一条消息，也可以使可选必需段或重复段非重复。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-185">For abstract messages, this implies that you cannot remove a segment from a message, nor can you make a mandatory segment optional or a repeating segment non-repeating.</span></span> <span data-ttu-id="a6aeb-186">如果添加一个段，您必须执行在消息的结尾或在消息中重复组的末尾。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-186">If you add a segment, you must do so at the end of a message or at the end of a repeating group within a message.</span></span>  
  
 <span data-ttu-id="a6aeb-187">Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="a6aeb-187">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="a6aeb-188">所有触发器事件和消息结构从 2.1 版开始，一直到版本 2.5 的支持。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-188">Support of all trigger events and message structures starting with V2.1 and continuing through V2.5.</span></span>  
  
-   <span data-ttu-id="a6aeb-189">通过添加段并根据需要调整段和重复的本地化支持。</span><span class="sxs-lookup"><span data-stu-id="a6aeb-189">Support of localization through adding segments and tailoring segment optionally and repetition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6aeb-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6aeb-190">See Also</span></span>  
 <span data-ttu-id="a6aeb-191">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a6aeb-191">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="a6aeb-192">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="a6aeb-192">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="a6aeb-193">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="a6aeb-193">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)