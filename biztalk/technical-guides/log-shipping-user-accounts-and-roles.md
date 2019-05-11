---
title: 日志传送用户帐户和角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60dedeadb90f01daeb6e476727b75af1e0ea5be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400378"
---
# <a name="log-shipping-user-accounts-and-roles"></a>日志传送用户帐户和角色
BizTalk Server 日志传送由 SQL Server 代理作业来自动执行还原的备份和日志的过程。 权限不正确可能会导致 BizTalk Server 日志传送失败执行还原操作。 配置要将数据库还原的用户帐户必须有权承载 BizTalk 管理数据库的生产数据库实例。 在大多数情况下这意味着，服务帐户的灾难恢复上驱动 BizTalk Server 日志传送作业的 SQL Server 代理作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例需要一个登录名以及承载生产数据库实例的权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。 这假定 SQL Server 代理服务帐户已配置为作业所有者。  

 BizTalk Server 包含名为 BTS_BACKUP_USERS，以便配置来还原数据库的用户帐户不需要 SQL Server 系统管理员权限的 SQL Server 角色。  

 在配置时将作为 BizTalk Server 日志传送的一部分执行数据库还原操作的用户帐户，请验证以下各项：  

- 若要使用配置中的映射用户的域帐户下运行 SQL Server 代理服务配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (在**安全**，**登录名**) 上每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由还原的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送作业。  

- 配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录帐户对于此用户，并将此用户分配给每个服务器上的 BizTalk BTS_BACKUP_USERS SQL 角色。  

- 向此用户分配[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上运行的计算机的系统管理员角色[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理数据库。  

- 帐户执行备份和还原操作必须具有读取和写入访问权限在 UNC 共享其中创建备份文件。
