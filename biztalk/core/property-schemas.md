---
title: "属性架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb50536b2521e77994baf0b6457206614b7eed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="property-schemas"></a>属性架构

## <a name="promoted-properties"></a>提升的属性
在 Microsoft 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，提升属性启用各种 BizTalk 服务器组件访问的数据的键项，在此上下文中称为可分辨的字段和属性而无需知道如何查找到达实例消息中的字段这些消息本身中。 对于不同类型的消息，您可以决定需要将哪些数据项升级到更高的可见级别。 根据所选择的用于升级此类字段的方式，您可能需要创建和定义一个关联属性架构。  
  
> [!NOTE]
>  升级属性仅限于非重复元素/特性。  
  
 可分辨字段只能在业务流程中进行访问，不需要创建相应的属性架构。 如果仅需要在业务流程中访问升级的消息数据，您可以将数据升级为一个或多个可分辨字段。  
  
 属性字段可以在各个 BizTalk Server 组件（包括管道和业务流程）中进行访问。 属性字段还可用于消息路由。 如果需要在上下文（而不是在业务流程）中访问升级的消息数据，您必须创建一个或多个属性架构来描述要升级的数据。  
  
 属性架构是一种与消息架构相关联的特殊架构。 它用于将实例消息中的特定值升级到消息上下文中。 属性升级提供了一种集中机制，通过该机制，您可以从实例消息中请求所定义的关键信息，并使其可更方便地被负责对通过 BizTalk Server 的消息进行处理的 BizTalk Server 组件访问。  
  
## <a name="create-property-schema-overview"></a>创建属性架构概述
 您可以通过使用 BizTalk Server 的快速升级功能自动创建默认属性架构。 这是创建属性字段升级所需的属性架构最简单的方法。 有关如何执行快速提升的详细信息，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
 你还可以创建新属性架构。 打开 BizTalk 项目时，选择 BizTalk 项目，右键单击并选择**添加**，单击**新项**，然后单击**架构**。  
  
> [!NOTE]
>  - 如果属性架构与消息架构相关联，则这两个架构必须位于同一 BizTalk 项目中。 不支持将属性架构与其所关联的消息架构分隔在不同的 BizTalk 项目中。  
>
>  - 如果有两个属性架构具有相同的命名空间，即使它们定义在不同的程序集中，在运行时也不能正确解析。 在运行时将发生路由失败。  

## <a name="distinguished-fields-and-property-fields"></a>可分辨的字段和属性字段 
 属性升级有两种类型：可分辨字段和属性字段。 后一种类型使用属性架构。 在 BizTalk 编辑器中，你通过进行管理这两种类型的属性提升**升级属性**对话框中，你通过使用访问**升级属性**属性**架构**节点。  
  
> [!NOTE]
>  - 对于可以升级的值有一些限制。 有关详细信息，请参阅中的表[提升属性](../core/promoting-properties.md)。  
>
>  - 可分辨字段不显示在筛选器表达式中。 只有属性字段才显示在筛选器表达式中。  
  
 与消息架构相比，属性架构十分简单。 在架构树中，你仅允许插入**Field 元素**的即时子节点的节点**架构**节点，创建结构，它是两个级别。 大多数情况下，你设置的属性**Field 元素**作为你的节点将为**Field 元素**显示在消息架构中的节点。 您只能使用 XSD 简单类型。  
  
> [!IMPORTANT]
>  不应对正在由其他架构使用的架构进行重命名。 包括已为其建立了升级的属性架构。 如果这样做，正在使用的架构不能以查找其他架构，因为它包含的名称将不再准确。  
  
 **属性架构基**属性是唯一的**Field 元素**节点在属性架构中显示。 此属性默认情况下，为空，但可以设置为**MessageDataPropertyBase**或**MessageContextPropertyBase**，这会导致在**propSchFieldBase**属性添加到**fieldInfo**具有一个或多个这些值的批注元素。  
  
 当**propSchFieldBase**属性设置为**MessageDataPropertyBase**，这意味着提升属性的值对应于在消息中，如某些字段值的数据。 当**propSchFieldBase**属性设置为**MessageContextPropertyBase**，则表明提升属性的值可能来自，如信封的其他位置，或者它可能是由设置管道组件。  
  
 **字段元素**属性架构中的节点还具有一个名为属性**敏感信息**，后者当设置为**是**，将会使相应的值不能从中查看BizTalk 资源管理器和消息事件和服务实例跟踪，这样既保留了其敏感的性质。  请参阅**敏感信息**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关详细信息。
  
 下面的属性架构的 XML 架构定义 (XSD) 语言表示形式包含一个批注，该批注与将该架构标识为属性架构 (schema_type="property") 的架构元素相关联。 它还包含三个**Field 元素**节点下面**架构**节点。 第一个**Field 元素**节点，名为 PromProp1，没有为定义的值其**属性架构基**属性，但后两个**Field 元素**节点具有属性设置为**MessageDataPropertyBase**和**MessageContextPropertyBase**分别。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
           targetNamespace="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
       <xs:appinfo>  
  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)