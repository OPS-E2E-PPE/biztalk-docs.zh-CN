---
title: 在还原目标系统后解决登录问题 |Microsoft 文档
description: 将 SQL Server 登录脚本来解决在 BizTalk Server 中的孤立的用户日志传送
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 559302718c9fe504c9c264de92f6a4af161d91f9
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013796"
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a>在还原目标系统后解决登录问题

## <a name="orphaned-users"></a>孤立的用户
根据如何在部署过程配置的源系统，"孤立"用户可能需要解析。 孤立的数据库用户是不具有相应安全的用户登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 使系统联机使用之前创建这些用户的相应登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL Management Studio (在**安全**，**登录名**)。 你可以在任何时刻，创建这些登录名，但我们建议你创建它们时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志传送。  
  
 创建的登录名应该对应于的 Windows 帐户和组时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统和任何登录名已手动创建并在任何已配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-创建角色。 如果这些登录名对应于本地 Windows 帐户或组、 帐户和组必须先创建然后才能添加登录名。 如果未更改的 BizTalk server 的计算机名称，然后解决与本地帐户和组的登录名关联的用户。  
  
 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，你可以[KB 918992: SQL Server 实例间传输登录名和密码](https://support.microsoft.com/help/918992/how-to-transfer-logins-and-passwords-between-instances-of-sql-server)创建将必要的登录名添加到目标服务器的脚本。  
  
## <a name="see-also"></a>另请参阅  
 [日志传送疑难解答](../technical-guides/troubleshooting-log-shipping.md)
