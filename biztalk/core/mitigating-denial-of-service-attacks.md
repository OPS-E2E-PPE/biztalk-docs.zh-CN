---
title: "减少拒绝服务攻击 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPSec, message protection
- messages, size
- security, configuring
- Authentication Required property
- security, Internet Information Services (IIS) Lockdown Tool
- security, Denial of Service attacks
- discretionary access control lists (DACLs)
- IPSec, data protection
- Internet Information Services (IIS) Lockdown Tool
- Denial of Service attacks
ms.assetid: f39c0d0a-b890-4c48-874d-5cafbc71473c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94fe45a2882d85164ab81c13e78fca2ac26d0ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mitigating-denial-of-service-attacks"></a>减少拒绝服务攻击
建议使用以下缓解措施来保护您的 BizTalk Server 和服务免受拒绝服务攻击。 您必须确定其中哪些缓解措施适用于您的环境。  
  
-   **接收端口中使用的身份验证所需属性。** 默认情况下，BizTalk 将其接收的所有消息都发送到 MessageBox 数据库，即使这些消息来自未知或无法解析的参与方（来宾）。若要缓解攻击者将大量的消息发送到 BizTalk Server 以及扩散 （填充） 可能 MessageBox 数据库中，你可以使用**所需的身份验证**中仅接收到的接收端口属性来自 BizTalk 服务器知道的参与方的消息。 您可选择删除或挂起来自未知参与方的消息。 有关详细信息**所需的身份验证**属性，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。 除了**所需的身份验证**属性，则应考虑使用的外部机制，如防火墙端口筛选或 IP 地址阻止来防止拒绝服务攻击。  
  
-   **限制 BizTalk 可以接收的消息的大小。** 例如，当你使用 SOAP 接收适配器，你可以避免通过 maxRequestLength 属性设置接收非常大的消息大小\<httpRuntime > 到可接受的大小的元素。 \<HttpRuntime > 元素定义在 Machine.config 文件中，它位于\<*驱动器*>:\\<*Windows directory*> \Microsoft.NET\Framework\vX.X.XXXXX\CONFIG 目录。 有关详细信息\<httpRuntime > 元素，请参阅 Microsoft MSDN 网站， [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)。  
  
-   **有关使用强 Dacl 接收位置。** 建议在接收位置的存放位置中使用加强的随机访问控制列表 (DACL)。 例如，在文件接收位置从其中提取消息的目录中，必须使用加强的 DACL，以便只有经过授权的用户才能在此位置中存放消息。  
  
-   **使用 IPSec。** 如果不使用硬件或软件防火墙，则应使用 Internet 协议安全性 (IPSec) 在 BizTalk Server 将消息和数据从一个服务器传输到另一个服务器时对其进行保护。 有关 IPSec 的详细信息，请参阅 Microsoft 下载中心[http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)。  
  
## <a name="see-also"></a>另请参阅  
 [识别潜在的威胁](../core/identifying-potential-threats.md)   
 [Planning for Security](../core/planning-for-security.md)