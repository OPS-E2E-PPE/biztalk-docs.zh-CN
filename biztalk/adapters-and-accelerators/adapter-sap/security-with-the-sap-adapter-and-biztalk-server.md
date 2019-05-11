---
title: SAP 适配器与 BizTalk Server 的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials, protecting
- Enterprise Single Sign-On
- security, when using BizTalk Server
- security, protecting credentials
- SSO
ms.assetid: 702cd0f9-d8e1-4dad-8774-b552481d5390
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f7f35328c48b473fbdb571a937c6d9507f0800d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372888"
---
# <a name="security-with-the-sap-adapter-and-biztalk-server"></a>SAP 适配器与 BizTalk Server 安全性
配置发送端口或接收端口 （位置） 时使用 BizTalk Server 管理控制台，或者使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要检索的 BizTalk 解决方案的消息架构，必须提供凭据的 SAP 系统。 请务必以安全的方式来帮助防止暴露给潜在的恶意执行组件提供这些凭据。 本主题讨论如何最安全地提供的凭据[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]的 BizTalk Server 解决方案。  
  
 BizTalk 解决方案的上下文中的安全性的更多常规讨论是一个广泛的主题并不在此文档的范围。 有关如何使你的 BizTalk 解决方案更安全的信息，请参阅[安全和保护你的 BizTalk 消息](../../core/secure-and-protect-your-biztalk-messages.md)。  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>在使用时如何保护凭据使用适配器服务的 BizTalk 项目外接程序？  
 当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要检索的 BizTalk 解决方案的消息架构，必须提供用户名和密码为 SAP 系统。 您应仅执行此操作从**安全**选项卡上**配置适配器**对话框。 这可确保你的凭据将不显示在**Uri**字段[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]对话框中，有权访问您的计算机屏幕的任何人都可以读取。 详细了解如何通过使用检索消息架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，包括如何为 SAP 系统中输入用户名和密码，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>如何保护凭据时配置发送端口或接收位置？  
 BizTalk 解决方案使用 Microsoft BizTalk Wcf-custom 适配器使用 WCF 服务。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是使客户端能够使用 SAP 系统，就像 WCF 服务的 WCF 自定义绑定。 BizTalk 解决方案占用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过发送端口和接收位置配置为使用 Wcf-custom 适配器，这反过来，，配置为使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为其传输。 有关如何配置发送端口和接收的端口 （接收位置），包括如何配置 WCF 自定义适配器的详细信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。  
  
 配置中的 SAP 系统凭据**凭据**选项卡**Wcf-custom 传输属性**对话框中为发送端口或从**其他**选项卡**WCF 自定义传输属性**对话框中的接收位置。 由于 WCF 自定义适配器支持企业单一登录 (SSO)，您可以选择这些选项卡中的任何一个提供用户名和密码或 SSO 关联应用程序。 以下主题讨论这两个选项。  
  
### <a name="user-name-password-credentials"></a>用户名密码凭据  
 您应仅提供用户名和密码从**凭据**（适用于发送端口） 的选项卡或**其他**选项卡 （用于接收位置） 中**Wcf-custom 传输属性**对话框。 这可确保：  
  
-   你的凭据不会显示在**Uri**对话框的字段。 这可以阻止那些有权访问你的屏幕 （或具有权限，使他们能够查看发送端口或接收位置属性） 查看你的凭据。  
  
-   如果导出的发送端口或接收端口绑定，你的密码将不写入到绑定文件中。 这可以防止任何人从访问到文件中查看你的密码。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>企业单一登录和 SSO 关联应用程序  
 可以配置 Wcf-custom 适配器使用 SSO 来获取 SAP 系统的凭据。 SSO 使用数据库和主密钥进行加密和存储用户凭据。 它还提供服务，以将 Microsoft Windows 帐户映射到用于访问后端系统的辅助凭据。 通过使用 SSO，但可以映射到的用户名和密码在 SAP 系统上的 Windows 帐户。  
  
 使用 SSO*关联应用程序*并*SSO 映射*将凭据映射到后端系统。 关联应用程序是指的是一个系统或应用程序需要辅助凭据的 SSO 中的逻辑实体。 SSO 映射是与关联应用程序相关联。 它映射到该帐户用于访问关联系统或应用程序的辅助凭据的 Windows 帐户。 SSO 映射可以与 Windows 用户帐户或组相关联。  
  
 若要使用的 SSO [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，必须执行以下操作。  
  
1.  中用于保存 SAP 系统的密码凭据的用户的 SSO 创建关联应用程序。 此步骤通常由具有特殊类型的 SSO 管理权限的人员执行。  
  
2.  创建一个用户或组映射映射到的用户名称的 Windows 帐户的关联应用程序和用于建立与 SAP 系统的连接的密码。 具体取决于您的安装，用户可能无法执行此步骤是或可能还需要具有特殊类型的 SSO 管理权限的人员。  
  
> [!NOTE]
>  为 SSO 配置时，WCF 自定义适配器将使用提供的 SSO 服务从 SSO 数据库中获取 SAP 用户名和密码。 它提供了这些 （未加密的） 到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，以便该适配器可以打开与 SAP 系统的连接。 SSO 提供不加密或保护之间的连接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和 SAP 系统。  
  
 有关如何使用 SSO，包括有关如何创建关联应用程序和 SSO 映射信息的信息，请参阅[使用 SSO](../../core/using-sso.md)。 有关 SSO 的详细信息，请参阅[实现企业单一登录](../../core/implementing-enterprise-single-sign-on.md)。  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri 绑定属性  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面**AcceptCredentialsInUri**属性绑定。 此属性确定是否在连接 URI 中允许 SAP 系统凭据。 默认情况下**AcceptCredentialsInUri**是**false**和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]如果凭据包含在 URI 中将引发异常。  
  
 因为需要凭据以连接 URI 中存在某些编程方案提供此属性。 这应该永远不会是这种情况，在配置发送端口或接收位置，或使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]来检索从消息架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 在这种情况下，建议不要设置**AcceptCredentialsInUri**到**true**。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for ORacle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 **AcceptCredentialsInUri**绑定属性中不可用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中**绑定**选项卡配置 WCF 自定义或 WCF SAP 时接收或发送端口。 若要设置的值**AcceptCredentialsInUri**绑定属性，必须打开后已生成元数据中使用创建的适配器的绑定文件 （XML 文件） [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，然后找到在此绑定属性该文件。 指定此绑定属性的适当的值和保存绑定文件，然后导入绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)有关的说明。  
  
## <a name="see-also"></a>请参阅  
[最佳做法来保护 SAP 适配器](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
 [保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   