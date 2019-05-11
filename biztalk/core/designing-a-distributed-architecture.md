---
title: 设计分布式体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3e495fd45074398fbdedec2e4b8e3fb544f9e55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389721"
---
# <a name="designing-a-distributed-architecture"></a>设计分布式体系结构
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 中的主题提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)解决很多 BizTalk 环境是易受攻击的潜在安全威胁。 虽然设计您的体系结构时，安全性应是高优先级的列表，有一些在分布式环境中，例如高可用性、 可伸缩性和性能的其他注意事项。 本部分提供设计时可考虑的其他选项在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。  
  
## <a name="domains"></a>域  
 如果您所在公司执行主要面向 Internet 的通信，你可以从公司域中删除 intranet 服务。 相反，如果使用 BizTalk Server 要连接到其他应用程序或通过 intranet 连接的业务合作伙伴，您可以删除外围网络。 如果你的公司与少量的合作伙伴进行 Internet 和面向 intranet 的通信，则可以考虑将 intranet 服务和外围网络相结合。  
  
 如果你想要最大程度减少延迟时间以处理服务器和数据域中的 SQL 服务器之间的通信和安全问题，例如网络探查、 篡改数据包和主机欺骗内部网络中不考虑，则可以删除的处理和数据域之间的防火墙，然后合并这些域。 建议您然后使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来保护数据时对其从一台服务器到另一个。  
  
## <a name="sql-server-clustering"></a>SQL Server 群集  
 尽管不在本部分中的详细信息中所述，我们强烈建议您群集数据库故障转移保护。 有关 SQL Server 2008 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=131016 ](http://go.microsoft.com/fwlink/?LinkId=131016)。  
  
## <a name="messagebox-database"></a>MessageBox 数据库  
 具体取决于你的公司的消息吞吐量要求，可能需要添加 （或删除） MessageBox 数据库。 有关多个 messagebox 的详细信息，请参阅[Scaled-Out 数据库](../core/scaled-out-databases.md)。  
  
## <a name="see-also"></a>请参阅  
 [设计安全的体系结构](../core/designing-a-secure-architecture.md)   
 [规划高可用性](../core/planning-for-high-availability3.md)   
 [规划可持续性能](../core/planning-for-sustained-performance.md)   
 [为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)