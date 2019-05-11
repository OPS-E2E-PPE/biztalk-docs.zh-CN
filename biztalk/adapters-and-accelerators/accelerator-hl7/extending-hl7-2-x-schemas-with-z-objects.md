---
title: 扩展 HL7 2.X 架构使用 Z 对象 |Microsoft Docs
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
ms.openlocfilehash: 514df3e1676e08d33be3a9fb00c61e47925b7b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267853"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a><span data-ttu-id="0cc19-102">使用 Z 对象扩展 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="0cc19-102">Extending HL7 2.X Schemas with Z Objects</span></span>
<span data-ttu-id="0cc19-103">HL7 组织定义 HL7 2.X 架构，并要求所有发件人和接收方，以便识别和使用这些架构，因为组织定义它们。</span><span class="sxs-lookup"><span data-stu-id="0cc19-103">The HL7 organization defines HL7 2.X schemas, and expects all senders and receivers to recognize and use these schemas as the organization defines them.</span></span> <span data-ttu-id="0cc19-104">符合这些架构可确保互操作性。</span><span class="sxs-lookup"><span data-stu-id="0cc19-104">Conforming to the schemas ensures for interoperability.</span></span> <span data-ttu-id="0cc19-105">但是，HL7 标准允许你自定义现有 HL7 2.X 架构为特定的本地目的。</span><span class="sxs-lookup"><span data-stu-id="0cc19-105">However, the HL7 standard enables you to customize existing HL7 2.X schemas for your specific local purposes.</span></span> <span data-ttu-id="0cc19-106">此外可以定义整个新架构和对象。</span><span class="sxs-lookup"><span data-stu-id="0cc19-106">You can also define entirely new schemas and objects.</span></span> <span data-ttu-id="0cc19-107">使用哪些 HL7 标准调用 Z 对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0cc19-107">You do so with what the HL7 standard calls Z objects.</span></span>  
  
 <span data-ttu-id="0cc19-108">标准 HL7 不定义 Z 对象的值。</span><span class="sxs-lookup"><span data-stu-id="0cc19-108">The HL7 standard does not define the value of Z objects.</span></span> <span data-ttu-id="0cc19-109">已发布的 HL7 架构不包含它们。</span><span class="sxs-lookup"><span data-stu-id="0cc19-109">The published HL7 schemas do not include them.</span></span> <span data-ttu-id="0cc19-110">可以定义它们本地，并使用它们的所有本地的参与方的协议。</span><span class="sxs-lookup"><span data-stu-id="0cc19-110">You define them locally, and use them by agreement with all local parties.</span></span> <span data-ttu-id="0cc19-111">HL7 组织保留所有消息类型、 触发器事件、 段、 数据类型和表名称以供此本地使用开头"Z"。</span><span class="sxs-lookup"><span data-stu-id="0cc19-111">The HL7 organization reserves all message type, trigger event, segment, data type, and table names beginning with "Z" for this local use.</span></span> <span data-ttu-id="0cc19-112">由于前缀，HL7 标准调用这些站点定义的对象 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="0cc19-112">Because of the prefix, the HL7 standard calls these site-defined objects Z objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cc19-113">当将 Z 对象添加到现有的 HL7 定义架构时，你可以结束该架构的多个版本。</span><span class="sxs-lookup"><span data-stu-id="0cc19-113">When you add a Z object to an existing HL7-defined schema, you may end up with multiple versions of that schema.</span></span> <span data-ttu-id="0cc19-114">处理这些多个版本的最佳方法是使用中的 Namespace 功能[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0cc19-114">The best way to handle these multiple versions is to use the Namespace feature in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="0cc19-115">您可以在找到此功能**验证**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 （在参与方级别）。</span><span class="sxs-lookup"><span data-stu-id="0cc19-115">You can find this feature on the **Validation** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (at the party level).</span></span> <span data-ttu-id="0cc19-116">您还需要更改部署该项目的架构中的命名空间属性。</span><span class="sxs-lookup"><span data-stu-id="0cc19-116">You will also need to change the namespace property within the schema that you deploy for that project.</span></span>  
  
 <span data-ttu-id="0cc19-117">在创建或处理 Z 对象中，应遵循的规则为 Z 对象建立 HL7 组织...</span><span class="sxs-lookup"><span data-stu-id="0cc19-117">In creating or processing Z objects, you should follow the rules that the HL7 organization has established for Z objects..</span></span>  
  
 <span data-ttu-id="0cc19-118">将 Z 对象添加到现有的架构或创建新的 Z 消息架构时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将使用 Z 对象具有架构来处理 HL7 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="0cc19-118">When you add a Z object to an existing schema or create a new Z message schema, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use the schema with the Z object(s) to process the HL7-encoded message.</span></span> <span data-ttu-id="0cc19-119">此类型的 Z 对象是声明的 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="0cc19-119">This type of Z object is a declared Z object.</span></span> <span data-ttu-id="0cc19-120">此外可以使用未声明的 Z 段，集成引擎不会处理根据消息架构。</span><span class="sxs-lookup"><span data-stu-id="0cc19-120">You can also use an undeclared Z segment, which the integration engine will not process according to the message schema.</span></span> <span data-ttu-id="0cc19-121">有关此类型的 Z 段的详细信息，请参阅[处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="0cc19-121">For more information about this type of Z segment, see [Handling Undeclared Z Segments](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0cc19-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="0cc19-122">In This Section</span></span>  
  
-   [<span data-ttu-id="0cc19-123">创建已声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="0cc19-123">Creating Declared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [<span data-ttu-id="0cc19-124">在架构中创建自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="0cc19-124">Creating Custom Data Types in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [<span data-ttu-id="0cc19-125">在架构中创建自定义表</span><span class="sxs-lookup"><span data-stu-id="0cc19-125">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [<span data-ttu-id="0cc19-126">扩展枚举</span><span class="sxs-lookup"><span data-stu-id="0cc19-126">Extending Enumerations</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [<span data-ttu-id="0cc19-127">通过 Z 对象自定义消息</span><span class="sxs-lookup"><span data-stu-id="0cc19-127">Customizing Messages through Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)