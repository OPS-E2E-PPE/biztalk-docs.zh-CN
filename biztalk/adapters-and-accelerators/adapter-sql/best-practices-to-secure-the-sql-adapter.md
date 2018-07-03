---
title: 最佳做法来保护 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e32379d7-800a-49b7-a09a-6b3f04a6e5ef
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a5bb38e1ffd8c40e56b6e581273b8507159268b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007774"
---
# <a name="best-practices-to-secure-the-sql-adapter"></a>最佳做法来保护 SQL 适配器
完全更应遵循的最佳做法保护敏感数据时使用或开发的应用程序使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-sql-adapter-and-the-sql-server-database"></a>SQL 适配器与 SQL Server 数据库之间的连接的最佳安全方案  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不提供支持，可帮助向它与 SQL Server 数据库之间安全通信。 必须提供一种机制来帮助确保充分的适配器和 SQL Server 数据库之间交换数据的安全性。  
  
- 出于安全原因，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许您为连接 URI 中的 SQL Server 数据库提供用户名密码凭据。 请参阅本主题提供到凭据的替代方法的其余部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]还可以连接到 SQL Server 时使用 Windows 身份验证，才能生成元数据和执行操作，或通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 然后再使用 Windows 身份验证，必须将 Windows 用户添加为 SQL Server Management Studio 中的用户。 有关详细信息，请参阅[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
  有关详细信息，请参阅[SQL Server 和适配器之间的安全](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-biztalk-server"></a>使用 SQL 适配器与 BizTalk Server 的最佳安全方案  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许您为连接 URI 中的 SQL Server 数据库提供用户名密码凭据。  
  
- 当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，输入从 SQL Server 数据库的用户名密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上的发送端口，输入用户名称密码凭据的 SQL Server 数据库从**凭据**选项卡**WCF 自定义传输属性**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收位置，输入用户名称密码凭据的 SQL Server 数据库从**其他**选项卡**WCF 自定义传输属性**对话框。  
  
- 同时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据，配置发送端口，或配置接收端口，还可以使用 Windows 身份验证。 然后再使用 Windows 身份验证，必须将 Windows 用户添加为 SQL Server Management Studio 中的用户。 有关详细信息，请参阅[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
  有关详细信息，请参阅[SQL 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-programming-solutions"></a>使用 SQL 适配器与编程解决方案的最佳安全方案  
  
- 有时需要提供用户名称密码凭据的连接 URI; 中的 SQL Server 数据库但是，如果可能，应避免执行此操作。  
  
- 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，输入从 SQL Server 数据库的用户名密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 在 WCF 通道模型编程中，使用**凭据**属性上设置 SQL Server 数据库的用户名称密码凭据的通道工厂。  
  
- 在 WCF 服务模型编程中，使用**ClientCredentials**设置 SQL Server 数据库的用户名称密码凭据在 WCF 客户端上的属性。  
  
- 如果使用的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发送消息的跨进程边界到另一个服务或客户端，包含敏感的数据库的信息确保这些消息具有足够的安全措施应用以提供足够的数据你的环境中的保护。  
  
- 同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或从.NET 应用程序连接到 SQL Server，也可以使用 Windows 身份验证。 然后再使用 Windows 身份验证，必须将 Windows 用户添加为 SQL Server Management Studio 中的用户。 有关详细信息，请参阅[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
  有关详细信息，请参阅[使用 SQL 适配器的安全编程](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)。 
  
## <a name="security-best-practices-for-hosting-the-sql-adapter-in-iis"></a>承载在 IIS 中的 SQL 适配器的最佳安全方案  
 承载[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 Microsoft Internet 信息服务 (IIS) web 服务公开的操作显示[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]向 Web 客户端。 这些操作可能涉及到通过 Internet 交换敏感数据，因些应采取措施，以帮助确保此数据尽可能安全。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了两个标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级别安全机制。  
  
 您可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
 此外可以开发自定义 HTTP 绑定，以充分利用您的环境提供的其他安全机制。 用于详细了解安全特性[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。 
  
 托管时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为 Web 服务，Web 开发人员应采取的措施来防止直接传递给 SQL Server 数据库中的用户类型中的字符串。 例如，如果网站使用户可以输入一个值，将是 SELECT 语句中的 WHERE 子句的一部分，应扫描输入的字符串以防止将其他命令添加到该语句。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 支持诊断跟踪和消息日志记录。 通过配置文件或使用 Windows Management Instrumentation (WMI) 配置了诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或消息日志记录可以发出敏感信息记录的日志文件，其中它可能会暴露给观察未经授权的用户。  
  
 请按照 WCF 文档中提供的建议，以减少公开通过启用这些功能的潜在安全威胁。 至少，您应遵守以下最佳实践的诊断跟踪和消息日志记录：  
  
- 不要启用"详细"或"信息"在生产环境中的进行跟踪。 这可能会导致性能下降。 但是，必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档了解详细信息。  
  
- 请确保日志文件和配置文件受访问控制列表 (Acl)。  
  
  出现以下警告仅适用于客户端应用程序之间交换的消息和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 由于消息标头的消息操作是，这会显示上调用的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]由客户端。  
  
- 如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换消息的消息标头 （但不是在消息正文） 和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]记录。 由于消息标头的消息操作是，这会显示在客户端调用的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 如果`logEntireMessage`也是`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
  启用诊断跟踪时提高安全性的详细信息，请参阅[安全注意事项和有用提示，用于跟踪](https://msdn.microsoft.com/library/ms733053.aspx)。 有关启用消息日志记录时提高安全性的详细信息，请参阅[消息日志记录的安全问题](https://msdn.microsoft.com/library/ms730318.aspx)。
  
## <a name="see-also"></a>请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)