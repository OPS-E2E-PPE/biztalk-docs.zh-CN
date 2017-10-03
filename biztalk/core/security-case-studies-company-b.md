---
title: "安全案例研究： 公司 B |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 48bbb347-919a-435e-b7b1-34a4c0e65e59
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef0e37d4acda263822a2cf06095f2c8fd9989afe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-b"></a>安全案例研究： 公司 B
公司 B 是一家软件公司。 其业务模式依赖于与主要客户和主要供应商之间的电子事务。 公司 B 的事务通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实现。  
  
 公司 B 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来管理内部和外部部门之间的事务与通信。 公司 B 需要与大约 85 个内部应用程序和 2300 家贸易合作伙伴进行通信。 目前，该公司每月处理约 250 万份文档，估计到 2007 年底每月将处理 600 万份文档。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的威胁和安全性问题  
 公司 B 希望确保只接收和处理来自已验证源的消息。 该公司还希望能确保尽可能安全地接收和检索公司网络之外的文档。 通过从端口 80 和端口 443 的流量只允许从 Internet 分隔公司 B 的企业网络防火墙。 防火墙将拒绝所有其他通信。  
  
## <a name="security-architecture"></a>安全体系结构  
 下图显示了公司 B 使用的结构。 该公司使用 BizTalk Server 作为 Message Broker，以在内部应用程序之间进行通信，并处理和收发与其供应商和客户之间的适当格式的消息。 该公司需要处理不同格式的内部文档和外部文档。 这包括平面文件和 XML 文档。  
  
 **图 1 公司 B 安全体系结构**  
  
 ![公司 B 的体系结构](../core/media/bpi-cp-pc-company-b.gif "BPI_CP_PC_COMPANY_B")  
  
 公司 B 使用单个防火墙将公司计算机与 Internet 隔开。 作为附加安全措施，公司 B 合并了公司网络内所有服务器和工作站之间的 Internet 协议安全性 (IPsec) 通信。 该公司使用 IPsec 对其内部域的所有通信进行加密。  
  
 公司 B 使用文件共享服务器来接收平面文件。 这个文件共享服务器位于公司的网络和域之外。 此文件共享服务器与公司网络之间使用防火墙隔开。 公司 B 的外部合作伙伴将他们的平面文件文档发布到此文件共享服务器上，并通过加密的点对点隧道协议 (PPTP) 管道与该文件共享服务器通信。 该公司通过提供有效期为 30 天的合作伙伴密码来保护对文件共享服务器的访问。  
  
 公司 B 创建了自定义的文件移动应用程序，该应用程序可检索文件共享服务器上的平面文件文档，并将这些文档发送到 BizTalk Server 做进一步处理。 该公司的内部应用程序也可使用此自定义文件移动应用程序，将平面文件传递到 BizTalk Server。 BizTalk Server 将转换这些文档，并将它们发送给该公司的贸易合作伙伴。  
  
 BizTalk Server 将合作伙伴数据转换为内部应用程序格式之前，将验证数据是否具有发件人、收件人以及文档类型条目。 如果 BizTalk Server 接收到没有发件人、收件人或文档类型条目的消息，则会拒绝此消息，并由公司 B 的运作团队对此消息进行审核。 内部应用程序以各种格式发送消息，其中包括 EDIFACT、平面文件、XML 和 ANSI X12。  
  
 公司 B 也通过 HTTPS 从内部源和外部源接收文档。 外部合作伙伴将他们的文档发布在公司网络之外的 Web 服务器上。 此 Web 服务器与公司网络之间使用防火墙隔开。 自定义的文件移动应用程序也可通过 HTTPS 检索发布的文档。 公司 B 使用第三方产品对发送给贸易合作伙伴的消息进行加密和签名。 作为附加安全措施，公司 B 还对所有服务器进行夜间审核，以确保这些服务器的安全设置正确无误。 该公司对所有异常情况都进行记录，以备检查。  
  
## <a name="see-also"></a>另请参阅  
 
 [对于小型和中型公司的安全案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)