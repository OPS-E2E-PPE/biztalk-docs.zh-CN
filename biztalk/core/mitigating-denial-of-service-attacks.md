---
title: 缓解拒绝服务攻击 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9595bf828a1960f50090371232f25282fed21b6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394423"
---
# <a name="mitigating-denial-of-service-attacks"></a>缓解拒绝服务攻击
建议使用以下缓解措施来帮助保护你的 BizTalk 服务器和服务免受拒绝服务攻击。 您必须决定哪些缓解措施是适用于你的环境。  
  
-   **在接收端口中使用的身份验证所需属性。** 默认情况下，BizTalk 发送到 MessageBox 数据库接收的所有消息，即使它们来自未知或无法解析参与方 （来宾）。若要缓解攻击者向 BizTalk Server 发送大量消息以及扩散 （填满） 的可能性 MessageBox 数据库中，您可以使用**身份验证所需**中仅接收到的接收端口属性来自 BizTalk Server 已知的参与方的消息。 可以选择删除来自未知参与方的消息，或若要暂停使用它们。 有关详细信息**所需的身份验证**属性，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。 除了**身份验证所需**属性，应考虑使用外部机制，如防火墙端口筛选或 IP 地址阻止来防止拒绝服务攻击。  
  
-   **限制 BizTalk 可接收的消息的大小。** 例如，当您使用 SOAP 接收适配器，可以避免接收超大的消息大小的 maxRequestLength 属性设置通过\<httpRuntime\>元素为可接受的大小。 \<HttpRuntime\>元素定义在 Machine.config 文件中，位于\<*驱动器*\>:\\<*Windows目录*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG 目录。 有关详细信息\<httpRuntime\>元素，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=60948 ](http://go.microsoft.com/fwlink/?LinkId=60948)。  
  
-   **使用加强的 Dacl 的接收位置。** 建议使用加强的任意访问控制列表 (Dacl) 中的放置位置的接收位置。 例如，必须在目录中的文件接收位置从其中提取消息，使用加强的 Dacl，以便只有经过授权的用户可以在此位置中存放消息。  
  
-   **使用 IPSec。** 如果看不到使用硬件或软件防火墙，请使用 Internet 协议安全 (IPSec) 到另一个以帮助保护 BizTalk Server 将将其传输从一台服务器的消息和数据。 有关 IPSec 的详细信息，请参阅 Microsoft 下载中心[ http://go.microsoft.com/fwlink/?LinkId=60949 ](http://go.microsoft.com/fwlink/?LinkId=60949)。  
  
## <a name="see-also"></a>请参阅  
 [标识潜在威胁](../core/identifying-potential-threats.md)   
 [规划安全性](../core/planning-for-security.md)