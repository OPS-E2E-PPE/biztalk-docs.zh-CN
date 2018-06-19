---
title: 索引 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Index functoids, about Index functoids
- Index functoids
ms.assetid: 0c8ba427-881c-4b1f-92b9-61992d2a29df
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22881e7694fee872b7820b8b99157ef2cf20170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972579"
---
# <a name="index-functoid"></a><span data-ttu-id="c44f6-102">“索引”Functoid</span><span class="sxs-lookup"><span data-stu-id="c44f6-102">Index Functoid</span></span>
<span data-ttu-id="c44f6-103">**索引**functoid 使您能够选择从特定的记录序列中记录的信息。</span><span class="sxs-lookup"><span data-stu-id="c44f6-103">The **Index** functoid enables you to select information from a specific record in a series of records.</span></span> <span data-ttu-id="c44f6-104">每个**索引**functoid 从单个字段中收集信息。</span><span class="sxs-lookup"><span data-stu-id="c44f6-104">Each **Index** functoid collects information from a single field.</span></span>  
  
 <span data-ttu-id="c44f6-105">某些记录通常会在输入文件中出现多次。</span><span class="sxs-lookup"><span data-stu-id="c44f6-105">Certain records typically occur many times in an input file.</span></span> <span data-ttu-id="c44f6-106">例如，在天气报表中， **DailySummary**元素可能会出现多次。</span><span class="sxs-lookup"><span data-stu-id="c44f6-106">For example, in a weather report, the **DailySummary** element might occur many times.</span></span> <span data-ttu-id="c44f6-107">**DailySummary**元素可能包括使温度和大气压，风速的特性。</span><span class="sxs-lookup"><span data-stu-id="c44f6-107">The **DailySummary** element might include attributes for the temperature, the barometric pressure, and the wind speed.</span></span> <span data-ttu-id="c44f6-108">下面列出了一个示例气象报表的代码：</span><span class="sxs-lookup"><span data-stu-id="c44f6-108">The following code is an example of a weather report.</span></span>  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 <span data-ttu-id="c44f6-109">在基础架构中， **Max Occurs**属性**DailySummary**记录应设置为不受限制，以指示定期或循环记录。</span><span class="sxs-lookup"><span data-stu-id="c44f6-109">In the underlying schema, the **Max Occurs** property for the **DailySummary** record would be set to unbounded to indicate a recurring or looping record.</span></span> <span data-ttu-id="c44f6-110">这样，BizTalk 映射器就会将此记录编译为循环。</span><span class="sxs-lookup"><span data-stu-id="c44f6-110">BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="c44f6-111">假设你想要收集的前两个的天气信息**DailySummary**气象报告的记录。</span><span class="sxs-lookup"><span data-stu-id="c44f6-111">Suppose you want to collect weather information for the first two **DailySummary** records of the weather report.</span></span> <span data-ttu-id="c44f6-112">在 BizTalk 映射程序中每个属性从**DailySummary**记录传入的源架构可以连接到**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="c44f6-112">In BizTalk Mapper, each attribute from the **DailySummary** record of the incoming source schema can be connected to an **Index** functoid.</span></span> <span data-ttu-id="c44f6-113">接下来，每个**索引**functoid 可以指定**DailySummary**记录要从中信息： 第一个或第二个。</span><span class="sxs-lookup"><span data-stu-id="c44f6-113">In turn, each **Index** functoid can specify the **DailySummary** record from which to draw the information: the first or second.</span></span> <span data-ttu-id="c44f6-114">**索引**functoid 然后可以连接到目标架构的相应字段。</span><span class="sxs-lookup"><span data-stu-id="c44f6-114">The **Index** functoids can then be connected to the appropriate fields of the destination schema.</span></span>  
  
 <span data-ttu-id="c44f6-115">下图显示**索引**functoid 采用这种方式。</span><span class="sxs-lookup"><span data-stu-id="c44f6-115">The following figure shows **Index** functoids used in this way.</span></span>  
  
 <span data-ttu-id="c44f6-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span><span class="sxs-lookup"><span data-stu-id="c44f6-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span></span>  
<span data-ttu-id="c44f6-117">“索引”Functoid 示例</span><span class="sxs-lookup"><span data-stu-id="c44f6-117">Index Functoid Example</span></span>  
  
 <span data-ttu-id="c44f6-118">若要获取的第一天的每日摘要信息，请上限设置为三个**索引**functoid 具有其索引值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="c44f6-118">To get the daily summary information for the first day, the upper set of three **Index** functoids have their index values set to 1.</span></span> <span data-ttu-id="c44f6-119">若要获取第二天的每日摘要信息，请越小，将设置为三个**索引**functoid 具有它们设置为 2 的索引值。</span><span class="sxs-lookup"><span data-stu-id="c44f6-119">To get the daily summary information for the second day, the lower set of three **Index** functoids have their index values set to 2.</span></span>  
  
 <span data-ttu-id="c44f6-120">**索引**functoid 使用**配置\<Functoid\> Functoid**对话框以设置它们的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="c44f6-120">**Index** functoids use the **Configure \<Functoid\> Functoid** dialog box to set their input parameters.</span></span> <span data-ttu-id="c44f6-121">第一个输入参数标识源架构中循环记录内的某个字段。</span><span class="sxs-lookup"><span data-stu-id="c44f6-121">The first input parameter identifies a field within a looping record in the source schema.</span></span> <span data-ttu-id="c44f6-122">第二个和其后的输入参数指定特定的记录。</span><span class="sxs-lookup"><span data-stu-id="c44f6-122">The second and succeeding input parameters specify the particular record.</span></span> <span data-ttu-id="c44f6-123">您可以指定多个索引值以选择嵌套重复结构中的记录。</span><span class="sxs-lookup"><span data-stu-id="c44f6-123">You can specify multiple index values to select a record within nested repeating structures.</span></span> <span data-ttu-id="c44f6-124">最内层结构的索引值为第二个参数。</span><span class="sxs-lookup"><span data-stu-id="c44f6-124">The index value for the innermost structure is the second parameter.</span></span> <span data-ttu-id="c44f6-125">紧临的靠外一层结构的索引值为第三个参数，以此类推。</span><span class="sxs-lookup"><span data-stu-id="c44f6-125">The index value for the next outermost structure would be the third parameter, and so on.</span></span> <span data-ttu-id="c44f6-126">例如，假设前面**DailySummary**记录已内**WeeklyData**记录。</span><span class="sxs-lookup"><span data-stu-id="c44f6-126">For example, suppose that the preceding **DailySummary** records were inside **WeeklyData** records.</span></span> <span data-ttu-id="c44f6-127">若要检索**压力**从第一个**DailySummary**在第二个**WeeklyData**，第二个参数应为 1，并且第三个参数将为 2。</span><span class="sxs-lookup"><span data-stu-id="c44f6-127">To retrieve the **Pressure** from the first **DailySummary** in the second **WeeklyData**, the second parameter would be 1 and the third parameter would be 2.</span></span>  
  
 <span data-ttu-id="c44f6-128">请注意，此示例假定**压力**字段不重复。</span><span class="sxs-lookup"><span data-stu-id="c44f6-128">Notice that this example assumes the **Pressure** field does not repeat.</span></span> <span data-ttu-id="c44f6-129">如果字段未重复，索引就不会进入-开始计数便已为**压力**字段，而不是**每日摘要**。</span><span class="sxs-lookup"><span data-stu-id="c44f6-129">If the field did repeat, the indices would be off—the count would begin with the **Pressure** field, rather than the **Daily Summary**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c44f6-130">尽管索引序列输入参数通常为常数，但也可以使用来自源架构中某节点的链接。</span><span class="sxs-lookup"><span data-stu-id="c44f6-130">Although an index sequence input parameter is typically a constant, it is possible to use a link from a node in the source schema.</span></span> <span data-ttu-id="c44f6-131">如果此链接来自于一个循环记录，而该循环记录并不是第一个输入参数的父项，则索引序列输入值将来自输入实例消息中节点的第一个实例。</span><span class="sxs-lookup"><span data-stu-id="c44f6-131">If this link comes from a looping record that is not a parent of the first input parameter, the index sequence input value comes from the first instance of the node in the input instance message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c44f6-132">索引序列输入的值始终与源文档中的当前上下文相关。</span><span class="sxs-lookup"><span data-stu-id="c44f6-132">The value of the index sequence input is always in relation to the current context in the source document.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c44f6-133">**索引**functoid 必须具有如下许多索引值，因为没有从字段级别到根节点下的第一个级别的父节点。</span><span class="sxs-lookup"><span data-stu-id="c44f6-133">An **Index** functoid must have as many index values as there are parent nodes from the field level to the first level below the root node.</span></span> <span data-ttu-id="c44f6-134">例如，在多气象报表实例消息中必须具有两个索引值，</span><span class="sxs-lookup"><span data-stu-id="c44f6-134">For example, in the multiple weather report instance message, two index values are required.</span></span> <span data-ttu-id="c44f6-135">而单气象报表实例消息中只需要具有一个索引值。</span><span class="sxs-lookup"><span data-stu-id="c44f6-135">In the single weather report instance message, only one index value is required.</span></span> <span data-ttu-id="c44f6-136">未能设置所需的索引值数**索引**functoid 创建基于匹配的第一个输入的参数的源实例消息中的第一个节点的输出**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="c44f6-136">Failure to set the required number of index values of an **Index** functoid creates output based on the first node in the source instance message that matches the first input parameter of the **Index** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44f6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c44f6-137">See Also</span></span>  
 <span data-ttu-id="c44f6-138">[如何在向地图添加索引 Functoid](../core/how-to-add-index-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="c44f6-138">[How to Add Index Functoids to a Map](../core/how-to-add-index-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="c44f6-139">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="c44f6-139">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="c44f6-140">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c44f6-140">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="c44f6-141">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="c44f6-141">Record Count Functoid</span></span>](../core/record-count-functoid.md)