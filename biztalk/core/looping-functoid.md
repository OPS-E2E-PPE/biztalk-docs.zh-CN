---
title: 循环 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed86e27ebb2ff9a2eace4801906d61ed677c85af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380461"
---
# <a name="looping-functoid"></a>循环 Functoid

## <a name="overview--example"></a>概述和示例
**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。  
  
 下图显示**循环**functoid 在映射中用于将地址合并两个不同调查中收集到单个主地址列表。  
  
> [!NOTE]
>  **循环**并**值映射 （平展）** functoid 不应在一起。 如果一起使用，这会导致编译的映射，假定没有源循环依存关系如下的目标节点**循环**functoid。  
  
 ![映射的循环 functoid 用法。](../core/media/loopingfunctoid.gif "loopingfunctoid")  
  
 **FoodSurvey**并**FlowerSurvey**源架构的循环记录映射到循环**地址**目标架构的记录。 如果输入的实例消息具有三个**FoodSurvey**记录和两个**FlowerSurvey**记录**循环**functoid 将合并这些创建五个**地址**输出实例消息中的记录。  
  
 下面的代码是示例输入的实例消息。  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 此输入的实例消息生成以下输出实例消息处理在上图中的映射时。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 **FoodSurvey**并**FlowerSurvey**消息地址已合并。 组合的消息不指示每个地址的源。 如果你想要跟踪源，将添加**源**归于**地址**的记录**MasterAddress**架构和映射的常量值。 若要设置此值，连接 **FoodSurvey** 字段对新 **源** 字段。 在连接器一行中，修改 **链接属性** &#124; **编译器** &#124; **源链接** 属性设置为"副本名称"。 重复此流程的 **FlowerSurvey** 字段。 重新处理从上面输入的消息将生成以下输出：  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a>与节点之间的关系

 节点间的关系影响的行为**循环**functoid。 例如，链接的子节点和源架构中的其父级**循环**functoid 禁止创建目标节点。  
  
 Functoid 的源节点间的关系也会受到影响。 Functoid 连接到的源节点的非同级子字段**循环**functoid 可能产生意外的结果。 例如，使用**String Concatenate** functoid 将合并**FoodSurvey**名称字段和**FlowerSurvey** 中字段的地址名称到地址字段**MasterAddress**会生成以下输出实例消息：  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 请注意如何**名称**字段缺少**FoodSurvey**源消息，但存在可用于**FlowerSurvey**源消息。  
  
> [!IMPORTANT]
>  Functoid 连接到的源节点的子字段**循环**functoid 可能产生意外的结果，如果源节点不是同级。  
  
 **循环**functoid 是一个功能强大的构造，可以使用用于创建条件循环并将架构映射到目录。 此外，还有一些效果的重叠**循环**functoid 路径需要考虑在内。  
  
## <a name="next-steps"></a>后续步骤
  
-   [条件循环](../core/conditional-looping.md)  
  
-   [将平面架构转换为目录](../core/flat-schema-to-catalog.md)  
  
-   [循环路径](../core/loop-paths.md)  
  
## <a name="see-also"></a>请参阅  
 **表循环 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]