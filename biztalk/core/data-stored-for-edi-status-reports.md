---
title: 为 EDI 状态报告存储的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 498af225f64d58cdff962b34f276814f55f4498e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389793"
---
# <a name="data-stored-for-edi-status-reports"></a>为 EDI 状态报告存储的数据
EDI 状态报告中提供了两个级别的报告： 第一个 if**打开报告**属性选择一个协议，和第二个 if**存储事务集/负载以用于报告**为协议选择属性。 这些属性位于**常规属性**页**常规**选项卡中**协议属性**对话框。  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a>激活 EDI 报告存储的数据  
 如果**打开报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将保留所有已发送或接收的交换、 技术确认和功能确认的记录。  
  
 对于接收的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储以下信息：  
  
- 记录所有收到的交换。 这是显示在状态报告为 EDI 用户界面中的第一个信息。  
  
- 交换中包含的所有事务集的记录。 这不包括启用事务集存储时存储的所有详细信息。  
  
- 收到的交换中存在的所有技术确认的一条记录  
  
- 收到的交换中存在的所有功能确认的一条记录  
  
  > [!NOTE]
  >  如果交换具有多个功能组，将在状态报告 UI 中存储多个功能确认。 但是，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的一组重复功能确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储在状态报告 UI 中的最后一个功能确认。  
  
- 是否需要为收到的交换生成技术确认  
  
- 是否需要为收到的事务集生成功能确认  
  
  对于发送的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储以下信息：  
  
- 所发送交换的一条记录  
  
- 交换中包含的所有事务集的一条记录  
  
- 已发送交换中存在的所有技术确认的一条记录  
  
- 已发送交换中存在的所有功能确认的一条记录  
  
  EDI 状态报告 UI 将这些记录可显示的完整信息相关联。 例如，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收一个交换，并且技术确认和功能确认需要发送给原始消息的发件人在状态报告 UI 中可以轻松地找到此信息。  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a>如果启用了事务集存储存储的数据  
 如果**存储消息负载以用于报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储在发送或接收交换中找到的所有事务集的详细信息。 此级别的状态报告实现的所有执行激活 EDI 报告时，第一个级别报告以及事务集的特定信息。 EDI 接收管道和发送管道生成条目 BAM 数据库中为每个传入和传出组/事务集 (尽管"**存储消息负载报告**选择属性)。 如果交换被拒绝，则会不生成任何记录。  
  
 对于发送或接收的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储以下信息：  
  
-   事务集的内容。 在状态报告 UI，您可以查看交换中包含的事务集，然后查看事务集内容的实际。  
  
-   有关详细信息事务集，其中包括：  
  
|||  
|-|-|  
|信息|字段或值|  
|ApplicationSender|(GS02 或\<UNG2.1(UNG2.2)\>|  
|ApplicationReceiver|GS03 或\<UNG3.1(UNG3.2)\>|  
|GroupDate|GS04 或 UNG2.4|  
|GroupTime|GS05 或 UNG2.5|  
|TransactionSetId|ST01 或 UNH2.1(AN 字符串）|  
|InterchangeControlNo|ISA13|  
|GroupControlNo|GS06|  
|BtsDocType|命名空间 + 根节点名称|  
|TransactionSetControlID|ST02 或 UNH1|  
|TransactionSetStatus|接受 AcceptedWithError，或拒绝|  
|Direction|发送或接收|  
|BtsProcessingTime|在接收端：BTSReceiveTime （本地时间） 管道中<br /><br /> 在发送端：BTSSendTime （本地时间） 作为 ASM 组件在信封上标记|  
|BTS.MessageId|在接收端：来自消息属性的 BTSMessageId<br /><br /> 在发送端：<br /><br /> 对于单个事务集：BTSMessageId<br /><br /> 对于出站批：批处理 (不是批消息的 BTSMessageId) 中每个消息的事务集 BTSMessageId**注意：** 存储仅 – 将不会显示在 UI 中。|  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [为批处理状态报告存储的数据](../core/data-stored-for-batching-status-reports.md)   
 [为 AS2 状态报告存储的数据](../core/data-stored-for-as2-status-reports.md)