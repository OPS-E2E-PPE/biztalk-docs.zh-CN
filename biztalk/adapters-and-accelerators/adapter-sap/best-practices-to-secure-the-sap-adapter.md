---
title: 最佳做法来保护 SAP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, best practices
ms.assetid: e60014b5-ce2f-4fd4-be2a-921d5cd81267
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f51c25a3eff54d86e715b870c56848b896bfbee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374098"
---
# <a name="best-practices-to-secure-the-sap-adapter"></a>最佳做法来保护 SAP 适配器
本部分提供了更完整地保护敏感数据，使用或开发使用的应用程序时应遵循的最佳实践[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-sap-adapter-and-the-sap-system"></a>SAP 适配器与 SAP 系统之间的连接的最佳安全方案  
  
- 必须确保充分的适配器和 SAP 系统之间交换数据的安全性。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 SAP 安全网络通信 (SNC)。 您可以启用 SNC 或提供备用机制来帮助保护适配器与 SAP 系统之间的通信。  
  
- 为 SAP 系统连接 URI 中不提供用户名密码凭据。 请参阅以下替代方法的各节提供到凭据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 确保你想要接收 SAP 项目 （Rfc、 Idoc 和 Trfc） 从 SAP 程序 ID 的唯一侦听器能够访问该程序 id。 这是因为有权访问程序 ID 的任何侦听器可以从该程序 id。 接收项目  
  
- 请注意，如果多个侦听器同时使用 SAP 程序 ID，SAP 将随机选择的每个传出项目 （RFC、 IDOC 或 tRFC） 侦听器。  
  
  有关详细信息，请参阅[SAP 系统和适配器之间的安全](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-biztalk-server"></a>使用 SAP 适配器与 BizTalk Server 的最佳安全方案  
  
- 为 SAP 系统连接 URI 中不提供用户名密码凭据。  
  
- 当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，输入从 SAP 系统的用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 配置适用于的 BizTalk WCF 自定义适配器时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上的发送端口，输入从 SAP 系统的用户名密码凭据**凭据**选项卡**配置 WCF 自定义传输**对话框。  
  
- 配置适用于的 BizTalk WCF 自定义适配器时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收位置，输入从 SAP 系统的用户名密码凭据**其他**选项卡**配置 WCF 自定义传输**对话框。  
  
  有关详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。
  
## <a name="security-best-practices-for-consuming-the-sap-adapter-with-programming-solutions"></a>使用编程解决方案的 SAP 适配器的最佳安全方案  
  
- 有时需要提供 SAP 系统连接 URI; 中的用户名称密码凭据但是，如果可能，应避免执行此操作。  
  
- 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，输入从 SAP 系统的用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 在 WCF 通道模型编程中，使用**凭据**属性上设置 SAP 系统的用户名称密码凭据的通道工厂。  
  
- 在 WCF 服务模型编程中，使用**ClientCredentials**设置 SAP 系统的用户名称密码凭据在 WCF 客户端上的属性。  
  
- 如果使用的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送消息的跨进程边界到另一个服务或客户端，包含敏感的数据库的信息确保这些消息具有足够的安全措施应用以提供足够的数据你的环境中的保护。  
  
  有关详细信息，请参阅[使用 SAP 适配器的安全编程](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)。  
  
## <a name="security-best-practices-for-hosting-the-sap-adapter-in-iis"></a>承载在 IIS 中的 SAP 适配器的最佳安全方案  
  
- 承载[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 Microsoft Internet 信息服务 (IIS) web 服务公开的操作显示[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]向 Web 客户端。 这些操作可能涉及到通过 Internet 交换敏感数据，因些应采取措施，以帮助确保此数据尽可能安全。  
  
   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了两个标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级别安全机制。  
  
   您可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
   此外可以开发自定义 HTTP 绑定，以充分利用您的环境提供的其他安全机制。 用于详细了解安全特性[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 支持诊断跟踪和消息日志记录。 通过配置文件或使用 Windows Management Instrumentation (WMI) 配置了诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或消息日志记录可以发出敏感信息记录的日志文件，其中它可能会暴露给观察未经授权的用户。  
  
 请按照 WCF 文档中提供的建议，以减少公开通过启用这些功能的潜在安全威胁。 至少，您应遵守以下最佳实践的诊断跟踪和消息日志记录：  
  
- 不要启用"详细"或"信息"在生产环境中的进行跟踪。 这可能会导致性能下降。 但是，必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档了解详细信息。  
  
- 请确保日志文件和配置文件受访问控制列表 (Acl)。  
  
  出现以下警告仅适用于客户端应用程序之间交换的消息和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 由于消息标头的消息操作是，这会显示上调用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]由客户端。  
  
- 如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换消息的消息标头 （但不是在消息正文） 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]记录。 由于消息标头的消息操作是，这会显示在客户端调用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 如果`logEntireMessage`也是`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
   启用诊断跟踪时提高安全性的详细信息，请参阅[安全注意事项和有用提示，用于跟踪](https://msdn.microsoft.com/library/ms733053.aspx)。 有关启用消息日志记录时提高安全性的详细信息，请参阅[消息日志记录的安全问题](https://msdn.microsoft.com/library/ms730318.aspx)。  
  
## <a name="see-also"></a>请参阅  
[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   