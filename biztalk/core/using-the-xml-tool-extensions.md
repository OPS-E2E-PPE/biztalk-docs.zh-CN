---
title: 使用 XML 工具扩展 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5613bf15-6c0a-4a82-b200-24d0801d7ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976082fc14eb37d550956ec447eb63938706daa3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006310"
---
# <a name="using-the-xml-tool-extensions"></a><span data-ttu-id="5c613-102">使用 XML 工具扩展</span><span class="sxs-lookup"><span data-stu-id="5c613-102">Using the XML Tool Extensions</span></span>
<span data-ttu-id="5c613-103">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 XML 工具扩展，您可以对架构、映射和消息实例执行任务。</span><span class="sxs-lookup"><span data-stu-id="5c613-103">The XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enable you to perform tasks on schemas, maps, and message instances.</span></span> <span data-ttu-id="5c613-104">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 环境中，您可以在设计时使用这些扩展。</span><span class="sxs-lookup"><span data-stu-id="5c613-104">You use these extensions at design time in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="5c613-105">您可以执行的任务有：</span><span class="sxs-lookup"><span data-stu-id="5c613-105">The tasks you can perform are:</span></span>  
  
-   <span data-ttu-id="5c613-106">**验证架构**。</span><span class="sxs-lookup"><span data-stu-id="5c613-106">**Validating a schema**.</span></span> <span data-ttu-id="5c613-107">此操作将根据 EDI 规则对 EDI 架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="5c613-107">This operation validates an EDI schema based on EDI rules.</span></span> <span data-ttu-id="5c613-108">有关详细信息，请参阅[验证架构 (EDI)](../core/validating-a-schema-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="5c613-108">For more information, see [Validating a Schema (EDI)](../core/validating-a-schema-edi.md).</span></span>  
  
-   <span data-ttu-id="5c613-109">**验证消息实例**。</span><span class="sxs-lookup"><span data-stu-id="5c613-109">**Validating a message instance**.</span></span> <span data-ttu-id="5c613-110">此操作将验证单个事务集（没有交换和组标头）或包含多个事务集的完整批处理交换（带有交换和组标头）。</span><span class="sxs-lookup"><span data-stu-id="5c613-110">This operation validates a single transaction set (without interchange and group headers) or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span> <span data-ttu-id="5c613-111">若要验证未批处理的交换，需要从实例中删除交换和组标头。</span><span class="sxs-lookup"><span data-stu-id="5c613-111">To validate an unbatched interchange, you need to remove the interchange and group headers from the instance.</span></span> <span data-ttu-id="5c613-112">有关详细信息，请参阅[验证实例 (EDI)](../core/validating-an-instance-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="5c613-112">For more information, see [Validating an Instance (EDI)](../core/validating-an-instance-edi.md).</span></span>  
  
-   <span data-ttu-id="5c613-113">**生成的消息实例**。</span><span class="sxs-lookup"><span data-stu-id="5c613-113">**Generating a message instance**.</span></span> <span data-ttu-id="5c613-114">此操作可以生成完整的批处理交换或不带交换和组标头的事务集。</span><span class="sxs-lookup"><span data-stu-id="5c613-114">This operation generates either a complete batched interchange or a transaction set without interchange and group headers.</span></span> <span data-ttu-id="5c613-115">您必须指定分隔符、标识符以及要用于生成实例的其他格式设置。</span><span class="sxs-lookup"><span data-stu-id="5c613-115">You must specify the separators, identifiers, and other formatting used to generate the instance.</span></span> <span data-ttu-id="5c613-116">有关详细信息，请参阅[生成实例 (EDI)](../core/generating-an-instance-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="5c613-116">For more information, see [Generating an Instance (EDI)](../core/generating-an-instance-edi.md).</span></span>  
  
-   <span data-ttu-id="5c613-117">**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="5c613-117">**Testing a map**.</span></span> <span data-ttu-id="5c613-118">此操作将根据源文档和映射生成输出文档（带有虚构数据）。</span><span class="sxs-lookup"><span data-stu-id="5c613-118">This operation generates an output document (with fictitious data) based upon a source document and a map.</span></span> <span data-ttu-id="5c613-119">有关详细信息，请参阅[测试映射](../core/testing-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="5c613-119">For more information, see [Testing a Map](../core/testing-a-map.md).</span></span>  
  
-   <span data-ttu-id="5c613-120">**验证地图**。</span><span class="sxs-lookup"><span data-stu-id="5c613-120">**Validating a map**.</span></span> <span data-ttu-id="5c613-121">此操作将生成两个文件，一个包含映射的基础 XSLT，另一个包含扩展对象。</span><span class="sxs-lookup"><span data-stu-id="5c613-121">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span> <span data-ttu-id="5c613-122">有关详细信息，请参阅[验证映射 (EDI)](../core/validating-a-map-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="5c613-122">For more information, see [Validating a Map (EDI)](../core/validating-a-map-edi.md).</span></span>  
  
 <span data-ttu-id="5c613-123">在 BizTalk Server 中，这些扩展处理 EDI 架构、 映射和消息实例。</span><span class="sxs-lookup"><span data-stu-id="5c613-123">In BizTalk Server, these extensions work on EDI schemas, maps, and message instances.</span></span> <span data-ttu-id="5c613-124">使用这些扩展，您可以更有效地处理复杂的 EDI 架构、映射和交换。</span><span class="sxs-lookup"><span data-stu-id="5c613-124">These extensions enable you to work more effectively with complex EDI schemas, maps, and interchanges.</span></span>  
  
 <span data-ttu-id="5c613-125">默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序将启用 XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="5c613-125">XML Tool extensions are enabled by default by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="5c613-126">如果双击在解决方案资源管理器的 Visual Studio 中，架构**架构编辑器扩展**的架构的属性设置为**EDI 架构编辑器扩展**。</span><span class="sxs-lookup"><span data-stu-id="5c613-126">If you double-click a schema in Solution Explorer of Visual Studio, the **Schema Editor Extensions** property of the schema is set to **EDI Schema Editor Extension**.</span></span> <span data-ttu-id="5c613-127">这样才能使 XML 工具扩展正常工作。</span><span class="sxs-lookup"><span data-stu-id="5c613-127">This is required for the XML Tool extensions to function.</span></span> <span data-ttu-id="5c613-128">您可以选择其他架构编辑器扩展，同时保持选中 EDI 扩展。</span><span class="sxs-lookup"><span data-stu-id="5c613-128">You can select other schema editor extension while leaving the EDI extensions selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c613-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c613-129">See Also</span></span>  
 <span data-ttu-id="5c613-130">[生成实例 (EDI)](../core/generating-an-instance-edi.md) </span><span class="sxs-lookup"><span data-stu-id="5c613-130">[Generating an Instance (EDI)](../core/generating-an-instance-edi.md) </span></span>  
 <span data-ttu-id="5c613-131">[验证实例 (EDI)](../core/validating-an-instance-edi.md) </span><span class="sxs-lookup"><span data-stu-id="5c613-131">[Validating an Instance (EDI)](../core/validating-an-instance-edi.md) </span></span>  
 <span data-ttu-id="5c613-132">[验证架构 (EDI)](../core/validating-a-schema-edi.md) </span><span class="sxs-lookup"><span data-stu-id="5c613-132">[Validating a Schema (EDI)](../core/validating-a-schema-edi.md) </span></span>  
 <span data-ttu-id="5c613-133">[测试映射](../core/testing-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="5c613-133">[Testing a Map](../core/testing-a-map.md) </span></span>  
 [<span data-ttu-id="5c613-134">验证映射 (EDI)</span><span class="sxs-lookup"><span data-stu-id="5c613-134">Validating a Map (EDI)</span></span>](../core/validating-a-map-edi.md)