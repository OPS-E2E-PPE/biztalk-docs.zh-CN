---
title: 记录计数 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Record Count functoids
ms.assetid: e6aab13f-afbe-4401-abbe-020570e2ff16
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87653709bf5d52c21537064bad286078ad625cf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268741"
---
# <a name="record-count-functoid"></a><span data-ttu-id="abff7-102">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="abff7-102">Record Count Functoid</span></span>
<span data-ttu-id="abff7-103">**记录计数**functoid 计数输入的实例消息中的记录。</span><span class="sxs-lookup"><span data-stu-id="abff7-103">The **Record Count** functoid counts records in the input instance message.</span></span>  
  
 <span data-ttu-id="abff7-104">**记录计数**functoid 有一个输入和一个输出。</span><span class="sxs-lookup"><span data-stu-id="abff7-104">The **Record Count** functoid has one input and one output.</span></span> <span data-ttu-id="abff7-105">输入是源自源架构中某个循环记录的链接。</span><span class="sxs-lookup"><span data-stu-id="abff7-105">The input is a link from a looping record in the source schema.</span></span> <span data-ttu-id="abff7-106">输出**记录计数**functoid 是实际输入的实例消息中的循环记录的计数。</span><span class="sxs-lookup"><span data-stu-id="abff7-106">The output of the **Record Count** functoid is the count of the looping record in an actual input instance message.</span></span>  
  
 <span data-ttu-id="abff7-107">循环记录与输入实例消息中重复任意次数的元素相对应。</span><span class="sxs-lookup"><span data-stu-id="abff7-107">Looping records correspond to elements that repeat an unpredictable number of times in an input instance message.</span></span> <span data-ttu-id="abff7-108">例如，在采购订单，**项**元素可能会出现多次。</span><span class="sxs-lookup"><span data-stu-id="abff7-108">For example, in a purchase order, the **Item** element might occur many times.</span></span> <span data-ttu-id="abff7-109">并且，**项**元素可能包括产品、 说明、 价格和数量。</span><span class="sxs-lookup"><span data-stu-id="abff7-109">And, the **Item** element might include products, descriptions, prices, and quantities.</span></span> <span data-ttu-id="abff7-110">下面的代码显示了此类采购订单的一个简单示例：</span><span class="sxs-lookup"><span data-stu-id="abff7-110">The following code is a simplified example of such a purchase order.</span></span>  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://RecordFunctoid.PurchaseOrder">  
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
  
 <span data-ttu-id="abff7-111">**Max Occurs**属性**项**记录设置为不受限制。</span><span class="sxs-lookup"><span data-stu-id="abff7-111">The **Max Occurs** property for the **Item** record is set as unbounded.</span></span> <span data-ttu-id="abff7-112">这指示**项**记录循环和 BizTalk 映射程序编译时循环，该记录。</span><span class="sxs-lookup"><span data-stu-id="abff7-112">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="abff7-113">假设你想要查找的总数**项**元素中的采购订单输入实例消息并将结果放在输出实例消息中的字段。</span><span class="sxs-lookup"><span data-stu-id="abff7-113">Suppose you want to find the total number of **Item** elements in the purchase order input instance message and place the result in a field in the output instance message.</span></span>  
  
 <span data-ttu-id="abff7-114">下图显示**记录计数**functoid 对传入的采购订单中的项的数目进行计数，然后将该值放**ItemCount**字段**SummedPO**输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="abff7-114">The following figure shows a **Record Count** functoid that counts the number of items in an incoming purchase order and puts that value in the **ItemCount** field in the **SummedPO** output instance message.</span></span>  
  
 <span data-ttu-id="abff7-115">![显示使用情况的记录计数 functoid 的映射。](../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span><span class="sxs-lookup"><span data-stu-id="abff7-115">![Map showing the use of the record count functoid.](../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span></span>  
<span data-ttu-id="abff7-116">“记录计数”Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="abff7-116">Record Count Functoid Map</span></span>  
  
 <span data-ttu-id="abff7-117">请注意， **Max Occurs**属性**项**记录将**unbounded**。</span><span class="sxs-lookup"><span data-stu-id="abff7-117">Notice that the **Max Occurs** property for the **Item** record would be **unbounded**.</span></span> <span data-ttu-id="abff7-118">这指示**项**记录循环和 BizTalk 映射程序编译时循环，该记录。</span><span class="sxs-lookup"><span data-stu-id="abff7-118">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="abff7-119">对于前面的示例采购订单实例消息，其中包含两个**项**元素、 的值**ItemCount**字段将设置为 2。</span><span class="sxs-lookup"><span data-stu-id="abff7-119">For the preceding sample purchase order instance message, which contained two **Item** elements, the value of the **ItemCount** field will be set to 2.</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="abff7-120">你还可以使用**记录计数**functoid 重复字段元素进行计数。</span><span class="sxs-lookup"><span data-stu-id="abff7-120">You can also use the **Record Count** functoid to count repeating field elements.</span></span> <span data-ttu-id="abff7-121">不仅仅限于记录。</span><span class="sxs-lookup"><span data-stu-id="abff7-121">It is not restricted to records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abff7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abff7-122">See Also</span></span>  
 <span data-ttu-id="abff7-123">[如何在向地图添加记录计数 Functoid](../core/how-to-add-record-count-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="abff7-123">[How to Add Record Count Functoids to a Map](../core/how-to-add-record-count-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="abff7-124">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="abff7-124">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="abff7-125">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="abff7-125">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="abff7-126">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="abff7-126">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="abff7-127">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="abff7-127">Looping Functoid</span></span>](../core/looping-functoid.md)