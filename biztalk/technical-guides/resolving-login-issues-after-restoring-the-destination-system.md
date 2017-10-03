---
title: "在还原目标系统后解决登录问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e691e690552f6decb3eed5f55dd17295c21a4efd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a>在还原目标系统后解决登录问题
根据如何在部署过程配置的源系统，"孤立"用户可能需要解析。 孤立的数据库用户是不具有相应安全的用户登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 使系统联机使用之前创建这些用户的相应登录名[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL Management Studio (在**安全**，**登录名**)。 你可以在任何时刻，创建这些登录名，但我们建议你创建它们时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志传送。  
  
 创建的登录名应该对应于的 Windows 帐户和组时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]源系统和任何登录名已手动创建并在任何已配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-创建角色。 如果这些登录名对应于本地 Windows 帐户或组、 帐户和组必须先创建然后才能添加登录名。 如果未更改的 BizTalk server 的计算机名称，然后解决与本地帐户和组的登录名关联的用户。  
  
 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，请按照 Microsoft 知识库文章 918992 中的步骤[如何传输登录名和密码的 SQL Server 2005 的实例和 SQL Server 2008 之间](http://go.microsoft.com/fwlink/?LinkId=157143)(http://go.microsoft.com/fwlink/？LinkId = 157143) 创建会将必要的登录名添加到目标服务器的脚本。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)