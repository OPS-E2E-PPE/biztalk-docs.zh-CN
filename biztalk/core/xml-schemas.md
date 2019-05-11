---
title: XML 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f46a4ed9f834d09993dfa2edb48b3e875b0f3699
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298401"
---
# <a name="xml-schemas"></a><span data-ttu-id="289ad-102">XML 架构</span><span class="sxs-lookup"><span data-stu-id="289ad-102">XML Schemas</span></span>
<span data-ttu-id="289ad-103">XML 架构描述了在 XML 中表示的业务文档。</span><span class="sxs-lookup"><span data-stu-id="289ad-103">An XML schema describes a business document that is represented in XML.</span></span> <span data-ttu-id="289ad-104">由于 Microsoft BizTalk Server 使用 XML 作为其规范表示形式的业务文档，入站和出站文档不需要任何转换。</span><span class="sxs-lookup"><span data-stu-id="289ad-104">Because Microsoft BizTalk Server uses XML as its canonical representation for business documents, inbound and outbound documents do not require any translation.</span></span> <span data-ttu-id="289ad-105">可以在 BizTalk 编辑器中使用仅可在所有架构，且不需要启用任何架构编辑器扩展属性的基本集创建 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-105">XML schemas can be created in BizTalk Editor using only the basic set of properties that are available within all schemas, and do not require any schema editor extensions to be enabled.</span></span>  
  
 <span data-ttu-id="289ad-106">有几种方法可在其中创建 BizTalk Server 中的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-106">There are several ways in which you can create XML schemas in BizTalk Server.</span></span> <span data-ttu-id="289ad-107">这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="289ad-107">These include:</span></span>  
  
- <span data-ttu-id="289ad-108">**创建新架构**。</span><span class="sxs-lookup"><span data-stu-id="289ad-108">**Creating a new schema**.</span></span> <span data-ttu-id="289ad-109">此架构创建方法涉及向 BizTalk 项目中添加新架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-109">This method of schema creation involves adding a new schema to a BizTalk project.</span></span> <span data-ttu-id="289ad-110">在中**解决方案资源管理器**，右键单击 BizTalk 项目，单击**添加**，单击**新项**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="289ad-110">In **Solution Explorer**, right-click the BizTalk project, click **Add**, click **New Item**, and then click **Schema**.</span></span> <span data-ttu-id="289ad-111">通过添加多个节点在架构树视图中生成的架构的结构。</span><span class="sxs-lookup"><span data-stu-id="289ad-111">Build up the structure of the schema by adding various nodes in the schema tree view.</span></span>  
  
- <span data-ttu-id="289ad-112">**创建新的架构，结合其他架构**。</span><span class="sxs-lookup"><span data-stu-id="289ad-112">**Creating a new schema, in conjunction with other schemas**.</span></span> <span data-ttu-id="289ad-113">对于现实生活中的复杂架构，则更有可能使用其他现有架构中提供的类型生成您的消息的架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-113">For complex schemas in the real world, you are more likely to build the schemas for your messages by using types provided in other existing schemas.</span></span> <span data-ttu-id="289ad-114">通过使用导入的 XML 架构定义 (XSD) 语言概念，包括和重新定义架构，您可以充分利用已在其他架构中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="289ad-114">By using the XML Schema definition (XSD) language concepts of importing, including, and redefining schemas, you can take advantage of types already defined in other schemas.</span></span> <span data-ttu-id="289ad-115">有关将多个架构一起使用的详细信息，请参阅[使用其他架构的](../core/schemas-that-use-other-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="289ad-115">For more information about using multiple schemas together, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span>  
  
- <span data-ttu-id="289ad-116">**从实例消息生成架构**。</span><span class="sxs-lookup"><span data-stu-id="289ad-116">**Generating a schema from an instance message**.</span></span> <span data-ttu-id="289ad-117">可以生成对应于特定的实例消息，只要该实例消息包含格式正确的 XML 的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-117">You can generate an XML schema that corresponds to a particular instance message as long as that instance message consists of well-formed XML.</span></span> <span data-ttu-id="289ad-118">使用**添加生成的项-  *\<BizTalk 项目名称\>*** 对话框中，通过单击来访问**添加生成的项**上**项目**菜单中，若要执行此类型的架构生成操作。</span><span class="sxs-lookup"><span data-stu-id="289ad-118">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="289ad-119">此类型的生成操作只能用于生成 XML 架构、 不是属性架构或平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-119">This type of generation operation can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
- <span data-ttu-id="289ad-120">**将架构从旧的架构规范语言迁移到 XSD**。</span><span class="sxs-lookup"><span data-stu-id="289ad-120">**Migrating a schema from an older schema specification language to XSD**.</span></span> <span data-ttu-id="289ad-121">可以从已通过使用以前版本的 BizTalk Server，以 XML 数据缩减 (XDR) 格式存储架构开发的架构的 BizTalk Server 中生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-121">You can generate an XML schema for BizTalk Server from a schema that was developed by using a previous version of BizTalk Server, which stored schemas in XML-Data Reduced (XDR) format.</span></span> <span data-ttu-id="289ad-122">有关如何将旧 XDR 架构迁移到 BizTalk Server 使用的 XSD 格式的详细信息，请参阅[从以前版本的 BizTalk Server 迁移架构](../core/schema-migration-from-previous-versions-of-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="289ad-122">For more information about how to migrate older XDR schemas to the XSD format used by BizTalk Server, see [Schema Migration from Previous Versions of BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md).</span></span>  
  
   <span data-ttu-id="289ad-123">此外可以生成基于 XSD 从使用文档类型定义 (DTD) 语法表示的文档架构的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-123">You can also generate an XML schema based on XSD from a document schema expressed by using the Document Type Definition (DTD) syntax.</span></span>  
  
   <span data-ttu-id="289ad-124">使用**添加生成的项-  *\<BizTalk 项目名称\>*** 对话框中，通过单击来访问**添加生成的项**上**项目**菜单中，若要执行此类型的架构生成操作。</span><span class="sxs-lookup"><span data-stu-id="289ad-124">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="289ad-125">这些类型的生成操作只能用于生成 XML 架构、 不是属性架构或平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="289ad-125">These types of generation operations can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
  <span data-ttu-id="289ad-126">无论您使用的架构创建方法将继续通过修改架构，以便它提供了其相应的实例消息的足够完整的说明。</span><span class="sxs-lookup"><span data-stu-id="289ad-126">Whichever schema creation technique you use, you will continue by modifying the schema so that it provides a sufficiently complete description of its corresponding instance messages.</span></span> <span data-ttu-id="289ad-127">若要开始这些任务，请参阅[管理节点架构中](../core/managing-the-nodes-within-a-schema.md)，[设置节点属性](../core/how-to-set-node-properties.md)，并[使用现有节点](../core/working-with-existing-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="289ad-127">To get started on these tasks, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md), [Setting Node Properties](../core/how-to-set-node-properties.md), and [Working with Existing Nodes](../core/working-with-existing-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289ad-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="289ad-128">See Also</span></span>  
 [<span data-ttu-id="289ad-129">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="289ad-129">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)