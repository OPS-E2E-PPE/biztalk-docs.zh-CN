---
title: "BizTalk Server 中的 HL7 快捷键的术语表 |Microsoft 文档"
description: "常见术语和定义知道并了解用于 BizTalk Accelerator HL7"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffb9c18a-5fe5-448f-b115-0973e9d12952
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90a98fd1c30aed5bb38cca99774f610a59dedaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="glossary"></a><span data-ttu-id="b0f5b-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="b0f5b-103">Glossary</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="b0f5b-104">BizTalk Accelerator for HL7 使用以下术语和定义。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-104"> BizTalk Accelerator for HL7 uses the following terms and definitions.</span></span>

## <a name="a"></a><span data-ttu-id="b0f5b-105">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="b0f5b-105">A</span></span>    
 <span data-ttu-id="b0f5b-106">**项目**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-106">**artifact**  </span></span>  
 <span data-ttu-id="b0f5b-107">构成 HL7 V3.0 投票的项目将导致发现、 分析和设计活动导致的消息的规范创建可交付结果。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-107">The artifacts that comprise the HL7 V3.0 ballot are the deliverables resulting from the discovery, analysis, and design activities leading to the creation of message specifications.</span></span>  
  
 <span data-ttu-id="b0f5b-108">中的 HL7 V3.0 标准，构成文档的组件是项目。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-108">Within the HL7 V3.0 standards, the components that make up the documentation are artifacts.</span></span> <span data-ttu-id="b0f5b-109">这包括情节提要、 应用程序角色、 触发事件、 域的消息信息模型规范 (D MIMs)、 进行了优化的消息信息模型规范 (R MIMs)、 分层的消息说明 specificatins(HMDs)、 消息类型和交互。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-109">This includes storyboards, application roles, trigger events, Domain Message Information Model specifications (D-MIMs), Refined Message Information Model specifications (R-MIMs), Hierarchical Message Description specificatins(HMDs), message types, and interactions.</span></span>  
  
 <span data-ttu-id="b0f5b-110">**项目标识符**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-110">**artifact identifier**  </span></span>  
 <span data-ttu-id="b0f5b-111">技术委员会提交，并为每个项目提供了通过串联小节、 域和项目代码、 6 位数而非有意义数字、 2 位数字的领域代码，和 2 位数的版本号分配的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-111">A Technical Committee submits and gives each artifact a unique identifier that is assigned by concatenating the subsection, domain and artifact code, a 6-digit, non-meaningful number, a 2-digit Realm code, and a 2-digit version number.</span></span>  

## <a name="c"></a><span data-ttu-id="b0f5b-112">C</span><span class="sxs-lookup"><span data-stu-id="b0f5b-112">C</span></span>
  
 <span data-ttu-id="b0f5b-113">**基数**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-113">**cardinality**  </span></span>  
 <span data-ttu-id="b0f5b-114">数据元素 （数据元素内的对象视图的个别事件可能重复的时间数） 或分层消息说明 （最小和最大次数的消息元素） 中的列的属性。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-114">The property of a data element (the number of times a data element may repeat within an individual occurrence of an object view) or column in the Hierarchical Message Description (the minimum and maximum number of occurrences of the message element).</span></span> <span data-ttu-id="b0f5b-115">请参阅分层消息说明。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-115">See Hierarchical Message Description.</span></span>  
  
## <a name="d"></a><span data-ttu-id="b0f5b-116">D</span><span class="sxs-lookup"><span data-stu-id="b0f5b-116">D</span></span>   
 <span data-ttu-id="b0f5b-117">**域**</span><span class="sxs-lookup"><span data-stu-id="b0f5b-117">**domain**</span></span>    
 1. <span data-ttu-id="b0f5b-118">问题或使用者通过一组的 HL7 消息或由系统 （"应用程序域"） 进行寻址。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-118">The problem or subject to be addressed by a set of HL7 messages or by a system ("application domain").</span></span> <span data-ttu-id="b0f5b-119">卫生保健感兴趣的特定区域。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-119">A particular area of interest in health care.</span></span> 
 2. <span data-ttu-id="b0f5b-120">可能的值的数据类型、 属性或数据类型组件的组。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-120">The set of possible values of a data type, attribute, or data type component.</span></span> <span data-ttu-id="b0f5b-121">请参阅词汇域。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-121">See vocabulary domain.</span></span> 
 3. <span data-ttu-id="b0f5b-122">在 HL7，如药房，实验室，患者管理兴趣组。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-122">An interest group within HL7, such as Pharmacy, Laboratory, Patient Administration.</span></span>  
  
## <a name="e"></a><span data-ttu-id="b0f5b-123">E</span><span class="sxs-lookup"><span data-stu-id="b0f5b-123">E</span></span> 
 <span data-ttu-id="b0f5b-124">**事件**</span><span class="sxs-lookup"><span data-stu-id="b0f5b-124">**event**</span></span>    
 1. <span data-ttu-id="b0f5b-125">促进因素导致值得注意的状态更改的对象。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-125">A stimulus that causes a noteworthy state change of an object.</span></span> <span data-ttu-id="b0f5b-126">指示调用对象的行为的信号。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-126">A signal that invokes the behavior of an object.</span></span> <span data-ttu-id="b0f5b-127">请参阅触发器事件。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-127">See trigger event.</span></span> 
 2. <span data-ttu-id="b0f5b-128">语气词汇域值。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-128">A vocabulary domain value for Mood.</span></span>  
  
 
## <a name="h"></a><span data-ttu-id="b0f5b-129">H</span><span class="sxs-lookup"><span data-stu-id="b0f5b-129">H</span></span>
<span data-ttu-id="b0f5b-130">**分层消息说明 (HMD)**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-130">**Hierarchical Message Description (HMD)**  </span></span>  
 <span data-ttu-id="b0f5b-131">消息其分组、 序列、 可选性和基数的确切字段的规范。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-131">A specification of the exact fields of a message and their grouping, sequence, optionality, and cardinality.</span></span> <span data-ttu-id="b0f5b-132">包含一个或多个交互的消息类型，或者表示一个或多个常见的消息元素类型。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-132">Either contains message types for one or more interactions or represents one or more common message element types.</span></span> <span data-ttu-id="b0f5b-133">这是 HL7 消息的主要规范结构。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-133">This is the primary normative structure for HL7 messages.</span></span>  
  
## <a name="m"></a><span data-ttu-id="b0f5b-134">M</span><span class="sxs-lookup"><span data-stu-id="b0f5b-134">M</span></span>  
 <span data-ttu-id="b0f5b-135">**必需**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-135">**mandatory**  </span></span>  
 <span data-ttu-id="b0f5b-136">在分层消息说明 (HMD) 列。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-136">A column in the Hierarchical Message Description (HMD).</span></span> <span data-ttu-id="b0f5b-137">如果属性必备，基于此属性的所有消息元素包含必须包含非 null 值，或者它们必须具有不为 null 的默认值。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-137">If the inclusion for an attribute mandatory, all message elements based on this attribute must contain a non-null value, or they must have a default that is not null.</span></span>  
  
  
 <span data-ttu-id="b0f5b-138">**消息**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-138">**message**  </span></span>  
 <span data-ttu-id="b0f5b-139">一个信息包传递到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-139">A package of information communicated from one application to another.</span></span> <span data-ttu-id="b0f5b-140">请参阅消息类型和消息实例。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-140">See message type and message instance.</span></span>  
  
 <span data-ttu-id="b0f5b-141">**消息的开发框架 (MDF)**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-141">**Message Development Framework (MDF)**  </span></span>  
 <span data-ttu-id="b0f5b-142">模型、 方法和工具，前者构成用于指定 HL7 V3.0 消息的方法的集合。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-142">The collection of models, methods, and tools that comprise the methodology for specifying HL7 V3.0 messages.</span></span> <span data-ttu-id="b0f5b-143">HL7 标准的开发人员使用此框架。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-143">Developers of the HL7 standards use this framework.</span></span> <span data-ttu-id="b0f5b-144">V3.0 指南汇总了方法的内容。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-144">The V3.0 Guide summarizes the content of the methodology.</span></span>  
  
 <span data-ttu-id="b0f5b-145">**消息元素**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-145">**message element**  </span></span>  
 <span data-ttu-id="b0f5b-146">一种消息类型中的结构单位。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-146">A unit of structure within a message type.</span></span>  
  
 <span data-ttu-id="b0f5b-147">**消息元素类型**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-147">**message element type**  </span></span>  
 <span data-ttu-id="b0f5b-148">描述消息的元素之一的消息类型的部分。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-148">A portion of a message type that describes one of the elements of the message.</span></span>  
  
 <span data-ttu-id="b0f5b-149">**消息实例**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-149">**message instance**  </span></span>  
 <span data-ttu-id="b0f5b-150">为特定传输格式化消息。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-150">A message that is formatted for a specific transmission.</span></span> <span data-ttu-id="b0f5b-151">相同的消息类型可描述两条消息且标识具有相同的交互和值、 存在，或缺乏所发送的数据和不同基数的集合中的变体由于在实例尚未存在差异。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-151">The same message type can describe two messages  and identify with the same interaction and yet vary in the instance because of variations in values, presence, or absence of the data being sent and different cardinalities of collections.</span></span> <span data-ttu-id="b0f5b-152">否则，相同的消息可能在不同的实例，如果在不同时间或按不同的发件人发送。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-152">Otherwise, identical messages may be different instances if they are sent at different times or by a different sender.</span></span>  
  
 <span data-ttu-id="b0f5b-153">**消息负载**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-153">**message payload**  </span></span>  
 <span data-ttu-id="b0f5b-154">消息中传送数据。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-154">Data carried in a message.</span></span>  
  
 <span data-ttu-id="b0f5b-155">**消息类型**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-155">**message type**  </span></span>  
 <span data-ttu-id="b0f5b-156">指定在分层消息说明 (HMD) 的消息元素组织。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-156">The organization of message elements that is specified in a Hierarchical Message Description (HMD).</span></span> <span data-ttu-id="b0f5b-157">每种消息类型是作为一部分交互模型中的一个或多个交互传达的。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-157">Each message type is communicated as part of one or more interactions in the interaction model.</span></span> <span data-ttu-id="b0f5b-158">消息类型实际上构成一套用于构造一条消息，给定一组特定的实例数据的规则。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-158">A message type in effect constitutes a set of rules for constructing a message given a specific set of instance data.</span></span> <span data-ttu-id="b0f5b-159">它还定义用于分析一条消息，还原实例数据的规则。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-159">It also defines the rules for parsing a message to recover the instance data.</span></span> <span data-ttu-id="b0f5b-160">消息类型的实现技术规范，无关，因此，如果使用相同的消息类型和不同的实现技术规范发送相同的数据，可以从相互转译消息类型。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-160">The message type is independent of the Implementation Technology Specification, so that if the same data is sent using the same message type and different implementation technology specifications, the message type can be transliterated from one to the other.</span></span>  

## <a name="p"></a><span data-ttu-id="b0f5b-161">P</span><span class="sxs-lookup"><span data-stu-id="b0f5b-161">P</span></span>  
 <span data-ttu-id="b0f5b-162">**属性**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-162">**property**  </span></span>  
 <span data-ttu-id="b0f5b-163">任何属性、 关联、 方法或类或对象定义的状态模型。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-163">Any attribute, association, method, or state model defined for a class or object.</span></span> <span data-ttu-id="b0f5b-164">在 HMD，状态将类、 属性或关联的角色名称作为它的名称的列会显示在引用信息模型 (RIM)。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-164">In an HMD, the column that states the name of the class, attribute, or association role name as it appears in the Reference Information Model (RIM).</span></span>  

## <a name="r"></a><span data-ttu-id="b0f5b-165">R</span><span class="sxs-lookup"><span data-stu-id="b0f5b-165">R</span></span>  
 <span data-ttu-id="b0f5b-166">**参考信息模型 (RIM)**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-166">**Reference Information Model (RIM)**  </span></span>  
 <span data-ttu-id="b0f5b-167">HL7 信息模型的所有其他信息模型 (例如，R MIMs) 和消息派生。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-167">The HL7 information model from which all other information models (for example, R-MIMs) and messages derive.</span></span>  
  
 <span data-ttu-id="b0f5b-168">**完善的消息信息模型 (R MIM)**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-168">**Refined Message Information Model (R-MIM)**  </span></span>  
 <span data-ttu-id="b0f5b-169">信息结构，它表示一组消息的要求。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-169">An information structure that represents the requirements for a set of messages.</span></span> <span data-ttu-id="b0f5b-170">可能包含从 RIM 类克隆的其他类的边缘约束的子集。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-170">A constrained subset of the RIM that may contain additional classes that are cloned from RIM classes.</span></span> <span data-ttu-id="b0f5b-171">包含类、 属性、 关联和数据类型来支持一个或多个分层消息说明 (HMDs)。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-171">Contains those classes, attributes, associations, and data types that are needed to support one or more Hierarchical Message Description (HMDs).</span></span> <span data-ttu-id="b0f5b-172">一条消息可以显示为 R MIM 中的类通过特定途径。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-172">A single message can be shown as a particular pathway through the classes within an R-MIM.</span></span>  

## <a name="s"></a><span data-ttu-id="b0f5b-173">S</span><span class="sxs-lookup"><span data-stu-id="b0f5b-173">S</span></span>  
 <span data-ttu-id="b0f5b-174">**方案**  </span><span class="sxs-lookup"><span data-stu-id="b0f5b-174">**scenario**  </span></span>  
 <span data-ttu-id="b0f5b-175">在统一建模语言 (UML)，"通过的单个用例的执行的单个路径"。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-175">In Unified Modeling Language (UML), "a single path of execution through a single use case".</span></span> <span data-ttu-id="b0f5b-176">为适用于卫生保健的交互的序列定义事件的语句。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-176">A statement of events defined as a sequence of interactions relevant in health care.</span></span> <span data-ttu-id="b0f5b-177">方案提供了一套建模 committee 需要在域中，通常会出现的交互。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-177">The scenario provides one set of interactions that the modeling committee expects to typically occur in the domain.</span></span> <span data-ttu-id="b0f5b-178">通常情况下，将构造序列图来显示一组对于单个方案的交互。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-178">Usually, a sequence diagram is constructed to show a group of interactions for a single scenario.</span></span> <span data-ttu-id="b0f5b-179">每个方案显示为交互模型的子集。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-179">Each scenario is displayed as a subset of the interaction model.</span></span>  
  
 <span data-ttu-id="b0f5b-180">**架构**</span><span class="sxs-lookup"><span data-stu-id="b0f5b-180">**schema**</span></span>    
 1. <span data-ttu-id="b0f5b-181">图表的演示文稿、 结构化的框架中或计划。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-181">A diagrammatic presentation, a structured framework, or a plan.</span></span> 
 2. <span data-ttu-id="b0f5b-182">一组需要在文档或数据集是该语法的有效表达式的上下文中的顺序，需满足的要求。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-182">A set of requirements that need to be met in order for a document or set of data to be a valid expression within the context of that grammar.</span></span> <span data-ttu-id="b0f5b-183">XML 架构是文档的结构或数据集的规范标准通用标记语言 (SGML) 中。</span><span class="sxs-lookup"><span data-stu-id="b0f5b-183">An XML schema is a specification in Standard Generalized Markup Language (SGML) of the structure of a document or set of data.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0f5b-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b0f5b-184">Next steps</span></span>
[<span data-ttu-id="b0f5b-185">方-BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="b0f5b-185">Parties - BTAHL7 Configuration Explorer</span></span>](parties-tab.md)  
[<span data-ttu-id="b0f5b-186">全局设置-BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="b0f5b-186">Global Settings - BTAHL7 Configuration Explorer</span></span>](global-settings-tab.md)  
[<span data-ttu-id="b0f5b-187">MLLP 传输属性对话框的 UI 帮助</span><span class="sxs-lookup"><span data-stu-id="b0f5b-187">MLLP Transport Properties Dialog Box UI Help</span></span>](mllp-transport-properties-dialog-box-ui-help.md)