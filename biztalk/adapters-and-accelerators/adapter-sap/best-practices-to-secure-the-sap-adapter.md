---
title: "最佳做法来保护 SAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security, best practices
ms.assetid: e60014b5-ce2f-4fd4-be2a-921d5cd81267
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34d6c56af06bb6b8dc0831c354d494bb62ad5bfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-sap-adapter"></a>最佳做法来保护 SAP 适配器
本部分提供了你应遵循的更完整地保护敏感数据，当你使用或开发的应用程序使用的最佳做法[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-sap-adapter-and-the-sap-system"></a>SAP 适配器和 SAP 系统之间的连接的最佳安全方案  
  
-   你必须确保足够的适配器和 SAP 系统之间交换的数据的安全级别。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 SAP 安全网络通信 (SNC)。 你可以启用 SNC 或提供替代机制以帮助在适配器和 SAP 系统之间的通信安全。  
  
-   SAP 系统连接 URI 中未提供用户名密码凭据。 请参阅以下替代方法的各节提供凭据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   确保你想要接收 SAP 项目 （Rfc、 Idoc 和 tRFCs） 从 SAP 程序 ID 的唯一侦听器能够访问该程序 id。 这是因为有权访问程序 ID 的任何侦听器可以接收项目，从该程序 id。  
  
-   请注意，如果多个侦听器同时使用 SAP 程序 ID，SAP 将随机选择的每个传出项目 （RFC、 IDOC 或 tRFC） 侦听器。  
  
 有关详细信息，请参阅[SAP 系统和适配器之间的安全性](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-biztalk-server"></a>使用 BizTalk Server 中的 SAP 适配器的最佳安全方案  
  
-   SAP 系统连接 URI 中未提供用户名密码凭据。  
  
-   当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，为 SAP 系统从输入用户名密码凭据**安全**选项卡**配置适配器**对话框。  
  
-   当你配置的 BizTalk WCF 自定义适配器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上发送端口，输入用户名密码凭据的 SAP 系统从**凭据**选项卡**配置 WCF 自定义传输**对话框。  
  
-   当你配置的 BizTalk WCF 自定义适配器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上接收位置，输入用户名密码凭据的 SAP 系统从**其他**选项卡**配置 WCF 自定义传输**对话框。  
  
 有关详细信息，请参阅[安全性与 SAP 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-programming-solutions"></a>使用编程解决方案的 SAP 适配器的最佳安全方案  
  
-   有时需要提供用户的名称密码凭据连接 URI; 中的 SAP 系统但是，如果可能，应避免执行此操作。  
  
-   当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，为 SAP 系统从输入用户名密码凭据**安全**选项卡**配置适配器**对话框。  
  
-   在 WCF 通道模型编程中，使用**凭据**属性用于设置 SAP 系统的用户名称密码凭据的通道工厂。  
  
-   在 WCF 服务模型编程中，使用**ClientCredentials** WCF 客户端设置的 SAP 系统的用户名称密码凭据上的属性。  
  
-   如果应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]跨进程边界到另一个服务或客户端，包含敏感的数据库信息的发送消息确保这些消息具有足够的安全措施提供足够的数据你的环境中的保护。  
  
 有关详细信息，请参阅[SAP 适配器使用的安全编程](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)。  
  
## <a name="security-best-practices-for-hosting-the-sap-adapter-in-iis"></a>承载在 IIS 中的 SAP 适配器的最佳安全方案  
  
-   承载[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 Microsoft Internet 信息服务 (IIS) 作为 Web 服务公开操作显示[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Web 客户端。 这些操作可能会涉及到通过 Internet，交换敏感数据，因此你应采取措施以帮助确保此数据尽可能安全。  
  
     [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供以下两种标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供不存在任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级安全机制。  
  
     你可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]来生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
     您还可以开发自定义的 HTTP 绑定，以便利用你的环境提供的其他安全机制。 有关安全性的详细信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]支持诊断跟踪和消息日志记录。 通过配置文件或通过使用 Windows Management Instrumentation (WMI)，请配置诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或日志记录可以发出要记录的敏感信息的消息文件，其中它可能会暴露给观察未经授权的用户。  
  
 请遵循 WCF 文档中提供的建议，以缓解公开通过启用这些功能的潜在安全威胁。 至少，你应遵守以下最佳做法诊断跟踪和消息日志记录：  
  
-   不要启用"详细"或在生产环境中的"信息"跟踪。 这可能会导致性能下降。 但是，你必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，你必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档以了解更多信息。  
  
-   确保日志文件和配置文件受访问控制列表 (Acl)。  
  
 以下警告尤其适用于在客户端应用程序之间交换的消息和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 由于消息标头中的消息操作，这将显示上调用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]客户端。  
  
-   如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换的消息的消息标头 （但不是消息正文） 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]记录。 由于消息标头中的消息操作，这将显示客户端调用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 如果`logEntireMessage`也`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
     有关提高安全性，当你启用诊断跟踪的详细信息，请参阅[安全问题和跟踪的有用提示](https://msdn.microsoft.com/library/ms733053.aspx)。 有关提高安全性，当你启用消息日志记录的详细信息，请参阅[的消息日志记录的安全问题](https://msdn.microsoft.com/library/ms730318.aspx)。  
  
## <a name="see-also"></a>另请参阅  
[保护你的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   