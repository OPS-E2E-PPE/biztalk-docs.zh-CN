---
title: 设计安全的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacd6bf8414ac91e2fb6d7846fd3b650c90b6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351676"
---
# <a name="designing-a-secure-architecture"></a>设计安全的体系结构
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 中的主题提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)解决很多 BizTalk 环境是易受攻击的潜在安全威胁。 但是，您需要评估你的业务资产，需考虑您的业务，并可用于保护你的资产和缓解潜在威胁来确定最佳体系结构是为你的资源的威胁。 此部分提供了可以考虑在设计时额外的安全选项在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。  
  
## <a name="firewalls"></a>防火墙  
 可以使用物理 （硬件） 或软件防火墙来限制对资源的访问，您的环境中。 尽管本主题[大型分布式体系结构](../core/large-distributed-architecture.md)使用 Forefront Threat Management Gateway (TMG) 2010年服务器，您可以创建相似的体系结构使用硬件或第三方软件防火墙，只要您打开和配置不同的 BizTalk Server 组件之间进行通信所需的端口。 有关 BizTalk Server 所使用的端口的详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。  
  
## <a name="active-directory"></a>Active Directory  
 在示例部署中，Active Directory® 目录服务用于创建服务器的每个组周围的严格的安全边界。 使用单向信任，可以进一步保护 BizTalk Server 环境免受由于作为应用程序数据域中创建的帐户下运行的 BizTalk Server 处理服务器上运行其他非 BizTalk Server 应用程序中的漏洞的攻击。 数据域不信任其他任何域中的任何帐户，因为另一个域中的帐户的安全威胁使 BizTalk Server 环境不会受到攻击。  
  
## <a name="ipsec-and-ssl"></a>IPSec 和 SSL  
 如果你的环境未造成严重提供需要的安全防火墙级别的威胁，但网络段连接的数据，处理，并且服务域不是物理上安全免受各种网络攻击 （例如，数据包探查或篡改），仍需要保护的数据，随着从一台服务器添加到另一个。 在这种情况下，您可以使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 从一台服务器之间的通信进行加密。  
  
## <a name="see-also"></a>请参阅  
 [设计分布式体系结构](../core/designing-a-distributed-architecture.md)   
 [规划安全性](../core/planning-for-security.md)   
 [为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)