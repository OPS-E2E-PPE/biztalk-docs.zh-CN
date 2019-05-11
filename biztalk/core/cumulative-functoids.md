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
ms.openlocfilehash: c3f2b9a53a41072dd98edf486ce1b8abcedfbae2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353431"
---
# <a name="cumulative-functoids"></a><span data-ttu-id="9c8d3-102">累计 Functoid</span><span class="sxs-lookup"><span data-stu-id="9c8d3-102">Cumulative Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="9c8d3-103">概述</span><span class="sxs-lookup"><span data-stu-id="9c8d3-103">Overview</span></span>
<span data-ttu-id="9c8d3-104">**累积**functoid 减少到单个值如求和、 连接的字符串或平均值的一系列值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-104">**Cumulative** functoids reduce a series of values to a single value such as a sum, a concatenated string, or an average.</span></span>  

 <span data-ttu-id="9c8d3-105">所有**累计**functoid 都接受两个输入参数：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-105">All **Cumulative** functoids accept two input parameters:</span></span>  

1. <span data-ttu-id="9c8d3-106">要累计的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-106">The value to accumulate.</span></span> <span data-ttu-id="9c8d3-107">此值是为所有数值**累计**除 functoid**累计连接**functoid 需要字符串值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-107">This value is numeric for all **Cumulative** functoids except the **Cumulative Concatenate** functoid which expects a string value.</span></span> <span data-ttu-id="9c8d3-108">值是一个链接，通常从**字段属性**， **Field 元素**，或**记录**节点 (使用其**混合**属性设置为 **，则返回 true**)。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-108">The value is a link, often from a **Field Attribute**, **Field Element**, or **Record** node (with its **Mixed** property set to **True**).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9c8d3-109">如果没有祖先，则**记录**循环节点在架构树中的节点，使用**累计**functoid 是不必要的。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-109">If none of the ancestor **Record** nodes in the schema tree are looping, using a **Cumulative** functoid is unnecessary.</span></span>  

2. <span data-ttu-id="9c8d3-110">作用域内的累积值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-110">The scope within which the value is accumulated.</span></span> <span data-ttu-id="9c8d3-111">该参数可选。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-111">This argument is optional.</span></span> <span data-ttu-id="9c8d3-112">参数指示如何密切相关的指定的值必须具有要累计。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-112">The argument indicates how closely related the specified values must be to be accumulated.</span></span>  

   <span data-ttu-id="9c8d3-113">下表显示了作用域参数和其效果的值：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-113">The following table shows the values for the scoping parameter and its effect:</span></span>  

|<span data-ttu-id="9c8d3-114">作用域参数值</span><span class="sxs-lookup"><span data-stu-id="9c8d3-114">Scoping Parameter Value</span></span>|<span data-ttu-id="9c8d3-115">效果</span><span class="sxs-lookup"><span data-stu-id="9c8d3-115">Effect</span></span>|  
|-----------------------------|------------|  
|<span data-ttu-id="9c8d3-116">0（零）</span><span class="sxs-lookup"><span data-stu-id="9c8d3-116">0 (zero)</span></span>|<span data-ttu-id="9c8d3-117">累计整个实例消息。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-117">Accumulate the value over the entire instance message.</span></span> <span data-ttu-id="9c8d3-118">默认值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-118">The default.</span></span>|  
|<span data-ttu-id="9c8d3-119">1 （一）</span><span class="sxs-lookup"><span data-stu-id="9c8d3-119">1 (one)</span></span>|<span data-ttu-id="9c8d3-120">累计具有同一父元素的元素或属性值的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-120">Accumulate the value of element or attribute values with the same parent element.</span></span>|  
|<span data-ttu-id="9c8d3-121">2</span><span class="sxs-lookup"><span data-stu-id="9c8d3-121">2</span></span>|<span data-ttu-id="9c8d3-122">累计具有同一祖父元素的元素或属性值的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-122">Accumulate the value of element or attribute values with the same grandparent element.</span></span>|  
|<span data-ttu-id="9c8d3-123">3 个或更高版本</span><span class="sxs-lookup"><span data-stu-id="9c8d3-123">3 or greater</span></span>|<span data-ttu-id="9c8d3-124">累计按照前面的模式 （曾祖父、 大增祖父等） 的渐进式更广范围的元素或属性值的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-124">Accumulate the value of element or attribute values of progressively wider scope following the preceding pattern (great-grandparent, great-great-grandparent, etc.).</span></span>|  

## <a name="example"></a><span data-ttu-id="9c8d3-125">示例</span><span class="sxs-lookup"><span data-stu-id="9c8d3-125">Example</span></span>  
 <span data-ttu-id="9c8d3-126">使用的示例**累计**functoid 可能跨采购订单和成本。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-126">An example of using a **Cumulative** functoid might be summing costs across a purchase order.</span></span> <span data-ttu-id="9c8d3-127">以下代码是采购订单的示例。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-127">The following code is an example of a purchase order.</span></span>  

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

 <span data-ttu-id="9c8d3-128">**Max Occurs**属性**项**当然会记录**unbounded**。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-128">The **Max Occurs** property for the **Item** record would, of course, be **unbounded**.</span></span> <span data-ttu-id="9c8d3-129">这表示 item 记录循环和 BizTalk 映射器将编译此记录作为循环。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-129">This indicates that the item record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  

 <span data-ttu-id="9c8d3-130">下图显示了映射使用**乘法**functoid 和一个**累计**functoid 到聚合项记录从传入采购订单，并输出结果中的**POTotal**字段：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-130">The following figure shows a map using a **Multiplication** functoid and a **Cumulative Sum** functoid to aggregate item records from an incoming purchase order and output the results in the **POTotal** field:</span></span>  

 <span data-ttu-id="9c8d3-131">![显示使用情况累计 functoid 的映射。](../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span><span class="sxs-lookup"><span data-stu-id="9c8d3-131">![Map showing usage of the cumulative sum functoid.](../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span></span>  


 <span data-ttu-id="9c8d3-132">映射将生成以下输出与前面的数据和默认作用域参数值为 0 （零）：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-132">The map produces the following output with the preceding data and with the default scoping parameter value, 0 (zero):</span></span>  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

 <span data-ttu-id="9c8d3-133">在此示例中，所有**项**记录下**LineItems**记录参与累计，作用域参数的默认值指示整个消息内累计值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-133">In this example, all the **Item** records under the **LineItems** record participate in the accumulation—the default for the scoping parameter indicates accumulating the values across the entire message.</span></span> <span data-ttu-id="9c8d3-134">**价格**并**Quantity**字段发送到**乘法**functoid。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-134">The **Price** and **Quantity** fields are sent to a **Multiplication** functoid.</span></span> <span data-ttu-id="9c8d3-135">输出**乘法**functoid 将成为到输入**累计和**functoid。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-135">The output of the **Multiplication** functoid becomes the input to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="9c8d3-136">输出**累计**functoid 是累计的值作为**项**记录遍历输入的采购订单中。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-136">The output of the **Cumulative Sum** functoid is the accumulated value as the **Item** records are traversed in the input purchase order.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9c8d3-137">输入的累计聚合发生输入的链接所源自的父记录。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-137">The cumulative aggregation of input takes place over the parent record from which the input link originates.</span></span> <span data-ttu-id="9c8d3-138">即使**累计**functoid 从另一个 functoid 中获取其输入，累计聚合到用作输入的 functoid 的输入链接的父记录会发生**累计**functoid。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-138">Even when the **Cumulative** functoid gets its input from another functoid, the cumulative aggregation takes place over the parent record of the input links to the functoid that serves as input to the **Cumulative** functoid.</span></span>  

 <span data-ttu-id="9c8d3-139">更改作用域参数为 1 （一） 并略微修改输出架构，将生成输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-139">Changing the scoping parameter to 1 (one) and modifying the output schema slightly, yields output like the following:</span></span>  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  

 <span data-ttu-id="9c8d3-140">将作用域参数设置为 1 （一） 表示累计具有同一父级的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-140">Setting the scoping parameter to 1 (one) indicates accumulating values for elements or attributes with the same parent.</span></span> <span data-ttu-id="9c8d3-141">这里**价格**和**数量**字段具有**项**作为父级，以便提取 functoid 计算值之和每个个体**项**。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-141">Here the **Price** and **Quantity** fields have **Item** as a parent so that the functoid sums values for each individual **Item**.</span></span>  

 <span data-ttu-id="9c8d3-142">如果作用域参数为 2，该 functoid 将累计具有同一祖父级的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-142">If the scoping parameter is 2, the functoid accumulates values for elements or attributes with the same grandparent.</span></span> <span data-ttu-id="9c8d3-143">祖父**价格**并**Quantity**字段是**LineItems**记录。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-143">The grandparent of the **Price** and **Quantity** fields is the **LineItems** record.</span></span> <span data-ttu-id="9c8d3-144">因为只有一个**LineItems**记录在实例消息中，结果是使用默认值相同：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-144">Because there is only one **LineItems** record in the instance message, the result is the same as using the default value:</span></span>  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

> [!NOTE]
>  <span data-ttu-id="9c8d3-145">累计 functoid (除**累积字符串**functoid) 忽略非数值输入。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-145">Cumulative functoids (except for the **Cumulative String** functoid) ignore non-numeric input.</span></span> <span data-ttu-id="9c8d3-146">例如，输入的值"3"将被忽略。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-146">For example, an input value of "three" is ignored.</span></span>  

 <span data-ttu-id="9c8d3-147">**累计平均**，**累计最小**，并**累计最大**functoid 的行为方式类似于**累计和**functoid。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-147">The **Cumulative Average**, **Cumulative Minimum**, and **Cumulative Maximum** functoids behave similarly to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="9c8d3-148">**累积字符串**连接字符串而不聚合数值。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-148">The **Cumulative String** concatenates strings rather than aggregating numeric values.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="9c8d3-149">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="9c8d3-149">Available functoids</span></span>

 <span data-ttu-id="9c8d3-150">**累计**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-150">The **Cumulative** functoids are:</span></span> 

* <span data-ttu-id="9c8d3-151">累计平均</span><span class="sxs-lookup"><span data-stu-id="9c8d3-151">Cumulative Average</span></span>
* <span data-ttu-id="9c8d3-152">累计连接</span><span class="sxs-lookup"><span data-stu-id="9c8d3-152">Cumulative Concatenate</span></span>
* <span data-ttu-id="9c8d3-153">累计最大</span><span class="sxs-lookup"><span data-stu-id="9c8d3-153">Cumulative Maximum</span></span>
* <span data-ttu-id="9c8d3-154">累计最小</span><span class="sxs-lookup"><span data-stu-id="9c8d3-154">Cumulative Minimum</span></span>
* <span data-ttu-id="9c8d3-155">累计和</span><span class="sxs-lookup"><span data-stu-id="9c8d3-155">Cumulative Sum</span></span>

<span data-ttu-id="9c8d3-156">有关这些 functoid 的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-156">More details on these functoids are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="9c8d3-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c8d3-157">See Also</span></span>  
- [<span data-ttu-id="9c8d3-158">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="9c8d3-158">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="9c8d3-159">**累计 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9c8d3-159">**Cumulative Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
