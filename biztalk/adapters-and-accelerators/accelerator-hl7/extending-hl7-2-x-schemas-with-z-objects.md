---
title: 扩展 HL7 2.X 架构具有 Z 对象 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204653"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a><span data-ttu-id="bb079-102">扩展 HL7 2.X 架构具有 Z 对象</span><span class="sxs-lookup"><span data-stu-id="bb079-102">Extending HL7 2.X Schemas with Z Objects</span></span>
<span data-ttu-id="bb079-103">HL7 组织定义 HL7 2.X 架构，并要求所有发件人和接收方，来识别并使用这些架构，因为组织定义它们。</span><span class="sxs-lookup"><span data-stu-id="bb079-103">The HL7 organization defines HL7 2.X schemas, and expects all senders and receivers to recognize and use these schemas as the organization defines them.</span></span> <span data-ttu-id="bb079-104">符合架构时，可确保的互操作性。</span><span class="sxs-lookup"><span data-stu-id="bb079-104">Conforming to the schemas ensures for interoperability.</span></span> <span data-ttu-id="bb079-105">但是，HL7 标准允许你自定义现有 HL7 2.X 架构为你特定的本地目的。</span><span class="sxs-lookup"><span data-stu-id="bb079-105">However, the HL7 standard enables you to customize existing HL7 2.X schemas for your specific local purposes.</span></span> <span data-ttu-id="bb079-106">你还可以定义全新的架构和对象。</span><span class="sxs-lookup"><span data-stu-id="bb079-106">You can also define entirely new schemas and objects.</span></span> <span data-ttu-id="bb079-107">使用哪些 HL7 标准调用 Z 对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bb079-107">You do so with what the HL7 standard calls Z objects.</span></span>  
  
 <span data-ttu-id="bb079-108">标准 HL7 未定义 Z 对象的值。</span><span class="sxs-lookup"><span data-stu-id="bb079-108">The HL7 standard does not define the value of Z objects.</span></span> <span data-ttu-id="bb079-109">已发布的 HL7 架构不包含它们。</span><span class="sxs-lookup"><span data-stu-id="bb079-109">The published HL7 schemas do not include them.</span></span> <span data-ttu-id="bb079-110">可以定义这些本地，并通过与所有本地方协议使用它们。</span><span class="sxs-lookup"><span data-stu-id="bb079-110">You define them locally, and use them by agreement with all local parties.</span></span> <span data-ttu-id="bb079-111">HL7 组织保留所有消息类型、 触发器事件、 段、 数据类型和表名称以"Z"开头为此本地使用。</span><span class="sxs-lookup"><span data-stu-id="bb079-111">The HL7 organization reserves all message type, trigger event, segment, data type, and table names beginning with "Z" for this local use.</span></span> <span data-ttu-id="bb079-112">由于前缀，HL7 标准调用这些站点定义对象 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="bb079-112">Because of the prefix, the HL7 standard calls these site-defined objects Z objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb079-113">当你将 Z 对象添加到现有的 HL7 定义架构时，你可以结束使用该架构的多个版本。</span><span class="sxs-lookup"><span data-stu-id="bb079-113">When you add a Z object to an existing HL7-defined schema, you may end up with multiple versions of that schema.</span></span> <span data-ttu-id="bb079-114">若要处理这些多个版本的最佳方式是使用中的 Namespace 功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb079-114">The best way to handle these multiple versions is to use the Namespace feature in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="bb079-115">您可以在找到此功能**验证**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 （在方级别）。</span><span class="sxs-lookup"><span data-stu-id="bb079-115">You can find this feature on the **Validation** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (at the party level).</span></span> <span data-ttu-id="bb079-116">你还需要更改在部署该项目的架构中的命名空间属性。</span><span class="sxs-lookup"><span data-stu-id="bb079-116">You will also need to change the namespace property within the schema that you deploy for that project.</span></span>  
  
 <span data-ttu-id="bb079-117">在创建或处理 Z 对象时，你应遵循 HL7 组织已建立的 Z 对象的规则...</span><span class="sxs-lookup"><span data-stu-id="bb079-117">In creating or processing Z objects, you should follow the rules that the HL7 organization has established for Z objects..</span></span>  
  
 <span data-ttu-id="bb079-118">当你将 Z 对象添加到现有架构或创建一个新的 Z 消息架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将使用具有 Z 对象架构来处理 HL7 编码消息。</span><span class="sxs-lookup"><span data-stu-id="bb079-118">When you add a Z object to an existing schema or create a new Z message schema, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use the schema with the Z object(s) to process the HL7-encoded message.</span></span> <span data-ttu-id="bb079-119">此类型的 Z 对象是一个声明的 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="bb079-119">This type of Z object is a declared Z object.</span></span> <span data-ttu-id="bb079-120">你还可以使用未声明的 Z 段，该集成引擎不会根据消息架构处理。</span><span class="sxs-lookup"><span data-stu-id="bb079-120">You can also use an undeclared Z segment, which the integration engine will not process according to the message schema.</span></span> <span data-ttu-id="bb079-121">有关此类型的 Z 段的详细信息，请参阅[处理未声明 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="bb079-121">For more information about this type of Z segment, see [Handling Undeclared Z Segments](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb079-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="bb079-122">In This Section</span></span>  
  
-   [<span data-ttu-id="bb079-123">创建声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="bb079-123">Creating Declared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [<span data-ttu-id="bb079-124">在架构中创建自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="bb079-124">Creating Custom Data Types in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [<span data-ttu-id="bb079-125">在架构中创建自定义的表</span><span class="sxs-lookup"><span data-stu-id="bb079-125">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [<span data-ttu-id="bb079-126">扩展枚举</span><span class="sxs-lookup"><span data-stu-id="bb079-126">Extending Enumerations</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [<span data-ttu-id="bb079-127">自定义消息通过 Z 对象</span><span class="sxs-lookup"><span data-stu-id="bb079-127">Customizing Messages through Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)