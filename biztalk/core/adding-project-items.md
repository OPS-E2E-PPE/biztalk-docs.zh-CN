---
title: 添加项目项 |Microsoft Docs
description: 添加到 BizTalk Server 项目在 Visual Studio 中的业务流程、 架构、 映射和管道
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0fc88bcf2f843e7d22b47a69ccae1b7b3fcd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360911"
---
# <a name="add-project-items"></a><span data-ttu-id="d9e82-103">添加项目项</span><span class="sxs-lookup"><span data-stu-id="d9e82-103">Add Project Items</span></span>
<span data-ttu-id="d9e82-104">在 BizTalk 项目系统的上下文中，项目项是指配置的项，例如映射或架构。</span><span class="sxs-lookup"><span data-stu-id="d9e82-104">In the context of the BizTalk project system, a project item is a configured item, such as a map or schema.</span></span> <span data-ttu-id="d9e82-105">BizTalk 应用程序可能包含一个或多个业务流程、 架构、 映射和管道。</span><span class="sxs-lookup"><span data-stu-id="d9e82-105">A BizTalk application might contain one or more orchestrations, schemas, maps, and pipelines.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9e82-106">当将某个项添加到项目中时，不句点 （.） 在名称中使用因为句点是.NET 命名空间的分隔符。</span><span class="sxs-lookup"><span data-stu-id="d9e82-106">When you add an item to a project, do not use a period (.) in the name because a period is a separator for the .NET namespace.</span></span> <span data-ttu-id="d9e82-107">如果项名称中使用句点，则项的类型名称将包含下划线 (_) 而不是一段。</span><span class="sxs-lookup"><span data-stu-id="d9e82-107">If you use a period in the item name, the Type Name of the item will contain an underscore (_) instead of a period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9e82-108">将架构、 映射或管道添加到一个文件夹中，当**完全限定的名称**属性自动生成并包含命名空间和类型。</span><span class="sxs-lookup"><span data-stu-id="d9e82-108">When you add a schema, map, or pipeline to a folder, the **Fully Qualified Name** property is automatically generated and includes the namespace and type.</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="d9e82-109">业务流程</span><span class="sxs-lookup"><span data-stu-id="d9e82-109">Orchestrations</span></span>  
 <span data-ttu-id="d9e82-110">业务流程是以 XLANG/s 语言表示的业务流程的表示形式。</span><span class="sxs-lookup"><span data-stu-id="d9e82-110">An orchestration is a representation of a business process expressed in the XLANG/s language.</span></span> <span data-ttu-id="d9e82-111">XLANG/s 可用于补充现有过程语言，如 Microsoft[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]和 Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d9e82-111">XLANG/s can be used to complement existing procedural languages such as Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] and Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)].</span></span>  
  
 <span data-ttu-id="d9e82-112">业务流程设计器可用于创建你想要在 BizTalk 项目中包含的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d9e82-112">You can use Orchestration Designer to create the orchestrations that you want to include in a BizTalk project.</span></span> <span data-ttu-id="d9e82-113">在业务流程设计器中创建的所有业务流程具有.odx 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d9e82-113">All orchestrations that you create in Orchestration Designer have an .odx file extension.</span></span>  
  
## <a name="schemas"></a><span data-ttu-id="d9e82-114">架构</span><span class="sxs-lookup"><span data-stu-id="d9e82-114">Schemas</span></span>  
 <span data-ttu-id="d9e82-115">架构是文档或消息结构的定义。</span><span class="sxs-lookup"><span data-stu-id="d9e82-115">A schema is the definition of the structure for a document or message.</span></span> <span data-ttu-id="d9e82-116">因为它涉及到的记录和结构中的字段，它包含属性信息。</span><span class="sxs-lookup"><span data-stu-id="d9e82-116">It contains property information as it pertains to the records and fields within the structure.</span></span> <span data-ttu-id="d9e82-117">如果适用，架构可以包含多个子架构。</span><span class="sxs-lookup"><span data-stu-id="d9e82-117">If appropriate, a schema can contain multiple subschemas.</span></span>  
  
 <span data-ttu-id="d9e82-118">可以使用 BizTalk 编辑器导入、 编辑或创建架构。</span><span class="sxs-lookup"><span data-stu-id="d9e82-118">You can use BizTalk Editor to import, edit, or create schemas.</span></span> <span data-ttu-id="d9e82-119">然后，可以使用创建 BizTalk 映射器中生成映射的架构。</span><span class="sxs-lookup"><span data-stu-id="d9e82-119">You can then use the schemas that you create to generate maps in BizTalk Mapper.</span></span> <span data-ttu-id="d9e82-120">使用 BizTalk 编辑器中保存的所有架构都具有.xsd 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d9e82-120">All schemas that you save by using BizTalk Editor have an .xsd file extension.</span></span>  
  
 <span data-ttu-id="d9e82-121">有关架构和 BizTalk 编辑器的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="d9e82-121">For more information about schemas and BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
## <a name="maps"></a><span data-ttu-id="d9e82-122">地图</span><span class="sxs-lookup"><span data-stu-id="d9e82-122">Maps</span></span>  
 <span data-ttu-id="d9e82-123">地图是另一个架构中定义的记录和一个架构中的字段和记录和字段之间的对应关系的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d9e82-123">A map is an XML file that defines the correspondence between the records and fields in one schema and the records and fields in another schema.</span></span> <span data-ttu-id="d9e82-124">创建基于行业标准、 非行业标准 （如内部标准或遗留问题） 或现有文件的映射。</span><span class="sxs-lookup"><span data-stu-id="d9e82-124">You create maps based on industry standards, non-industry standards (such as internal standards or legacy issues), or existing files.</span></span> <span data-ttu-id="d9e82-125">当你想要将数据接收或发送从一种格式之间转换时，您可以创建映射。</span><span class="sxs-lookup"><span data-stu-id="d9e82-125">You create maps when you want to transform data that you receive or send from one format to another.</span></span> <span data-ttu-id="d9e82-126">BizTalk 映射器可用于创建 BizTalk 项目中包含的映射。</span><span class="sxs-lookup"><span data-stu-id="d9e82-126">You can use BizTalk Mapper to create maps that you include in a BizTalk project.</span></span> <span data-ttu-id="d9e82-127">在 BizTalk 映射器中保存的所有映射都具有.btm 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d9e82-127">All maps that you save in BizTalk Mapper have a .btm file extension.</span></span> <span data-ttu-id="d9e82-128">有关 BizTalk 映射器的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="d9e82-128">For more information about BizTalk Mapper, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="pipelines"></a><span data-ttu-id="d9e82-129">管道</span><span class="sxs-lookup"><span data-stu-id="d9e82-129">Pipelines</span></span>  
 <span data-ttu-id="d9e82-130">可以使用管道设计器创建接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="d9e82-130">You can use Pipeline Designer to create receive and send pipelines.</span></span> <span data-ttu-id="d9e82-131">管道是软件基础结构，用于定义和链接来处理消息接收或发送的 BizTalk Server 的一个或多个阶段。</span><span class="sxs-lookup"><span data-stu-id="d9e82-131">A pipeline is a software infrastructure that defines and links one or more stages for processing messages received or sent by BizTalk Server.</span></span> <span data-ttu-id="d9e82-132">管道按特定顺序实现各个阶段，并包括诸如编码或解码、 组装或拆装以及加密或解密。</span><span class="sxs-lookup"><span data-stu-id="d9e82-132">The pipelines implement the stages in a specific order and include functions such as encoding or decoding, assembling or disassembling, and encrypting or decrypting.</span></span>  
  
 <span data-ttu-id="d9e82-133">在 BizTalk 项目中包含的默认管道引用可以只能处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="d9e82-133">The default pipeline references included in a BizTalk project can process only XML documents.</span></span> <span data-ttu-id="d9e82-134">如果你想要处理平面文件、 EDI 文档或其他文件类型，则必须创建新的管道，根据需要。</span><span class="sxs-lookup"><span data-stu-id="d9e82-134">If you want to process flat files, EDI documents, or other file types, you must create new pipelines as appropriate.</span></span> <span data-ttu-id="d9e82-135">使用管道设计器创建的所有管道均都具有.btp 扩展名。</span><span class="sxs-lookup"><span data-stu-id="d9e82-135">All pipelines created with Pipeline Designer have a .btp extension.</span></span> <span data-ttu-id="d9e82-136">有关管道和管道设计器的详细信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="d9e82-136">For more information about pipelines and Pipeline Designer, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
## <a name="valid-files-for-biztalk-projects"></a><span data-ttu-id="d9e82-137">BizTalk 项目的有效文件</span><span class="sxs-lookup"><span data-stu-id="d9e82-137">Valid Files for BizTalk Projects</span></span>  
 <span data-ttu-id="d9e82-138">与 BizTalk 项目时，可以包含许多不同的文件，例如 HTML 文件、 XML 文件、 接收管道文件和架构文件。</span><span class="sxs-lookup"><span data-stu-id="d9e82-138">When you work with a BizTalk project, you can include many different files, such as HTML files, XML files, receive pipeline files, and schema files.</span></span> <span data-ttu-id="d9e82-139">与 BizTalk Server 程序集可以包含由 Visual Studio 生成系统支持的任何对象。</span><span class="sxs-lookup"><span data-stu-id="d9e82-139">With BizTalk Server, the assembly can contain any object supported by the Visual Studio build system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e82-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9e82-140">See Also</span></span>  
 [<span data-ttu-id="d9e82-141">处理 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="d9e82-141">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)