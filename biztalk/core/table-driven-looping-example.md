---
title: "表驱动循环示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids, code sample
- Table Looping functoids
- Table Extractor functoids
- Table Looping functoids, about Table Looping functoids
- Table Extractor functoids, about Table Extractor functoids
- code samples, Table Looping functoids
- Table Looping functoids, code sample
- code samples, Table Extractor functoids
ms.assetid: d890bdb1-12a6-4001-9748-737b1f2bab79
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="table-driven-looping-example"></a><span data-ttu-id="5722e-102">表驱动循环示例</span><span class="sxs-lookup"><span data-stu-id="5722e-102">Table-Driven Looping Example</span></span>
<span data-ttu-id="5722e-103">本部分简要介绍映射使用**表循环**和**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="5722e-103">This section briefly describes a map using the **Table Looping** and **Table Extractor** functoids.</span></span> <span data-ttu-id="5722e-104">有关选择的详细信息，将放置、 链接和配置 functoid，请参阅[如何添加表循环和一个映射到表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="5722e-104">For detailed information about selecting, placing, linking, and configuring the functoids, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="5722e-105">假设您有一个需要在文档中使用的地址的列表，该文档需要单独的发货地址和帐单邮寄地址。</span><span class="sxs-lookup"><span data-stu-id="5722e-105">Suppose you have a list of addresses that you need to use in a document requiring separate ship-to and bill-to addresses.</span></span> <span data-ttu-id="5722e-106">这些地址可能如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="5722e-106">The addresses might appear like the following code.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.Addresses">  
    <Address>  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address>  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="5722e-107">可采用的输出形式之一如以下代码所示，可复制这些地址但使用属性对其进行标记：</span><span class="sxs-lookup"><span data-stu-id="5722e-107">One form the output could take would be the following code, duplicating the addresses but marking them with attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.POAddresses">  
    <Address Type="ShipTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City><State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="ShipTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="5722e-108">`The following figure shows a map using the`  **表****循环**`functoid and`**表****提取器**   `functoids to generate the desired output instance message.`</span><span class="sxs-lookup"><span data-stu-id="5722e-108">`The following figure shows a map using the`  **Table** **Looping**  `functoid and`  **Table** **Extractor**  `functoids to generate the desired output instance message.`</span></span>  
  
 <span data-ttu-id="5722e-109">![映射表循环和表提取程序 functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span><span class="sxs-lookup"><span data-stu-id="5722e-109">![Map the Table Looping and Table Extractor functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span></span>  
<span data-ttu-id="5722e-110">“表循环”和“表提取程序”Functoid</span><span class="sxs-lookup"><span data-stu-id="5722e-110">TableLooping and Extractor Functoids</span></span>  
  
 <span data-ttu-id="5722e-111">请注意，**表循环**functoid 指向输入和输出架构中的记录级别元素。</span><span class="sxs-lookup"><span data-stu-id="5722e-111">Notice that the **Table Looping** functoid links to the record-level element in both the input and output schemas.</span></span> <span data-ttu-id="5722e-112">此链接可确保创建封闭的结构，从而确保在记录内创建元素。</span><span class="sxs-lookup"><span data-stu-id="5722e-112">The link ensures the creation of the enclosing structure and, thus, the creation of the elements within the record.</span></span> <span data-ttu-id="5722e-113">此外请注意，有一个**表提取程序**functoid 输出架构中每个字段。</span><span class="sxs-lookup"><span data-stu-id="5722e-113">Also notice that there is one **Table Extractor** functoid for each field in the output schema.</span></span>  
  
 <span data-ttu-id="5722e-114">输入架构中的记录的链接是中的第一个参数**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="5722e-114">The link to the record in the input schema is the first parameter in the **Configure \<Functoid\> Functoid**dialog box.</span></span>  
  
 <span data-ttu-id="5722e-115">第二个参数是 functoid 网格表中的列数： 以一个列的每个地址类型、 名称、 街道、 城市、 州和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="5722e-115">The second parameter is the number of columns in the grid table of the functoid: one column each for the address type, name, street, city, state, and postal code.</span></span> <span data-ttu-id="5722e-116">紧随第二个参数之后是在该网格表中可能显示的所有值的列表。</span><span class="sxs-lookup"><span data-stu-id="5722e-116">Following the second parameter is a list of all of the values that may appear in the grid table.</span></span> <span data-ttu-id="5722e-117">这些值包括地址类型的字符串常数（“ShipTo”、“BillTo”），以及指向地址的字段的链接。</span><span class="sxs-lookup"><span data-stu-id="5722e-117">These include string constants for the address type ("ShipTo", "BillTo"), as well as links to the fields of the address.</span></span> <span data-ttu-id="5722e-118">请注意，指向地址字段的链接都具有名称。</span><span class="sxs-lookup"><span data-stu-id="5722e-118">Notice that the links to the address fields have names.</span></span> <span data-ttu-id="5722e-119">对映射中的链接进行命名，可以简化构造表的过程。</span><span class="sxs-lookup"><span data-stu-id="5722e-119">Naming the links in the map simplifies constructing the table.</span></span> <span data-ttu-id="5722e-120">否则，完整路径出现在**配置表循环 Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="5722e-120">Otherwise, full paths appear in the **Configure Table Looping Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="5722e-121">配置后**表循环**functoid，您可以构造表使用**配置表循环 Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="5722e-121">After you have configured the **Table Looping** functoid, you can construct the table using the **Configure Table Looping Functoid** dialog box.</span></span> <span data-ttu-id="5722e-122">单击省略号，此时将显示对话框 (**...**) 与关联的按钮**表循环网格**中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="5722e-122">The dialog appears when you click the ellipsis (**…**) button associated with the **Table Looping Grid** property in the **Properties** window.</span></span>  
  
 <span data-ttu-id="5722e-123">请注意，有六个列中指定**配置表循环 Functoid**对话框： 输出架构中每个字段的一列。</span><span class="sxs-lookup"><span data-stu-id="5722e-123">Notice that there are six columns as specified in the **Configure Table Looping Functoid** dialog: one column for each field in the output schema.</span></span> <span data-ttu-id="5722e-124">下拉列表中显示的字段，还为指定的中的第三个和以下参数的可能值**配置表循环 Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="5722e-124">The dropdown shows the possible values for a field, also as specified by the third and following parameters in the **Configure Table Looping Functoid** dialog.</span></span> <span data-ttu-id="5722e-125">表包含两行，分别对应于输出架构中的每个记录类型。</span><span class="sxs-lookup"><span data-stu-id="5722e-125">The table has two rows, one for each type of record in the output schema.</span></span> <span data-ttu-id="5722e-126">因为存在两行，所以此映射将为每个输入记录生成两个记录。</span><span class="sxs-lookup"><span data-stu-id="5722e-126">Because there are two rows, this map produces two records for every input record.</span></span> <span data-ttu-id="5722e-127">如果存在四行，则每个输入记录将有四个输出记录。</span><span class="sxs-lookup"><span data-stu-id="5722e-127">If there were four rows, there would be four output records for each input record.</span></span>  
  
 <span data-ttu-id="5722e-128">作为**表循环**functoid 采用每个记录，它在表中记录的值填充，然后将一个行发送到的一次**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="5722e-128">As the **Table Looping** functoid takes each record, it fills in the table with the values from the record, and then sends one row at a time to the **Table Extractor** functoids.</span></span> <span data-ttu-id="5722e-129">**表提取程序**functoid 每个表行中提取一个值，并将其传递到输出实例消息中链接的字段。</span><span class="sxs-lookup"><span data-stu-id="5722e-129">The **Table Extractor** functoids each extract one value from the table row and pass it on to the linked field in the output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5722e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5722e-130">See Also</span></span>  
 <span data-ttu-id="5722e-131">[表循环 Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-131">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="5722e-132">[表提取程序 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-132">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="5722e-133">[表驱动循环配置](../core/table-driven-looping-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-133">[Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md) </span></span>  
 <span data-ttu-id="5722e-134">[如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-134">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="5722e-135">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-135">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="5722e-136">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-136">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="5722e-137">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-137">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="5722e-138">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="5722e-138">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="5722e-139">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="5722e-139">Record Count Functoid</span></span>](../core/record-count-functoid.md)