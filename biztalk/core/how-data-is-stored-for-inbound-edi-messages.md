---
title: "如何将数据存储用于入站的 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60cc8743cd945ad231f3a42f9cbd4f0e76b418d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a>入站 EDI 消息数据的存储方式
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]执行以下操作来生成状态报表项的入站的交换以及在到它的响应中发送该确认：  
  
1.  当 EDI 接收管道将入站消息 XML 发送到 MessageBox 时，接收管道会在状态报告数据存储区中使用以下值创建以下条目：  
  
    -   为收到的每个交换创建一个状态报告条目，并将“状态”设置为“已接受”、“部分接受”或“已拒绝”  
  
    -   为每个技术（交换）确认创建一个状态报告条目（为每个交换创建一个条目），并将“状态”设置为“已生成”  
  
    -   为每个功能确认创建一个状态报告条目（在 X12 中为每个组分别创建一个条目，在 EDIFACT 中则为所有组仅创建一个条目），同时将“状态”设置为“已生成”。  
  
2.  在发送管道将确认发送到贸易合作伙伴之后，EDI 发送管道会相应地将“交换确认”状态和“功能确认”状态条目更新为“已发送”。 不会对“交换”状态条目进行任何更改。  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a>接收管道为入站交换存储的数据  
 接收管道在状态报告数据存储区中为它接收的每个交换创建一条记录。 存储的数据包括：  
  
-   记录类型 = 交换状态  
  
-   交换方向 = 接收  
  
-   交换接收器 = 更新数据  
  
-   交换发件人 = 更新数据  
  
-   交换日期 = 更新数据  
  
-   交换时间 = 更新数据  
  
-   交换控件 ID = 更新数据  
  
-   交换状态： 更新数据  
  
-   交换中组的计数 = 更新数据（在 EDIFACT 中，组是可选的，如果不存在，值为“不可用”）  
  
-   交换接收端口 ID = 更新数据  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>接收管道为每个为了响应入站交换而生成的技术确认存储的数据  
 发送管道在状态报告数据存储区中为其发送的每个技术确认创建一条记录。 技术确认是使用仅对于 EDIFACT 了 UCI 段 X12 和 CONTRL 消息 TA1。 所需的项的大多数数据是可从交换标头/预告片段 （ISA/IEA 或 UNB/UNZ）。 从发送端口属性提供了其他数据。 存储的数据包括：  
  
-   记录类型 = 交换 ACK 状态  
  
-   交换确认方向 = 接收  
  
-   交换接收器 = （所需的相关） 的更新数据  
  
-   交换发件人 = （所需的相关） 的更新数据  
  
-   交换日期 = 更新数据  
  
-   交换控件 ID = （所需的相关） 的更新数据  
  
-   交换 ACK 状态 =\<预期或不适用 >。 如果在传入的交换中配置了技术确认或对其进行了赋值，状态 = 预期。 否则，状态 = 不可用。  
  
-   交换 ACK 控件 ID =\<不值 >  
  
-   交换 ACK 日期 =\<不值 >  
  
-   交换 ACK 时间 =\<不值 >  
  
-   确认/操作代码 =\<不值 >  
  
-   ACK 注意代码 =\<不值 >  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a>发送管道为每个为了响应入站交换而生成的技术确认更新的数据  
 对于发送管道发送的每个技术确认，发送管道会更新所接收相关交换的状态报告条目。 数据的来源为发送管道创建的交换信封。  
  
 EDI 组装器使用传入的确认的 UCI 和 TA1 段中的数据来定位数据存储区中的记录：  
  
|ACK 中的字段|数据存储区中的字段|注释|  
|-------------------|--------------------------|-------------|  
|交换发送方 ID|交换收件人|-|  
|交换接收方 ID|交换发件人|-|  
|-|交换日期|-|  
|交换控制编号|交换控制 ID|-|  
|-|交换方向 = 接收|在保留交换方案中是必需的，以便实现唯一性。|  
|记录类型|交换 ACK 状态|-|  
  
 存储的数据包括：  
  
-   记录类型 = 交换 ACK 状态  
  
-   交换确认方向 = 发送 - 现有数据  
  
-   交换确认状态 = “已处理”或“已发送” – 更新数据  
  
-   交换接收器 = 现有数据  
  
-   交换发件人 = 现有数据  
  
-   交换日期 = 现有数据  
  
-   交换控件 ID = 现有数据  
  
-   交换 ACK 控件 ID = 更新数据  
  
-   交换 ACK 日期 = 更新数据  
  
-   交换 ACK 时间 = 更新数据  
  
-   确认/操作代码 = 现有数据  
  
-   确认注释代码 = 现有数据  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>接收管道为每个为了响应入站交换而生成的功能确认存储的数据  
 发送管道在状态报告数据存储区中为其发送的每个功能确认创建一条记录。 发送管道在状态报告数据存储区为其发送的每个功能确认（为了响应收到的交换）创建一条记录。 如果 EDIFACT 中不存在任何组，仍然会创建一个功能确认。 将使用功能组标头/尾部（GS/GE 或 UNG/UNE）中的数据填充功能确认状态报告条目。 技术确认是 997 X12 和完整 CONTRL 消息 EDIFACT。 存储的数据包括：  
  
-   记录类型 = 功能 ACK 状态  
  
-   功能确认方向 = 接收  
  
-   功能 ACK 状态 =\<预期或不适用 >。 如果选中了 PAM 中的功能确认选项卡，则状态将设置为“预期”。 否则，状态将设置为“不可用”。  
  
-   交换接收器 = （所需的相关） 的更新数据  
  
-   交换发件人 = （所需的相关） 的更新数据  
  
-   交换日期 = 更新数据  
  
-   交换控件 ID = （所需的相关） 的更新数据  
  
-   组控制编号 = 更新数据（对于关联是必需的。 在 EDIFACT 中，如果不存在任何组段，则使用 UNH.1 对此字段进行赋值）  
  
-   功能 ID 代码 = 更新数据（如果不存在组，则在 EDIFACT 中不赋值）  
  
-   事务集的计数 = 数据（在 EDIFACT 中，映射到 UNE.1 并且 UNG/UNE 存在；如果不存在任何组段，则映射到 UNZ.1）  
  
-   功能 ACK 交换的控件 ID =\<不值 >  
  
-   功能 ACK 交换日期 =\<不值 >  
  
-   功能 ACK 交换时间 =\<不值 >  
  
-   计数的事务集传递 =\<不值 >  
  
-   计数的事务集接受 =\<不值 >  
  
-   确认/操作代码 =\<不值 >  
  
-   错误/语法错误代码 =\<不值 >  
  
-   其他 X12 ACK 错误代码 2 =\<不值 >  
  
-   其他 X12 ACK 错误代码 3 =\<不值 >  
  
-   其他 X12 ACK 错误代码 4 =\<不值 >  
  
-   其他 X12 ACK 错误代码 5 =\<不值 >  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a>发送管道为每个为了响应入站交换而生成的功能确认更新的数据  
 对于发送管道发送的每个功能确认，发送管道会更新所接收相关交换的状态报告条目。 数据的来源为发送管道创建的交换信封。  
  
 EDI 组装器使用传入的确认的交换和组标头段中的数据来定位数据存储中的记录：  
  
|ACK 中的字段|数据存储区中的字段|注释|  
|-------------------|--------------------------|-------------|  
|交换发送方 ID|交换收件人|-|  
|交换接收方 ID|交换发件人|-|  
|交换日期|交换日期|-|  
|交换控制编号|交换控制 ID|-|  
|组控制编号|组控制编号|在 EDIFACT 中可选|  
|-|交换方向 = 接收|在保留交换方案中是必需的，以便实现唯一性。|  
|记录类型|功能确认状态|-|  
  
 存储的数据包括：  
  
-   记录类型 = 功能 ACK 状态  
  
-   功能确认方向 = 发送 - 现有数据  
  
-   功能确认状态 = 已处理/已发送 – 更新数据  
  
-   交换接收器 = 现有数据  
  
-   交换发件人 = 现有数据  
  
-   交换日期 = 现有数据  
  
-   交换控件 ID = 现有数据  
  
-   组控制编号 = 现有数据  
  
-   功能 ID 代码 = 现有数据  
  
-   事务集计数 = 现有数据  
  
-   功能确认交换控制 ID = 更新数据  
  
-   功能确认交换日期 = 更新数据  
  
-   功能确认交换时间 = 更新数据  
  
-   接收的事务集的计数 = 现有数据  
  
-   接受的事务集的计数 = 现有数据  
  
-   确认/操作代码 = 现有数据  
  
-   错误/语法错误代码 = 现有数据  
  
-   附加 X12 确认错误代码 2 = 现有数据  
  
-   其他 X12 ACK 错误代码 3 = 现有数据  
  
-   其他 X12 ACK 错误代码 4 = 现有数据  
  
-   其他 X12 ACK 错误代码 5 = 现有数据  
  
## <a name="see-also"></a>另请参阅  
 [如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [如何将数据存储用于出站 EDI 消息](../core/how-data-is-stored-for-outbound-edi-messages.md)