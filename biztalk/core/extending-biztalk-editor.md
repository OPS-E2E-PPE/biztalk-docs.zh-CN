---
title: 扩展 BizTalk 编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77c93ab2-0a9b-4c9d-81e5-3871fc8e6e13
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724ab7d8575a1db33654a0115530de6a259ca88e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388199"
---
# <a name="extending-biztalk-editor"></a><span data-ttu-id="01963-102">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="01963-102">Extending BizTalk Editor</span></span>
<span data-ttu-id="01963-103">BizTalk 编辑器旨在允许使用扩展来支持其他实例消息格式。</span><span class="sxs-lookup"><span data-stu-id="01963-103">BizTalk Editor is designed to allow extensions that support alternative instance message formats.</span></span> <span data-ttu-id="01963-104">实际上，XML 格式是 BizTalk 编辑器内置的唯一格式。</span><span class="sxs-lookup"><span data-stu-id="01963-104">In fact, the XML format is the only format that is built into BizTalk Editor.</span></span> <span data-ttu-id="01963-105">甚至还支持对平面文件格式，包含在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，作为 BizTalk 编辑器扩展，从而充当可以通过此类扩展添加的功能类型的一个很好示例。</span><span class="sxs-lookup"><span data-stu-id="01963-105">Even support for flat file formats, which is included in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], is implemented as a BizTalk Editor extension, thereby serving as a good example of the type of functionality that can be added by such extensions.</span></span>  
  
 <span data-ttu-id="01963-106">一般情况下，BizTalk 编辑器扩展保留其自定义数据作为 XML 架构定义 (XSD) 语言批注与对应于在架构树中节点的 XSD 元素相关联。</span><span class="sxs-lookup"><span data-stu-id="01963-106">In general, BizTalk Editor extensions persist their custom data as XML Schema definition (XSD) language annotations associated with the XSD elements that correspond to the nodes in the schema tree.</span></span> <span data-ttu-id="01963-107">同样，扩展由 BizTalk 编辑器的平面文件扩展添加的批注集用作在 BizTalk 编辑器扩展可以保留其自定义数据架构中的方法的一个很好示例。</span><span class="sxs-lookup"><span data-stu-id="01963-107">Again, the extensive set of annotations added by the Flat File Extension to BizTalk Editor serves as a good example of the way in which BizTalk Editor extensions can persist their custom data in the schema.</span></span>  
  
 <span data-ttu-id="01963-108">BizTalk 编辑器扩展是扩展功能的 BizTalk 编辑器中的.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="01963-108">BizTalk Editor extensions are .NET assemblies that extend the functionality of BizTalk Editor.</span></span> <span data-ttu-id="01963-109">若要将标识为扩展，程序集必须具有实现的一个类**IExtension**接口，并必须位于产品安装目录中的 Developer Tools\Schema Editor Extensions 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="01963-109">To be identified as an extension, an assembly must have one class that implements the **IExtension** interface, and must be located under the Developer Tools\Schema Editor Extensions folder in the product installation directory.</span></span>  
  
 <span data-ttu-id="01963-110">扩展开发人员必须具有其程序集引用 Microsoft.BizTalk.SchemaEditor.Extensibility.dll，其中包含公开扩展的功能向 BizTalk 编辑器所需的所有接口的定义。</span><span class="sxs-lookup"><span data-stu-id="01963-110">The developer of an extension must have its assembly reference the Microsoft.BizTalk.SchemaEditor.Extensibility.dll, which contains the definition of all the interfaces needed for exposing extended functionality to BizTalk Editor.</span></span> <span data-ttu-id="01963-111">这些接口定义下**Microsoft.BizTalk.SchemaEditor.Extensibility**命名空间。</span><span class="sxs-lookup"><span data-stu-id="01963-111">Those interfaces are defined under the **Microsoft.BizTalk.SchemaEditor.Extensibility** namespace.</span></span>  
  
 <span data-ttu-id="01963-112">**IExtension**接口是的扩展，BizTalk 编辑器中从其访问扩展的功能，例如属性管理器、 自定义视图、 架构验证、 本地实例生成和本机入口点实例验证。</span><span class="sxs-lookup"><span data-stu-id="01963-112">The **IExtension** interface is the entry point for the extension, from which BizTalk Editor accesses the extended functionality, such as property managers, custom views, schema validation, native instance generation, and native instance validation.</span></span>  
  
 <span data-ttu-id="01963-113">给定的架构可以具有多个扩展与之关联，但只有一个可以在给定的时间; 设置为标准这在中设置**标准**的属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="01963-113">A given schema can have multiple extensions associated with it, but only one can be set as the standard at a given time; this is set in the **Standard** property of the **Schema** node.</span></span> <span data-ttu-id="01963-114">当前设置为标准的扩展是用于本地实例生成和验证，以及架构验证。</span><span class="sxs-lookup"><span data-stu-id="01963-114">The extension currently set as the standard is the one used for native instance generation and validation, and for schema validation.</span></span>  
  
 <span data-ttu-id="01963-115">扩展可以通过编辑给定的架构与相关联**架构编辑器扩展**的属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="01963-115">Extensions can be associated with a given schema by editing the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="01963-116">与架构关联的扩展有关的信息存储在该架构内**批注**的元素**架构**元素，如以下 XSD 片断中所示。</span><span class="sxs-lookup"><span data-stu-id="01963-116">The information about the extensions associated with a schema is stored in the schema itself, within the **annotation** element of the **schema** element, as illustrated in the following XSD fragment.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema11"  
        xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
        targetNamespace="http://BizTalk_Server_Project1.Schema11"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <schemaEditorExtension:schemaInfo namespaceAlias="b"  
                extensionClass="Microsoft.BizTalk.FlatFileExtension.FlatFileExtension"  
                standardName="Flat File"  
                xmlns:schemaEditorExtension="http://schemas.microsoft.com/BizTalk/2003/SchemaEditorExtensions" />  
            <b:schemaInfo schema_type="document" root_reference="Root"  
                is_receipt="no" schema_name="abc"  
                standard="Flat File"  
                count_positions_by_byte="false" />   
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="Root">  
        ...  
  
```  
  
 <span data-ttu-id="01963-117">实例化后的扩展对象，框架将调用**初始化**方法**IExtension**接口，传递**ITree**对象，以便扩展可以访问有关在架构树的信息。</span><span class="sxs-lookup"><span data-stu-id="01963-117">After instantiating the extension object, the framework invokes the **Initialize** method of the **IExtension** interface, passing an **ITree** object so that the extension can access information about the schema tree.</span></span> <span data-ttu-id="01963-118">例如，扩展可以遍历所有子节点，通过访问**ITree.RootNode**属性。</span><span class="sxs-lookup"><span data-stu-id="01963-118">For example, the extension could traverse all child nodes by accessing the **ITree.RootNode** property.</span></span>  
  
 <span data-ttu-id="01963-119">本部分介绍在 BizTalk 编辑器扩展可以将集成到 BizTalk 编辑器环境并将自身挂接到现有 BizTalk 编辑器命令的方法。</span><span class="sxs-lookup"><span data-stu-id="01963-119">This section describes the ways in which a BizTalk Editor extension can integrate into the BizTalk Editor environment and hook itself into existing BizTalk Editor commands.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01963-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="01963-120">In This Section</span></span>  
  
-   [<span data-ttu-id="01963-121">属性管理器</span><span class="sxs-lookup"><span data-stu-id="01963-121">Property Managers</span></span>](../core/property-managers.md)  
  
-   [<span data-ttu-id="01963-122">自定义视图</span><span class="sxs-lookup"><span data-stu-id="01963-122">Custom Views</span></span>](../core/custom-views.md)  
  
-   [<span data-ttu-id="01963-123">架构验证</span><span class="sxs-lookup"><span data-stu-id="01963-123">Schema Validation</span></span>](../core/schema-validation1.md)  
  
-   [<span data-ttu-id="01963-124">实例验证</span><span class="sxs-lookup"><span data-stu-id="01963-124">Instance Validation</span></span>](../core/instance-validation.md)  
  
-   [<span data-ttu-id="01963-125">实例生成</span><span class="sxs-lookup"><span data-stu-id="01963-125">Instance Generation</span></span>](../core/instance-generation.md)