---
title: 事务性消息批 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1790c05-e3f7-4667-8a9e-f6f208e55e40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbc6d3a450106df1b67aa2c0e8fb1ada2f1a9e95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399224"
---
# <a name="transactional-message-batches"></a>事务性消息批
某些适配器必须协调外部与内部事务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务。 例如，SQL 适配器附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须协调[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务。 若要执行此操作，适配器需要访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务对象。 事务对象显式创建并与批处理相关联，然后将批处理提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有一个关联的事务对象的批处理调用事务性批处理。 通过提供你自己的 Microsoft 分布式事务处理协调器 (MSDTC) 事务对象，可以实现"得到了保证，一次且仅一次"，传递的数据输入和输出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 像 SQL 适配器的事务数据库适配器由于该批处理的单个事务，在外部数据库中具有死锁的可能性。 这是 SQL 适配器的批大小是硬编码到其中一个原因。  
  
 应适配器需要登记附加资源管理器，如另一个数据库或 MSMQ，该事务的作用域内，它必须创建并传递给消息引擎显式外部事务。 创建外部事务并将其与批处理关联是被调用事务性批处理。 事务性适配器是使适配器使用的事务批处理通过显式创建的外部的 Microsoft 分布式事务处理协调器 (MSDTC) 事务。  
  
 适配器提供的一个原因[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务是确保，或者[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或外部系统具有数据的记录。 此记录可确保一次且只有一次传递消息。  
  
> [!NOTE]
>  有关 MSDTC 的详细信息，请参阅分布式事务处理协调器处的文档： [ http://go.microsoft.com/fwlink/?LinkId=44297 ](http://go.microsoft.com/fwlink/?LinkId=44297)。  
  
 文件适配器是适配器的不需要访问事务由于它所管理的外部文件操作不是适配器的事务的示例。 在这种情况下，适配器不提供将事务对象传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 SQL 适配器，但是，与 SQL 数据库交互，并可能之外的其他操作其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息的交互。 外部 MSDTC 事务在这种情况下很有用的适配器要传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [处理事务](../core/handling-transactions.md)