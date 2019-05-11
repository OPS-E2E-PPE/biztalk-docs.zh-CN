---
title: 确定潜在的威胁 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43489c8cc0d70f4c4264778cf65672391e242eaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382791"
---
# <a name="identifying-potential-threats"></a>标识潜在威胁
可以使用 STRIDE 模型来识别潜在威胁的 BizTalk Server 部署。 STRIDE 是派生自以下类别的首字母缩写：*S*poofing identity *T*篡改数据， *R*epudiation，*我*表示信息泄露*D*表示拒绝服务，和特权提升。 本部分包含潜在威胁的 BizTalk Server 环境，和机制来降低这些的示例。  
  
 **身份欺骗**  
  
- 如果将密码保存在绑定文件，并保存这些绑定文件时，未经授权的用户无法读取密码和使用它们来连接到 BizTalk 服务器，并可能造成损害。 不应将密码保存在绑定文件中，并应使用自由访问控制列表 (Dacl) 来限制对可能包含敏感数据的文件的访问权限。  
  
  **篡改数据**  
  
- 恶意用户可以截获到 BizTalk Server 中，来自合作伙伴的消息和修改消息的内容。 可以使用数字签名以防止恶意用户篡改消息，尽管它们是在传输过程中。  
  
  **否认性**  
  
- 您需要跟踪的 BizTalk 发送和接收的消息。 可以使用数字签名，证明您发送的消息并，你的合作伙伴向你发送了一条消息。  
  
  **信息泄露**  
  
- 恶意用户可以读取 BizTalk Server 和 Microsoft SQL Server™ 之间的明文通信。 可以使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来帮助保护服务器之间的通信。 可以使用防火墙来限制对每个服务器的访问。 可以使用加密来帮助确保消息的隐私，而它是在传输过程中。  
  
- 未经授权的用户可以访问网络共享或目录的信息。 可以使用加强的任意访问控制列表 (Dacl) 来限制帐户的访问权限的使用的资源。  
  
- 运行 BizTalk 主机实例的计算机上的 Windows 管理员可以错误行为和不同级别的攻击 （例如，信息泄露或拒绝服务）。 但是，在大多数情况下，您可以限制到特定主机的计算机攻击者攻击这些攻击。  
  
  **拒绝服务**  
  
- 恶意用户可以将大量的消息发送到 BizTalk Server 中，这可能会阻止 BizTalk 接收有效的消息。 有关此类威胁的缓解措施的详细信息，请参阅[缓解拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。  
  
  **特权提升**  
  
- 在受信任环境中，你不信任的代码运行时或当恶意用户利用软件或配置缺陷时，通常会发生特权提升威胁。 您必须确保您信任程序集和在环境中部署其他组件。 若要提升权限攻击的可能性降到最低，应使用非重叠、 最低权限的帐户，并应避免使用管理帐户的运行的时服务和操作。 您应尽量少组件、 应用程序，并在环境中运行的服务的数。  
  
## <a name="see-also"></a>请参阅  
 [缓解拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [规划安全性](../core/planning-for-security.md)