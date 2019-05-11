---
title: 使用 BizTalk 编辑器创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32b4667e0f9777ccf21f26fdfc38a2d12946998
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389886"
---
# <a name="create-schemas-using-biztalk-editor"></a><span data-ttu-id="c019d-102">使用 BizTalk 编辑器创建架构</span><span class="sxs-lookup"><span data-stu-id="c019d-102">Create Schemas Using BizTalk Editor</span></span>

## <a name="overview"></a><span data-ttu-id="c019d-103">概述</span><span class="sxs-lookup"><span data-stu-id="c019d-103">Overview</span></span>
<span data-ttu-id="c019d-104">BizTalk 编辑器是在 Microsoft 内部运行的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="c019d-104">BizTalk Editor is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="c019d-105">可以使用它来创建、 编辑和管理与你的应用程序使用的架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-105">You can use it to create, edit, and manage schemas for use with your application.</span></span> <span data-ttu-id="c019d-106">BizTalk 编辑器使用分层记录和字段的自有图形系统来表示实例消息的结构，并使用 XML 架构定义 (XSD) 语言来存储它定义的架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-106">BizTalk Editor uses its own graphical system of hierarchical records and fields to represent the structure of instance messages, and uses the XML Schema definition (XSD) language to store the schemas that it defines.</span></span> <span data-ttu-id="c019d-107">这是而不考虑在其中交换实例消息的格式，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="c019d-107">This is true regardless of the format in which instance messages are exchanged.</span></span> <span data-ttu-id="c019d-108">例如，假设您与贸易合作伙伴交换平面文件。</span><span class="sxs-lookup"><span data-stu-id="c019d-108">For example, suppose that you exchange flat files with a trading partner.</span></span> <span data-ttu-id="c019d-109">当 BizTalk Server 处理这些平面文件，它将其转换到和从符合 XSD 架构定义在 BizTalk 编辑器中的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="c019d-109">As BizTalk Server processes those flat files, it converts them to and from an XML format that conforms to an XSD schema that you defined in BizTalk Editor.</span></span>  
  
 <span data-ttu-id="c019d-110">下图中所示，可以安排好的业务流程内使用使用 BizTalk 编辑器创建的架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-110">The schemas you create using BizTalk Editor can be used within an orchestrated business process, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="c019d-111">![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")</span><span class="sxs-lookup"><span data-stu-id="c019d-111">![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")</span></span>  
  
 <span data-ttu-id="c019d-112">架构还用于通过组装器和拆装器将实例消息从一种格式，如翻译平面文件格式和 XML 之间。</span><span class="sxs-lookup"><span data-stu-id="c019d-112">Schemas are also used by assemblers and disassemblers for translating instance messages from one format to another, such as between a flat file format and XML.</span></span> <span data-ttu-id="c019d-113">架构还在实例消息转换，其中的实例消息中的数据用于构造具有不同结构的实例消息中发挥重要作用。</span><span class="sxs-lookup"><span data-stu-id="c019d-113">Schemas also play an important role in instance message transformation, wherein the data in an instance message is used to construct an instance message with a different structure.</span></span> <span data-ttu-id="c019d-114">新的实例消息可能是语义上等效，如采购订单的不同表示形式也可能是需要部分或全部在其内容中的原始实例消息中的数据的实例消息的不同但相关类型。</span><span class="sxs-lookup"><span data-stu-id="c019d-114">The new instance message might be semantically equivalent, such as different representations of a purchase order, or it might be a different but related type of instance message that requires some or all of the data from the original instance message in its content.</span></span>  
  
 <span data-ttu-id="c019d-115">有关将所有实例消息都翻译成符合 XSD 架构的 XML 格式的一个重要原因是为了简化将消息从一种结构转换为另一种结构的过程。</span><span class="sxs-lookup"><span data-stu-id="c019d-115">An important reason for translating all instance messages into an XML format that conforms to an XSD schema is to simplify the process of transforming a message from one structure into another structure.</span></span> <span data-ttu-id="c019d-116">消息结构通常是其语法差异尽管在语义上等效的。</span><span class="sxs-lookup"><span data-stu-id="c019d-116">Message structures are typically semantically equivalent despite their syntactic differences.</span></span> <span data-ttu-id="c019d-117">例如，您和您的贸易合作伙伴可能会以不同的方式，构建采购订单，但它们所包含的基本信息是相同的这样它们自动来回转换。</span><span class="sxs-lookup"><span data-stu-id="c019d-117">For example, you and your trading partner might structure your purchase orders differently, but the basic information they contain is the same, allowing them to be transformed back and forth automatically.</span></span> <span data-ttu-id="c019d-118">第一个，则将所有实例消息转换为相应的 XSD 架构控制的 XML 格式，可以 XML 和非 XML 格式之间来回转换和从一种 XML 结构转换为另一个实例消息。</span><span class="sxs-lookup"><span data-stu-id="c019d-118">By first converting all instance messages into an XML format governed by a corresponding XSD schema, the instance messages can be translated back and forth between XML and non-XML formats, and transformed from one XML structure to another.</span></span> <span data-ttu-id="c019d-119">实例消息翻译与实例消息转换之间的差别的详细信息，请参阅[数据转换](../core/data-transformation.md)。</span><span class="sxs-lookup"><span data-stu-id="c019d-119">For more information about the distinction between instance message translation and instance message transformation, see [Data Transformation](../core/data-transformation.md).</span></span>  
  
 <span data-ttu-id="c019d-120">Microsoft Visual Studio 环境中的辅助工具向 BizTalk 编辑器为 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="c019d-120">The companion tool to BizTalk Editor within the Microsoft Visual Studio environment is BizTalk Mapper.</span></span> <span data-ttu-id="c019d-121">使用 BizTalk 编辑器创建定义的结构和相关的实例消息的对格式的架构后，使用 BizTalk 映射器以图形方式定义如何将符合某种架构的实例消息 (源实例消息和架构） 转换为符合另一个架构 （目标实例消息和架构） 的实例消息。</span><span class="sxs-lookup"><span data-stu-id="c019d-121">After you use BizTalk Editor to create the schemas that define the structure and format of a pair of related instance messages, you use BizTalk Mapper to graphically define how to transform an instance message conforming to one schema (the source instance message and schema) into an instance message conforming to another schema (the destination instance message and schema).</span></span> <span data-ttu-id="c019d-122">此类转换的规范使用可扩展样式表语言转换 (XSLT) 实现的并保存为文件称为的映射。</span><span class="sxs-lookup"><span data-stu-id="c019d-122">The specification of such transformations is implemented using Extensible Stylesheet Language Transformations (XSLT) and persisted as files called maps.</span></span> <span data-ttu-id="c019d-123">有关 BizTalk 映射器的概念性和程序性信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="c019d-123">For conceptual and procedural information about BizTalk Mapper, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span> <span data-ttu-id="c019d-124">有关 BizTalk 映射器属性和 functoid 的参考信息，请参阅**映射属性参考**并**Functoid 参考**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  </span><span class="sxs-lookup"><span data-stu-id="c019d-124">For reference information about BizTalk Mapper properties and functoids, see the **Map Property Reference** and **Functoid Reference**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="c019d-125">使用 BizTalk 编辑器中，您可以打开未包含任何结构的空架构，可以打开现有的 XSD 架构，也可以从非 XSD 源生成架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-125">Using BizTalk Editor, you can open a blank schema that contains no structure, you can open an existing XSD schema, or you can generate a schema from a non-XSD source.</span></span> <span data-ttu-id="c019d-126">当从非 XSD 源生成架构时，BizTalk 编辑器将解释源的结构，并生成是它的 XSD 表示形式的架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-126">When you generate a schema from a non-XSD source, BizTalk Editor interprets the structure of the source and produces a schema that is an XSD representation of it.</span></span> <span data-ttu-id="c019d-127">您可以编辑的任何记录和显示在 BizTalk 编辑器架构树视图中，字段，然后将结构保存为 BizTalk 架构。</span><span class="sxs-lookup"><span data-stu-id="c019d-127">You can edit any records and fields that appear in the BizTalk Editor schema tree view, and then save the structure as a BizTalk schema.</span></span>  
  
 <span data-ttu-id="c019d-128">有关使用 BizTalk 编辑器的键盘快捷方式的信息，请参阅[BizTalk 编辑器键盘快捷方式](../core/biztalk-editor-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="c019d-128">For information about using the keyboard shortcuts for BizTalk Editor, see [BizTalk Editor Keyboard Shortcuts](../core/biztalk-editor-keyboard-shortcuts.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c019d-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c019d-129">Next steps</span></span>
  
-   [<span data-ttu-id="c019d-130">规划架构创建</span><span class="sxs-lookup"><span data-stu-id="c019d-130">Planning for Schema Creation</span></span>](../core/planning-for-schema-creation.md)  
  
-   [<span data-ttu-id="c019d-131">关于实例消息</span><span class="sxs-lookup"><span data-stu-id="c019d-131">About Instance Messages</span></span>](../core/about-instance-messages.md)  
  
-   [<span data-ttu-id="c019d-132">关于架构</span><span class="sxs-lookup"><span data-stu-id="c019d-132">About Schemas</span></span>](../core/about-schemas.md)  
  
-   [<span data-ttu-id="c019d-133">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="c019d-133">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)  
  
-   [<span data-ttu-id="c019d-134">创建架构</span><span class="sxs-lookup"><span data-stu-id="c019d-134">Creating Schemas</span></span>](../core/creating-schemas.md)  
  
-   [<span data-ttu-id="c019d-135">使用“BizTalk 平面文件架构向导”创建架构</span><span class="sxs-lookup"><span data-stu-id="c019d-135">Creating Schemas Using BizTalk Flat File Schema Wizard</span></span>](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [<span data-ttu-id="c019d-136">测试架构</span><span class="sxs-lookup"><span data-stu-id="c019d-136">Testing Schemas</span></span>](../core/testing-schemas.md)  
  
-   [<span data-ttu-id="c019d-137">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="c019d-137">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)  
  
-   [<span data-ttu-id="c019d-138">创建架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="c019d-138">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)  
  
-   [<span data-ttu-id="c019d-139">架构生成和验证的已知问题</span><span class="sxs-lookup"><span data-stu-id="c019d-139">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)