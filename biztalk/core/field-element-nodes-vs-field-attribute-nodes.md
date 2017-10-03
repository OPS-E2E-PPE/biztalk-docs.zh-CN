---
title: "“字段元素”节点与字段属性节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d90f622e20bbdbace6804b2418cb68fd2ad60da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>“字段元素”节点与“字段属性”节点

## <a name="overview"></a>概述
使用平面文件架构的平面文件拆装器控制入站平面文件实例消息转换为其等效的 XML 格式，和由控制如何出站的平面文件汇编方式 XML 消息被转换为其等效项平面文件实例消息。 在构造此类架构，你使用**Field 元素**节点或**字段特性**节点尤其是定位在控制架构是否在平面文件实例中的特定字段消息对应于 XML 元素或等效的 XML 格式的消息中的 XML 属性。  

## <a name="example"></a>示例  
 例如，左对齐、 星号填充字段值"`red*****`"在平面文件实例消息可以转化为其等效的 XML 表示形式中两个不同的方式取决于架构中的该字段是否**字段元素**节点或**字段特性**节点。 当通过架构中表示该字段**Field 元素**节点其**节点名称**属性设置为"color"，且包含**记录**节点都有其**节点名称**属性设置为"shirt"，等效的 XML （以粗体类型显示） 的平面文件字段。  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 当通过架构中表示该相同的平面文件字段**字段特性**节点其**节点名称**属性设置为颜色，且包含**记录**节点都有其**节点名称**属性设置为 shirt，平面文件显示的字段是 （粗体类型） 的 XML 等效项：  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  平面文件架构具有进一步限制，在给定**记录**节点，从属**字段特性**节点必须早从属**记录**节点或**字段元素**节点。  
  
## <a name="see-also"></a>另请参阅  
-  [字段注意事项](../core/field-considerations.md)
-  **节点名称**属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]