---
title: 最佳做法来保护 Oracle 数据库适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, best practices for connection between the Oracle Database adapter and the Oracle database
- security, best practices for WCF diagnostic tracing and message logging
- security, best practices for hosting the Oracle Database adapter in IIS
- credentials
- security, best practices
- security
- security, best practices for consuming the Oracle Database adapter with BizTalk Server
- security, protecting sensitive data
- user name password credential
- security, best practices for consuming the Oracle Database adapter with programming solutions
ms.assetid: 689e8442-91c9-4fe0-a0a0-ce5f5a98ab38
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab079e2114eb606ef90e6c40d0857ec8668e1dca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529624"
---
# <a name="best-practices-to-secure-the-oracle-database-adapter"></a>最佳做法来保护 Oracle 数据库适配器
本部分提供了更完整地保护敏感数据，使用或开发使用的应用程序时应遵循的最佳实践[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-database-adapter-and-the-oracle-database"></a>Oracle 数据库适配器和 Oracle 数据库之间的连接的最佳安全方案  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不提供支持，可帮助向它与 Oracle 数据库之间安全通信。 必须提供一种机制来帮助确保充分的适配器和 Oracle 数据库之间交换数据的安全性。  
  
- 为 Oracle 数据库连接 URI 中不提供用户名密码凭据。 请参阅以下替代方法的各节提供到凭据的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还可以连接到 Oracle 数据库时使用 Windows 身份验证，才能生成元数据和执行操作，或通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。  
  
  有关详细信息，请参阅[Oracle 数据库和适配器之间的安全](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)。  
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-biztalk-server"></a>使用 Oracle 数据库适配器与 BizTalk Server 的最佳安全方案  
  
- 为 Oracle 数据库连接 URI 中不提供用户名密码凭据。  
  
- 当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，输入从 Oracle 数据库用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]上的发送端口，用于从 Oracle 数据库输入用户名称密码凭据**凭据**选项卡**配置 WCF 自定义传输**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收位置，输入用户名称密码凭据用于从 Oracle 数据库**其他**选项卡**配置 WCF 自定义传输**对话框。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还可以连接到 Oracle 数据库时使用 Windows 身份验证，才能生成元数据和执行通过操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。  
  
  有关详细信息，请参阅[Oracle 数据库适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-programming-solutions"></a>使用 Oracle 数据库适配器与编程解决方案的最佳安全方案  
  
- 有时需要提供用户名称密码凭据的连接 URI; 中的 Oracle 数据库但是，如果可能，应避免执行此操作。  
  
- 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，输入从 Oracle 数据库用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 在 WCF 通道模型编程中，使用**凭据**属性上设置 Oracle 数据库的用户名称密码凭据的通道工厂。  
  
- 在 WCF 服务模型编程中，使用**ClientCredentials**设置 Oracle 数据库的用户名称密码凭据在 WCF 客户端上的属性。  
  
- 如果使用的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]发送消息的跨进程边界到另一个服务或客户端，包含敏感的数据库的信息确保这些消息具有足够的安全措施应用以提供足够的数据你的环境中的保护。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还可以连接到 Oracle 数据库时使用 Windows 身份验证，才能生成元数据和执行通过操作[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。  
  
  有关详细信息，请参阅[安全使用 Oracle 数据库适配器编程](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)。  
  
## <a name="security-best-practices-for-hosting-the-oracle-database-adapter-in-iis"></a>承载在 IIS 中的 Oracle 数据库适配器的最佳安全方案  
 承载[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Microsoft Internet 信息服务 (IIS) web 服务公开的操作显示[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]向 Web 客户端。 这些操作可能涉及到通过 Internet 交换敏感数据，因些应采取措施，以帮助确保此数据尽可能安全。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了两个标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级别安全机制。  
  
 您可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
 此外可以开发自定义 HTTP 绑定，以充分利用您的环境提供的其他安全机制。 用于详细了解安全特性[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 支持诊断跟踪和消息日志记录。 通过配置文件或使用 Windows Management Instrumentation (WMI) 配置了诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或消息日志记录可以发出敏感信息记录的日志文件，其中它可能会暴露给观察未经授权的用户。  
  
 请按照 WCF 文档中提供的建议，以减少公开通过启用这些功能的潜在安全威胁。 至少，您应遵守以下最佳实践的诊断跟踪和消息日志记录：  
  
- 不要启用"详细"或"信息"在生产环境中的进行跟踪。 这可能会导致性能下降。 但是，必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档了解详细信息。  
  
- 请确保日志文件和配置文件受访问控制列表 (Acl)。  
  
  出现以下警告仅适用于客户端应用程序之间交换的消息和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 由于消息标头的消息操作是，这会显示上调用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由客户端。  
  
- 如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换消息的消息标头 （但不是在消息正文） 和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]记录。 由于消息标头的消息操作是，这会显示在客户端调用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 如果`logEntireMessage`也是`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
  启用诊断跟踪时提高安全性的详细信息，请参阅[安全注意事项和有用提示，用于跟踪](https://msdn.microsoft.com/library/ms733053.aspx)。 有关启用消息日志记录时提高安全性的详细信息，请参阅[消息日志记录的安全问题](https://msdn.microsoft.com/library/ms730318.aspx)。 
  
## <a name="see-also"></a>请参阅  
[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)