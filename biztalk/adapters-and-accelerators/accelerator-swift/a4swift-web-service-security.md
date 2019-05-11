---
title: A4SWIFT Web 服务安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS security
- Web service [A4SWIFT]
- security, transport-level security
- security, message-level security
- ASP.NET security
- A4SWIFT, Web service
- A4SWIFT, security
- security, IIS
- security, ASP.NET
- security, Web service
- messages, security
ms.assetid: e6c7d275-569f-47f6-81fb-10bcd86ff417
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eca05508f9771a61f31cc648675a477f56193702
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378709"
---
# <a name="a4swift-web-service-security"></a>A4SWIFT Web 服务安全性
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务默认情况下安装在高度安全的混合安全模型。 在 iis/ASP.NET 模型 Web 服务之间存在信任边界[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]站点和[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库。  
  
## <a name="iis-and-aspnet-security-settings"></a>IIS 和 ASP.NET 安全设置  
 当调用[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务器上，IIS 首先验证用户身份使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证。 Web 服务的 web.config 设置默认情况下，为使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]不使用模拟，身份验证和验证调用方的成员[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]用户组。 如果调用方的成员[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]用户组中，Web 服务方法在应用程序池的进程标识下运行。 有关[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，这是默认应用程序池的[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]。  
  
 有关[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务的 Web 方法调用方，收件箱中删除该消息[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务必须模拟调用方**删除**并**GetCheckedOutUser**方法。 这些是原始调用方的上下文中运行的唯一方法。 因为[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务模拟这些 Web 方法的调用方，调用方必须拥有对其调用方起作用的 SharePoint 文档库上设置的显式权限。  
  
## <a name="a4swift-secure-communication-settings"></a>A4SWIFT 安全通信设置  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 关心保证的完整性和保密性的 Web 服务消息，因为其从排列[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]到[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]向网络上的 BizTalk 应用程序。 若要提供最高级别的安全性[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]支持两个级别的应用程序之间安全通信： 传输级别和消息级别。  
  
## <a name="transport-level-security"></a>传输级安全  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 支持之间的 SSL 通信[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]，则[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 传递消息时自动调整 MRSR 站点安全设置。  
  
 此外可以实现对之间的通信安全的 Internet 协议安全 (IPSec)[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 有关实施之间进行安全通信的 IPSec 的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，请参阅"保护您部署的 BizTalk Server"BizTalk Server 帮助中。  
  
  
## <a name="message-level-security"></a>消息级安全性  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 消息级安全性通过提供完整性的消息进行数字签名。 签名的消息[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]中详细介绍[InfoPath 安全性](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)。