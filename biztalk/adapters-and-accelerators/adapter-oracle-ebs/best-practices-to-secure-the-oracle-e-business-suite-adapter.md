---
title: "最佳做法来保护 Oracle E-business Suite 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d492d22-2a1f-4b91-9000-a4d74c6fb2fb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd530d653f1fb5403d1632d94ed688ad7ca8a3b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-oracle-e-business-suite-adapter"></a>最佳做法来保护 Oracle E-business Suite 适配器
本部分提供了你应遵循的更完整地保护敏感数据，当你使用或开发的应用程序使用的最佳做法[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-e-business-adapter-and-the-oracle-database"></a>Oracle E-business 适配器和 Oracle 数据库之间的连接的最佳安全方案  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]未提供对它与 Oracle E-business Suite 之间安全通信帮助支持。 必须提供一种机制来帮助确保足够的适配器和 Oracle 数据库之间交换的数据的安全级别。  
  
-   连接 URI 中的 Oracle 数据库不提供用户名密码凭据。 请参阅以下替代方法的各节提供凭据的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可用于在将连接到 Oracle E-business Suite 时使用 Windows 身份验证才能生成元数据和执行操作，不论是通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 使用 Windows 身份验证之前, 必须执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
 有关详细信息，请参阅[Oracle E-business Suite 和适配器之间的安全性](../../adapters-and-accelerators/adapter-oracle-ebs/security-between-oracle-e-business-suite-and-the-adapter.md)。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-biztalk-server"></a>使用 BizTalk Server 的 Oracle E-business 适配器的最佳安全方案  
  
-   应避免提供为 Oracle E-business Suite 连接 URI 中的用户名密码凭据。  
  
-   当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，输入从 Oracle E-business Suite 的用户名称密码凭据**安全**选项卡**配置适配器**对话框。  
  
-   当你配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]上发送端口，输入用户名密码凭据用于从 Oracle 数据库**凭据**选项卡**配置 WCF 自定义传输**对话框。  
  
-   当你配置的 BizTalk WCF 自定义适配器[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]上接收位置，输入用户名密码凭据用于从 Oracle 数据库**其他**选项卡**配置 WCF 自定义传输**对话框。  
  
-   导出绑定文件中的应用程序从后[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须手动删除的值**OraclePassword**从绑定文件中，绑定属性 （以明文形式可用），然后在每个主机上再次指定它其中将使用导出的绑定。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可用于在将连接到 Oracle E-business Suite 时使用 Windows 身份验证才能生成元数据和执行操作，不论是通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 使用 Windows 身份验证之前, 必须执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
-   如果应用程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]跨进程边界到另一个服务或客户端，包含敏感的数据库信息的发送消息确保这些消息具有足够的安全措施提供足够的数据你的环境中的保护。  
  
 有关详细信息，请参阅[安全性与 Oracle E-business Suite 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)。  
  
## <a name="security-best-practices-for-consuming-the-oracle-e-business-adapter-with-programming-solutions"></a>使用编程解决方案的 Oracle E-business 适配器的最佳安全方案  
  
-   应避免连接 URI 中的 Oracle 数据库提供用户名密码凭据。  
  
-   当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，输入用于从 Oracle 数据库的用户名密码凭据**安全**选项卡**配置适配器**对话框。  
  
-   在 WCF 通道模型编程中，使用**凭据**属性用于设置 Oracle 数据库的用户名称密码凭据的通道工厂。  
  
-   在 WCF 服务模型编程中，使用**ClientCredentials**上 WCF 客户端，以设置用于 Oracle 数据库用户名密码凭据的属性。  
  
-   如果应用程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]跨进程边界到另一个服务或客户端，包含敏感的数据库信息的发送消息确保这些消息具有足够的安全措施提供足够的数据你的环境中的保护。  
  
-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还可用于在将连接到 Oracle E-business Suite 时使用 Windows 身份验证才能生成元数据和执行操作，不论是通过[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 使用 Windows 身份验证之前, 必须执行中列出的步骤[连接到使用 Windows 身份验证的 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。  
  
 有关详细信息，请参阅[适配器的安全注意事项](../../core/security-considerations-for-adapters.md)。  
  
## <a name="security-best-practices-for-hosting-the-oracle-e-business-adapter-in-iis"></a>承载在 IIS 中的 Oracle E-business 适配器的最佳安全方案  
 承载[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在 Microsoft Internet 信息服务 (IIS) 作为 Web 服务公开操作显示[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Web 客户端。 这些操作可能会涉及到通过 Internet，交换敏感数据，因此你应采取措施以帮助确保此数据尽可能安全。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供以下两种标准 HTTP 传输绑定： **BasicHttpBinding**基本 HTTP 传输提供不存在任何安全机制; **WSHttpBinding**支持这两个传输级别和消息级安全机制。  
  
 你可以使用**BasicHttpBinding**通过 HTTPS 连接或使用**WSHttpBinding**来帮助保护你的数据。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]来生成 LOB 项目的 WCF 服务。 此向导仅支持使用**BasicHttpBinding**。  
  
 您还可以开发自定义的 HTTP 绑定，以便利用你的环境提供的其他安全机制。 有关安全性的详细信息功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供，请参阅"保护服务和客户端"，网址[http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725)。  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>WCF 诊断跟踪和消息日志记录的最佳安全方案  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]支持诊断跟踪和消息日志记录。 通过配置文件或通过使用 Windows Management Instrumentation (WMI)，请配置诊断跟踪和消息日志记录。 根据你设置的配置选项[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪或日志记录可以发出要记录的敏感信息的消息文件，其中它可能会暴露给观察未经授权的用户。  
  
 请遵循 WCF 文档中提供的建议，以缓解公开通过启用这些功能的潜在安全威胁。 至少，你应遵守以下最佳做法诊断跟踪和消息日志记录：  
  
-   不要启用"详细"或在生产环境中的"信息"跟踪。 这可能会导致性能下降。 但是，你必须启用"警告"，并在生产环境中的"错误"跟踪。 如果启用跟踪时，你必须采取适当的安全措施来保护你的数据。 请参阅 WCF 文档以了解更多信息。  
  
-   确保日志文件和配置文件受访问控制列表 (Acl)。  
  
 以下警告尤其适用于在客户端应用程序之间交换的消息和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]诊断跟踪可以记录交换的消息的标头 （但不是正文） 与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 由于消息标头中的消息操作，这将显示上调用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]客户端。  
  
-   如果[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]启用消息日志记录和`logMessagesAtServiceLevel`是`true`，适配器客户端之间交换的消息的消息标头 （但不是消息正文） 和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]记录。 由于消息标头中的消息操作，这将显示客户端调用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 如果`logEntireMessage`也`true`，将记录消息正文。 这可能会显示敏感数据库信息。  
  
 有关提高安全性，当你启用诊断跟踪的详细信息，请参阅"安全问题和有用提示为跟踪"网址[http://go.microsoft.com/fwlink/?LinkId=89796](http://go.microsoft.com/fwlink/?LinkId=89796)。 有关提高安全性，当你启用消息日志记录的详细信息，请参阅"安全问题的消息日志记录"在[http://go.microsoft.com/fwlink/?LinkId=89797](http://go.microsoft.com/fwlink/?LinkId=89797)。  
  
## <a name="see-also"></a>另请参阅  
 [保护 Oracle EBS 应用程序](secure-your-oracle-ebs-applications.md)