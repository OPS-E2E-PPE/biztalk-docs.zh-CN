---
title: 循环 Functoid |Microsoft 文档
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
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22262837"
---
# <a name="looping-functoid"></a>“循环”Functoid

## <a name="overview--example"></a>概述和示例
**循环** functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。  
  
 下图显示 **循环**functoid 映射中用于组合地址从两个不同的调查问卷收集到单个主地址列表。  
  
> [!NOTE]
>  **循环** 和 **值映射 （平展）** functoid 应不能一起使用。 如果两者共同使用，这会导致的编译的地图，假定循环依赖关系如下的目标节点没有源 **循环** functoid。  
  
 ![映射的循环 functoid 用法。](../core/media/loopingfunctoid.gif "loopingfunctoid")  
  
 **FoodSurvey** 和 **FlowerSurvey** 的源架构的循环记录映射到循环 **地址** 记录的目标架构。 如果输入的实例消息具有三个 **FoodSurvey** 记录和第二个 **FlowerSurvey** 记录， **循环**functoid 将合并这些文件以创建五个 **地址** 输出实例消息中的记录。  
  
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
  
 此输入的实例消息生成以下输出实例消息时由前面的图中的映射。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 **FoodSurvey** 和 **FlowerSurvey** 现在合并的邮件地址。 合并的消息不指示每个地址的源。 如果你想要跟踪源，将添加 **源** 属性设为 **地址** 记录的 **MasterAddress** 架构和映射的常量值。 若要设置此值，连接 **FoodSurvey** 字段对新 **源** 字段。 在连接器一行中，修改 **链接属性** &#124; **编译器** &#124; **源链接** 属性设置为"副本名称"。 重复此流程的 **FlowerSurvey** 字段。 重新处理输入的消息从上面生成以下输出︰  
  
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

 在节点之间的关系会影响的行为 **循环** functoid。 例如，链接的子节点和到源架构中的其父 **循环** functoid 阻止创建目标节点。  
  
 Functoid 也受源节点之间的关系。 连接到的源节点的同级子字段 functoid **循环** functoid 可能产生意外的结果。 例如，使用 **字符串连接** functoid 组合 **FoodSurvey** 名称字段和 **FlowerSurvey** 到中的地址名称字段的地址字段 **MasterAddress** 会产生以下输出实例消息︰  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 请注意如何 **名称** 字段是缺少 **FoodSurvey** 源消息，但呈现的 **FlowerSurvey** 源消息。  
  
> [!IMPORTANT]
>  连接到的源节点的子字段 functoid **循环** functoid 可能产生意外的结果，如果源节点不是同级。  
  
 **循环** functoid 是一个功能强大的构造，可以使用创建条件循环并将架构映射到目录。 也有一些副作用的重叠 **循环** functoid 路径需要考虑在内。  
  
## <a name="next-steps"></a>后续步骤
  
-   [条件循环](../core/conditional-looping.md)  
  
-   [将平面架构转换为目录](../core/flat-schema-to-catalog.md)  
  
-   [循环路径](../core/loop-paths.md)  
  
## <a name="see-also"></a>另请参阅  
 **表循环 Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]