---
title: 修改 2.xml 架构以使用 BizTalk 编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dd1c4cd8909564ff39c78b5b1a9e4fc248d93f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972854"
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a><span data-ttu-id="c3430-102">修改 2.xml 架构以使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="c3430-102">Modifying 2.XML Schemas to Work with BizTalk Editor</span></span>
<span data-ttu-id="c3430-103">HL7 2.xml 架构需要进行修改以使用正确 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="c3430-103">HL7 2.XML schemas require modification to work properly with Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span> <span data-ttu-id="c3430-104">下面介绍如何修改 HL7 V2。若要使你能够使用它们与 BizTalk 编辑器中的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c3430-104">The following describes how to modify HL7 V2.XML schemas to enable you to use them with BizTalk Editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c3430-105">Update2XMLSchema 工具自动执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c3430-105">The Update2XMLSchema tool performs these steps automatically.</span></span> <span data-ttu-id="c3430-106">请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3430-106">See [Update2XMLSchema Tool](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) for more information.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="c3430-107">**Nillable**特性可以出现在架构中的元素上。</span><span class="sxs-lookup"><span data-stu-id="c3430-107">The **nillable** attribute can occur in a schema on an element.</span></span> <span data-ttu-id="c3430-108">如果设置为 **，则返回 true**，它指示父元素的实例可以具有**xsi: nil ="true"** 属性。</span><span class="sxs-lookup"><span data-stu-id="c3430-108">If set to **true**, it indicates that the instance of the parent element can have an **xsi:nil="true"** attribute.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c3430-109"> 在编译和分析/序列化期间，将忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="c3430-109"> ignores this attribute during compilation and during parsing/serialization.</span></span>  
  
### <a name="to-modify-2xml-schemas"></a><span data-ttu-id="c3430-110">若要修改 2.xml 架构</span><span class="sxs-lookup"><span data-stu-id="c3430-110">To modify 2.XML schemas</span></span>  
  
1. <span data-ttu-id="c3430-111">在 fields.xsd 文件中，必须删除的实例**导入**并将其替换为**包括**。</span><span class="sxs-lookup"><span data-stu-id="c3430-111">In the fields.xsd file, you must remove instances of **import** and replace them with **include**.</span></span> <span data-ttu-id="c3430-112">例如，搜索以下文本的 fields.xsd 文件：</span><span class="sxs-lookup"><span data-stu-id="c3430-112">For example, search the fields.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
   ```  
  
    <span data-ttu-id="c3430-113">并更改为以下文本：</span><span class="sxs-lookup"><span data-stu-id="c3430-113">And change the text to the following:</span></span>  
  
   ```  
   <xsd:include schemaLocation="datatypes.xsd"/>   
   ```  
  
2. <span data-ttu-id="c3430-114">在 segments.xsd 文件中，必须删除包含文本 processContents 的行的所有实例 ="lax"。</span><span class="sxs-lookup"><span data-stu-id="c3430-114">In the segments.xsd file, you must remove all instances of the lines that contain the text processContents="lax".</span></span> <span data-ttu-id="c3430-115">例如，搜索以下文本的 segments.xsd 文件：</span><span class="sxs-lookup"><span data-stu-id="c3430-115">For example, search the segments.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
   ```  
  
    <span data-ttu-id="c3430-116">And</span><span class="sxs-lookup"><span data-stu-id="c3430-116">And</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any"/>   
   ```  
  
    <span data-ttu-id="c3430-117">并删除这些行。</span><span class="sxs-lookup"><span data-stu-id="c3430-117">And remove those lines.</span></span>  
  
3. <span data-ttu-id="c3430-118">对于所有架构，在标记 xsd: schema，必须添加以下行：</span><span class="sxs-lookup"><span data-stu-id="c3430-118">For all schemas, under the tag xsd:schema, you must add the following line:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c3430-119">如果你已添加使用 Microsoft 的架构不添加此行[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]因为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]自动为您执行此。</span><span class="sxs-lookup"><span data-stu-id="c3430-119">Do not add this line if you have added the schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] because [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does this for you automatically.</span></span>  
  
   ```  
   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
   ```  
  
    <span data-ttu-id="c3430-120">例如，在文件 ADT_A01.xsd 中，搜索以下文本：</span><span class="sxs-lookup"><span data-stu-id="c3430-120">For example, in the file ADT_A01.xsd, search for the following text:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="urn:hl7-org:v2xml"   
    targetNamespace="urn:hl7-org:v2xml">   
   ```  
  
    <span data-ttu-id="c3430-121">并更改为以下文本：</span><span class="sxs-lookup"><span data-stu-id="c3430-121">And change the text to the following:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:hl7-org:v2xml"  
    targetNamespace="urn:hl7-org:v2xml"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
   ```  
  
4. <span data-ttu-id="c3430-122">对于所有架构，必须添加根引用。</span><span class="sxs-lookup"><span data-stu-id="c3430-122">For all schemas, you must add a root reference.</span></span> <span data-ttu-id="c3430-123">例如，在 ADT_A01.xsd 文件中，搜索以下文本：</span><span class="sxs-lookup"><span data-stu-id="c3430-123">For example, in the ADT_A01.xsd file, search for the following text:</span></span>  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />   
   ```  
  
    <span data-ttu-id="c3430-124">并将文本更改为：</span><span class="sxs-lookup"><span data-stu-id="c3430-124">And change the text to:</span></span>  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />  
   <xsd:annotation>   
     <xsd:appinfo>   
       <schemaInfo root_reference="ADT_A01"  
    xmlns="http://schemas.microsoft.com/BizTalk/2003" />   
     </xsd:appinfo>   
   </xsd:annotation>   
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="c3430-125">如果使用的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，可以使用以下过程来添加此 root_reference。</span><span class="sxs-lookup"><span data-stu-id="c3430-125">If you are using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can add this root_reference by using the following procedure.</span></span>  
  
### <a name="to-add-the-root-reference"></a><span data-ttu-id="c3430-126">若要添加根引用</span><span class="sxs-lookup"><span data-stu-id="c3430-126">To add the root reference</span></span>  
  
1.  <span data-ttu-id="c3430-127">在解决方案资源管理器中双击你想要编辑的架构。</span><span class="sxs-lookup"><span data-stu-id="c3430-127">In Solution Explorer, double-click the schema you want to edit.</span></span>  
  
2.  <span data-ttu-id="c3430-128">在属性窗格中向下滚动属性**root_reference**，从下拉列表中，单击具有相同的架构名称的属性。</span><span class="sxs-lookup"><span data-stu-id="c3430-128">In the Properties pane, scroll down to the property **root_reference**, and from the drop-down list, click the property with the same schema name.</span></span>  
  
3.  <span data-ttu-id="c3430-129">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="c3430-129">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3430-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3430-130">See Also</span></span>  
 [<span data-ttu-id="c3430-131">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="c3430-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)