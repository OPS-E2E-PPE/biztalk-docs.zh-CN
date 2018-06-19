---
title: 禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查 |Microsoft 文档
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
ms.openlocfilehash: b33333efd055a659557513ecc8e0b53a42bc30ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297709"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a>禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查
> [!NOTE]  
>  本主题是仅适用于 Windows Server 2003。  
  
 应禁用服务检查 Windows Server 2003 Service Pack 1 和 Service Pack 2 的拒绝。 这是因为在某些高负载情况下，Windows Server 2003 SP1 和 SP2 拒绝服务检查可能不正确地标识有效的 TCP/IP 连接为拒绝服务攻击。  
  
> [!IMPORTANT]  
>  如果你确信不会从实际拒绝服务攻击，则应禁用此功能仅在 intranet 方案。  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a>如何拒绝服务可能会影响 TCP/IP 连接  
 Windows Server 2003 SP1 和 SP2 实现一项安全功能，从而减少并发的 TCP/IP 连接到服务器的队列的大小。 此功能有助于防止拒绝服务攻击。 在负荷条件下 TCP/IP 协议在 Windows Server 2003 SP1 或更高版本可能不正确地标识为拒绝服务攻击的有效的 TCP/IP 连接。 这可能会发生时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载过大。  
  
## <a name="modifying-the-registry-entry"></a>修改的注册表项  
 有关详细信息，请参阅 Microsoft 知识库文章 899599， ["BizTalk Server 主机实例失败，并将常规网络错误写入应用程序日志在 BizTalk Server 基于服务器处理大量的文档"](http://go.microsoft.com/fwlink/?LinkId=158860) (http://go.microsoft.com/fwlink/?LinkId=158860)。 请按照本文中的说明创建**SynAttackProtect**运行该主机的 SQL Server 的计算机上的注册表项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和运行的任何计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在运行 Windows Server2003 SP1 或更高版本。  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a>优化管理的拒绝服务攻击的保护级别的注册表设置  
 在某些情况下你可能想要保持拒绝服务保护但减少主动性应用拒绝服务的功能。 可通过执行以下步骤优化的拒绝服务保护功能的默认行为：  
  
1.  确保**SynAttackProtect**注册表项设置为 REG_DWORD 值**1**中所述[http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477)。  
  
2.  配置**TcpMaxHalfOpen**注册表项中所述[http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478)。  
  
3.  配置**TcpMaxHalfOpenRetried**注册表项中所述[http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479)。  
  
## <a name="see-also"></a>另请参阅  
 [操作的准备工作核对清单](../technical-guides/operational-readiness-checklists.md)