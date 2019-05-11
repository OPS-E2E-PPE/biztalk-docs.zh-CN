---
title: SQL Server 故障转移期间 BizTalk Server 主机实例的行为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cd4f60d37ecf994b258991bb1b0947c2f28d7bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358218"
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间 BizTalk Server 主机实例的行为
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库存储在 Microsoft 的群集实例上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]暂时不可用如果的群集的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]发生故障转移。 本部分介绍与关联的主机实例的行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库都不可用。  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间进程内主机实例的行为  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据不可用，则进程内实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]之前连接到主机将被回收[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]还原。 一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]还原数据库、 文档处理正常恢复。  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间独立主机实例的行为  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据不可用，则的独立的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机将暂停，并将在其中生成类似于以下的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志：  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库还原类似于以下的信息性消息写入到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志和正常处理简历的文档：  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a>请参阅  
 [主机](../core/hosts.md)