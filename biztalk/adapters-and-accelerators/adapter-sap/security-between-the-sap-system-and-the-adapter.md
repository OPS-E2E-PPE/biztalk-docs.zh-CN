---
title: SAP 系统和适配器之间的安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca967a375e1d64a7e3f720648fb7eb8ceede98b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372893"
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>SAP 系统和适配器之间的安全性
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持以帮助其与 SAP 服务器之间安全通信的 SAP 安全网络通信 (SNC) 或用户名称密码凭据。 用户名密码凭据仅提供到 SAP 系统; 连接的身份验证它们不提供任何安全性上通过连接交换的数据。 不能同时使用 SNC 和用户名称密码凭据。  
  
## <a name="sap-secure-network-communications"></a>SAP 安全网络通信  
 安全网络通信 (SNC) 是可帮助提供有关 SAP 客户端和 SAP 应用程序服务器之间交换的数据的应用程序级安全，SAP 系统体系结构中的软件层。  
  
 SNC 提供以下优势：  
  
- SNC 面向应用程序级的、 端到端的安全。 SNC 有助于保护两个 SNC 受保护的组件 （例如，之间 SAPgui 和 SAP 系统应用程序服务器） 之间的所有通信。  
  
- 您可以实现 SAP 系统不直接提供 （如单一登录或将智能卡进行身份验证） 的其他安全功能。  
  
- 您可以自定义 SNC 实现。 可以使用所选的安全产品，并选择你想要使用的算法。  
  
- 您可以在任何时候更改安全产品，而不会影响 SAP 系统的业务应用程序。  
  
  若要使用 SNC，必须配置 SAP 服务器和运行的客户端[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 在 SAP 服务器上配置安全网络通信 (SNC)。 请参阅 SAP 文档有关的指南。  
  
- SAP 客户端 Dll 的计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装，您还必须拥有 SNC 相关 Dll 的。 有关这些 Dll 的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)][必备软件](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)。  
  
- 若要配置适配器以使用 SNC，必须在 SAP 连接 URI 设置 UseSnc 参数。 有关 SAP 连接 URI 的详细信息，请参阅[配置的 SAP 适配器的连接 URI](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)。 此外，必须设置**SncLibrary**并**必须提供 SncPartnerName**绑定属性。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
## <a name="user-name-password-credentials"></a>用户名密码凭据  
 你可以提供给适配器的连接 URI 中的用户名称密码凭据。 适配器使用这些凭据时打开的连接上的 SAP 系统的用户进行身份验证。 这些凭据提供到 SAP 系统; 连接的身份验证的级别但是，它们不提供消息级或传输级身份验证 （或授权） 的数据通过网络传输。  
  
 出于此原因，必须提供一种安全机制来帮助确保适当的授权、 身份验证、 数据隐私和数据适配器与 SAP 系统之间交换的数据完整性级别。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面**AcceptCredentialsInUri**属性绑定。 此属性确定是否在连接 URI 中允许 SAP 系统凭据。 默认情况下**AcceptCredentialsInUri**为 false 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]如果凭据包含在 URI 中将引发异常。 有关详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 帮助提供更高的安全性网络上的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。  
  
 以明文形式的连接 URI 中指定的用户名和密码。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供了多种方法，通过它可以更安全地提供这些凭据。  
  
-   有关如何更安全地提供 BizTalk 解决方案中的 SAP 系统凭据的信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。  
  
-   有关如何更安全地提供编程解决方案中的 SAP 系统凭据的信息，请参阅[使用 SAP 适配器的安全编程](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)。  
  
## <a name="security-concerns-for-inbound-scenarios"></a>入站方案的安全问题  
 有权访问 SAP 程序 ID 的任何侦听器可能会接收所有 SAP 项目 （Rfc、 Idoc 和 Trfc） 发送到该程序 id。 如果多个侦听器已注册到的程序 ID，SAP 将随机分配到的侦听器之一到达该程序 ID 的项目。 因此，应，保证你想要使用特定的程序 ID 接收消息的侦听器有权访问该程序 id。 此外，因为 SAP 随机将项目发送到侦听器附加到程序 ID，它是最佳做法将程序 Id 专用于一个侦听器。  
  
## <a name="see-also"></a>请参阅  
[最佳做法来保护 SAP 适配器](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)