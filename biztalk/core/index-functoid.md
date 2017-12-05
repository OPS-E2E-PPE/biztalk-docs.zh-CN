---
title: "索引 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Index functoids, about Index functoids
- Index functoids
ms.assetid: 0c8ba427-881c-4b1f-92b9-61992d2a29df
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22881e7694fee872b7820b8b99157ef2cf20170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="index-functoid"></a>“索引”Functoid
**索引**functoid 使您能够选择从特定的记录序列中记录的信息。 每个**索引**functoid 从单个字段中收集信息。  
  
 某些记录通常会在输入文件中出现多次。 例如，在天气报表中， **DailySummary**元素可能会出现多次。 **DailySummary**元素可能包括使温度和大气压，风速的特性。 下面列出了一个示例气象报表的代码：  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 在基础架构中， **Max Occurs**属性**DailySummary**记录应设置为不受限制，以指示定期或循环记录。 这样，BizTalk 映射器就会将此记录编译为循环。  
  
 假设你想要收集的前两个的天气信息**DailySummary**气象报告的记录。 在 BizTalk 映射程序中每个属性从**DailySummary**记录传入的源架构可以连接到**索引**functoid。 接下来，每个**索引**functoid 可以指定**DailySummary**记录要从中信息： 第一个或第二个。 **索引**functoid 然后可以连接到目标架构的相应字段。  
  
 下图显示**索引**functoid 采用这种方式。  
  
 ![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")  
“索引”Functoid 示例  
  
 若要获取的第一天的每日摘要信息，请上限设置为三个**索引**functoid 具有其索引值设置为 1。 若要获取第二天的每日摘要信息，请越小，将设置为三个**索引**functoid 具有它们设置为 2 的索引值。  
  
 **索引**functoid 使用**配置\<Functoid\> Functoid**对话框以设置它们的输入的参数。 第一个输入参数标识源架构中循环记录内的某个字段。 第二个和其后的输入参数指定特定的记录。 您可以指定多个索引值以选择嵌套重复结构中的记录。 最内层结构的索引值为第二个参数。 紧临的靠外一层结构的索引值为第三个参数，以此类推。 例如，假设前面**DailySummary**记录已内**WeeklyData**记录。 若要检索**压力**从第一个**DailySummary**在第二个**WeeklyData**，第二个参数应为 1，并且第三个参数将为 2。  
  
 请注意，此示例假定**压力**字段不重复。 如果字段未重复，索引就不会进入-开始计数便已为**压力**字段，而不是**每日摘要**。  
  
> [!NOTE]
>  尽管索引序列输入参数通常为常数，但也可以使用来自源架构中某节点的链接。 如果此链接来自于一个循环记录，而该循环记录并不是第一个输入参数的父项，则索引序列输入值将来自输入实例消息中节点的第一个实例。  
  
> [!NOTE]
>  索引序列输入的值始终与源文档中的当前上下文相关。  
  
> [!IMPORTANT]
>  **索引**functoid 必须具有如下许多索引值，因为没有从字段级别到根节点下的第一个级别的父节点。 例如，在多气象报表实例消息中必须具有两个索引值， 而单气象报表实例消息中只需要具有一个索引值。 未能设置所需的索引值数**索引**functoid 创建基于匹配的第一个输入的参数的源实例消息中的第一个节点的输出**索引**functoid。  
  
## <a name="see-also"></a>另请参阅  
 [如何在向地图添加索引 Functoid](../core/how-to-add-index-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [“记录计数”Functoid](../core/record-count-functoid.md)