---
title: 值映射 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca60ff3024eb1b4cadc42e42c65a0c44c82ef5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292614"
---
# <a name="value-mapping-functoid"></a>值映射 Functoid
**值映射**functoid 在其第一个参数为 true，则返回其第二个参数的值。 提取 functoid 的一个常见用途是将一个字段的属性更改为记录的属性。 若要通过将多个记录转换为一条记录平展输入消息的一部分，请使用[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
 下图显示了具有的地图**值映射**functoid 用于将一个字段的属性更改为记录的属性。  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
值映射 Functoid 映射  
  
 下面的代码演示的输入的实例消息中的一对名称和值分配给**名称**并**值**属性。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 上面的映射可以将此消息转换为一个其中值分配给具有单独的记录中的相应名称的属性。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 **相等**functoid 测试的值**名称**属性。 第一个**相等**的值的 functoid 测试**名称**是否为"WindSpeed"。 当**名称**为"WindSpeed，"第一个**相等**functoid 将返回**True**。 这反过来允许**值映射**若要设置的值的 functoid **WindSpeed**输出实例消息中的属性。  
  
## <a name="suppressing-the-creation-of-empty-tags"></a>取消创建空标记  
 若要取消空标记，请使用控制值映射 functoid，如果或不创建某个标记。 如果值的计算结果为 true，目标将创建字段;否则将不创建目标字段。 在循环方案中，使用判断 functoid 并将其连接到的目标记录或字段。 如果条件的计算结果为 false，将不会创建该标记。 有关示例，请参阅[条件循环](../core/conditional-looping.md)。  
  
## <a name="forcing-the-creation-of-empty-tags"></a>强制创建空标记  
 若要强制创建空标记，可以添加一个值的目标字段或链接值属性中**Concatenate** functoid 到目标字段。  在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则可以通过选择强制生成空标记"\<空\>"目标字段的值属性中的值。 在这种情况下将使用空值创建字段。  
  
## <a name="see-also"></a>请参阅  
 [值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)   
 [如何添加值映射 Functoid 映射到](../core/how-to-add-value-mapping-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)