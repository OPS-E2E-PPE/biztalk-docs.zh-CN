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
# <a name="index-functoid"></a>索引 Functoid
**索引**functoid，您可以选择从一系列记录中的特定记录的信息。 每个**索引**functoid 从单个字段中收集的信息。  
  
 某些记录通常会在输入文件中出现多次。 例如，在气象报表**DailySummary**元素可能多次出现。 **DailySummary**元素可能包含温度、 气压和风速的属性。 以下代码是天气报告的示例。  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 在基础架构中， **Max Occurs**属性**DailySummary**记录将被设置为 unbounded 若要表示重复或循环记录。 BizTalk 映射器将此记录编译为循环。  
  
 假设你想要收集气象信息前两个**DailySummary**天气报告的记录。 在 BizTalk 映射器中，每个属性从**DailySummary**传入源架构的记录可以连接到**索引**functoid。 接下来，每个**索引**functoid 可以指定**DailySummary**记录从其提取信息： 第一个或第二个。 **索引**functoid 就可连接到目标架构的相应字段。  
  
 下图显示**索引**以这种方式使用的 functoid。  
  
 ![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")  
索引 Functoid 示例  
  
 若要获取的第一天的每日摘要信息，上面一组三个**索引**functoid 具有的索引值设置为 1。 若要获取第二天的每日摘要信息，越低，组的三个**索引**functoid 将其设置为 2 的索引值。  
  
 **索引**functoid 使用**配置\<Functoid\> Functoid**对话框来设置其输入的参数。 第一个输入的参数标识的循环记录中的源架构中的字段。 第二个和其后的输入的参数指定特定的记录。 可以指定多个索引值，以选择嵌套重复结构中的记录。 最内层结构的索引值是第二个参数。 下一步最外面的结构的索引值将是第三个参数，等等。 例如，假设上述**DailySummary**记录了内部**WeeklyData**记录。 若要检索**压力**从第一个**DailySummary**在第二个**WeeklyData**、 第二个参数应为 1 和第三个参数应为 2。  
  
 请注意，此示例假定**压力**字段没有重复。 如果字段确实为重复，则索引会关闭，计数将开头**压力**字段中，而不是**每日摘要**。  
  
> [!NOTE]
>  尽管索引序列输入的参数通常为常量，则可以使用源架构中的节点的链接。 如果此链接来自于不是父级的第一个输入参数的循环记录中，索引序列输入的值将来自输入的实例消息中的节点的第一个实例。  
  
> [!NOTE]
>  索引序列输入的值始终是相对于源文档中的当前上下文。  
  
> [!IMPORTANT]
>  **索引**functoid 必须具有为许多索引值，因为没有从字段级别到根节点下的第一个级别的父节点。 例如，在多个气象报表实例消息中，两个索引值是必需的。 在单气象报表实例消息中，则需要一个索引值。 未能设置所需的数量的索引值**索引**创建基于匹配的第一个输入的参数的源实例消息中的第一个节点的输出**索引**functoid。  
  
## <a name="see-also"></a>请参阅  
 [如何向映射添加索引 Functoid](../core/how-to-add-index-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)