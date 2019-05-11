---
title: 为 AS2 状态报告存储的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45a115ed95546b99c52358d9cf15e51882991406
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352927"
---
# <a name="data-stored-for-as2-status-reports"></a>为 AS2 状态报告存储的数据
AS2 状态报告中提供了两个级别的报告： 第一个 if**打开报告**为协议选择属性 (从**常规属性**页**常规**选项卡中**协议属性**对话框)，如果为协议选择不可否认数据库存储属性，第二个。  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a>激活 AS2 报告存储的数据  
 如果**打开报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将保留记录所有发送或接收 AS2 消息和 Mdn。  
  
 对于接收的 AS2 消息，BizTalk Server 将存储以下信息：  
  
- AS2 消息的记录。  
  
  对于接收或发送 MDN （同步或异步），BizTalk Server 将存储以下信息：  
  
- MDN 的记录。  
  
  状态报告 UI AS2 消息记录到相应的 MDN 记录的关联。  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a>如果启用重新发送 AS2 消息未收到 MDN 时存储数据  
 如果**MDN 未收到时重新发送 AS2 消息**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将记录以下信息：  
  
-   每次重新发送尝试的时间  
  
-   每次重新发送尝试的状态  
  
-   每次重新发送尝试的索引  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a>启用不可否认数据库存储存储的数据  
 由以下启用不可否认数据库存储所选协议属性：  
  
- 已为出站编码 AS2 消息启用 NRR  
  
- 已为解码后的出站 AS2 消息启用 NRR  
  
- 已为入站 MDN 启用 NRR  
  
- 已为入站编码 AS2 消息启用 NRR  
  
- 已为入站解码 AS2 消息启用 NRR  
  
- 已为出站 MDN 启用 NRR  
  
  如果选择一个或多个以上的属性，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储以下信息：  
  
- 任何 AS2 消息和任何 MDN （带有或不带 AS2 标头） 的内容的内容。  
  
## <a name="data-stored-for-edi-over-as2"></a>通过 AS2 为 EDI 存储的数据  
 如果**打开报告**属性已选，同时为 EDI 协议和 AS2 协议，然后可以将 AS2 消息记录 （包含 EDI 负载） 与 EDI 消息记录关联起来。  
  
 如果启用了事务集存储，你可以在状态报告 UI 中显示事务集详细信息和 AS2 消息内容的详细信息。  
  
> [!NOTE]
>  必须使用 AS2EdiReceive 或 AS2EdiSend 管道以有权访问这些报表。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [为 EDI 状态报告存储的数据](../core/data-stored-for-edi-status-reports.md)   
 [为批处理状态报告存储的数据](../core/data-stored-for-batching-status-reports.md)