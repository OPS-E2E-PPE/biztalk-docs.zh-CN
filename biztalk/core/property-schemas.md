---
title: 属性架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8ffc953ecc4b68f2f3c0f195b3dd268f526b86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398457"
---
# <a name="property-schemas"></a>属性架构

## <a name="promoted-properties"></a>升级的属性
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，升级属性允许各个 BizTalk Server 组件访问的数据的键项，在此上下文中称为可分辨的字段和属性字段，而无需了解如何查找的实例消息中到达这些消息本身中。 对于不同类型的消息，可以确定哪些数据需要提升到更可见级别。 具体取决于如何选择升级此类字段，您可能需要创建和定义关联的属性架构。  
  
> [!NOTE]
>  升级的属性仅限于非重复元素/属性。  
  
 可分辨的字段只能在业务流程中访问，并且不需要创建相应属性架构。 如果仅需要访问升级的消息数据从业务流程中，可以将数据升级为一个或多个可分辨字段。  
  
 属性字段是可从各种 BizTalk Server 组件，包括管道和业务流程内部访问。 属性字段还可以用于消息路由。 如果你需要访问升级消息数据从上下文以外的其他业务流程中，则必须创建一个或多个属性架构来描述您要升级的数据。  
  
 属性架构是使用消息架构相关联的特殊架构。 它用于将实例消息中的特定值升级到消息上下文。 属性升级提供了一种用于提取关键信息来自定义实例消息中，并使其更轻松地访问 BizTalk Server 组件，处理消息，则通过 BizTalk 的集中式的机制服务器。  
  
## <a name="create-property-schema-overview"></a>创建属性架构概述
 通过使用 BizTalk Server 的快速升级功能，可以自动创建默认属性架构。 这是创建用于属性字段升级所需的属性架构的最简单方法。 有关如何执行快速升级的详细信息，请参阅[如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
 此外可以创建新的属性架构。 打开 BizTalk 项目时，选择 BizTalk 项目中，右键单击并选择**外**，单击**新项**，然后单击**架构**。  
  
> [!NOTE]
>  - 如果与消息架构相关联的属性架构，这两个必须在相同的 BizTalk 项目中。 不支持从不同的 BizTalk 项目中其关联的消息架构分隔属性架构。  
>
>  - 如果您有两个属性架构具有相同的命名空间，即使它们在不同的程序集定义，架构将无法解析正确地在运行时。 在运行时，将发生路由失败。  

## <a name="distinguished-fields-and-property-fields"></a>可分辨的字段和属性字段 
 有两种类型的属性升级： 可分辨字段和属性字段。 后一种类型使用属性架构。 在 BizTalk 编辑器中，这两种类型的属性升级使用来管理**升级属性**对话框中，使用访问**升级属性**属性**架构**节点。  
  
> [!NOTE]
>  - 有一些限制，您可以将升级的值。 有关详细信息，请参阅中的表[升级属性](../core/promoting-properties.md)。  
>
>  - 可分辨的字段不显示在筛选表达式中。 只有属性字段显示在筛选器表达式。  
  
 属性架构十分简单与消息架构进行比较时。 在架构树中，仅允许您插入**Field 元素**节点的直接子节点作为节点**架构**节点，创建两层级别的结构。 大多数情况下，设置的属性**字段元素**作为您的节点一样**Field 元素**出现在消息架构中的节点。 您仅限于使用 XSD 简单类型。  
  
> [!IMPORTANT]
>  不应重命名任何正由另一个架构的架构。 这包括已为其建立升级的属性架构。 如果这样做，正在使用的架构不能以查找其他架构，因为它包含的名称将不再准确。  
  
 **Property Schema Base**属性仅适用于**Field 元素**节点属性架构中的显示方式。 此属性默认情况下，为空白，但可以设置为**MessageDataPropertyBase**或**MessageContextPropertyBase**，从而导致**propSchFieldBase**属性要添加到**fieldInfo**批注元素包含一个或多个这些值。  
  
 当**propSchFieldBase**属性设置为**MessageDataPropertyBase**，这意味着升级属性的值对应于消息，例如，某些字段的值中的数据。 当**propSchFieldBase**属性设置为**MessageContextPropertyBase**，这意味着升级属性的值可能是从其他，信封，如位置或，它可能是由设置管道组件。  
  
 **字段元素**属性架构中的节点还具有一个名为属性**敏感信息**，它设置为时**是**，将使相应的值在中不可见BizTalk 浏览器和消息事件和服务实例跟踪，从而保留其敏感性。  请参阅**敏感信息**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]的更多详细信息。
  
 以下 XML 架构定义 (XSD) 语言表示的属性架构包含批注与该架构标识为属性架构的架构元素相关联 (schema_type ="property")。 它还包含三个**Field 元素**节点下面**架构**节点。 第一个**Field 元素**节点，名为 PromProp1，没有值定义为其**Property Schema Base**属性，但后两个**字段元素**节点具有属性设置为**MessageDataPropertyBase**并**MessageContextPropertyBase**分别。  
  
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
  
## <a name="see-also"></a>请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)