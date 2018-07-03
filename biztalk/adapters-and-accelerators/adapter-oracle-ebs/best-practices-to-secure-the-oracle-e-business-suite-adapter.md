---
title: 最佳做法来保护 Oracle E-business Suite 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d492d22-2a1f-4b91-9000-a4d74c6fb2fb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 464670a268d0a320ceb2c83de71d083c915e6809
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990030"
---
# <a name="best-practices-to-secure-the-oracle-e-business-suite-adapter"></a>最佳做法来保护 Oracle E-business Suite 适配器
本部分提供了更完整地保护敏感数据，使用或开发使用的应用程序时应遵循的最佳实践[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-e-business-adapter-and-the-oracle-database"></a>Oracle E-business 适配器和 Oracle 数据库之间的连接的最佳安全方案  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不提供支持，可帮助向它与 Oracle E-business Suite 之间安全通信。 必须提供一种机制来帮助确保充分的适配器和 Oracle 数据库之间交换数据的安全性。  
  
- 为 Oracle 数据库连接 URI 中不提供用户名密码凭据。 请参阅以下替代方法的各节提供到凭据的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可以将连接到 Oracle E-business Suite 时，使用 Windows 身份验证才能生成元数据和执行操作，或通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
  有关详细信息，请参阅[Oracle E-business Suite 和适配器之间的安全](../../adapters-and-accelerators/adapter-oracle-ebs/security-between-oracle-e-business-suite-and-the-adapter.md)。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-biztalk-server"></a>使用 Oracle E-business 适配器与 BizTalk Server 的最佳安全方案  
  
- 应避免提供适用于 Oracle E-business Suite 连接 URI 中的用户名称密码凭据。  
  
- 当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，输入从 Oracle E-business Suite 的用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]上的发送端口，用于从 Oracle 数据库输入用户名称密码凭据**凭据**选项卡**配置 WCF 自定义传输**对话框。  
  
- 当配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收位置，输入用户名称密码凭据用于从 Oracle 数据库**其他**选项卡**配置 WCF 自定义传输**对话框。  
  
- 导出绑定文件中的应用程序从后[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则必须手动删除的值**OraclePassword**从绑定文件中，绑定 （以明文形式提供） 的属性，然后在每个主机上再次指定它其中将使用导出的绑定。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可以将连接到 Oracle E-business Suite 时，使用 Windows 身份验证才能生成元数据和执行操作，或通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
- 如果使用的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发送消息的跨进程边界到另一个服务或客户端，包含敏感的数据库的信息确保这些消息具有足够的安全措施应用以提供足够的数据你的环境中的保护。  
  
  有关详细信息，请参阅[Oracle E-business Suite 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-programming-solutions"></a>使用 Oracle E-business 适配器与编程解决方案的最佳安全方案  
  
- 应避免在连接 URI 中的 Oracle 数据库提供用户名密码凭据。  
  
- 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，输入从 Oracle 数据库用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
- 在 WCF 通道模型编程中，使用**凭据**属性上设置 Oracle 数据库的用户名称密码凭据的通道工厂。  
  
- 在 WCF 服务模型编程中，使用**ClientCredentials**设置 Oracle 数据库的用户名称密码凭据在 WCF 客户端上的属性。  
  
- 如果使用的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]发送消息的跨进程边界到另一个服务或客户端，包含敏感的数据库的信息确保这些消息具有足够的安全措施应用以提供足够的数据你的环境中的保护。  
  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可以将连接到 Oracle E-business Suite 时，使用 Windows 身份验证才能生成元数据和执行操作，或通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 之前使用 Windows 身份验证，必须先执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
  有关详细信息，请参阅[适配器的安全注意事项](../../core/security-considerations-for-adapters.md)。  
  
## <a name="security-best-practices-for-hosting-the-oracle-e-business-adapter-in-iis"></a>承载在 IIS 中的 Oracle E-business 适配器的最佳安全方案  
 承载[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在 Microsoft Internet 信息服务 (IIS) web 服务公开的操作显示[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]向 Web 客户端。 这些操作可能涉及到通过 Internet 交换敏感数据，因些应采取措施，以帮助确保此数据尽可能安全。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供了两个标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级别安全机制。  
  
 您可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
 此外可以开发自定义 HTTP 绑定，以充分利用您的环境提供的其他安全机制。 用于详细了解安全特性[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅"保护服务和客户端"，网址[ http://go.microsoft.com/fwlink/?LinkId=89725 ](http://go.microsoft.com/fwlink/?LinkId=89725)。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 支持诊断跟踪和消息日志记录。 通过配置文件或使用 Windows Management Instrumentation (WMI) 配置了诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或消息日志记录可以发出敏感信息记录的日志文件，其中它可能会暴露给观察未经授权的用户。  
  
 请按照 WCF 文档中提供的建议，以减少公开通过启用这些功能的潜在安全威胁。 至少，您应遵守以下最佳实践的诊断跟踪和消息日志记录：  
  
- 不要启用"详细"或"信息"在生产环境中的进行跟踪。 这可能会导致性能下降。 但是，必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档了解详细信息。  
  
- 请确保日志文件和配置文件受访问控制列表 (Acl)。  
  
  出现以下警告仅适用于客户端应用程序之间交换的消息和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 由于消息标头的消息操作是，这会显示上调用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由客户端。  
  
- 如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换消息的消息标头 （但不是在消息正文） 和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]记录。 由于消息标头的消息操作是，这会显示在客户端调用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 如果`logEntireMessage`也是`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
  启用诊断跟踪时提高安全性的详细信息，请参阅"安全问题和有用提示为跟踪"网址[ http://go.microsoft.com/fwlink/?LinkId=89796 ](http://go.microsoft.com/fwlink/?LinkId=89796)。 启用消息日志记录时提高安全性的详细信息，请参阅"安全问题的消息日志记录"网址[ http://go.microsoft.com/fwlink/?LinkId=89797 ](http://go.microsoft.com/fwlink/?LinkId=89797)。  
  
## <a name="see-also"></a>请参阅  
 [保护 Oracle EBS 应用程序](secure-your-oracle-ebs-applications.md)