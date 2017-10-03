---
title: "累积 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cumulative-functoids"></a><span data-ttu-id="6a12a-102">“累计”Functoid</span><span class="sxs-lookup"><span data-stu-id="6a12a-102">Cumulative Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="6a12a-103">概述</span><span class="sxs-lookup"><span data-stu-id="6a12a-103">Overview</span></span>
<span data-ttu-id="6a12a-104">**累积**functoid 减少到单个值如 sum、 串联的字符串或平均值的一系列值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-104">**Cumulative** functoids reduce a series of values to a single value such as a sum, a concatenated string, or an average.</span></span>  
  
 <span data-ttu-id="6a12a-105">所有**的累积**functoid 接受两个输入参数：</span><span class="sxs-lookup"><span data-stu-id="6a12a-105">All **Cumulative** functoids accept two input parameters:</span></span>  
  
1.  <span data-ttu-id="6a12a-106">要累积的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-106">The value to accumulate.</span></span> <span data-ttu-id="6a12a-107">此值是所有数值**的累积**除 functoid**累积串联**functoid 期望的字符串值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-107">This value is numeric for all **Cumulative** functoids except the **Cumulative Concatenate** functoid which expects a string value.</span></span> <span data-ttu-id="6a12a-108">值是一个链接，通常从**字段特性**， **Field 元素**，或**记录**节点 (使用其**混合**属性设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="6a12a-108">The value is a link, often from a **Field Attribute**, **Field Element**, or **Record** node (with its **Mixed** property set to **True**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a12a-109">如果未的上级**记录**架构树中的节点，将循环，使用**的累积**functoid 是不必要的。</span><span class="sxs-lookup"><span data-stu-id="6a12a-109">If none of the ancestor **Record** nodes in the schema tree are looping, using a **Cumulative** functoid is unnecessary.</span></span>  
  
2.  <span data-ttu-id="6a12a-110">累计值的作用域。</span><span class="sxs-lookup"><span data-stu-id="6a12a-110">The scope within which the value is accumulated.</span></span> <span data-ttu-id="6a12a-111">此参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="6a12a-111">This argument is optional.</span></span> <span data-ttu-id="6a12a-112">此参数表示要累计的指定值之间必须具有的紧密相关性。</span><span class="sxs-lookup"><span data-stu-id="6a12a-112">The argument indicates how closely related the specified values must be to be accumulated.</span></span>  
  
 <span data-ttu-id="6a12a-113">下表显示了作用域参数的值及其作用：</span><span class="sxs-lookup"><span data-stu-id="6a12a-113">The following table shows the values for the scoping parameter and its effect:</span></span>  
  
|<span data-ttu-id="6a12a-114">作用域参数值</span><span class="sxs-lookup"><span data-stu-id="6a12a-114">Scoping Parameter Value</span></span>|<span data-ttu-id="6a12a-115">效果</span><span class="sxs-lookup"><span data-stu-id="6a12a-115">Effect</span></span>|  
|-----------------------------|------------|  
|<span data-ttu-id="6a12a-116">0（零）</span><span class="sxs-lookup"><span data-stu-id="6a12a-116">0 (zero)</span></span>|<span data-ttu-id="6a12a-117">累计整个实例消息的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-117">Accumulate the value over the entire instance message.</span></span> <span data-ttu-id="6a12a-118">默认值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-118">The default.</span></span>|  
|<span data-ttu-id="6a12a-119">1（一）</span><span class="sxs-lookup"><span data-stu-id="6a12a-119">1 (one)</span></span>|<span data-ttu-id="6a12a-120">累计具有同一父元素的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-120">Accumulate the value of element or attribute values with the same parent element.</span></span>|  
|<span data-ttu-id="6a12a-121">2</span><span class="sxs-lookup"><span data-stu-id="6a12a-121">2</span></span>|<span data-ttu-id="6a12a-122">累计具有同一祖父元素的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-122">Accumulate the value of element or attribute values with the same grandparent element.</span></span>|  
|<span data-ttu-id="6a12a-123">3 或更大</span><span class="sxs-lookup"><span data-stu-id="6a12a-123">3 or greater</span></span>|<span data-ttu-id="6a12a-124">累计按照前面的模式逐渐增大的作用域（曾祖父、高曾祖父等）的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-124">Accumulate the value of element or attribute values of progressively wider scope following the preceding pattern (great-grandparent, great-great-grandparent, etc.).</span></span>|  

## <a name="example"></a><span data-ttu-id="6a12a-125">示例</span><span class="sxs-lookup"><span data-stu-id="6a12a-125">Example</span></span>  
 <span data-ttu-id="6a12a-126">使用的示例**的累积**functoid 可能跨采购订单求和成本。</span><span class="sxs-lookup"><span data-stu-id="6a12a-126">An example of using a **Cumulative** functoid might be summing costs across a purchase order.</span></span> <span data-ttu-id="6a12a-127">下面列出了一个示例采购订单的代码：</span><span class="sxs-lookup"><span data-stu-id="6a12a-127">The following code is an example of a purchase order.</span></span>  
  
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
  
 <span data-ttu-id="6a12a-128">**Max Occurs**属性**项**当然，将记录**unbounded**。</span><span class="sxs-lookup"><span data-stu-id="6a12a-128">The **Max Occurs** property for the **Item** record would, of course, be **unbounded**.</span></span> <span data-ttu-id="6a12a-129">这表示项记录循环和 BizTalk 映射程序编译时循环，该记录。</span><span class="sxs-lookup"><span data-stu-id="6a12a-129">This indicates that the item record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="6a12a-130">下图显示了映射使用**乘法**functoid 和**累计和**functoid 聚合项记录从传入的采购订单和输出中的结果**POTotal**字段：</span><span class="sxs-lookup"><span data-stu-id="6a12a-130">The following figure shows a map using a **Multiplication** functoid and a **Cumulative Sum** functoid to aggregate item records from an incoming purchase order and output the results in the **POTotal** field:</span></span>  
  
 <span data-ttu-id="6a12a-131">![映射累计和 functoid 显示的用法。] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span><span class="sxs-lookup"><span data-stu-id="6a12a-131">![Map showing usage of the cumulative sum functoid.](../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span></span>  

  
 <span data-ttu-id="6a12a-132">该映射将生成以下输出，其中包含前面的数据，以及默认的作用域参数值，即 0（零）：</span><span class="sxs-lookup"><span data-stu-id="6a12a-132">The map produces the following output with the preceding data and with the default scoping parameter value, 0 (zero):</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="6a12a-133">在此示例中，所有**项**记录下**LineItems**记录参与累积-作用域参数的默认值，该值指示对整个消息通过累积值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-133">In this example, all the **Item** records under the **LineItems** record participate in the accumulation—the default for the scoping parameter indicates accumulating the values across the entire message.</span></span> <span data-ttu-id="6a12a-134">**价格**和**数量**字段发送到**乘法**functoid。</span><span class="sxs-lookup"><span data-stu-id="6a12a-134">The **Price** and **Quantity** fields are sent to a **Multiplication** functoid.</span></span> <span data-ttu-id="6a12a-135">输出**乘法**functoid 成为的输入**累计和**functoid。</span><span class="sxs-lookup"><span data-stu-id="6a12a-135">The output of the **Multiplication** functoid becomes the input to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="6a12a-136">输出**累计和**functoid 是作为的累计的值**项**记录遍历输入的采购订单中。</span><span class="sxs-lookup"><span data-stu-id="6a12a-136">The output of the **Cumulative Sum** functoid is the accumulated value as the **Item** records are traversed in the input purchase order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a12a-137">输入的累计聚合发生在输入链接所源自的父记录中。</span><span class="sxs-lookup"><span data-stu-id="6a12a-137">The cumulative aggregation of input takes place over the parent record from which the input link originates.</span></span> <span data-ttu-id="6a12a-138">即使**的累积**functoid 从另一个 functoid 中获取其输入，累积聚合对正在通过输入链接的父记录用作输入 functoid**累积**functoid。</span><span class="sxs-lookup"><span data-stu-id="6a12a-138">Even when the **Cumulative** functoid gets its input from another functoid, the cumulative aggregation takes place over the parent record of the input links to the functoid that serves as input to the **Cumulative** functoid.</span></span>  
  
 <span data-ttu-id="6a12a-139">将作用域参数更改为 1（一）并略微修改输出架构后，生成的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="6a12a-139">Changing the scoping parameter to 1 (one) and modifying the output schema slightly, yields output like the following:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="6a12a-140">将作用域参数设置为 1（一）表示累计具有同一父级的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-140">Setting the scoping parameter to 1 (one) indicates accumulating values for elements or attributes with the same parent.</span></span> <span data-ttu-id="6a12a-141">此处**价格**和**数量**字段具有**项**作为父项，以便 functoid 对值求和的每个人**项**。</span><span class="sxs-lookup"><span data-stu-id="6a12a-141">Here the **Price** and **Quantity** fields have **Item** as a parent so that the functoid sums values for each individual **Item**.</span></span>  
  
 <span data-ttu-id="6a12a-142">如果作用域参数为 2，则该 functoid 将累计具有同一祖父级的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-142">If the scoping parameter is 2, the functoid accumulates values for elements or attributes with the same grandparent.</span></span> <span data-ttu-id="6a12a-143">祖父**价格**和**数量**字段是**LineItems**记录。</span><span class="sxs-lookup"><span data-stu-id="6a12a-143">The grandparent of the **Price** and **Quantity** fields is the **LineItems** record.</span></span> <span data-ttu-id="6a12a-144">因为只有一个**LineItems**实例消息中记录，结果等同于使用默认值：</span><span class="sxs-lookup"><span data-stu-id="6a12a-144">Because there is only one **LineItems** record in the instance message, the result is the same as using the default value:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="6a12a-145">累积的 functoid (除**累积字符串**functoid) 忽略非数字输入。</span><span class="sxs-lookup"><span data-stu-id="6a12a-145">Cumulative functoids (except for the **Cumulative String** functoid) ignore non-numeric input.</span></span> <span data-ttu-id="6a12a-146">例如，输入值“三”将被忽略。</span><span class="sxs-lookup"><span data-stu-id="6a12a-146">For example, an input value of "three" is ignored.</span></span>  
  
 <span data-ttu-id="6a12a-147">**累积平均**，**累计最小**，和**累计最大**functoid 的行为方式类似于**累计和**functoid。</span><span class="sxs-lookup"><span data-stu-id="6a12a-147">The **Cumulative Average**, **Cumulative Minimum**, and **Cumulative Maximum** functoids behave similarly to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="6a12a-148">**累积字符串**连接字符串，而不是聚合数字值。</span><span class="sxs-lookup"><span data-stu-id="6a12a-148">The **Cumulative String** concatenates strings rather than aggregating numeric values.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="6a12a-149">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="6a12a-149">Available functoids</span></span>
  
 <span data-ttu-id="6a12a-150">**的累积**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="6a12a-150">The **Cumulative** functoids are:</span></span> 

* <span data-ttu-id="6a12a-151">累计平均</span><span class="sxs-lookup"><span data-stu-id="6a12a-151">Cumulative Average</span></span>
* <span data-ttu-id="6a12a-152">累计连接</span><span class="sxs-lookup"><span data-stu-id="6a12a-152">Cumulative Concatenate</span></span>
* <span data-ttu-id="6a12a-153">累计最大</span><span class="sxs-lookup"><span data-stu-id="6a12a-153">Cumulative Maximum</span></span>
* <span data-ttu-id="6a12a-154">累计最小</span><span class="sxs-lookup"><span data-stu-id="6a12a-154">Cumulative Minimum</span></span>
* <span data-ttu-id="6a12a-155">累计和</span><span class="sxs-lookup"><span data-stu-id="6a12a-155">Cumulative Sum</span></span>

<span data-ttu-id="6a12a-156">在这些 functoid 的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a12a-156">More details on these functoids are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a12a-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a12a-157">See Also</span></span>  
-  [<span data-ttu-id="6a12a-158">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="6a12a-158">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="6a12a-159">**累积 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6a12a-159">**Cumulative Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>