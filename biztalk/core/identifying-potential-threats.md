---
title: "识别潜在的威胁 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d20f17ee3d1c4d1291de27ae73d18fed3e604fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-potential-threats"></a>识别潜在的威胁
您可以使用 STRIDE 模型来对 BizTalk Server 部署的潜在威胁进行分类。 STRIDE 是派生自以下类别的首字母缩写： *S*哄骗标识*T*篡改数据， *R*epudiation，*我*璝泄露*D*用以服务和特权提升。 本部分列举了对 BizTalk Server 环境的潜在威胁及相应的威胁缓解机制。  
  
 **欺骗标识**  
  
-   如果您将密码保存在绑定文件中并保存这些绑定文件，则未经授权的用户可能会读取密码并使用这些密码连接到 BizTalk Servers，从而可能造成损害。 您不应该将密码保存在绑定文件中，而应使用任意访问控制列表 (DACL) 来限制访问可能包含敏感数据的文件。  
  
 **篡改数据**  
  
-   恶意用户可能会截获合作伙伴发送到 BizTalk Server 的消息，并修改消息内容。 您可以使用数字签名，以防消息在传输过程中遭恶意用户篡改。  
  
 **否认性**  
  
-   您需要跟踪 BizTalk 发送和接收的消息。 可以使用数字签名以证明您发送的消息以及合作伙伴发送给您的消息。  
  
 **信息泄露**  
  
-   恶意用户可能会读取 BizTalk Server 和 Microsoft SQL Server™ 之间的明文通信。 您可使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来保证服务器间的通信安全。 可以使用防火墙来限制对每台服务器的访问。 此外，还可以使用加密在消息传输过程中保护隐私。  
  
-   未经授权的用户可能会访问网络共享位置或目录下的信息。 您可以使用加强的任意访问控制列表 (DACL) 进行限制，仅将访问权限授予需要使用这些资源的帐户。  
  
-   运行 BizTalk 主机实例的计算机的 Windows 管理员有可能误操作，从而招致不同级别的攻击（例如信息泄露或拒绝服务）。 不过，在大多数情况下，您都可以将这些攻击限制在攻击者已对其计算机造成危害的特定主机上。  
  
 **拒绝服务**  
  
-   恶意用户可能会向 BizTalk Server 发送大量的消息，从而阻止 BizTalk 接收有效的消息。 有关对此威胁的缓解技术的详细信息，请参阅[减少拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。  
  
 **特权提升**  
  
-   当在受信任环境中运行不受信任代码时，或是当恶意用户利用软件或配置缺陷时，通常会出现特权提升威胁。 您必须确保在环境中部署的程序集和其他组件是受信任的。 若要最大程度地降低特权提升攻击的可能性，则不同帐户的权限不得重复，并要满足最低权限原则。此外，对于运行时服务和操作，应避免使用管理帐户。 您还应最大程度地减少环境中运行的组件、应用程序和服务数。  
  
## <a name="see-also"></a>另请参阅  
 [减少拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [Planning for Security](../core/planning-for-security.md)