---
title: "为动态的消息类型发现创建自定义标头架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: befed0c7e7f5754cdf901e91698ed7269621d4b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a><span data-ttu-id="736e5-102">为动态的消息类型发现创建自定义标头架构</span><span class="sxs-lookup"><span data-stu-id="736e5-102">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>
<span data-ttu-id="736e5-103">在大多数情况下，应为 SWIFT 反汇编程序 SWIFT 标头架构配置属性来指定默认 SWIFT 标头架构 (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema)。</span><span class="sxs-lookup"><span data-stu-id="736e5-103">In most scenarios, you should specify the default SWIFT header schema (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) for the SWIFT Header Schema configuration property of the SWIFT disassembler.</span></span> <span data-ttu-id="736e5-104">SWIFT 反汇编程序使用默认 SWIFT 标头架构来分析消息标头符合 SWIFT 标准规范，并具有所需的提升到的属性促进动态架构解析 （和"双 type"的子类型解析SWIFT 消息，如 MT574_IRSLST 和 MT574_W8BENO）。</span><span class="sxs-lookup"><span data-stu-id="736e5-104">The SWIFT disassembler uses the default SWIFT header schema to parse message headers that conform to the SWIFT standard specification, and has the necessary promoted properties to facilitate dynamic schema resolution (and sub-type resolution for "dual type" SWIFT messages like MT574_IRSLST and MT574_W8BENO).</span></span> <span data-ttu-id="736e5-105">有关默认 SWIFT 标头架构并了解如何 SWIFT 反汇编程序执行架构解析的详细信息，请参阅[动态消息类型发现和架构解决](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="736e5-105">For more information about the default SWIFT header schema and to understand how the SWIFT disassembler performs schema resolution, see [Dynamic Message Type Discovery and Schema Resolution](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span></span>  
  
 <span data-ttu-id="736e5-106">对于其他方案，其中的消息包含非 SWIFT 标准标头数据，可用于自定义标头架构标头分析和动态消息类型发现。</span><span class="sxs-lookup"><span data-stu-id="736e5-106">For other scenarios where messages contain non-SWIFT standard header data, you can use a custom header schema for header parsing and dynamic message type discovery.</span></span> <span data-ttu-id="736e5-107">若要创建和自定义标头架构用于动态架构解析，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="736e5-107">To create and use a custom header schema for dynamic schema resolution, do the following:</span></span>  
  
1.  <span data-ttu-id="736e5-108">创建自定义架构 SWIFT 反汇编程序可用于结构上分析的预期的标头数据格式。</span><span class="sxs-lookup"><span data-stu-id="736e5-108">Create a custom schema that the SWIFT disassembler can use to structurally parse the expected header data format.</span></span>  
  
2.  <span data-ttu-id="736e5-109">标识架构中的哪些字段将保存的值，该值指示消息类型。</span><span class="sxs-lookup"><span data-stu-id="736e5-109">Identify which fields in the schema will hold the value(s) indicating message type.</span></span>  
  
3.  <span data-ttu-id="736e5-110">将 A4SWIFT 属性架构 (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) 添加到的"属性架构列表"的自定义标头架构并将提升到相应的字段，用于指示消息类型使用以下[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]属性：</span><span class="sxs-lookup"><span data-stu-id="736e5-110">Add the A4SWIFT Property Schema (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) to the "Property schemas list" of the custom header schema and promote the appropriate fields that indicate message type using the following [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] properties:</span></span>  
  
    -   <span data-ttu-id="736e5-111">**A4SWIFT_MessageType**</span><span class="sxs-lookup"><span data-stu-id="736e5-111">**A4SWIFT_MessageType**</span></span>  
  
    -   <span data-ttu-id="736e5-112">**A4SWIFT_MessageType2** (可选如果**A4SWIFT_MessageTypes**使用)</span><span class="sxs-lookup"><span data-stu-id="736e5-112">**A4SWIFT_MessageType2** (optional if **A4SWIFT_MessageTypes** is used)</span></span>  
  
    -   <span data-ttu-id="736e5-113">**A4SWIFT_SecondaryMessageType** （可选）</span><span class="sxs-lookup"><span data-stu-id="736e5-113">**A4SWIFT_SecondaryMessageType** (optional)</span></span>  
  
4.  <span data-ttu-id="736e5-114">生成和部署自定义标头架构。</span><span class="sxs-lookup"><span data-stu-id="736e5-114">Build and deploy the custom header schema.</span></span>  
  
5.  <span data-ttu-id="736e5-115">设置为自定义标头架构 SWIFT 反汇编程序 （在你接收的管道项目） 的 SWIFT 标头架构配置属性。</span><span class="sxs-lookup"><span data-stu-id="736e5-115">Set the SWIFT Header Schema configuration property of the SWIFT disassembler (in your receive pipeline project) to the custom header schema.</span></span>  
  
 <span data-ttu-id="736e5-116">有关这些及其他提升的属性的详细信息，请参阅[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="736e5-116">For more information about these and other promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span> <span data-ttu-id="736e5-117">有关使用 BizTalk 编辑器来创建和编辑架构、 升级属性使用属性架构，并生成和部署架构项目的详细信息，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="736e5-117">For more information about using BizTalk Editor to create and edit schemas, promote properties using a property schema, and build and deploy schema projects, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="736e5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="736e5-118">See Also</span></span>  
 [<span data-ttu-id="736e5-119">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="736e5-119">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)