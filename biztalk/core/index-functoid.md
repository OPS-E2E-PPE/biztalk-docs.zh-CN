---
title: 索引 Functoid |Microsoft Docs
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
ms.openlocfilehash: 826f1464b78027faf268ddce7dfea97271ff8698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332092"
---
# <a name="index-functoid"></a><span data-ttu-id="acf30-102">索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="acf30-102">Index Functoid</span></span>
<span data-ttu-id="acf30-103">**索引**functoid，您可以选择从一系列记录中的特定记录的信息。</span><span class="sxs-lookup"><span data-stu-id="acf30-103">The **Index** functoid enables you to select information from a specific record in a series of records.</span></span> <span data-ttu-id="acf30-104">每个**索引**functoid 从单个字段中收集的信息。</span><span class="sxs-lookup"><span data-stu-id="acf30-104">Each **Index** functoid collects information from a single field.</span></span>  
  
 <span data-ttu-id="acf30-105">某些记录通常会在输入文件中出现多次。</span><span class="sxs-lookup"><span data-stu-id="acf30-105">Certain records typically occur many times in an input file.</span></span> <span data-ttu-id="acf30-106">例如，在气象报表**DailySummary**元素可能多次出现。</span><span class="sxs-lookup"><span data-stu-id="acf30-106">For example, in a weather report, the **DailySummary** element might occur many times.</span></span> <span data-ttu-id="acf30-107">**DailySummary**元素可能包含温度、 气压和风速的属性。</span><span class="sxs-lookup"><span data-stu-id="acf30-107">The **DailySummary** element might include attributes for the temperature, the barometric pressure, and the wind speed.</span></span> <span data-ttu-id="acf30-108">以下代码是天气报告的示例。</span><span class="sxs-lookup"><span data-stu-id="acf30-108">The following code is an example of a weather report.</span></span>  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 <span data-ttu-id="acf30-109">在基础架构中， **Max Occurs**属性**DailySummary**记录将被设置为 unbounded 若要表示重复或循环记录。</span><span class="sxs-lookup"><span data-stu-id="acf30-109">In the underlying schema, the **Max Occurs** property for the **DailySummary** record would be set to unbounded to indicate a recurring or looping record.</span></span> <span data-ttu-id="acf30-110">BizTalk 映射器将此记录编译为循环。</span><span class="sxs-lookup"><span data-stu-id="acf30-110">BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="acf30-111">假设你想要收集气象信息前两个**DailySummary**天气报告的记录。</span><span class="sxs-lookup"><span data-stu-id="acf30-111">Suppose you want to collect weather information for the first two **DailySummary** records of the weather report.</span></span> <span data-ttu-id="acf30-112">在 BizTalk 映射器中，每个属性从**DailySummary**传入源架构的记录可以连接到**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="acf30-112">In BizTalk Mapper, each attribute from the **DailySummary** record of the incoming source schema can be connected to an **Index** functoid.</span></span> <span data-ttu-id="acf30-113">接下来，每个**索引**functoid 可以指定**DailySummary**记录从其提取信息： 第一个或第二个。</span><span class="sxs-lookup"><span data-stu-id="acf30-113">In turn, each **Index** functoid can specify the **DailySummary** record from which to draw the information: the first or second.</span></span> <span data-ttu-id="acf30-114">**索引**functoid 就可连接到目标架构的相应字段。</span><span class="sxs-lookup"><span data-stu-id="acf30-114">The **Index** functoids can then be connected to the appropriate fields of the destination schema.</span></span>  
  
 <span data-ttu-id="acf30-115">下图显示**索引**以这种方式使用的 functoid。</span><span class="sxs-lookup"><span data-stu-id="acf30-115">The following figure shows **Index** functoids used in this way.</span></span>  
  
 <span data-ttu-id="acf30-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span><span class="sxs-lookup"><span data-stu-id="acf30-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span></span>  
<span data-ttu-id="acf30-117">索引 Functoid 示例</span><span class="sxs-lookup"><span data-stu-id="acf30-117">Index Functoid Example</span></span>  
  
 <span data-ttu-id="acf30-118">若要获取的第一天的每日摘要信息，上面一组三个**索引**functoid 具有的索引值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="acf30-118">To get the daily summary information for the first day, the upper set of three **Index** functoids have their index values set to 1.</span></span> <span data-ttu-id="acf30-119">若要获取第二天的每日摘要信息，越低，组的三个**索引**functoid 将其设置为 2 的索引值。</span><span class="sxs-lookup"><span data-stu-id="acf30-119">To get the daily summary information for the second day, the lower set of three **Index** functoids have their index values set to 2.</span></span>  
  
 <span data-ttu-id="acf30-120">**索引**functoid 使用**配置\<Functoid\> Functoid**对话框来设置其输入的参数。</span><span class="sxs-lookup"><span data-stu-id="acf30-120">**Index** functoids use the **Configure \<Functoid\> Functoid** dialog box to set their input parameters.</span></span> <span data-ttu-id="acf30-121">第一个输入的参数标识的循环记录中的源架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="acf30-121">The first input parameter identifies a field within a looping record in the source schema.</span></span> <span data-ttu-id="acf30-122">第二个和其后的输入的参数指定特定的记录。</span><span class="sxs-lookup"><span data-stu-id="acf30-122">The second and succeeding input parameters specify the particular record.</span></span> <span data-ttu-id="acf30-123">可以指定多个索引值，以选择嵌套重复结构中的记录。</span><span class="sxs-lookup"><span data-stu-id="acf30-123">You can specify multiple index values to select a record within nested repeating structures.</span></span> <span data-ttu-id="acf30-124">最内层结构的索引值是第二个参数。</span><span class="sxs-lookup"><span data-stu-id="acf30-124">The index value for the innermost structure is the second parameter.</span></span> <span data-ttu-id="acf30-125">下一步最外面的结构的索引值将是第三个参数，等等。</span><span class="sxs-lookup"><span data-stu-id="acf30-125">The index value for the next outermost structure would be the third parameter, and so on.</span></span> <span data-ttu-id="acf30-126">例如，假设上述**DailySummary**记录了内部**WeeklyData**记录。</span><span class="sxs-lookup"><span data-stu-id="acf30-126">For example, suppose that the preceding **DailySummary** records were inside **WeeklyData** records.</span></span> <span data-ttu-id="acf30-127">若要检索**压力**从第一个**DailySummary**在第二个**WeeklyData**、 第二个参数应为 1 和第三个参数应为 2。</span><span class="sxs-lookup"><span data-stu-id="acf30-127">To retrieve the **Pressure** from the first **DailySummary** in the second **WeeklyData**, the second parameter would be 1 and the third parameter would be 2.</span></span>  
  
 <span data-ttu-id="acf30-128">请注意，此示例假定**压力**字段没有重复。</span><span class="sxs-lookup"><span data-stu-id="acf30-128">Notice that this example assumes the **Pressure** field does not repeat.</span></span> <span data-ttu-id="acf30-129">如果字段确实为重复，则索引会关闭，计数将开头**压力**字段中，而不是**每日摘要**。</span><span class="sxs-lookup"><span data-stu-id="acf30-129">If the field did repeat, the indices would be off—the count would begin with the **Pressure** field, rather than the **Daily Summary**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acf30-130">尽管索引序列输入的参数通常为常量，则可以使用源架构中的节点的链接。</span><span class="sxs-lookup"><span data-stu-id="acf30-130">Although an index sequence input parameter is typically a constant, it is possible to use a link from a node in the source schema.</span></span> <span data-ttu-id="acf30-131">如果此链接来自于不是父级的第一个输入参数的循环记录中，索引序列输入的值将来自输入的实例消息中的节点的第一个实例。</span><span class="sxs-lookup"><span data-stu-id="acf30-131">If this link comes from a looping record that is not a parent of the first input parameter, the index sequence input value comes from the first instance of the node in the input instance message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acf30-132">索引序列输入的值始终是相对于源文档中的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="acf30-132">The value of the index sequence input is always in relation to the current context in the source document.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="acf30-133">**索引**functoid 必须具有为许多索引值，因为没有从字段级别到根节点下的第一个级别的父节点。</span><span class="sxs-lookup"><span data-stu-id="acf30-133">An **Index** functoid must have as many index values as there are parent nodes from the field level to the first level below the root node.</span></span> <span data-ttu-id="acf30-134">例如，在多个气象报表实例消息中，两个索引值是必需的。</span><span class="sxs-lookup"><span data-stu-id="acf30-134">For example, in the multiple weather report instance message, two index values are required.</span></span> <span data-ttu-id="acf30-135">在单气象报表实例消息中，则需要一个索引值。</span><span class="sxs-lookup"><span data-stu-id="acf30-135">In the single weather report instance message, only one index value is required.</span></span> <span data-ttu-id="acf30-136">未能设置所需的数量的索引值**索引**创建基于匹配的第一个输入的参数的源实例消息中的第一个节点的输出**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="acf30-136">Failure to set the required number of index values of an **Index** functoid creates output based on the first node in the source instance message that matches the first input parameter of the **Index** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf30-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="acf30-137">See Also</span></span>  
 <span data-ttu-id="acf30-138">[如何向映射添加索引 Functoid](../core/how-to-add-index-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="acf30-138">[How to Add Index Functoids to a Map](../core/how-to-add-index-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="acf30-139">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="acf30-139">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="acf30-140">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="acf30-140">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="acf30-141">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="acf30-141">Record Count Functoid</span></span>](../core/record-count-functoid.md)