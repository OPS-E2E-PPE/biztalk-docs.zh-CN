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
# <a name="extending-biztalk-editor"></a>扩展 BizTalk 编辑器
BizTalk 编辑器旨在允许使用扩展来支持其他实例消息格式。 实际上，XML 格式是 BizTalk 编辑器内置的唯一格式。 甚至还支持对平面文件格式，包含在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，作为 BizTalk 编辑器扩展，从而充当可以通过此类扩展添加的功能类型的一个很好示例。  
  
 一般情况下，BizTalk 编辑器扩展保留其自定义数据作为 XML 架构定义 (XSD) 语言批注与对应于在架构树中节点的 XSD 元素相关联。 同样，扩展由 BizTalk 编辑器的平面文件扩展添加的批注集用作在 BizTalk 编辑器扩展可以保留其自定义数据架构中的方法的一个很好示例。  
  
 BizTalk 编辑器扩展是扩展功能的 BizTalk 编辑器中的.NET 程序集。 若要将标识为扩展，程序集必须具有实现的一个类**IExtension**接口，并必须位于产品安装目录中的 Developer Tools\Schema Editor Extensions 文件夹下。  
  
 扩展开发人员必须具有其程序集引用 Microsoft.BizTalk.SchemaEditor.Extensibility.dll，其中包含公开扩展的功能向 BizTalk 编辑器所需的所有接口的定义。 这些接口定义下**Microsoft.BizTalk.SchemaEditor.Extensibility**命名空间。  
  
 **IExtension**接口是的扩展，BizTalk 编辑器中从其访问扩展的功能，例如属性管理器、 自定义视图、 架构验证、 本地实例生成和本机入口点实例验证。  
  
 给定的架构可以具有多个扩展与之关联，但只有一个可以在给定的时间; 设置为标准这在中设置**标准**的属性**架构**节点。 当前设置为标准的扩展是用于本地实例生成和验证，以及架构验证。  
  
 扩展可以通过编辑给定的架构与相关联**架构编辑器扩展**的属性**架构**节点。 与架构关联的扩展有关的信息存储在该架构内**批注**的元素**架构**元素，如以下 XSD 片断中所示。  
  
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
  
 实例化后的扩展对象，框架将调用**初始化**方法**IExtension**接口，传递**ITree**对象，以便扩展可以访问有关在架构树的信息。 例如，扩展可以遍历所有子节点，通过访问**ITree.RootNode**属性。  
  
 本部分介绍在 BizTalk 编辑器扩展可以将集成到 BizTalk 编辑器环境并将自身挂接到现有 BizTalk 编辑器命令的方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [属性管理器](../core/property-managers.md)  
  
-   [自定义视图](../core/custom-views.md)  
  
-   [架构验证](../core/schema-validation1.md)  
  
-   [实例验证](../core/instance-validation.md)  
  
-   [实例生成](../core/instance-generation.md)