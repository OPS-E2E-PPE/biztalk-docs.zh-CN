---
title: SQL 适配器与 BizTalk Server 的安全性 |Microsoft Docs
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
ms.openlocfilehash: 179051a8d9522ca760780c7a7f1060789129724e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367936"
---
# <a name="security-with-the-sql-adapter-and-biztalk-server"></a>SQL 适配器与 BizTalk Server 安全性
配置发送端口或接收端口 （位置） 时使用 BizTalk Server 管理控制台，或者使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要检索的 BizTalk 解决方案的消息架构，必须提供凭据的 SQL Server 数据库。 请务必以安全的方式来帮助防止暴露给潜在的恶意执行组件提供这些凭据。 本主题讨论如何最安全地提供的凭据[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]的 BizTalk Server 解决方案。  
  
 BizTalk 解决方案的上下文中的安全性的更多常规讨论是一个广泛的主题并不在此文档的范围。 有关如何使你的 BizTalk 解决方案更安全的信息，请参阅[安全和保护你的 BizTalk 消息](../../core/secure-and-protect-your-biztalk-messages.md)。
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>在使用时如何保护凭据使用适配器服务的 BizTalk 项目外接程序？  
 当你使用[!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]若要检索的 BizTalk 解决方案的消息架构，必须提供用户名和密码**安全**选项卡上**配置适配器**对话框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]将不允许您设置凭据**配置 URI**字段。 这可以提高安全性，通过防止凭据以明文形式显示。 详细了解如何通过使用检索消息架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，包括如何为 SQL Server 数据库中输入用户名和密码，请参阅[获取 Visual Studio 中使用 SQL 适配器中的SQLServer操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>如何保护凭据时配置发送端口或接收位置？  
 BizTalk 解决方案使用 Microsoft BizTalk Wcf-custom 适配器使用 WCF 服务。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是使客户端能够使用 SQL Server 数据库，就像 WCF 服务的 WCF 自定义绑定。 BizTalk 解决方案使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过发送端口和接收位置配置为使用 Wcf-custom 适配器。 Wcf-custom 适配器，反过来，配置为使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为其传输。 有关如何配置发送端口和接收的端口 （接收位置），包括如何配置 WCF 自定义适配器的详细信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
 配置中的 SQL Server 数据库凭据**凭据**选项卡**Wcf-custom 传输属性**对话框中为发送端口或从**其他**选项卡**Wcf-custom 传输属性**对话框中的接收位置。 由于 WCF 自定义适配器支持企业单一登录 (SSO)，可以选择这些选项卡中的任何一个提供用户名和密码或 SSO 关联应用程序。 以下主题讨论这两个选项。  
  
### <a name="user-name-password-credentials"></a>用户名密码凭据  
 您应仅提供用户名和密码从**凭据**（适用于发送端口） 的选项卡或**其他**选项卡 （用于接收位置） 中**Wcf-custom 传输属性**对话框。 这可确保：  
  
-   你的凭据不会显示在**地址 (URI)** 对话框的字段。 这可以阻止那些有权访问你的屏幕 （或具有权限，使他们能够查看发送端口或接收位置属性） 查看你的凭据。  
  
-   如果导出的发送端口或接收端口绑定，你的密码将不写入到绑定文件中。 这可以防止任何人访问到文件中查看你的密码。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>企业单一登录和 SSO 关联应用程序  
 你可以配置 Wcf-custom 适配器，以便它使用企业单一登录 (SSO) 来获取 SQL Server 数据库的凭据。 SSO 使用数据库和主密钥进行加密和存储用户凭据。 它还提供服务，以将 Microsoft Windows 帐户映射到用于访问后端系统的辅助凭据。 通过使用 SSO，您可以映射到的用户名和密码在 SQL Server 数据库上的 Windows 帐户。  
  
 使用 SSO*关联应用程序*并*SSO 映射*将凭据映射到后端系统。 关联应用程序是指的是一个系统或应用程序需要辅助凭据的 SSO 中的逻辑实体。 SSO 映射是与关联应用程序相关联。 它映射到该帐户用于访问关联系统或应用程序的辅助凭据的 Windows 帐户。 SSO 映射可以与 Windows 用户帐户或组相关联。  
  
 若要使用的 SSO [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，必须执行以下操作。  
  
1.  中用于保存 SQL Server 数据库的名称密码凭据的用户的 SSO 创建关联应用程序。 此步骤通常由具有特殊类型的 SSO 管理权限的人员执行。  
  
2.  创建一个用户或组映射映射到的用户名和密码，以用来建立与 SQL Server 数据库的连接的 Windows 帐户与关联应用程序。 具体取决于您的安装，用户可能能够执行此步骤中，或可能还需要具有特殊类型的 SSO 管理权限的人员。  
  
> [!NOTE]
>  为 SSO 配置时，WCF 自定义适配器将使用提供的 SSO 服务从 SSO 数据库中获取 SQL Server 用户名和密码。 它提供了这些 （未加密的） 到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以便该适配器可以打开与 SQL Server 数据库的连接。 SSO 提供不加密或保护之间的连接[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server 数据库。  
  
 有关如何使用 SSO，包括有关如何创建关联应用程序和 SSO 映射信息的信息，请参阅[使用 SSO](../../core/using-sso.md)。 有关 SSO 的详细信息，请参阅[实现企业单一登录](../../core/implementing-enterprise-single-sign-on.md)。
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri 绑定属性  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持**AcceptCredentialsInUri**属性绑定。 在连接 URI 中永远不会允许凭据。  
  
## <a name="see-also"></a>请参阅  
[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)