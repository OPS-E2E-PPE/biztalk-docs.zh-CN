---
title: 扩展 BizTalk 编辑器 |Microsoft 文档
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
ms.openlocfilehash: 8f8e4f574e652420ae11410e52268a199639cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246237"
---
# <a name="extending-biztalk-editor"></a>扩展 BizTalk 编辑器
BizTalk 编辑器允许使用扩展来支持其他实例消息格式。 实际上，XML 格式是 BizTalk 编辑器内置的唯一格式。 即使对平面文件格式（包含在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中）的支持也是通过 BizTalk 编辑器扩展来实现的，因此，该扩展可作为此类扩展可添加的功能类型的有效示例。  
  
 通常，BizTalk 编辑器扩展将其自定义数据保存为 XML 架构定义 (XSD) 语言批注，这些批注与对应于架构树中节点的 XSD 元素相关联。 此外，平面文件扩展向 BizTalk 编辑器添加的扩展批注集也可作为 BizTalk 编辑器扩展在机构中保存其自定义数据的有效示例。  
  
 BizTalk 编辑器扩展是用于扩展 BizTalk 编辑器功能的 .NET 程序集。 若要标识作为扩展，程序集必须实现的一个类**IExtension**接口，并且必须位于产品的安装目录中的开发人员 Tools\Schema 编辑器扩展文件夹下。  
  
 扩展开发人员必须令其程序集引用 Microsoft.BizTalk.SchemaEditor.Extensibility.dll，其中包含向 BizTalk 编辑器公开扩展功能所需的所有接口的定义。 在定义那些接口**Microsoft.BizTalk.SchemaEditor.Extensibility**命名空间。  
  
 **IExtension**接口是的扩展，BizTalk 编辑器从中访问的扩展的功能，如属性管理器、 自定义视图、 架构验证、 本地实例生成和本机入口点实例验证。  
  
 给定的架构可以具有多个与其关联的扩展，但只有一个可以在给定的时间; 设置为标准这在中设置**标准**属性**架构**节点。 当前设置为标准的扩展即为本地实例生成和验证以及架构验证所使用的扩展。  
  
 扩展可以通过编辑给定架构与相关联**架构编辑器扩展**属性**架构**节点。 有关与架构关联的扩展的信息存储在架构本身内,**批注**元素**架构**元素，如下面的 XSD 段中所示。  
  
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
  
 实例化后的扩展对象，框架将调用**初始化**方法**IExtension**接口，将传递**ITree**对象，以便扩展可以访问有关架构树的信息。 例如，扩展无法遍历所有子节点，通过访问**ITree.RootNode**属性。  
  
 本部分介绍将 BizTalk 编辑器扩展集成到 BizTalk 编辑器环境中并将扩展本身与现有 BizTalk 编辑器命令挂接的方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [属性管理器](../core/property-managers.md)  
  
-   [自定义视图](../core/custom-views.md)  
  
-   [架构验证](../core/schema-validation1.md)  
  
-   [实例验证](../core/instance-validation.md)  
  
-   [生成实例](../core/instance-generation.md)