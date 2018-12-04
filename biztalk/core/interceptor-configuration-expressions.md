---
title: 侦听器配置表达式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6cc008e1e8b6acad53c2fcebd59160931cdc96
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826293"
---
# <a name="interceptor-configuration-expressions"></a>侦听器配置表达式
BAM 侦听器配置文件使用筛选器表达式来确定一个活动，并使用数据表达式构造存储的数据元素，用作相关 ID 或继续标记或类似用途。 无论用于什么用途，单个表达式的标识由侦听器配置文件中`expression`元素和包含一个或多个操作使用逆波兰表示法，也称为后缀表示法。  
  
## <a name="about-reverse-polish-notation"></a>关于逆波兰表示法  
 在逆波兰表示法 (RPN) 中，操作数的优先级高于运算符，因而不必使用括号作为优先运算符。 堆栈用于保存值，而所有运算或者将值推送到堆栈上，或者从堆栈中弹出（删除）值，或者执行推送和弹出的组合以完成某个运算。  
  
 例如，如果要计算表达式  
  
 `5 + (10 - 2)`  
  
 将该表达式转换为等效的 RPN 结果，形式如下  
  
 `5 10 2 - +`  
  
 该表达式计算过程如下：  
  
|输入|运算|堆栈|  
|-----------|---------------|-----------|  
|5|推送|5|  
|10|推送|5, 10|  
|2|推送|5, 10, 2|  
|-|减|5, 8|  
|+|添加|13|  
  
 假设 RPN 系统支持字符串连接运算，也可以计算下列表达式  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 将该表达式转换为等效的 RPN 符号可生成：  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 该表达式计算过程如下：  
  
|输入|运算|堆栈|  
|-----------|---------------|-----------|  
|"快速 brown"|推送|"The quick brown "|  
|"fox"|推送|"The quick brown ", "fox "|  
|"jumped over the lazy"|推送|"The quick brown ", "fox ", "jumped over the lazy "|  
|"dog."|推送|"The quick brown ", "fox ", "jumped over the lazy ", "dog."|  
|+|连接|"The quick brown ", "fox ", "jumped over the lazy dog."|  
|+|连接|"The quick brown ", "fox jumped over the lazy dog."|  
|+|连接|"The quick brown fox jumped over the lazy dog."|  
  
 正如您所见，可以支持任意数量的运算，包括比较、布尔运算和用于检索适合于所参与运算的值的自定义运算。 各值将在此堆栈中进行累计并根据各个运算被推送到堆栈和弹出堆栈。  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a>侦听器配置文件中的逆波兰表示法  
 将编写两种类型的表达式在侦听器配置文件： 筛选器表达式和数据表达式。 筛选器表达式的预期 RPN 表达式是一个布尔值的结果`true`或`false`而数据表达式堆栈上的单个值。  
  
### <a name="filter-expressions"></a>筛选器表达式  
 筛选器表达式的计算结果为布尔值`true`或`false`，用于标识特定事件来跟踪在 WF 或 WFC 应用程序中。 在 WF 应用程序中，通常根据活动名称和事件进行筛选。 例如，你可能想要选择**FoodAndDrinksPolicy**活动时**已关闭**。 使用 WF 运算，则可将此筛选器表示为：  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 将此表达式转换为 RPN 可生成：  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 将此表达式转换为侦听器配置文件的等效表达式将生成以下 XML：  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 最后，此表达式计算，如下所示假设**GetActivityName**返回"DessertPolicy"和**GetActivityEvent**返回"Closed":  
  
|输入|运算|堆栈|  
|-----------|---------------|-----------|  
||GetActivityName|"DessertPolicy"|  
|"FoodAndDrinksPolicy"|常量|"DessertPolicy", "FoodAndDrinksPolicy"|  
|等于|比较|False|  
||GetActivityEvent|False, Closed|  
|"Closed"|常量|False, "Closed", "Closed"|  
|等于|比较|False, True|  
|And|逻辑和|False|  
  
 在堆栈上保留的值是布尔值`False`。 这将导致不会激发相应事件。 如果活动名为 "FoodAndDrinksPolicy"，则计算结果将为布尔值 `True`。  
  
 可以使用 WCF 操作来构造类似表达式 （使用类似计算）`GetEndpointName`和`GetOperationName`。  
  
### <a name="data-expressions"></a>数据表达式  
 数据表达式用于定义单个字符串数据值。 数据表达式是通过不包含任何表达式`Filter`元素。 数据表达式由`OnEvent`元素`CorrelationID`， `ContinuationToken`， `Reference`，和`Update`。  
  
 通常要求使用已标记的时间戳来更新 BAM 活动数据库。 例如，您可能想要捕获事件以如下格式的字符串开头的时间"启动： \<EventTime\>"。 为此，需要使用类似以下格式的表达式（其中 + 表示连接）：  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 将此表达式转换为 RPN 可生成：  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 此表达式转换为等效的表达式`Update`以下 XML 中的侦听器配置文件结果中的元素：  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 下表显示了在事件时间为“12:00 PM”的情况下如何解释该表达式。  
  
|输入|运算|堆栈|  
|-----------|---------------|-----------|  
|"启动:"|常量|"启动:"|  
|GetContextProperty(EventTime)|推送|"启动:"，"2006年-09-27T12:00:34.000Z"|  
|连接|连接|"启动： 2006年-09-27T12:00:34.000Z"|  
  
 使用更新命令的值将为"启动： 2006年-09-27T12:00:34.000Z"。  
  
> [!NOTE]
>  不要在数据表达式中使用比较运算符“And”或“Equals”。 如果使用这两种运算符，则部署侦听器配置文件时将收到一个错误。  
  
## <a name="in-this-section"></a>本节内容  
 [侦听器运算](../core/interceptor-operations.md)  
  
## <a name="see-also"></a>请参阅  
 [侦听器配置文件的结构](../core/structure-of-an-interceptor-configuration-file.md)
