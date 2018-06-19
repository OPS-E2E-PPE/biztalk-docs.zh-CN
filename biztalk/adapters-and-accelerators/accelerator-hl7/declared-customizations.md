---
title: 声明自定义项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 767fdd543b1cb5d87bf3ec1c1943ac81d91c6ea4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204781"
---
# <a name="declared-customizations"></a><span data-ttu-id="e721d-102">声明的自定义项</span><span class="sxs-lookup"><span data-stu-id="e721d-102">Declared Customizations</span></span>
<span data-ttu-id="e721d-103">借助声明自定义，你可以修改或添加到 HL7 消息灵活。</span><span class="sxs-lookup"><span data-stu-id="e721d-103">With declared customizations, you have the flexibility of modifying or adding to HL7 messages.</span></span> <span data-ttu-id="e721d-104">你甚至可以定义新类型的消息。</span><span class="sxs-lookup"><span data-stu-id="e721d-104">You can even define a new type of message.</span></span> <span data-ttu-id="e721d-105">你可以在任何通过以下方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e721d-105">You can do this in any of the following ways:</span></span>  
  
-   <span data-ttu-id="e721d-106">通过定义新的消息类型或触发器事件更改一条消息的定义</span><span class="sxs-lookup"><span data-stu-id="e721d-106">Changing the definition of a message by defining a new message type or trigger event</span></span>  
  
-   <span data-ttu-id="e721d-107">将新段添加到现有的消息类型</span><span class="sxs-lookup"><span data-stu-id="e721d-107">Adding a new segment to an existing message type</span></span>  
  
-   <span data-ttu-id="e721d-108">更改现有的消息部分 （段、 字段、 组件或子组件） 的数据类型</span><span class="sxs-lookup"><span data-stu-id="e721d-108">Changing the data type of an existing message part (segment, field, component, or subcomponent)</span></span>  
  
-   <span data-ttu-id="e721d-109">更改可以使用现有的消息部分中的潜在值</span><span class="sxs-lookup"><span data-stu-id="e721d-109">Changing the potential values that you can use in an existing message part</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e721d-110">你可以更改声明的 Z 对象或 HL7 架构中的标准对象中使用的枚举值。</span><span class="sxs-lookup"><span data-stu-id="e721d-110">You can change the enumeration values used in declared Z objects or the standard objects in HL7 schemas.</span></span> <span data-ttu-id="e721d-111">若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="e721d-111">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
 <span data-ttu-id="e721d-112">修改或通过添加、 维护以及关联的当前定义的消息类型中的自定义对象将添加到 HL7 消息。</span><span class="sxs-lookup"><span data-stu-id="e721d-112">You modify or add to HL7 messages by adding, maintaining, and associating custom objects within the currently defined message types.</span></span> <span data-ttu-id="e721d-113">HL7 标准调用这些自定义对象"Z 对象"来区分它们来自符合 HL7 标准的现有对象。</span><span class="sxs-lookup"><span data-stu-id="e721d-113">The HL7 standards call these custom objects "Z objects" to distinguish them from existing objects that conform to the HL7 standard.</span></span> <span data-ttu-id="e721d-114">使用 BizTalk 编辑器定义 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="e721d-114">You use BizTalk Editor to define Z objects.</span></span> <span data-ttu-id="e721d-115">此外可以使用 BizTalk 编辑器若要使用的所有触发器事件传播到 Z 对象更新的功能和抽象的消息，其中包括它。</span><span class="sxs-lookup"><span data-stu-id="e721d-115">You also use BizTalk Editor to work with features that propagate updates to a Z object across all the trigger events and abstract messages that include it.</span></span> <span data-ttu-id="e721d-116">有关创建 Z 对象的详细信息，请参阅[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="e721d-116">For more information about creating Z objects, see [Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md).</span></span>  
  
 <span data-ttu-id="e721d-117">你可以使用 Z 对象来指定为可以以 HL7 标准中未指定的方式使用的段的本地定义。</span><span class="sxs-lookup"><span data-stu-id="e721d-117">You can use Z objects to give local definitions to segments that you use in ways not specified in the HL7 standard.</span></span> <span data-ttu-id="e721d-118">进行这些更改向架构的 HL7 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 在计算机上安装的安装向导。</span><span class="sxs-lookup"><span data-stu-id="e721d-118">You make these changes to the schemas that the BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Setup Wizard installed on your computer.</span></span> <span data-ttu-id="e721d-119">然后可以与其他共享这些修改的架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]与其交换消息的安装。</span><span class="sxs-lookup"><span data-stu-id="e721d-119">You can then share these modified schemas with other [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] installations with which you exchange messages.</span></span>  
  
## <a name="types-of-z-objects"></a><span data-ttu-id="e721d-120">类型的 Z 对象</span><span class="sxs-lookup"><span data-stu-id="e721d-120">Types of Z Objects</span></span>  
 <span data-ttu-id="e721d-121">HL7 标准 (2.X) 当前支持下列形式的自定义项：</span><span class="sxs-lookup"><span data-stu-id="e721d-121">The HL7 standard (2.X) currently supports the following forms of customization:</span></span>  
  
-   <span data-ttu-id="e721d-122">**自定义触发事件。**</span><span class="sxs-lookup"><span data-stu-id="e721d-122">**Custom trigger events.**</span></span> <span data-ttu-id="e721d-123">如果你在本地区域和需要新的消息结构，或想要支持不包含在标准的触发器事件，则可以创建使用 Z 作为前缀，例如，Z05 新触发器事件。</span><span class="sxs-lookup"><span data-stu-id="e721d-123">If you are at a local area and need a new message structure, or want to support a trigger event that is not included within the standard, you can create a new trigger event using a Z prefix, for example, Z05.</span></span> <span data-ttu-id="e721d-124">在这种情况下，必须定义抽象的消息和包含的段的模式来创建新的本地消息架构。</span><span class="sxs-lookup"><span data-stu-id="e721d-124">In this case, you must create a new local message schema by defining the abstract message and the pattern of included segments.</span></span>  
  
-   <span data-ttu-id="e721d-125">**自定义的段。**</span><span class="sxs-lookup"><span data-stu-id="e721d-125">**Custom segments.**</span></span> <span data-ttu-id="e721d-126">如果要在已受支持的触发器事件的因而需要进行其他数据的上下文中的本地区域可以创建新的段和包括分段内的需要的数据元素。</span><span class="sxs-lookup"><span data-stu-id="e721d-126">If you are at a local area, in the context of an already supported trigger event, and in need of additional data, you can create a new segment or segments and include the wanted data elements within the segment.</span></span> <span data-ttu-id="e721d-127">必须指定使用现有的 HL7 数据类型的段中的元素。</span><span class="sxs-lookup"><span data-stu-id="e721d-127">You must specify the elements within the segment using existing HL7 data types.</span></span> <span data-ttu-id="e721d-128">你可以通过在架构中创建一条新记录在 BizTalk 编辑器中，创建自定义 Z 段。</span><span class="sxs-lookup"><span data-stu-id="e721d-128">You can create custom Z segments in BizTalk Editor, by creating a new record in the schema.</span></span> <span data-ttu-id="e721d-129">有关详细信息，请参阅[创建声明 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="e721d-129">For more information, see [Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md).</span></span> <span data-ttu-id="e721d-130">或者，你可以添加通过访问数据库，然后将该 Z 段添加到消息结构的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="e721d-130">Alternatively, you can add a Z segment through the Access database, and then adding that Z segment to the message structure.</span></span> <span data-ttu-id="e721d-131">有关详细信息，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="e721d-131">For more information, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
-   <span data-ttu-id="e721d-132">**自定义数据子类型。**</span><span class="sxs-lookup"><span data-stu-id="e721d-132">**Custom data subtypes.**</span></span> <span data-ttu-id="e721d-133">HL7 例如提供支持的数据类型的列表、 格式化文本、 扫描图像，音频数据。</span><span class="sxs-lookup"><span data-stu-id="e721d-133">HL7 provides a list of supported data types, for example, formatted text, scanned image, audio data.</span></span> <span data-ttu-id="e721d-134">但是，如果你想要定义其他数据类型，你可以执行以便通过前缀用于"Z"助记键，从而创建 Z 数据键入。</span><span class="sxs-lookup"><span data-stu-id="e721d-134">However, if you want to define additional data types, you can do so by prefixing the mnemonic used with a "Z", thereby creating a Z data type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e721d-135">不允许的情况下，该标准中，若要创建新的数据类型，或将元素添加到现有段的范围内。</span><span class="sxs-lookup"><span data-stu-id="e721d-135">It is not permissible, within the confines of the standard, to create new data types or to add elements to an existing segment.</span></span> <span data-ttu-id="e721d-136">仍 less 是它允许以执行当前未使用的元素，它重新定义它以满足某些其他目的。</span><span class="sxs-lookup"><span data-stu-id="e721d-136">Still less is it permissible to take an element that is not currently used and to redefine it to meet some additional purpose.</span></span> <span data-ttu-id="e721d-137">另一方面，支持旧接口的组织可能需要适应这种做法。</span><span class="sxs-lookup"><span data-stu-id="e721d-137">On the other hand, organizations that support legacy interfaces may need to accommodate such practices.</span></span>  
  
-   <span data-ttu-id="e721d-138">**自定义的表。**</span><span class="sxs-lookup"><span data-stu-id="e721d-138">**Custom tables.**</span></span> <span data-ttu-id="e721d-139">消息中的许多现有对象有有限的特定值范围被枚举由 HL7 通用架构定义的表中所定义。</span><span class="sxs-lookup"><span data-stu-id="e721d-139">Many existing objects within messages have a limited range of specific values, as defined by enumerations in tables defined by HL7 common schemas.</span></span> <span data-ttu-id="e721d-140">你可以修改这些枚举，以通过创建 Z 表启用其他值。</span><span class="sxs-lookup"><span data-stu-id="e721d-140">You can modify these enumerations to enable additional values by creating Z tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e721d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e721d-141">See Also</span></span>  
 <span data-ttu-id="e721d-142">[未声明的自定义项](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="e721d-142">[Undeclared Customizations](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md) </span></span>  
 <span data-ttu-id="e721d-143">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e721d-143">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="e721d-144">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e721d-144">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="e721d-145">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="e721d-145">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="e721d-146">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="e721d-146">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)