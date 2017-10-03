---
title: "A4SWIFT Web 服务安全 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8510172517d58475d855d258b72b16271835dbc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-web-service-security"></a>A4SWIFT Web 服务安全性
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]默认情况下的 Web 服务安装在高度安全的混合安全模型。 Web 服务之间存在信任边界 IIS/ASP.NET 模型中[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]站点，与[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]数据库。  
  
## <a name="iis-and-aspnet-security-settings"></a>IIS 和 ASP.NET 安全设置  
 当调用[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务器，IIS 首先验证用户身份使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证。 Web 服务的 web.config 设置默认情况下，为使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证不进行模拟，并验证调用方为属于[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]用户组。 如果调用方的成员[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]用户组中，Web 服务方法在应用程序池的进程标识下运行。 有关[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，这是默认应用程序池[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]。  
  
 有关[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务以将消息从 Web 方法调用方的收件箱删除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务必须模拟调用方为**删除**和**GetCheckedOutUser**方法。 这些是原始调用方的上下文中运行的唯一方法。 因为[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]Web 服务上模拟时这些 Web 方法的调用方，调用方必须在调用方负责在其 SharePoint 文档库上设置的显式权限。  
  
## <a name="a4swift-secure-communication-settings"></a>A4SWIFT 安全通信设置  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]与从传递保证的完整性和保密性的 Web 服务消息而言[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]到[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]到跨网络的 BizTalk 应用程序。 若要提供安全的最高级别[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]支持两个级别的应用程序之间的安全通信： 传输级别和消息级别。  
  
## <a name="transport-level-security"></a>传输级安全性  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]支持之间的 SSL 通信[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web 服务， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]在传输消息时自动适应 MRSR 站点安全设置。  
  
 此外可以实现对之间的通信安全的 Internet 协议安全性 (IPSec)[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
 有关实施之间进行安全通信的 IPSec[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，请参阅中的"保护你部署的 BizTalk Server"[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
  
## <a name="message-level-security"></a>消息级安全性  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]消息级安全性被通过进行数字签名错误消息提供完整性。 消息签名[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]中详细介绍[InfoPath 安全](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)。