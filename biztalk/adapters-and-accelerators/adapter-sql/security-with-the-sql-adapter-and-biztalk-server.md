---
title: 使用 SQL 适配器和 BizTalk Server 的安全 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc439d65-1d7e-4e6e-bb0d-a8cb9f0607b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0bc410a651c179daf43c47fb573d1772f6c1e01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225773"
---
# <a name="security-with-the-sql-adapter-and-biztalk-server"></a>使用 SQL 适配器和 BizTalk Server 的安全
配置发送端口或接收端口 （位置） 时使用 BizTalk Server 管理控制台或使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要检索 BizTalk 解决方案的消息架构，你必须提供凭据的 SQL Server 数据库。 请务必在一个安全的方法，可帮助防止它们被暴露给潜在的恶意 actors 中提供这些凭据。 本主题讨论如何最安全地提供的凭据[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]BizTalk Server 解决方案。  
  
 BizTalk 解决方案的上下文中的安全的更多常规讨论是广泛的主题，以及不在本文档的范围。 有关如何使 BizTalk 解决方案更安全的信息，请参阅[安全和保护 BizTalk 消息](../../core/secure-and-protect-your-biztalk-messages.md)。
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>当我使用时如何保护凭据使用适配器服务 BizTalk Project 外接程序？  
 当你使用[!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]要检索 BizTalk 解决方案的消息架构，您必须提供用户名和密码从**安全**选项卡上**配置适配器**对话框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]不允许你在中设置凭据**配置 URI**字段。 这提高了安全性防止凭据以明文形式出现。 有关如何通过使用来检索消息架构的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，包括如何输入 SQL Server 数据库的用户名和密码，请参阅[为使用 SQL 适配器的VisualStudio中的SQLServer操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>如何保护凭据时配置发送端口或接收位置？  
 BizTalk 解决方案使用 Microsoft BizTalk WCF 自定义适配器来使用 WCF 服务。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是使客户端能够使用 SQL Server 数据库，就像它是 WCF 服务的 WCF 自定义绑定。 BizTalk 解决方案使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过发送端口和接收配置为使用 WCF 自定义适配器的位置。 WCF 自定义适配器，反过来，配置为使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用作其传输方式。 有关如何配置发送端口和接收的端口 （接收位置），包括如何配置 WCF 自定义适配器的详细信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
 配置中的 SQL Server 数据库凭据**凭据**选项卡**WCF 自定义传输属性**对话框发送端口或从**其他**选项卡**WCF 自定义传输属性**对话框接收位置。 WCF 自定义适配器支持企业单一登录 (SSO)，因为你还可以选择这些选项卡中的任何一个提供用户名和密码或 SSO 关联应用程序。 以下主题讨论这两个选项。  
  
### <a name="user-name-password-credentials"></a>用户名密码凭据  
 你应仅提供用户名和密码从**凭据**选项卡 （对于发送端口） 或**其他**选项卡 （用于接收位置） 中**WCF 自定义传输属性**对话框。 这可确保以下项：  
  
-   你的凭据将不会显示在**地址 (URI)** 对话框中的字段。 这可以阻止有权访问你的屏幕 （或具有权限，使他们能够查看发送端口或接收位置属性） 的那些看到你的凭据。  
  
-   如果导出发送端口或接收端口绑定，你的密码将不写入到绑定文件中。 这可以防止任何人都具有访问权限到文件查看你的密码。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>企业单一登录和 SSO Affiliate 应用程序  
 你可以配置 WCF 自定义适配器，以便它使用企业单一登录 (SSO) 来获取凭据的 SQL Server 数据库。 SSO 使用数据库和主密钥进行加密和存储用户凭据。 它还提供服务，以 Microsoft Windows 帐户映射到用于访问后端系统的辅助凭据。 通过使用 SSO，你可以映射到的用户名和密码在 SQL Server 数据库上的 Windows 帐户。  
  
 SSO 使用*affiliate 应用程序*和*SSO 映射*映射到后端系统的凭据。 关联应用程序是指系统或需要辅助凭据的应用程序的 sso 的逻辑实体。 SSO 映射是与关联应用程序相关联。 它映射到该帐户用于访问关联系统或应用程序的辅助凭据的 Windows 帐户。 SSO 映射可以与 Windows 用户帐户或与组相关联。  
  
 若要使用具有 SSO [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须执行以下操作。  
  
1.  在 SSO 来保留 SQL Server 数据库的名称密码凭据的用户中创建关联应用程序。 通常由拥有 SSO 管理权限的特殊类型执行此步骤。  
  
2.  创建一个用户或组映射的关联应用程序将你的 Windows 帐户映射到的用户名称和用于建立与 SQL Server 数据库的连接的密码。 具体取决于你的安装，用户可能能够执行此步骤中，或它可能需要具有特殊类型的 SSO 管理权限的人员。  
  
> [!NOTE]
>  为 SSO 配置时，WCF 自定义适配器使用提供的 SSO 服务从 SSO 数据库中获取的 SQL Server 用户名和密码。 它提供了这些 （未加密的） 到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以便该适配器可以打开与 SQL Server 数据库的连接。 SSO 跨之间的连接提供任何加密或保护[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server 数据库。  
  
 有关如何使用 SSO，包括有关如何创建关联应用程序和 SSO 映射信息的信息请参阅[使用 SSO](../../core/using-sso.md)。 有关 SSO 的更多常规信息，请参阅[实现 Enterprise 上单一登录](../../core/implementing-enterprise-single-sign-on.md)。
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri 绑定属性  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持**AcceptCredentialsInUri**绑定属性。 在连接 URI 中永远不会允许凭据。  
  
## <a name="see-also"></a>另请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)