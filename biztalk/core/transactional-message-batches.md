---
title: 事务性消息批处理 |Microsoft 文档
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
ms.openlocfilehash: 28be423aa500ba8950b5b2100ce68dba7743bd79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279525"
---
# <a name="transactional-message-batches"></a>事务性消息批
某些适配器必须协调内部的外部事务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务。 例如，SQL 适配器随附[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须协调[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务。 若要执行此操作，该适配器需要访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务对象。 显式创建事务对象，然后批处理提交到与批处理相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 具有关联的事务的对象的一批调用事务性批处理。 通过提供你自己的 Microsoft 分布式事务处理协调器 (MSDTC) 事务对象，你可以实现"保证，一次且仅一次"，传送数据进出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 由于使用批处理的单个事务情况下，如 SQL 适配器的事务数据库适配器具有外部数据库中的死锁的可能性。 这是 SQL 适配器的批处理大小是硬编码到其中一个原因。  
  
 应适配器需要登记其他资源管理器，例如其他数据库或 MSMQ，该事务范围内的，它必须创建并传递给 the Messaging Engine 显式的外部事务。 创建一个外部事务，并将其与批处理相关联是调用事务性批处理。 事务适配器是使适配器使用的事务批处理通过显式创建外部的 Microsoft 分布式事务处理协调器 (MSDTC) 事务。  
  
 适配器提供的一个原因[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与事务是确保它或者[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或外部系统具有的数据的记录。 此记录可确保消息传送一次且只有一次。  
  
> [!NOTE]
>  有关 MSDTC 的详细信息，请参阅分布式事务处理协调器处的文档： [http://go.microsoft.com/fwlink/?LinkId=44297](http://go.microsoft.com/fwlink/?LinkId=44297)。  
  
 文件适配器是适配器的不需要对事务的访问因为它所管理的外部文件操作不是适配器的事务性的示例。 在这种情况下，该适配器不提供事务对象到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 SQL 适配器，另一方面，与 SQL 数据库交互，并且可能具有之外的其他操作其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息的交互。 外部 MSDTC 事务在这种情况下可能有意义的适配器将传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [处理事务](../core/handling-transactions.md)