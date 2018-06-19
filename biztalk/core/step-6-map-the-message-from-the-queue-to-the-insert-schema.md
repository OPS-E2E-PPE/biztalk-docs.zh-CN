---
title: 步骤 6 （在本地）： 创建一个可映射到 Insert 架构从队列消息的转换 |Microsoft 文档
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
ms.openlocfilehash: 02b2be9659714beb4b9a52f4c2a9dd1e5b3ea47f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276589"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a>步骤 6 （在本地）： 创建一个可映射到 Insert 架构从队列消息的转换
收到的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从 Service Bus 队列将是**ECommerceSalesOrder.xsd**架构。 但是，若要插入到消息**SalesOrder**表，消息必须为**插入**中生成的架构[步骤 5 （在本地）： 生成用于插入消息 inito 架构SalesOrder 表](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)。 因此，在本主题中，我们创建一个映射，以便转换**ECommerceSalesOrder.xsd**到 Insert 操作架构的架构。  
  
### <a name="to-create-a-map"></a>创建映射的步骤  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你已创建，右键单击项目，指向**添加**，然后单击**新项**。 在**新项**对话框中，选择**映射**，输入映射名称为`SalesOrder_SQL.btm`，然后单击**添加**。  
  
2.  在映射中，对于源架构中，选择**ECommerceSalesOrder.xsd**。 对于目标架构中，选择**TableOperations.SalesOrder.xsd (Insert)** 架构。  
  
3.  直接映射源架构和目标架构中的以下节点：  
  
    |源架构|目标架构|  
    |-------------------|------------------------|  
    |CompanyCode|CompanyCode|  
    |PartId|PartNum|  
    |数量|Qty|  
    |AskPrice|UnitAskPrice|  
    |注释|CustomerComments|  
  
4.  使用**日期和时间**functoid 映射到值**DateRequested**和**ShipDate**目标架构中的元素。 这些节点将不会映射到源架构中的各个节点， 相反，当前日期和时间将传递给这些节点通过使用**日期和时间**functoid。  
  
    1.  拖放式**日期和时间**functoid 从工具箱拖到映射器图面。  
  
    2.  连接到 functoid **DateRequested**目标架构中的元素。  
  
    3.  另一个拖放式**日期和时间**functoid 并连接到**ShipDate**目标架构中的元素。  
  
5.  映射使用源和目标架构中的以下节点**字符串连接**functoid:  
  
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
  
     对每个字符串连接映射集执行以下步骤：  
  
    1.  拖放式**字符串连接**functoid 从工具箱拖到映射器图面。  
  
    2.  将源树中添加每个元素，作为输入到**字符串连接**functoid。  
  
    3.  拖动并配置的输出**字符串连接**functoid 到目标架构中的元素。  
  
         设置好的映射类似于以下内容：  
  
         ![要转换架构映射](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)