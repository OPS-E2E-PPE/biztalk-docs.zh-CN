---
title: 使用 XML 工具扩展 |Microsoft Docs
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
ms.openlocfilehash: fd45548534cc9cbd7968d39e810210acf472cf0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302684"
---
# <a name="using-the-xml-tool-extensions"></a><span data-ttu-id="40be1-102">使用 XML 工具扩展</span><span class="sxs-lookup"><span data-stu-id="40be1-102">Using the XML Tool Extensions</span></span>
<span data-ttu-id="40be1-103">XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使您能够执行的任务上架构、 映射和消息实例。</span><span class="sxs-lookup"><span data-stu-id="40be1-103">The XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enable you to perform tasks on schemas, maps, and message instances.</span></span> <span data-ttu-id="40be1-104">在设计时使用这些扩展[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="40be1-104">You use these extensions at design time in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="40be1-105">你可以执行的任务包括：</span><span class="sxs-lookup"><span data-stu-id="40be1-105">The tasks you can perform are:</span></span>  
  
- <span data-ttu-id="40be1-106">**验证架构**。</span><span class="sxs-lookup"><span data-stu-id="40be1-106">**Validating a schema**.</span></span> <span data-ttu-id="40be1-107">此操作将验证 EDI 架构根据 EDI 规则。</span><span class="sxs-lookup"><span data-stu-id="40be1-107">This operation validates an EDI schema based on EDI rules.</span></span> <span data-ttu-id="40be1-108">有关详细信息，请参阅[验证架构 (EDI)](../core/validating-a-schema-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="40be1-108">For more information, see [Validating a Schema (EDI)](../core/validating-a-schema-edi.md).</span></span>  
  
- <span data-ttu-id="40be1-109">**验证消息实例**。</span><span class="sxs-lookup"><span data-stu-id="40be1-109">**Validating a message instance**.</span></span> <span data-ttu-id="40be1-110">此操作将验证单个事务集 （没有交换和组标头） 或包含多个事务的完整批处理的交换设置 （带有交换和组标头）。</span><span class="sxs-lookup"><span data-stu-id="40be1-110">This operation validates a single transaction set (without interchange and group headers) or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span> <span data-ttu-id="40be1-111">若要验证未批处理的交换，需要从实例中删除交换和组标头。</span><span class="sxs-lookup"><span data-stu-id="40be1-111">To validate an unbatched interchange, you need to remove the interchange and group headers from the instance.</span></span> <span data-ttu-id="40be1-112">有关详细信息，请参阅[验证实例 (EDI)](../core/validating-an-instance-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="40be1-112">For more information, see [Validating an Instance (EDI)](../core/validating-an-instance-edi.md).</span></span>  
  
- <span data-ttu-id="40be1-113">**生成消息实例**。</span><span class="sxs-lookup"><span data-stu-id="40be1-113">**Generating a message instance**.</span></span> <span data-ttu-id="40be1-114">此操作将生成完整的批的交换或事务集没有交换和组标头。</span><span class="sxs-lookup"><span data-stu-id="40be1-114">This operation generates either a complete batched interchange or a transaction set without interchange and group headers.</span></span> <span data-ttu-id="40be1-115">必须指定分隔符、 标识符和其他用于生成该实例的格式设置。</span><span class="sxs-lookup"><span data-stu-id="40be1-115">You must specify the separators, identifiers, and other formatting used to generate the instance.</span></span> <span data-ttu-id="40be1-116">有关详细信息，请参阅[生成实例 (EDI)](../core/generating-an-instance-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="40be1-116">For more information, see [Generating an Instance (EDI)](../core/generating-an-instance-edi.md).</span></span>  
  
- <span data-ttu-id="40be1-117">**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="40be1-117">**Testing a map**.</span></span> <span data-ttu-id="40be1-118">此操作将生成输出文档 （具有虚构数据） 基于源文档和映射。</span><span class="sxs-lookup"><span data-stu-id="40be1-118">This operation generates an output document (with fictitious data) based upon a source document and a map.</span></span> <span data-ttu-id="40be1-119">有关详细信息，请参阅[测试映射](../core/testing-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="40be1-119">For more information, see [Testing a Map](../core/testing-a-map.md).</span></span>  
  
- <span data-ttu-id="40be1-120">**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="40be1-120">**Validating a map**.</span></span> <span data-ttu-id="40be1-121">此操作将生成包含基础映射和包含扩展对象的文件的 XSLT 的文件。</span><span class="sxs-lookup"><span data-stu-id="40be1-121">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span> <span data-ttu-id="40be1-122">有关详细信息，请参阅[验证映射 (EDI)](../core/validating-a-map-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="40be1-122">For more information, see [Validating a Map (EDI)](../core/validating-a-map-edi.md).</span></span>  
  
  <span data-ttu-id="40be1-123">在 BizTalk Server 中，这些扩展处理 EDI 架构、 映射和消息实例。</span><span class="sxs-lookup"><span data-stu-id="40be1-123">In BizTalk Server, these extensions work on EDI schemas, maps, and message instances.</span></span> <span data-ttu-id="40be1-124">这些扩展使您能够更有效地处理复杂的 EDI 架构、 映射和交换。</span><span class="sxs-lookup"><span data-stu-id="40be1-124">These extensions enable you to work more effectively with complex EDI schemas, maps, and interchanges.</span></span>  
  
  <span data-ttu-id="40be1-125">默认情况下将启用 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="40be1-125">XML Tool extensions are enabled by default by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="40be1-126">如果您双击解决方案资源管理器的 Visual Studio 中，架构**架构编辑器扩展**架构的属性设置为**EDI 架构编辑器扩展**。</span><span class="sxs-lookup"><span data-stu-id="40be1-126">If you double-click a schema in Solution Explorer of Visual Studio, the **Schema Editor Extensions** property of the schema is set to **EDI Schema Editor Extension**.</span></span> <span data-ttu-id="40be1-127">这是必需的 XML 工具扩展正常工作。</span><span class="sxs-lookup"><span data-stu-id="40be1-127">This is required for the XML Tool extensions to function.</span></span> <span data-ttu-id="40be1-128">保持选中 EDI 扩展时，可以选择其他架构编辑器扩展。</span><span class="sxs-lookup"><span data-stu-id="40be1-128">You can select other schema editor extension while leaving the EDI extensions selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40be1-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="40be1-129">See Also</span></span>  
 <span data-ttu-id="40be1-130">[生成实例 (EDI)](../core/generating-an-instance-edi.md) </span><span class="sxs-lookup"><span data-stu-id="40be1-130">[Generating an Instance (EDI)](../core/generating-an-instance-edi.md) </span></span>  
 <span data-ttu-id="40be1-131">[验证实例 (EDI)](../core/validating-an-instance-edi.md) </span><span class="sxs-lookup"><span data-stu-id="40be1-131">[Validating an Instance (EDI)](../core/validating-an-instance-edi.md) </span></span>  
 <span data-ttu-id="40be1-132">[验证架构 (EDI)](../core/validating-a-schema-edi.md) </span><span class="sxs-lookup"><span data-stu-id="40be1-132">[Validating a Schema (EDI)](../core/validating-a-schema-edi.md) </span></span>  
 <span data-ttu-id="40be1-133">[测试映射](../core/testing-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="40be1-133">[Testing a Map](../core/testing-a-map.md) </span></span>  
 [<span data-ttu-id="40be1-134">验证映射 (EDI)</span><span class="sxs-lookup"><span data-stu-id="40be1-134">Validating a Map (EDI)</span></span>](../core/validating-a-map-edi.md)