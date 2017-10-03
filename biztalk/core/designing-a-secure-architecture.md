---
title: "设计安全的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 157c11477efb9dec455e9ac2de81736cd4ea72ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="designing-a-secure-architecture"></a>设计安全结构
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 主题中提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)消除了许多潜在的安全威胁到 BizTalk 环境的易受攻击。 不过，你需要评估你的业务资产、与你的业务相关的威胁以及可用于保护资产和缓解潜在威胁的资源，以确定适合你的最佳结构。 此部分提供其他安全选项，您可以在设计时考虑你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。  
  
## <a name="firewalls"></a>防火墙  
 可以使用物理（硬件）或软件防火墙来限制对环境中资源的访问。 尽管主题[大型分布式体系结构](../core/large-distributed-architecture.md)使用 Forefront Threat Management Gateway (TMG) 2010年服务器，你可以创建相似的体系结构通过使用硬件或第三方软件防火墙、，只要您打开和配置不同的 BizTalk Server 组件之间的通信所需的端口。 BizTalk Server 使用的端口的详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。  
  
## <a name="active-directory"></a>Active Directory  
 在示例部署中，用于创建严格的安全边界的服务器的每个组周围 Active Directory® 目录服务。 使用单向信任，你可以进一步保护 BizTalk Server 环境不会因处理服务器上运行的其他非 BizTalk Server 应用程序中的缺陷而遭受攻击，因为 BizTalk Server 应用程序在数据域中创建的帐户下运行。 由于数据域不信任其他任何域中的任何帐户，因此，如果其他域中的帐户受到威胁，也不会危及 BizTalk Server 环境。  
  
## <a name="ipsec-and-ssl"></a>IPSec 和 SSL  
 如果你的环境未造成需要防火墙所提供安全级别的关键威胁，但没有从物理上保护连接数据域、处理域和服务域的网络段免受各种网络攻击（例如，数据包探查或篡改），则你仍需要在服务器间传递数据时对其进行保护。 在这种情况下，可使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 对服务器之间的通信进行加密。  
  
## <a name="see-also"></a>另请参阅  
 [设计分布式体系结构](../core/designing-a-distributed-architecture.md)   
 [规划安全性](../core/planning-for-security.md)   
 [BizTalk server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)