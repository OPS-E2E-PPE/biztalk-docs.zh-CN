---
title: 禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688ff81133e60d5be5ef2f9d6826b9b6ca93919c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979262"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a>禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查
> [!NOTE]  
>  本主题是仅适用于 Windows Server 2003。  
  
 应禁用服务检查，Windows Server 2003 Service Pack 1 和 Service Pack 2 的拒绝。 这是因为在某些高负载情况下，Windows Server 2003 SP1 和 SP2 拒绝服务检查可能会错误地标识有效的 TCP/IP 连接为拒绝服务攻击。  
  
> [!IMPORTANT]  
>  当你确信您将不会受到实际拒绝服务攻击时，应禁用此功能仅在 intranet 方案中。  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a>如何拒绝服务可能会影响的 TCP/IP 连接  
 Windows Server 2003 SP1 和 SP2 实施一项安全功能，从而减少到服务器的并发 TCP/IP 连接队列的大小。 此功能有助于防止拒绝服务攻击。 在高负载情况下在 Windows Server 2003 SP1 或更高版本的 TCP/IP 协议可能错误地标识为拒绝服务攻击的有效的 TCP/IP 连接。 这可能会发生时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载过大。  
  
## <a name="modifying-the-registry-entry"></a>修改注册表项  
 有关详细信息，请参阅 Microsoft 知识库文章 899599， ["BizTalk Server 主机实例失败，并且当基于 BizTalk Server 的服务器处理大量文档时，常规网络错误写入到应用程序日志"](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>). 按照这篇文章中的说明来创建**SynAttackProtect**运行该主机的 SQL Server 的计算机上的注册表项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和运行的任何计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行 Windows Server2003 SP1 或更高版本。  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a>优化管理的拒绝服务攻击保护级别的注册表设置  
 在某些情况下您可能想要维护拒绝服务保护但减少的迫切程度应用拒绝服务的功能。 就可以通过执行以下步骤优化拒绝服务保护功能的默认行为：  
  
1.  絋粄**SynAttackProtect**注册表项设置为的 REG_DWORD 值**1**中所述[ http://go.microsoft.com/fwlink/?LinkId=111477 ](http://go.microsoft.com/fwlink/?LinkId=111477)。  
  
2.  配置**TcpMaxHalfOpen**注册表项中所述[ http://go.microsoft.com/fwlink/?LinkId=111478 ](http://go.microsoft.com/fwlink/?LinkId=111478)。  
  
3.  配置**TcpMaxHalfOpenRetried**注册表项中所述[ http://go.microsoft.com/fwlink/?LinkId=111479 ](http://go.microsoft.com/fwlink/?LinkId=111479)。  
  
## <a name="see-also"></a>请参阅  
 [操作准备就绪清单](../technical-guides/operational-readiness-checklists.md)