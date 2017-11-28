---
title: "创建使用 BizTalk 编辑器的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9e4c6496f43a9602ad56bc0e095d98f2da90d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-schemas-using-biztalk-editor"></a><span data-ttu-id="facb1-102">使用 BizTalk 编辑器创建架构</span><span class="sxs-lookup"><span data-stu-id="facb1-102">Create Schemas Using BizTalk Editor</span></span>

## <a name="overview"></a><span data-ttu-id="facb1-103">概述</span><span class="sxs-lookup"><span data-stu-id="facb1-103">Overview</span></span>
<span data-ttu-id="facb1-104">BizTalk 编辑器是在 Microsoft 内部运行的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="facb1-104">BizTalk Editor is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="facb1-105">您可以使用它来创建、编辑和管理要用于应用程序的架构。</span><span class="sxs-lookup"><span data-stu-id="facb1-105">You can use it to create, edit, and manage schemas for use with your application.</span></span> <span data-ttu-id="facb1-106">BizTalk 编辑器使用其自己的分层记录和字段的图形系统来表示实例消息的结构，并使用 XML 架构定义 (XSD) 语言存储其定义的架构。</span><span class="sxs-lookup"><span data-stu-id="facb1-106">BizTalk Editor uses its own graphical system of hierarchical records and fields to represent the structure of instance messages, and uses the XML Schema definition (XSD) language to store the schemas that it defines.</span></span> <span data-ttu-id="facb1-107">不论实例消息以何种格式进行交换都是如此。</span><span class="sxs-lookup"><span data-stu-id="facb1-107">This is true regardless of the format in which instance messages are exchanged.</span></span> <span data-ttu-id="facb1-108">例如，假设您要与贸易合作伙伴交换平面文件。</span><span class="sxs-lookup"><span data-stu-id="facb1-108">For example, suppose that you exchange flat files with a trading partner.</span></span> <span data-ttu-id="facb1-109">当 BizTalk Server 处理这些平面文件时，它会将这些平面文件转换为符合 BizTalk 编辑器中所定义的 XSD 架构的 XML 格式，以及进行相反转换。</span><span class="sxs-lookup"><span data-stu-id="facb1-109">As BizTalk Server processes those flat files, it converts them to and from an XML format that conforms to an XSD schema that you defined in BizTalk Editor.</span></span>  
  
 <span data-ttu-id="facb1-110">使用 BizTalk 编辑器创建的架构可以用于已编排为业务流程的业务程序，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="facb1-110">The schemas you create using BizTalk Editor can be used within an orchestrated business process, as shown in the following figure.</span></span>  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 <span data-ttu-id="facb1-111">组装器和拆装器也可使用架构以将实例消息从一种格式翻译成另一种格式，例如，在平面文件格式与 XML 之间。</span><span class="sxs-lookup"><span data-stu-id="facb1-111">Schemas are also used by assemblers and disassemblers for translating instance messages from one format to another, such as between a flat file format and XML.</span></span> <span data-ttu-id="facb1-112">此外，架构还在实例消息转换中起着非常重要的作用，即实例消息中的数据可用于构造具有不同结构的实例消息。</span><span class="sxs-lookup"><span data-stu-id="facb1-112">Schemas also play an important role in instance message transformation, wherein the data in an instance message is used to construct an instance message with a different structure.</span></span> <span data-ttu-id="facb1-113">而新的实例消息可能与原始实例消息在语义上是相同的（例如，采购订单的不同表示形式），或它们的类型可能不同但相关，在新的实例消息的内容中需要原始实例消息中的部分或所有数据。</span><span class="sxs-lookup"><span data-stu-id="facb1-113">The new instance message might be semantically equivalent, such as different representations of a purchase order, or it might be a different but related type of instance message that requires some or all of the data from the original instance message in its content.</span></span>  
  
 <span data-ttu-id="facb1-114">之所以将所有实例消息翻译成符合 XSD 架构的 XML 格式，一个重要原因是为了简化消息从一种结构转换成另一种结构的过程。</span><span class="sxs-lookup"><span data-stu-id="facb1-114">An important reason for translating all instance messages into an XML format that conforms to an XSD schema is to simplify the process of transforming a message from one structure into another structure.</span></span> <span data-ttu-id="facb1-115">尽管消息结构在语法上存在差异，但它们通常在语义上是相同的。</span><span class="sxs-lookup"><span data-stu-id="facb1-115">Message structures are typically semantically equivalent despite their syntactic differences.</span></span> <span data-ttu-id="facb1-116">例如，您与您的贸易合作伙伴可能会以不同方式构建采购订单，但这些采购订单所包含的基本信息是相同的，这样它们才能自动地在格式间进行转换。</span><span class="sxs-lookup"><span data-stu-id="facb1-116">For example, you and your trading partner might structure your purchase orders differently, but the basic information they contain is the same, allowing them to be transformed back and forth automatically.</span></span> <span data-ttu-id="facb1-117">通过首先将所有实例消息转换成由对应的 XSD 架构控制的 XML 格式，这些实例消息就可以在 XML 格式和非 XML 格式之间进行翻译，并可从一种 XML 结构转换成另一种结构。</span><span class="sxs-lookup"><span data-stu-id="facb1-117">By first converting all instance messages into an XML format governed by a corresponding XSD schema, the instance messages can be translated back and forth between XML and non-XML formats, and transformed from one XML structure to another.</span></span> <span data-ttu-id="facb1-118">有关实例消息转换和实例消息转换之间的区别的详细信息，请参阅[数据转换](../core/data-transformation.md)。</span><span class="sxs-lookup"><span data-stu-id="facb1-118">For more information about the distinction between instance message translation and instance message transformation, see [Data Transformation](../core/data-transformation.md).</span></span>  
  
 <span data-ttu-id="facb1-119">在 Microsoft Visual Studio 环境中，BizTalk 编辑器的辅助工具为 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="facb1-119">The companion tool to BizTalk Editor within the Microsoft Visual Studio environment is BizTalk Mapper.</span></span> <span data-ttu-id="facb1-120">在使用 BizTalk 编辑器创建定义两个相关实例消息的结构和格式的架构后，可以使用 BizTalk 映射器以图形方式定义如何将符合某种架构的实例消息（源实例消息和架构）转换成符合另一种架构的实例消息（目标实例消息和架构）。</span><span class="sxs-lookup"><span data-stu-id="facb1-120">After you use BizTalk Editor to create the schemas that define the structure and format of a pair of related instance messages, you use BizTalk Mapper to graphically define how to transform an instance message conforming to one schema (the source instance message and schema) into an instance message conforming to another schema (the destination instance message and schema).</span></span> <span data-ttu-id="facb1-121">此类转换的规范是使用可扩展样式表语言转换 (XSLT) 实现的，并作为文件（称为映射）进行保存。</span><span class="sxs-lookup"><span data-stu-id="facb1-121">The specification of such transformations is implemented using Extensible Stylesheet Language Transformations (XSLT) and persisted as files called maps.</span></span> <span data-ttu-id="facb1-122">BizTalk 映射程序有关的概念性和程序性信息，请参阅[创建地图使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="facb1-122">For conceptual and procedural information about BizTalk Mapper, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span> <span data-ttu-id="facb1-123">有关 BizTalk 映射程序属性和 functoid 的参考信息，请参阅**映射属性引用**和**Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  </span><span class="sxs-lookup"><span data-stu-id="facb1-123">For reference information about BizTalk Mapper properties and functoids, see the **Map Property Reference** and **Functoid Reference**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="facb1-124">使用 BizTalk 编辑器，可以打开未包含任何结构的空架构、打开现有的 XSD 架构、和从非 XSD 源中生成架构。</span><span class="sxs-lookup"><span data-stu-id="facb1-124">Using BizTalk Editor, you can open a blank schema that contains no structure, you can open an existing XSD schema, or you can generate a schema from a non-XSD source.</span></span> <span data-ttu-id="facb1-125">从非 XSD 源中生成架构时，BizTalk 编辑器将解释该源的结构，并生成作为其 XSD 表示形式的架构。</span><span class="sxs-lookup"><span data-stu-id="facb1-125">When you generate a schema from a non-XSD source, BizTalk Editor interprets the structure of the source and produces a schema that is an XSD representation of it.</span></span> <span data-ttu-id="facb1-126">您可以编辑显示在 BizTalk 编辑器架构树视图中的任何记录和字段，然后将结构另存为 BizTalk 架构。</span><span class="sxs-lookup"><span data-stu-id="facb1-126">You can edit any records and fields that appear in the BizTalk Editor schema tree view, and then save the structure as a BizTalk schema.</span></span>  
  
 <span data-ttu-id="facb1-127">有关使用 BizTalk 编辑器的键盘快捷方式的信息，请参阅[BizTalk 编辑器键盘快捷键](../core/biztalk-editor-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="facb1-127">For information about using the keyboard shortcuts for BizTalk Editor, see [BizTalk Editor Keyboard Shortcuts](../core/biztalk-editor-keyboard-shortcuts.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="facb1-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="facb1-128">Next steps</span></span>
  
-   [<span data-ttu-id="facb1-129">规划架构创建</span><span class="sxs-lookup"><span data-stu-id="facb1-129">Planning for Schema Creation</span></span>](../core/planning-for-schema-creation.md)  
  
-   [<span data-ttu-id="facb1-130">有关实例消息</span><span class="sxs-lookup"><span data-stu-id="facb1-130">About Instance Messages</span></span>](../core/about-instance-messages.md)  
  
-   [<span data-ttu-id="facb1-131">有关架构</span><span class="sxs-lookup"><span data-stu-id="facb1-131">About Schemas</span></span>](../core/about-schemas.md)  
  
-   [<span data-ttu-id="facb1-132">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="facb1-132">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)  
  
-   [<span data-ttu-id="facb1-133">创建架构</span><span class="sxs-lookup"><span data-stu-id="facb1-133">Creating Schemas</span></span>](../core/creating-schemas.md)  
  
-   [<span data-ttu-id="facb1-134">创建架构使用 BizTalk 平面文件架构向导</span><span class="sxs-lookup"><span data-stu-id="facb1-134">Creating Schemas Using BizTalk Flat File Schema Wizard</span></span>](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [<span data-ttu-id="facb1-135">测试架构</span><span class="sxs-lookup"><span data-stu-id="facb1-135">Testing Schemas</span></span>](../core/testing-schemas.md)  
  
-   [<span data-ttu-id="facb1-136">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="facb1-136">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)  
  
-   [<span data-ttu-id="facb1-137">创建架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="facb1-137">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)  
  
-   [<span data-ttu-id="facb1-138">架构生成和验证已知的问题</span><span class="sxs-lookup"><span data-stu-id="facb1-138">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)