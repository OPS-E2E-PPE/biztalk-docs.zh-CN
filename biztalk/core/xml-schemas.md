---
title: "XML 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86760d50b729419f31ba8186033181e0d03ad14c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="xml-schemas"></a><span data-ttu-id="f2547-102">XML 架构</span><span class="sxs-lookup"><span data-stu-id="f2547-102">XML Schemas</span></span>
<span data-ttu-id="f2547-103">XML 架构描述了以 XML 表示的业务文档。</span><span class="sxs-lookup"><span data-stu-id="f2547-103">An XML schema describes a business document that is represented in XML.</span></span> <span data-ttu-id="f2547-104">由于 Microsoft BizTalk Server 使用 XML 作为其规范表示形式的业务文档，入站和出站文档不需要进行任何变换。</span><span class="sxs-lookup"><span data-stu-id="f2547-104">Because Microsoft BizTalk Server uses XML as its canonical representation for business documents, inbound and outbound documents do not require any translation.</span></span> <span data-ttu-id="f2547-105">可以只使用在所有架构中都可用的一组基本属性在 BizTalk 编辑器中创建 XML 架构，并且不需要启用任何架构编辑器扩展。</span><span class="sxs-lookup"><span data-stu-id="f2547-105">XML schemas can be created in BizTalk Editor using only the basic set of properties that are available within all schemas, and do not require any schema editor extensions to be enabled.</span></span>  
  
 <span data-ttu-id="f2547-106">有几种方法可以在其中创建 BizTalk Server 中的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-106">There are several ways in which you can create XML schemas in BizTalk Server.</span></span> <span data-ttu-id="f2547-107">其中包括：</span><span class="sxs-lookup"><span data-stu-id="f2547-107">These include:</span></span>  
  
-   <span data-ttu-id="f2547-108">**创建新的架构**。</span><span class="sxs-lookup"><span data-stu-id="f2547-108">**Creating a new schema**.</span></span> <span data-ttu-id="f2547-109">此架构创建方法涉及向 BizTalk 项目中添加新架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-109">This method of schema creation involves adding a new schema to a BizTalk project.</span></span> <span data-ttu-id="f2547-110">在**解决方案资源管理器**，右键单击 BizTalk 项目，单击**添加**，单击**新项**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="f2547-110">In **Solution Explorer**, right-click the BizTalk project, click **Add**, click **New Item**, and then click **Schema**.</span></span> <span data-ttu-id="f2547-111">通过将各种节点添加架构树视图中，生成架构的结构。</span><span class="sxs-lookup"><span data-stu-id="f2547-111">Build up the structure of the schema by adding various nodes in the schema tree view.</span></span>  
  
-   <span data-ttu-id="f2547-112">**结合其他架构中创建新的架构，**。</span><span class="sxs-lookup"><span data-stu-id="f2547-112">**Creating a new schema, in conjunction with other schemas**.</span></span> <span data-ttu-id="f2547-113">对于实际情况中的复杂架构，您可能更希望使用其他现有架构中提供的类型来为消息生成架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-113">For complex schemas in the real world, you are more likely to build the schemas for your messages by using types provided in other existing schemas.</span></span> <span data-ttu-id="f2547-114">通过使用导入、包括和重新定义架构的 XML 架构定义 (XSD) 语言概念，可以利用在其他架构中已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="f2547-114">By using the XML Schema definition (XSD) language concepts of importing, including, and redefining schemas, you can take advantage of types already defined in other schemas.</span></span> <span data-ttu-id="f2547-115">有关结合使用多个架构的详细信息，请参阅[架构，使用其他架构](../core/schemas-that-use-other-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="f2547-115">For more information about using multiple schemas together, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span>  
  
-   <span data-ttu-id="f2547-116">**从实例消息生成架构**。</span><span class="sxs-lookup"><span data-stu-id="f2547-116">**Generating a schema from an instance message**.</span></span> <span data-ttu-id="f2547-117">只要特定的实例消息是由格式正确的 XML 组成，就可以生成对应于该实例消息的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-117">You can generate an XML schema that corresponds to a particular instance message as long as that instance message consists of well-formed XML.</span></span> <span data-ttu-id="f2547-118">使用**添加生成的项的 *\<BizTalk 项目名称\>*** 对话框中，通过单击访问**添加生成的项**上**项目**菜单上，若要执行此类型的架构生成操作。</span><span class="sxs-lookup"><span data-stu-id="f2547-118">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2547-119">此类生成操作只能用于生成 XML 架构，而不能用于生成属性架构或平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-119">This type of generation operation can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
-   <span data-ttu-id="f2547-120">**从较旧的架构规范语言的架构迁移到 XSD**。</span><span class="sxs-lookup"><span data-stu-id="f2547-120">**Migrating a schema from an older schema specification language to XSD**.</span></span> <span data-ttu-id="f2547-121">可以从开发的使用以 XML 数据简化 (XDR) 格式存储架构的 BizTalk Server 的早期版本的架构的 BizTalk Server 中生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-121">You can generate an XML schema for BizTalk Server from a schema that was developed by using a previous version of BizTalk Server, which stored schemas in XML-Data Reduced (XDR) format.</span></span> <span data-ttu-id="f2547-122">有关如何将较旧的 XDR 架构迁移到 BizTalk Server 使用的 XSD 格式的详细信息，请参阅[架构迁移从以前版本的 BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f2547-122">For more information about how to migrate older XDR schemas to the XSD format used by BizTalk Server, see [Schema Migration from Previous Versions of BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md).</span></span>  
  
     <span data-ttu-id="f2547-123">还可以从使用文档类型定义 (DTD) 语法表示的文档架构生成基于 XSD 的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-123">You can also generate an XML schema based on XSD from a document schema expressed by using the Document Type Definition (DTD) syntax.</span></span>  
  
     <span data-ttu-id="f2547-124">使用**添加生成的项的 *\<BizTalk 项目名称\>*** 对话框中，通过单击访问**添加生成的项**上**项目**菜单上，若要执行此类型的架构生成操作。</span><span class="sxs-lookup"><span data-stu-id="f2547-124">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2547-125">这些类型的生成操作只能用于生成 XML 架构，而不能用于生成属性架构或平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="f2547-125">These types of generation operations can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
 <span data-ttu-id="f2547-126">无论使用哪一种架构创建方法，都需要进一步修改架构，以便该架构可为其对应的实例消息提供足够完整的说明。</span><span class="sxs-lookup"><span data-stu-id="f2547-126">Whichever schema creation technique you use, you will continue by modifying the schema so that it provides a sufficiently complete description of its corresponding instance messages.</span></span> <span data-ttu-id="f2547-127">若要开始，这些任务，请参阅[管理架构节点内](../core/managing-the-nodes-within-a-schema.md)，[设置节点属性](../core/how-to-set-node-properties.md)，和[使用现有节点](../core/working-with-existing-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="f2547-127">To get started on these tasks, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md), [Setting Node Properties](../core/how-to-set-node-properties.md), and [Working with Existing Nodes](../core/working-with-existing-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2547-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2547-128">See Also</span></span>  
 [<span data-ttu-id="f2547-129">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="f2547-129">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)