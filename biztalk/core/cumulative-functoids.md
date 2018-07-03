---
title: 累计 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dffa6448511eca4d101423dbe356b82ff38aebb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004390"
---
# <a name="cumulative-functoids"></a>“累计”Functoid

## <a name="overview"></a>概述
**累积**functoid 减少到单个值如求和、 连接的字符串或平均值的一系列值。  

 所有**累计**functoid 都接受两个输入参数：  

1. 要累计的值。 此值是为所有数值**累计**除 functoid**累计连接**functoid 需要字符串值。 值是一个链接，通常从**字段属性**， **Field 元素**，或**记录**节点 (使用其**混合**属性设置为 **，则返回 true**)。  

   > [!NOTE]
   >  如果没有祖先，则**记录**循环节点在架构树中的节点，使用**累计**functoid 是不必要的。  

2. 累计值的作用域。 该参数可选。 此参数表示要累计的指定值之间必须具有的紧密相关性。  

   下表显示了作用域参数的值及其作用：  

|作用域参数值|效果|  
|-----------------------------|------------|  
|0（零）|累计整个实例消息的值。 默认值。|  
|1（一）|累计具有同一父元素的元素或属性的值。|  
|2|累计具有同一祖父元素的元素或属性的值。|  
|3 或更大|累计按照前面的模式逐渐增大的作用域（曾祖父、高曾祖父等）的元素或属性的值。|  

## <a name="example"></a>示例  
 使用的示例**累计**functoid 可能跨采购订单和成本。 下面列出了一个示例采购订单的代码：  

```  
<ns0:PurchaseOrder xmlns:ns0="http://CumulativeFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  

 **Max Occurs**属性**项**当然会记录**unbounded**。 这表示 item 记录循环和 BizTalk 映射器将编译此记录作为循环。  

 下图显示了映射使用**乘法**functoid 和一个**累计**functoid 到聚合项记录从传入采购订单，并输出结果中的**POTotal**字段：  

 ![显示使用情况累计 functoid 的映射。] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")  


 该映射将生成以下输出，其中包含前面的数据，以及默认的作用域参数值，即 0（零）：  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

 在此示例中，所有**项**记录下**LineItems**记录参与累计，作用域参数的默认值指示整个消息内累计值。 **价格**并**Quantity**字段发送到**乘法**functoid。 输出**乘法**functoid 将成为到输入**累计和**functoid。 输出**累计**functoid 是累计的值作为**项**记录遍历输入的采购订单中。  

> [!NOTE]
>  输入的累计聚合发生在输入链接所源自的父记录中。 即使**累计**functoid 从另一个 functoid 中获取其输入，累计聚合到用作输入的 functoid 的输入链接的父记录会发生**累计**functoid。  

 将作用域参数更改为 1（一）并略微修改输出架构后，生成的输出如下所示：  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  

 将作用域参数设置为 1（一）表示累计具有同一父级的元素或属性的值。 这里**价格**和**数量**字段具有**项**作为父级，以便提取 functoid 计算值之和每个个体**项**。  

 如果作用域参数为 2，则该 functoid 将累计具有同一祖父级的元素或属性的值。 祖父**价格**并**Quantity**字段是**LineItems**记录。 因为只有一个**LineItems**记录在实例消息中，结果是使用默认值相同：  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

> [!NOTE]
>  累计 functoid (除**累积字符串**functoid) 忽略非数值输入。 例如，输入值“三”将被忽略。  

 **累计平均**，**累计最小**，并**累计最大**functoid 的行为方式类似于**累计和**functoid。 **累积字符串**连接字符串而不聚合数值。  

## <a name="available-functoids"></a>可用的 functoid

 **累计**functoid 包括： 

* 累计平均
* 累计连接
* 累计最大
* 累计最小
* 累计和

有关这些 functoid 的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **累计 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
