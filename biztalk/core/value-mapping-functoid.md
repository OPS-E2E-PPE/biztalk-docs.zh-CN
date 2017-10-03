---
title: "值映射 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2bb8e89ed790fe9916efe69685ad667d9fe9403
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="value-mapping-functoid"></a>“值映射”Functoid
**值映射**functoid 返回其第二个参数的值，如果其第一个参数为 true。 该 functoid 通常用于将字段的属性更改为记录的属性。 若要通过将多个记录转换为单个记录平展输入消息的一部分，使用[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
 下图显示具有的映射**值映射**functoid 用于将字段的特性更改为一条记录的属性。  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
“值映射”Functoid 映射  
  
 下面的代码演示输入的实例消息中的一对名称和值将赋给**名称**和**值**属性。  
  
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
  
 上面的映射可以将此消息转换为以下消息，其中值分配给独立记录中具有相应名称的属性。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 **相等**functoid 测试的值**名称**属性。 第一个**相等**functoid 测试的值**名称**正在"WindSpeed。" 当**名称**是"WindSpeed，"第一个**相等**functoid 返回**True**。 这样，反过来，**值映射**functoid，若要设置的值**WindSpeed**输出实例消息中的属性。  
  
## <a name="suppressing-the-creation-of-empty-tags"></a>取消创建空标记  
 若要取消空标记，可以使用“值映射”functoid 控制是否创建某个标记。 如果值的计算结果为 True，则将创建目标字段，否则，不创建目标字段。 在循环方案中，使用“判断”functoid 并将其连接到目标记录或目标字段。 如果条件的计算结果为 false，则不创建标记。 有关示例，请参阅[条件循环](../core/conditional-looping.md)。  
  
## <a name="forcing-the-creation-of-empty-tags"></a>强制创建空标记  
 若要强制空标记来创建，可以添加一个值的目标字段或链接的值属性中**Concatenate** functoid 到目标字段。  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以通过选择强制生成空标记"\<空 >"的目标字段的值属性中的值。 在这种情况下，将使用空值创建字段。  
  
## <a name="see-also"></a>另请参阅  
 [映射 （拼合） Functoid 的值](../core/value-mapping-flattening-functoid.md)   
 [如何添加值映射到图 Functoid](../core/how-to-add-value-mapping-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)