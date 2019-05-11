---
title: 如何为入站的 EDI 消息存储数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a117bb89989977ab0050d0d6b4704002f316315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387467"
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a>如何为入站的 EDI 消息存储数据
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行以下操作生成的入站的交换和确认已发送到它的响应的状态报告条目：  
  
1.  入站的消息 XML 发送时 EDI 接收管道到 MessageBox，接收管道在状态报告功能，使用以下值的数据存储区中创建以下条目：  
  
    -   每个接收的交换，状态设置为已接受/部分接受/拒绝的一个状态报告条目  
  
    -   对于每个技术 （交换） 确认一个状态报告条目，每个状态的交换，一个设置为生成  
  
    -   每个功能确认的一个状态报告条目，为每个组在 X12，另一个用于所有组在 EDIFACT 中，状态将设置为生成。  
  
2.  发送管道发送后为贸易合作伙伴，EDI 确认管道将更新发送的交换确认状态和功能确认状态条目到已发送的根据需要。 交换状态条目不进行任何更改。  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a>接收管道为入站交换存储的数据  
 接收管道接收每个交换状态报告数据存储区创建一条记录。 存储的数据包括：  
  
-   记录类型 = 交换状态  
  
-   交换方向 = 接收  
  
-   交换接收方 = 更新数据  
  
-   交换发送方 = 更新数据  
  
-   交换日期 = 更新数据  
  
-   交换时间 = 更新数据  
  
-   交换控制 ID = 更新数据  
  
-   交换状态：更新数据  
  
-   交换中组的计数 = 更新数据 （在 EDIFACT 中，组是可选的如果不存在，值为不适用)  
  
-   交换接收端口 ID = 更新数据  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>接收管道为每个技术而生成的响应的入站交换确认存储的数据  
 发送管道创建状态报告数据存储区中的每个技术确认，它将发送一条记录。 只有 UCI 段对于 EDIFACT 具有用于 CONTRL 消息和 X12 TA1 技术确认。 可从交换标头/尾部段 （ISA/IEA 或 UNB/UNZ） 最多的数据所需的条目。 可从发送端口的属性的其他数据。 存储的数据包括：  
  
-   记录类型 = 交换确认状态  
  
-   交换确认方向 = 接收  
  
-   交换接收方 = 更新数据 （需要相关）  
  
-   交换发送方 = 更新数据 （需要相关）  
  
-   交换日期 = 更新数据  
  
-   交换控制 ID = 更新数据 （需要相关）  
  
-   交换确认状态 =\<预期或不适用\>。 如果配置了技术确认或将其值在传入的交换中，状态 = 预期。 否则为状态 = 不可用。  
  
-   交换确认控制 ID =\<未赋值\>  
  
-   交换确认日期 =\<未赋值\>  
  
-   交换确认时间 =\<未赋值\>  
  
-   确认/操作代码 =\<未赋值\>  
  
-   确认注释代码 =\<未赋值\>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a>为生成响应入站交换中每个技术确认更新的发送管道的数据  
 对于每个技术确认，发送管道发送，会更新接收相关交换状态报告条目。 数据源将是由发送管道创建的交换信封。  
  
 EDI 组装器定位在数据存储中使用的 UCI 和 TA1 段传入的确认中的数据，如下所示的记录：  
  
|ACK 中的字段|数据存储区中的字段|注释|  
|-------------------|--------------------------|-------------|  
|交换发送方 ID|交换接收方|-|  
|交换接收方 ID|交换发送方|-|  
|-|交换日期|-|  
|交换控制编号|交换控制 ID|-|  
|-|交换方向 = 接收|在保留的交换方案中的唯一性要求|  
|记录类型|交换确认状态|-|  
  
 存储的数据包括：  
  
-   记录类型 = 交换确认状态  
  
-   交换确认方向 = 发送-现有数据  
  
-   交换确认状态 = 处理或发送 – 更新数据  
  
-   交换接收方 = 现有数据  
  
-   交换发送方 = 现有数据  
  
-   交换日期 = 现有数据  
  
-   交换控制 ID = 现有数据  
  
-   交换确认控制 ID = 更新数据  
  
-   交换确认日期 = 更新数据  
  
-   交换确认时间 = 更新数据  
  
-   确认/操作代码 = 现有数据  
  
-   确认注释代码 = 现有数据  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>接收管道为每个功能而生成的响应的入站交换确认存储的数据  
 发送管道在发送每个功能确认状态报告数据存储区中创建一条记录。 发送管道在状态报告数据存储区中创建每个功能确认 （为了响应接收的交换） 发送一条的记录。 如果不不在 EDIFACT 中存在任何组，则仍将创建一个功能确认。 将从功能组标头/尾部 （GS/GE 或 UNG/UNE） 填充功能确认状态报告条目。 技术确认是 997 的 X12 和完整 CONTRL 消息的 EDIFACT。 存储的数据包括：  
  
-   记录类型 = 功能确认状态  
  
-   功能确认方向 = 接收  
  
-   功能确认状态 =\<预期或不适用\>。 如果选择了 PAM 中的功能确认选项卡，状态将设置为预期。 否则，状态将设置为不适用。  
  
-   交换接收方 = 更新数据 （需要相关）  
  
-   交换发送方 = 更新数据 （需要相关）  
  
-   交换日期 = 更新数据  
  
-   交换控制 ID = 更新数据 （需要相关）  
  
-   组控制编号 = 更新数据 （所需的相关。 在 EDIFACT 中如果不存在此字段的任何组段，则使用 UNH.1）  
  
-   功能 ID 代码 = 更新数据 （非值在 EDIFACT 中如果组不存在）  
  
-   事务集的计数 = 数据 （在 EDIFACT 中是否存在任何组段它映射到 UNE.1 并且 UNG/UNE 都存在或 UNZ.1)  
  
-   功能 ACK 交换控制 ID =\<未赋值\>  
  
-   功能确认交换日期 =\<未赋值\>  
  
-   功能确认交换时间 =\<未赋值\>  
  
-   计数传送的事务集 =\<未赋值\>  
  
-   接受的事务计数集 =\<未赋值\>  
  
-   确认/操作代码 =\<未赋值\>  
  
-   错误/语法错误代码 =\<未赋值\>  
  
-   附加 X12 确认错误代码 2 =\<未赋值\>  
  
-   附加 X12 确认错误代码 3 =\<未赋值\>  
  
-   附加 X12 确认错误代码 4 =\<未赋值\>  
  
-   附加 X12 确认错误代码 5 =\<未赋值\>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a>为生成响应入站交换中每个功能确认更新的发送管道的数据  
 对于发送管道发送每个功能确认，它更新接收相关交换状态报告条目。 数据源将是由发送管道创建的交换信封。  
  
 EDI 组装器定位在数据存储中使用的交换和组标头传入的确认段中的数据，如下所示的记录：  
  
|ACK 中的字段|数据存储区中的字段|注释|  
|-------------------|--------------------------|-------------|  
|交换发送方 ID|交换接收方|-|  
|交换接收方 ID|交换发送方|-|  
|交换日期|交换日期|-|  
|交换控制编号|交换控制 ID|-|  
|组控制编号|组控制编号|在 EDIFACT 中可选|  
|-|交换方向 = 接收|在保留的交换方案中的唯一性要求|  
|记录类型|功能确认状态|-|  
  
 存储的数据包括：  
  
-   记录类型 = 功能确认状态  
  
-   功能确认方向 = 发送-现有数据  
  
-   功能确认状态 = 处理/已发送 – 更新数据  
  
-   交换接收方 = 现有数据  
  
-   交换发送方 = 现有数据  
  
-   交换日期 = 现有数据  
  
-   交换控制 ID = 现有数据  
  
-   组控制编号 = 现有数据  
  
-   功能 ID 代码 = 现有数据  
  
-   事务集计数 = 现有数据  
  
-   功能 ACK 交换控制 ID = 更新数据  
  
-   功能 ACK 交换日期 = 更新数据  
  
-   功能 ACK 交换时间 = 更新数据  
  
-   接收的事务集计数 = 现有数据  
  
-   接受的事务集计数 = 现有数据  
  
-   确认/操作代码 = 现有数据  
  
-   错误/语法错误代码 = 现有数据  
  
-   附加 X12 确认错误代码 2 = 现有数据  
  
-   附加 X12 确认错误代码 3 = 现有数据  
  
-   附加 X12 确认错误代码 4 = 现有数据  
  
-   附加 X12 确认错误代码 5 = 现有数据  
  
## <a name="see-also"></a>请参阅  
 [如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [如何为出站 EDI 消息存储数据](../core/how-data-is-stored-for-outbound-edi-messages.md)