---
title: 累积 Functoid |Microsoft 文档
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
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240061"
---
# <a name="cumulative-functoids"></a>“累计”Functoid

## <a name="overview"></a>概述
**累积**functoid 减少到单个值如 sum、 串联的字符串或平均值的一系列值。  
  
 所有**的累积**functoid 接受两个输入参数：  
  
1.  要累积的值。 此值是所有数值**的累积**除 functoid**累积串联**functoid 期望的字符串值。 值是一个链接，通常从**字段特性**， **Field 元素**，或**记录**节点 (使用其**混合**属性设置为**True**)。  
  
    > [!NOTE]
    >  如果未的上级**记录**架构树中的节点，将循环，使用**的累积**functoid 是不必要的。  
  
2.  累计值的作用域。 此参数是可选的。 此参数表示要累计的指定值之间必须具有的紧密相关性。  
  
 下表显示了作用域参数的值及其作用：  
  
|作用域参数值|效果|  
|-----------------------------|------------|  
|0（零）|累计整个实例消息的值。 默认值。|  
|1（一）|累计具有同一父元素的元素或属性的值。|  
|2|累计具有同一祖父元素的元素或属性的值。|  
|3 或更大|累计按照前面的模式逐渐增大的作用域（曾祖父、高曾祖父等）的元素或属性的值。|  

## <a name="example"></a>示例  
 使用的示例**的累积**functoid 可能跨采购订单求和成本。 下面列出了一个示例采购订单的代码：  
  
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
  
 **Max Occurs**属性**项**当然，将记录**unbounded**。 这表示项记录循环和 BizTalk 映射程序编译时循环，该记录。  
  
 下图显示了映射使用**乘法**functoid 和**累计和**functoid 聚合项记录从传入的采购订单和输出中的结果**POTotal**字段：  
  
 ![映射累计和 functoid 显示的用法。] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")  

  
 该映射将生成以下输出，其中包含前面的数据，以及默认的作用域参数值，即 0（零）：  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 在此示例中，所有**项**记录下**LineItems**记录参与累积-作用域参数的默认值，该值指示对整个消息通过累积值。 **价格**和**数量**字段发送到**乘法**functoid。 输出**乘法**functoid 成为的输入**累计和**functoid。 输出**累计和**functoid 是作为的累计的值**项**记录遍历输入的采购订单中。  
  
> [!NOTE]
>  输入的累计聚合发生在输入链接所源自的父记录中。 即使**的累积**functoid 从另一个 functoid 中获取其输入，累积聚合对正在通过输入链接的父记录用作输入 functoid**累积**functoid。  
  
 将作用域参数更改为 1（一）并略微修改输出架构后，生成的输出如下所示：  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 将作用域参数设置为 1（一）表示累计具有同一父级的元素或属性的值。 此处**价格**和**数量**字段具有**项**作为父项，以便 functoid 对值求和的每个人**项**。  
  
 如果作用域参数为 2，则该 functoid 将累计具有同一祖父级的元素或属性的值。 祖父**价格**和**数量**字段是**LineItems**记录。 因为只有一个**LineItems**实例消息中记录，结果等同于使用默认值：  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  累积的 functoid (除**累积字符串**functoid) 忽略非数字输入。 例如，输入值“三”将被忽略。  
  
 **累积平均**，**累计最小**，和**累计最大**functoid 的行为方式类似于**累计和**functoid。 **累积字符串**连接字符串，而不是聚合数字值。  

## <a name="available-functoids"></a>可用的 functoid
  
 **的累积**functoid 均： 

* 累计平均
* 累计连接
* 累计最大
* 累计最小
* 累计和

在这些 functoid 的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **累积 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]