---
title: 步骤 6 （本地）：创建一个转换，以便将消息从队列到插入架构映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 382d408e1fdacbbdc6efe151eb7cf53286d497e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244292"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a>步骤 6 （本地）：创建一个转换，以便将消息从队列到插入架构映射
通过收到的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从服务总线队列都属于**ECommerceSalesOrder.xsd**架构。 但是，若要将消息插入**SalesOrder**表中，消息必须属于**插入**中生成的架构[步骤 5 （本地）：生成插入消息用于向 SalesOrder 表的架构](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)。 因此，在本主题中，我们创建一个映射来转换**ECommerceSalesOrder.xsd**到插入操作架构的架构。  

### <a name="to-create-a-map"></a>若要创建映射  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你已创建，右键单击项目，指向**添加**，然后单击**新项**。 在中**新项**对话框中，选择**映射**，输入作为映射名称`SalesOrder_SQL.btm`，然后单击**添加**。  

2. 在映射中，对于源架构中，选择**ECommerceSalesOrder.xsd**。 对于目标架构中，选择**TableOperations.SalesOrder.xsd (Insert)** 架构。  

3. 直接映射源和目标架构中的以下节点：  


   | 源架构 | 目标架构 |
   |---------------|--------------------|
   |  CompanyCode  |    CompanyCode     |
   |    PartId     |      PartNum       |
   |   Quantity    |        Qty         |
   |   AskPrice    |    UnitAskPrice    |
   |   注释    |  CustomerComments  |


4. 使用**日期和时间**functoid 以将值映射到**DateRequested**并**ShipDate**目标架构中的元素。 这些节点未映射到源架构中的各个节点。 相反，当前日期和时间传递到这些节点通过使用**日期和时间**functoid。  

   1.  拖放到**日期和时间**functoid 从工具箱拖到映射器图面。  

   2.  连接到 functoid **DateRequested**目标架构中的元素。  

   3.  拖放另一个**日期和时间**functoid 并将其连接到**ShipDate**目标架构中的元素。  

5. 映射使用源和目标架构中的以下节点**字符串连接**functoid:  

   |源架构|目标架构|  
   |-------------------|------------------------|  
   |Address\Line1|SellToAddress<br /><br /> BillToAddress|  
   |Address\Line2|SellToAddress<br /><br /> BillToAddress|  
   |Address\City|SellToAddress<br /><br /> BillToAddress|  
   |Address\State|SellToAddress<br /><br /> BillToAddress|  
   |Address\Country|SellToAddress<br /><br /> BillToAddress|  
   |Address\ZipCode|SellToAddress<br /><br /> BillToAddress|  
   |Contact\FirstName|PartnerContact|  
   |Contact\LastName||  

    为每个字符串连接映射集执行以下步骤：  

   1.  拖放到**字符串连接**functoid 从工具箱拖到映射器图面。  

   2.  将源树中的每个元素添加为的输入**字符串连接**functoid。  

   3.  拖放到配置的输出**字符串连接**functoid 到目标架构中的元素。  

        已完成的映射如下所示：  

        ![映射到转换架构](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")  

## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)