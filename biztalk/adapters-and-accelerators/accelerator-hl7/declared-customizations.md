---
title: 声明自定义设置 |Microsoft Docs
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
ms.openlocfilehash: 091612d1ad15f7ea841b5936beba1fcf7fc26ddf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988262"
---
# <a name="declared-customizations"></a><span data-ttu-id="45d28-102">声明自定义项</span><span class="sxs-lookup"><span data-stu-id="45d28-102">Declared Customizations</span></span>
<span data-ttu-id="45d28-103">使用声明的自定义项，可以修改或添加到 HL7 消息的灵活性。</span><span class="sxs-lookup"><span data-stu-id="45d28-103">With declared customizations, you have the flexibility of modifying or adding to HL7 messages.</span></span> <span data-ttu-id="45d28-104">甚至可以定义新类型的消息。</span><span class="sxs-lookup"><span data-stu-id="45d28-104">You can even define a new type of message.</span></span> <span data-ttu-id="45d28-105">可以通过以下方式之一执行此操作：</span><span class="sxs-lookup"><span data-stu-id="45d28-105">You can do this in any of the following ways:</span></span>  
  
- <span data-ttu-id="45d28-106">通过定义新的消息类型或触发器事件更改消息的定义</span><span class="sxs-lookup"><span data-stu-id="45d28-106">Changing the definition of a message by defining a new message type or trigger event</span></span>  
  
- <span data-ttu-id="45d28-107">将新段添加到现有的消息类型</span><span class="sxs-lookup"><span data-stu-id="45d28-107">Adding a new segment to an existing message type</span></span>  
  
- <span data-ttu-id="45d28-108">更改现有的消息部分 （段、 字段、 组件或子组件） 的数据类型</span><span class="sxs-lookup"><span data-stu-id="45d28-108">Changing the data type of an existing message part (segment, field, component, or subcomponent)</span></span>  
  
- <span data-ttu-id="45d28-109">更改可能可以使用现有的消息部分中的值</span><span class="sxs-lookup"><span data-stu-id="45d28-109">Changing the potential values that you can use in an existing message part</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="45d28-110">你可以在声明的 Z 对象或 HL7 架构中的标准对象中使用的枚举值。</span><span class="sxs-lookup"><span data-stu-id="45d28-110">You can change the enumeration values used in declared Z objects or the standard objects in HL7 schemas.</span></span> <span data-ttu-id="45d28-111">若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="45d28-111">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
  <span data-ttu-id="45d28-112">修改或添加到 HL7 消息通过添加、 维护和将在当前定义的消息类型的自定义对象相关联。</span><span class="sxs-lookup"><span data-stu-id="45d28-112">You modify or add to HL7 messages by adding, maintaining, and associating custom objects within the currently defined message types.</span></span> <span data-ttu-id="45d28-113">HL7 标准调用这些自定义对象"Z 对象"来区分它们来自符合 HL7 标准的现有对象。</span><span class="sxs-lookup"><span data-stu-id="45d28-113">The HL7 standards call these custom objects "Z objects" to distinguish them from existing objects that conform to the HL7 standard.</span></span> <span data-ttu-id="45d28-114">使用 BizTalk 编辑器来定义 Z 对象。</span><span class="sxs-lookup"><span data-stu-id="45d28-114">You use BizTalk Editor to define Z objects.</span></span> <span data-ttu-id="45d28-115">此外可以使用 BizTalk 编辑器来处理跨所有触发器事件传播对 Z 对象的更新的功能和将其包含的抽象消息。</span><span class="sxs-lookup"><span data-stu-id="45d28-115">You also use BizTalk Editor to work with features that propagate updates to a Z object across all the trigger events and abstract messages that include it.</span></span> <span data-ttu-id="45d28-116">有关创建 Z 对象的详细信息，请参阅[使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="45d28-116">For more information about creating Z objects, see [Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md).</span></span>  
  
  <span data-ttu-id="45d28-117">可以使用 Z 对象提供的使用方式的 HL7 标准中未指定的段的本地定义。</span><span class="sxs-lookup"><span data-stu-id="45d28-117">You can use Z objects to give local definitions to segments that you use in ways not specified in the HL7 standard.</span></span> <span data-ttu-id="45d28-118">进行这些更改对架构的 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 在计算机上安装的安装向导。</span><span class="sxs-lookup"><span data-stu-id="45d28-118">You make these changes to the schemas that the BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Setup Wizard installed on your computer.</span></span> <span data-ttu-id="45d28-119">然后可以与其他共享这些已修改的架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装与之交换消息。</span><span class="sxs-lookup"><span data-stu-id="45d28-119">You can then share these modified schemas with other [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] installations with which you exchange messages.</span></span>  
  
## <a name="types-of-z-objects"></a><span data-ttu-id="45d28-120">Z 对象类型</span><span class="sxs-lookup"><span data-stu-id="45d28-120">Types of Z Objects</span></span>  
 <span data-ttu-id="45d28-121">HL7 标准 (2.X) 当前支持自定义以下的形式：</span><span class="sxs-lookup"><span data-stu-id="45d28-121">The HL7 standard (2.X) currently supports the following forms of customization:</span></span>  
  
-   <span data-ttu-id="45d28-122">**自定义触发器的事件。**</span><span class="sxs-lookup"><span data-stu-id="45d28-122">**Custom trigger events.**</span></span> <span data-ttu-id="45d28-123">如果在本地区域和需要新的消息结构，或者想要支持不包括在标准的触发器事件，可以创建使用 Z 前缀，例如，Z05 的新触发器事件。</span><span class="sxs-lookup"><span data-stu-id="45d28-123">If you are at a local area and need a new message structure, or want to support a trigger event that is not included within the standard, you can create a new trigger event using a Z prefix, for example, Z05.</span></span> <span data-ttu-id="45d28-124">在这种情况下，必须定义抽象的消息和包含的段数模式来创建新的本地消息架构。</span><span class="sxs-lookup"><span data-stu-id="45d28-124">In this case, you must create a new local message schema by defining the abstract message and the pattern of included segments.</span></span>  
  
-   <span data-ttu-id="45d28-125">**自定义的段。**</span><span class="sxs-lookup"><span data-stu-id="45d28-125">**Custom segments.**</span></span> <span data-ttu-id="45d28-126">如果对象在本地区域中，在上下文中的已受支持的触发器事件，并需要其他数据，可以创建一个新段并包括所需的数据元素在段中。</span><span class="sxs-lookup"><span data-stu-id="45d28-126">If you are at a local area, in the context of an already supported trigger event, and in need of additional data, you can create a new segment or segments and include the wanted data elements within the segment.</span></span> <span data-ttu-id="45d28-127">必须指定使用现有的 HL7 数据类型的段中的元素。</span><span class="sxs-lookup"><span data-stu-id="45d28-127">You must specify the elements within the segment using existing HL7 data types.</span></span> <span data-ttu-id="45d28-128">您可以通过在架构中创建一个新的记录在 BizTalk 编辑器中，创建自定义的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="45d28-128">You can create custom Z segments in BizTalk Editor, by creating a new record in the schema.</span></span> <span data-ttu-id="45d28-129">有关详细信息，请参阅[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="45d28-129">For more information, see [Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md).</span></span> <span data-ttu-id="45d28-130">或者，可以添加到 Access 数据库，然后将该 Z 段添加到消息结构的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="45d28-130">Alternatively, you can add a Z segment through the Access database, and then adding that Z segment to the message structure.</span></span> <span data-ttu-id="45d28-131">有关详细信息，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="45d28-131">For more information, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
-   <span data-ttu-id="45d28-132">**自定义数据的子类型。**</span><span class="sxs-lookup"><span data-stu-id="45d28-132">**Custom data subtypes.**</span></span> <span data-ttu-id="45d28-133">HL7 提供了一系列支持的数据类型，例如，将格式化文本，扫描图像、 音频数据。</span><span class="sxs-lookup"><span data-stu-id="45d28-133">HL7 provides a list of supported data types, for example, formatted text, scanned image, audio data.</span></span> <span data-ttu-id="45d28-134">但是，如果你想要定义其他数据类型，您可以这样做通过前缀助记键与"Z"一起使用，从而创建 Z 数据键入。</span><span class="sxs-lookup"><span data-stu-id="45d28-134">However, if you want to define additional data types, you can do so by prefixing the mnemonic used with a "Z", thereby creating a Z data type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45d28-135">不允许，标准，若要创建新的数据类型，或将元素添加到现有段范围内。</span><span class="sxs-lookup"><span data-stu-id="45d28-135">It is not permissible, within the confines of the standard, to create new data types or to add elements to an existing segment.</span></span> <span data-ttu-id="45d28-136">仍小于是它允许以执行当前未使用的元素，它重新定义以满足某些其他用途。</span><span class="sxs-lookup"><span data-stu-id="45d28-136">Still less is it permissible to take an element that is not currently used and to redefine it to meet some additional purpose.</span></span> <span data-ttu-id="45d28-137">但是，支持旧接口的组织可能需要以适应这种做法。</span><span class="sxs-lookup"><span data-stu-id="45d28-137">On the other hand, organizations that support legacy interfaces may need to accommodate such practices.</span></span>  
  
-   <span data-ttu-id="45d28-138">**自定义的表。**</span><span class="sxs-lookup"><span data-stu-id="45d28-138">**Custom tables.**</span></span> <span data-ttu-id="45d28-139">在消息中的许多现有对象有有限的特定值，范围由通过 HL7 通用架构定义表中的枚举定义。</span><span class="sxs-lookup"><span data-stu-id="45d28-139">Many existing objects within messages have a limited range of specific values, as defined by enumerations in tables defined by HL7 common schemas.</span></span> <span data-ttu-id="45d28-140">您可以修改这些枚举，以将通过创建 Z 表启用其他值。</span><span class="sxs-lookup"><span data-stu-id="45d28-140">You can modify these enumerations to enable additional values by creating Z tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d28-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="45d28-141">See Also</span></span>  
 <span data-ttu-id="45d28-142">[未声明的自定义项](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="45d28-142">[Undeclared Customizations](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md) </span></span>  
 <span data-ttu-id="45d28-143">[使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="45d28-143">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="45d28-144">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="45d28-144">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="45d28-145">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="45d28-145">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="45d28-146">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="45d28-146">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)