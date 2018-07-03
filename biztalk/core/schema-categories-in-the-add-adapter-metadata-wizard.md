---
title: 中的架构类别添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927c676-f60a-449e-be43-6f75e28aefe1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46fd9ffab7aa4f8617e08a18824cc251ad9f4173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008006"
---
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a><span data-ttu-id="b424c-102">中的架构类别添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="b424c-102">Schema Categories in the Add Adapter Metadata Wizard</span></span>

## <a name="overview"></a><span data-ttu-id="b424c-103">概述</span><span class="sxs-lookup"><span data-stu-id="b424c-103">Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="b424c-104">本主题仅适用于实现的静态适配器**IStaticAdapterConfig**接口。</span><span class="sxs-lookup"><span data-stu-id="b424c-104">This topic is only for static adapters that implement the **IStaticAdapterConfig** interface.</span></span>  
  
 <span data-ttu-id="b424c-105">适配器可能会使用任意一种成千上万的架构将数据转换之前将其传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b424c-105">An adapter may use any one of thousands of schemas to transform data before passing it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b424c-106">向某个 BizTalk 项目添加元数据时，使用“添加适配器元数据”向导可以从与适配器交互的所有架构的列表中选择所需架构。</span><span class="sxs-lookup"><span data-stu-id="b424c-106">When adding metadata to a BizTalk project, use the Add Adapter Metadata Wizard to select a schema from a list of all the schemas with which the adapter interacts.</span></span>  
  
 <span data-ttu-id="b424c-107">在示例文件适配器中，CategorySchema.xml 文件是一个架构实例，它与适配器框架的 BiztalkAdapterFramework.xsd 文件一起用于填充服务架构的树视图组织。</span><span class="sxs-lookup"><span data-stu-id="b424c-107">In the sample file adapter, the CategorySchema.xml file is a schema instance that is used in conjunction with the Adapter Framework's BiztalkAdapterFramework.xsd file to populate a tree-view organization of service schemas.</span></span>  <span data-ttu-id="b424c-108">BizTalkAdapterFramework.xsd 文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] Developer Tools 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b424c-108">The BizTalkAdapterFramework.xsd file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools folder.</span></span>  
  
 <span data-ttu-id="b424c-109">应该创建此文件，以便按照对您的解决方案直观明了的方式来组织架构。</span><span class="sxs-lookup"><span data-stu-id="b424c-109">You should create this file so that it organizes the schemas in a manner that is intuitive to your solution.</span></span> <span data-ttu-id="b424c-110">CategorySchema.xml 中的现有类别仅作为示例，向您演示您可以在自己的树中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b424c-110">The existing categories in CategorySchema.xml are just an example of what you can do in your own tree.</span></span> <span data-ttu-id="b424c-111">这些类别与示例适配器所传递的数据没有任何特别的关联。</span><span class="sxs-lookup"><span data-stu-id="b424c-111">The categories do not have any particular relevance to the data that is passed by the sample adapter.</span></span> <span data-ttu-id="b424c-112">架构的组织方式对特定于应用程序的适配器尤为重要，适配器中可能包含成千上万的不同架构。</span><span class="sxs-lookup"><span data-stu-id="b424c-112">The organization of the schemas is particularly important with application-specific adapters, where thousands of different schemas may be available.</span></span> <span data-ttu-id="b424c-113">对于特定于传输的适配器，不必使用树视图组织。</span><span class="sxs-lookup"><span data-stu-id="b424c-113">For transport-specific adapters, this tree-view organization is unnecessary.</span></span>  
  
 <span data-ttu-id="b424c-114">下图显示**选择导入的服务**添加适配器元数据向导中的页。</span><span class="sxs-lookup"><span data-stu-id="b424c-114">The following figure shows the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="b424c-115">![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")</span><span class="sxs-lookup"><span data-stu-id="b424c-115">![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")</span></span>  
<span data-ttu-id="b424c-116">“添加适配器元数据”向导中的架构类别树视图</span><span class="sxs-lookup"><span data-stu-id="b424c-116">Tree view of the schema categories in the Add Adapter Metadata Wizard</span></span>  


## <a name="sample-xml"></a><span data-ttu-id="b424c-117">示例 XML</span><span class="sxs-lookup"><span data-stu-id="b424c-117">Sample XML</span></span>
  
 <span data-ttu-id="b424c-118">下面的代码显示 CategorySchema.xml 文件：</span><span class="sxs-lookup"><span data-stu-id="b424c-118">The following code shows the CategorySchema.xml file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<CategoryTree>  
     <DisplayName>Services Organization</DisplayName>  
     <DisplayDescription>An organization of application services</DisplayDescription>  
     <CategoryTreeNode>  
          <DisplayName>Health Care</DisplayName>  
          <Description>Services under Health Care</Description>  
          <CategoryTreeNode>  
               <DisplayName>Administrative</DisplayName>  
               <Description>Administrative Health Care Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Eligibility</DisplayName>  
                    <Description>Eligibility Verification Transactions</Description>  
                    <WSDLReference>ANSI X 12 270</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
     <CategoryTreeNode>  
          <DisplayName>Manufacturing</DisplayName>  
          <Description>Manufacturing Services</Description>  
          <CategoryTreeNode>  
               <DisplayName>Inventory</DisplayName>  
               <Description>Inventory Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Requisition</DisplayName>  
                    <Description>Requisition</Description>  
                    <WSDLReference>RequisitionService</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
</CategoryTree>  
```  
  
 <span data-ttu-id="b424c-119">此架构实例中存在下列节点类型：</span><span class="sxs-lookup"><span data-stu-id="b424c-119">The following node types appear in this schema instance:</span></span>  
  
- <span data-ttu-id="b424c-120">**CategoryTree。**</span><span class="sxs-lookup"><span data-stu-id="b424c-120">**CategoryTree.**</span></span> <span data-ttu-id="b424c-121">模型的系统信息的顶级结构。</span><span class="sxs-lookup"><span data-stu-id="b424c-121">Top-level structure of a model of system information.</span></span> <span data-ttu-id="b424c-122">包含零个或多个 CategoryTreeNode、 ExpandableCategoryTreeNode 和 ServiceTreeNode 节点。</span><span class="sxs-lookup"><span data-stu-id="b424c-122">Contains zero or more of the CategoryTreeNode, ExpandableCategoryTreeNode, and ServiceTreeNode nodes.</span></span>  
  
- <span data-ttu-id="b424c-123">**CategoryTreeNode。**</span><span class="sxs-lookup"><span data-stu-id="b424c-123">**CategoryTreeNode.**</span></span> <span data-ttu-id="b424c-124">包含零个或多个 CategoryTreeNode 和 ServiceTreeNode 节点。</span><span class="sxs-lookup"><span data-stu-id="b424c-124">Contains zero or more CategoryTreeNode and ServiceTreeNode nodes.</span></span> <span data-ttu-id="b424c-125">使用显示文件夹中的用户界面 (UI) 将一组相关服务为 CategoryTreeNode。</span><span class="sxs-lookup"><span data-stu-id="b424c-125">Use the CategoryTreeNode that appears as a folder in the user interface (UI) to group a set of related services.</span></span> <span data-ttu-id="b424c-126">通常，这包含显示名称和要显示的服务的描述。</span><span class="sxs-lookup"><span data-stu-id="b424c-126">Typically this contains a display name and description of the services to be displayed.</span></span> <span data-ttu-id="b424c-127">如果子节点的数目较小，适配器可能使用 CategoryTreeNode。</span><span class="sxs-lookup"><span data-stu-id="b424c-127">An adapter might use a CategoryTreeNode if the number of child nodes is small.</span></span>  
  
- <span data-ttu-id="b424c-128">**ExpandableCategoryTreeNode。**</span><span class="sxs-lookup"><span data-stu-id="b424c-128">**ExpandableCategoryTreeNode.**</span></span> <span data-ttu-id="b424c-129">展开时，将动态填充一个叶节点。</span><span class="sxs-lookup"><span data-stu-id="b424c-129">A leaf node that is dynamically populated when expanded.</span></span> <span data-ttu-id="b424c-130">ExpandableCategoryTreeNode 用作占位符，并出现在 UI 中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b424c-130">The ExpandableCategoryTreeNode is used as a placeholder and appears as a folder in the UI.</span></span> <span data-ttu-id="b424c-131">这可以用于延迟填充具有子元素的类别节点，直到用户单击以展开的节点。</span><span class="sxs-lookup"><span data-stu-id="b424c-131">This can be used to defer populating a category node with subelements until the user clicks to expand the node.</span></span> <span data-ttu-id="b424c-132">适配器可能会使用 ExpandableCategoryTreeNode，如果类别包含大量的子节点。</span><span class="sxs-lookup"><span data-stu-id="b424c-132">An adapter might use an ExpandableCategoryTreeNode if a category contains a large number of child nodes.</span></span>  
  
- <span data-ttu-id="b424c-133">**ServiceTreeNode。**</span><span class="sxs-lookup"><span data-stu-id="b424c-133">**ServiceTreeNode.**</span></span> <span data-ttu-id="b424c-134">ServiceTreeNode 为文档或叶节点，在 UI 中的显示，表示 Web 服务描述语言 (WSDL) 文件。</span><span class="sxs-lookup"><span data-stu-id="b424c-134">A ServiceTreeNode appears as a document, or leaf node, in the UI and represents a Web Services Description Language (WSDL) file.</span></span>  
  
  <span data-ttu-id="b424c-135">当用户单击来展开一个节点的文件夹时，适配器框架将调用**IStaticAdapterConfig.GetServiceOrganization**作为值传递的节点名称的适配器上的方法**NodeIdentifier**属性。</span><span class="sxs-lookup"><span data-stu-id="b424c-135">When a user clicks the folder to expand a node, the Adapter Framework calls the **IStaticAdapterConfig.GetServiceOrganization** method on the adapter passing the name of the node as the value of the **NodeIdentifier** attribute.</span></span> <span data-ttu-id="b424c-136">适配器应返回包含子节点 CategoryTree，若要添加 ExpandableCategoryTreeNode 下。</span><span class="sxs-lookup"><span data-stu-id="b424c-136">The adapter should return a CategoryTree containing the subnodes to add under the ExpandableCategoryTreeNode.</span></span> <span data-ttu-id="b424c-137">适配器框架 ExpandableCategoryTreeNode 替换 CategoryTreeNode 并向其添加返回 CategoryTree 的子级。</span><span class="sxs-lookup"><span data-stu-id="b424c-137">The Adapter Framework replaces the ExpandableCategoryTreeNode with a CategoryTreeNode and adds to it the children of the returned CategoryTree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b424c-138">在首次调用**IStaticAdapterConfig.GetServiceOrganization**适配器框架将传递的节点标识符为 null。</span><span class="sxs-lookup"><span data-stu-id="b424c-138">In the initial call to **IStaticAdapterConfig.GetServiceOrganization** the Adapter Framework passes null for the node identifier.</span></span> <span data-ttu-id="b424c-139">这将告知适配器返回根级别 CategoryTree。</span><span class="sxs-lookup"><span data-stu-id="b424c-139">This tells the adapter to return the root-level CategoryTree.</span></span>  
  
 <span data-ttu-id="b424c-140">下面是从 BiztalkAdapterFramework.xsd 文件中提取的类别树架构。</span><span class="sxs-lookup"><span data-stu-id="b424c-140">Below is the category tree schema extracted from the BiztalkAdapterFramework.xsd file.</span></span> <span data-ttu-id="b424c-141">这是用来填充从 XML 文件的特定应用程序依赖于实体框架的树形使用添加适配器元数据向导。</span><span class="sxs-lookup"><span data-stu-id="b424c-141">This is used by the Add Adapter Metadata Wizard as the skeleton tree with which to populate with specific application-dependent entities from an XML file.</span></span> <span data-ttu-id="b424c-142">在本例中该文件是 CategorySchema.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="b424c-142">In our example that file is the CategorySchema.xml file.</span></span>  
  
```  
<!-- Service Organization Tree schema used by Add Adapter Wizard -->  
    <xs:element name="CategoryTree" type="CategoryTree" />  
    <xs:complexType name="CategoryTree">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="DisplayDescription" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ExpandableCategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
        </xs:sequence>  
        <xs:attribute name="NodeIdentifier" type="xs:string" use="required"></xs:attribute>  
    </xs:complexType>  
    <xs:complexType name="CategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ServiceTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:element name="WSDLReference" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="b424c-143">之后修改 CategorySchema.xml 文件时，重新生成 AdapterManagement 项目，然后运行添加适配器元数据向导以确保正确显示 CategorySchema.xml 中表示的树。</span><span class="sxs-lookup"><span data-stu-id="b424c-143">After modifying your CategorySchema.xml file, rebuild the AdapterManagement project, and then run the Add Adapter Metadata Wizard to ensure that the tree represented in CategorySchema.xml appears correctly.</span></span>  
  
 <span data-ttu-id="b424c-144">有关运行添加适配器元数据向导的信息，请参阅**添加适配器元数据向导对话框** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="b424c-144">For information about running the Add Adapter Metadata Wizard, see the **Add Adapter Metadata Wizard Dialog Box** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>