---
title: "SAP 系统和适配器之间的安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1c0e37662b9c554d05b73ecf234da4b2ee547fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>SAP 系统和适配器之间的安全性
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持以帮助与 SAP 服务器之间的安全通信的 SAP 安全网络通信 (SNC) 或用户名称密码凭据。 用户名密码凭据仅提供用于连接到 SAP 系统中; 的授权它们不提供任何安全交换通过连接的数据。 不能同时使用 SNC 和用户名称密码凭据。  
  
## <a name="sap-secure-network-communications"></a>SAP 安全网络通信  
 安全网络通信 (SNC) 是可以帮助提供有关 SAP 客户端和 SAP 应用程序服务器之间交换的数据的应用程序级安全的 SAP 系统体系结构中的软件层。  
  
 SNC 提供以下优点：  
  
-   SNC 面向应用程序级别、 端到端安全。 SNC 可帮助保护 （例如，之间 SAPgui 和 SAP 系统应用程序服务器） 的两个 SNC 保护组件之间的所有通信。  
  
-   你可以实现 SAP 系统不直接提供 （如上单一登录或将智能卡用于身份验证） 的更多安全功能。  
  
-   你可以自定义 SNC 实现。 你可以使用所选的安全产品并选择你想要使用的算法。  
  
-   你可以随时更改安全产品，而不会影响 SAP 系统业务应用程序。  
  
 若要使用 SNC，必须配置 SAP 服务器和运行的客户端[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   SAP 服务器上配置安全网络通信 (SNC)。 请参阅 SAP 文档获取指导。  
  
-   上的计算机具有 SAP 客户端 Dll 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装，你还必须拥有 SNC 相关 Dll 的。 有关这些 Dll 的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)][软件必备项](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)。  
  
-   若要配置适配器后，以使用 SNC，必须在 SAP 连接 URI 中设置 UseSnc 参数。 有关 SAP 连接 URI 的详细信息，请参阅[配置 SAP 适配器的连接 URI](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)。 此外，你必须设置**SncLibrary**和**SncPartnerName**绑定属性。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
## <a name="user-name-password-credentials"></a>用户名密码凭据  
 你可以提供用户名凭据密码到中连接 URI 的适配器。 适配器使用这些凭据时将打开的连接，SAP 系统上的用户进行身份验证。 这些凭据提供的用于连接到 SAP 系统，则为授权级别但是，它们不提供消息级或传输级身份验证 （或授权） 的数据通过网络传输。  
  
 为此，你必须提供一种安全机制，以帮助确保适当的授权、 身份验证、 保护数据隐私和数据适配器和 SAP 系统之间的交换的数据完整性级别。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面**AcceptCredentialsInUri**绑定属性。 此属性确定是否允许连接 URI 中使用 SAP 系统凭据。 默认情况下， **AcceptCredentialsInUri**为 false 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]URI 中包括凭据时引发异常。 有关详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 帮助提供更高的安全性跨网络的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准的保护通过 Internet 协议 (IP) 网络的通信框架。  
  
 用户名和密码以明文形式连接 URI 中指定。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供多种方法，通过它你可以更安全地提供这些凭据。  
  
-   有关如何更安全地提供 BizTalk 解决方案中的 SAP 系统凭据的信息，请参阅[安全性与 SAP 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。  
  
-   有关如何更安全地提供编程解决方案中的 SAP 系统凭据的信息，请参阅[SAP 适配器使用的安全编程](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)。  
  
## <a name="security-concerns-for-inbound-scenarios"></a>入站方案的安全问题  
 有权访问 SAP 程序 ID 的任何侦听器可能接收所有 SAP 项目 （Rfc、 Idoc 和 tRFCs） 发送到该程序 id。 如果多个侦听器已注册到的程序 ID，SAP 将随机分配到一个侦听器到达该程序 ID 的项目。 因此，应，确保你想要通过使用特定的程序 ID 接收消息的侦听器有权访问该程序 id。 此外，由于 SAP 随机向附加到程序 ID 的侦听器发送项目，它是一种最佳做法，需将程序 Id 专用于一个侦听器。  
  
## <a name="see-also"></a>另请参阅  
[最佳做法来保护 SAP 适配器](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[保护你的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)