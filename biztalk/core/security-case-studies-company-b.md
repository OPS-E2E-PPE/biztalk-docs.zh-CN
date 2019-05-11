---
title: 安全性案例研究：公司 B |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 48bbb347-919a-435e-b7b1-34a4c0e65e59
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 650b05a10ae1cc6958e36e8184894de881cdc280
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251071"
---
# <a name="security-case-studies-company-b"></a>安全性案例研究：公司 B
该公司是一家软件公司。 其业务模式依赖于与主要客户和供应商的电子事务。 公司 B 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的事务的实现。  
  
 公司 B 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来管理事务和内部和外部应用程序之间的通信。 公司 B 与大约 85 个内部应用程序和 2300 家贸易合作伙伴进行通信。 当前，处理，每月大约 250 万份文档，并估计，它将处理 600 万份文档，每月结束时 2007年。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的威胁和安全问题  
 公司 B 希望确保它接收并只处理来自已验证源消息。 该公司还希望确保它可以接收和尽可能安全地检索来自其公司网络外部的文档。 将公司 B 的企业网络与 Internet 隔离的防火墙仅允许通过端口 80 和 443 端口的流量。 防火墙拒绝所有其他通信。  
  
## <a name="security-architecture"></a>安全体系结构  
 下图显示了公司 B 使用的多个体系结构。 公司 B 使用 BizTalk Server 作为 message broker 的内部应用程序之间进行通信和处理、 发送和接收正确格式的自其供应商和客户之间的消息。 公司 B 已处理格式不同的内部和外部文档。 这包括平面文件和 XML 文档。  
  
 **图 1 公司 B 安全性体系结构**  
  
 ![公司 B 的体系结构](../core/media/bpi-cp-pc-company-b.gif "BPI_CP_PC_COMPANY_B")  
  
 公司 B 使用单个防火墙用于将公司计算机与 Internet 隔离。 一层额外的安全，公司 B 合并之间所有其服务器和工作站位于公司网络内的 Internet 协议安全 (IPsec) 通信。 公司 B 使用 IPsec 在其内部域中的所有通信进行加密。  
  
 公司 B 使用文件共享服务器来接收平面文件。 此文件共享服务器驻留在公司的网络和域之外。 从公司网络之间使用防火墙隔开的文件共享服务器。 公司 B 的外部合作伙伴将他们的平面文件文档发布在此文件共享服务器上，并且它们与加密的点对点隧道协议 (PPTP) 管道通过在文件共享服务器通信。 公司 B 的有效期为 30 天的合作伙伴密码来保护对文件共享服务器访问。  
  
 公司 B 创建了一个自定义文件移动应用程序，从文件共享服务器检索的平面文件文档，并将其发送到 BizTalk Server 以进行其他处理。 公司 b 的内部应用程序还使用自定义文件移动应用程序将平面文件传递到 BizTalk Server。 BizTalk Server 将转换这些文档，并将其发送到公司 B 的贸易合作伙伴。  
  
 BizTalk Server 将合作伙伴数据转换为内部应用程序格式之前，将验证它具有发件人、 收件人和文档类型条目。 如果 BizTalk Server 接收一条消息，它没有发件人、 收件人或文档类型的条目，BizTalk Server 会拒绝该消息，并运营团队的公司 B 查看消息。 内部应用程序中以不同的格式包括 EDIFACT、 平面文件、 XML 和 ANSI X12 发送消息。  
  
 公司 B 还从内部和外部源接收通过 HTTPS 的文档。 外部合作伙伴将发布到公司网络外部的 Web 服务器文档。 从公司网络之间使用防火墙隔开此 Web 服务器。 自定义文件移动应用程序还将检索通过 HTTPS 发布的文档。 公司 B 使用第三方产品到其贸易合作伙伴的消息进行加密和签名。 作为附加的安全，公司 B 进行夜间审核，以确保它们具有正确的安全设置的所有服务器上。 公司 B 记录供审核的所有异常。  
  
## <a name="see-also"></a>请参阅  
 
 [小型和中型公司的安全性案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 
 [中小型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)