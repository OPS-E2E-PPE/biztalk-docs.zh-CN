---
title: "将证书安装适用于这些 WCF 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tools, Certificates Management Console
- certificates, installing [WCF adapters]
- certificates, Certificates Management Console
- certificates, WCF adapters
- WCF adapters, send locations
- receive locations, WCF adapters
- send locations, WCF adapters
- WCF adapters, receive locations
- WCF adapters, certificates
ms.assetid: 04dc065f-a6e8-4359-8696-2a3de24d531d
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 654e5300c253bbf4cede2113c9282b6a2f02862c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-certificates-for-the-wcf-adapters"></a>安装 WCF 适配器的证书
WCF 适配器可以利用公钥基础结构 (PKI) 数字证书来进行消息加密和解密、消息签名和验证（不可否认性）以及客户端验证。 本主题介绍将数字证书用于 WCF 适配器的不同证书使用方案和配置选项准则。  
  
## <a name="certificate-usage-scenarios-for-the-wcf-receive-locations"></a>WCF 接收位置的证书使用方案  
 下表显示如何安装 WCF 接收位置的证书。  
  
|证书使用|用户上下文|证书存储位置|证书类型|安装证书的时间|  
|-----------------------|------------------|--------------------------------|----------------------|--------------------------------------|  
|解密和签名取决于接收位置的安全设置。|与接收处理程序关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载接收位置，如每个主机实例的服务帐户，并导入到的服务证书**当前用户 \ 个人 （我）**存储。|私人证书|指定的值**服务证书的指纹**下列配置中的属性：<br /><br /> -**安全模式**WCF BasicHttp 属性接收位置设置为**消息**。<br />-**传输客户端凭据类型**WCF BasicHttp 属性接收位置设置为**证书**为**TransportCredentialOnly**安全模式。<br />-**消息客户端凭据类型**WCF WSHttp 属性接收位置设置为**无**，**证书**，或**用户名**有关**消息**安全模式。<br />-**传输客户端凭据类型**WCF NetTcp 属性接收位置设置为**无**或**证书**为**传输**安全模式。<br />-**消息客户端凭据类型**WCF NetTcp 属性接收位置设置为**无**，**用户名**，或**证书**有关**消息**安全模式。<br />-**消息客户端凭据类型**WCF NetTcp 属性接收位置设置为**Windows**，**用户名**，或**证书**为**TransportWithMessageCredential**安全模式。<br />-**安全模式**WCF NetMsmq 属性设置为**消息**或**同时**。|  
|客户端身份验证|N/A|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载接收位置为管理员，并导入 CA 证书链，客户端 X.509 证书到计算机的受信任根证书颁发机构证书存储区因此可以向此身份验证客户端接收位置。|客户端 X.509 证书的 CA 证书链|将客户端 X.509 证书的 CA 证书链安装到下列配置中的“受信任的根证书颁发机构”证书存储中。<br /><br /> -**消息客户端凭据类型**或**传输客户端凭据类型**WCF BasicHttp 属性接收位置设置为**证书**。<br />-**消息客户端凭据类型**或**传输客户端凭据类型**WCF WSHttp 属性接收位置设置为**证书**。<br />-**消息客户端凭据类型**或**传输客户端凭据类型**WCF NetTcp 属性接收位置设置为**证书**。<br />-**消息客户端凭据类型**或**MSMQ 身份验证模式**WCF NetMsmq 属性接收位置设置为**证书**。|  
  
> [!NOTE]
>  由于标准 WCF 收到适配器使用[ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)模式下，若要验证客户端证书，必须安装客户端 X.509 证书的 CA 证书链。 你可以使用 WCF 自定义或 WCF CustomIsolated 适配器 cange 到此默认行为。  
  
> [!NOTE]
>  对于独立的 WCF 接收适配器，您需要在独立主机实例和相应应用程序池之间匹配用户帐户。 有关 BizTalk 隔离主机的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
> [!NOTE]
>  WCF 自定义和 WCF CustomIsolated 接收位置、 用户上下文、 证书存储位置，并且要安装证书的证书类型而异**serviceCredentials**和**clientCredentials**行为元素设置。  
  
> [!NOTE]
>  如果接收位置使用的证书元素**终结点标识**属性，你还必须将已发布的服务标识的证书安装到中指定的证书存储区**终结点标识**属性。  
  
> [!NOTE]
>  除了使用主机实例服务帐户或管理员帐户登录到该计算机外，您还可使用适当的帐户通过“Run As”命令执行相同的操作。  
  
## <a name="certificate-usage-scenarios-for-the-wcf-send-ports"></a>WCF 发送端口的证书使用方案  
 下表显示如何安装 WCF 发送端口的证书。  
  
|证书使用|用户上下文|证书存储位置|证书类型|安装证书的时间|  
|-----------------------|------------------|--------------------------------|----------------------|--------------------------------------|  
|客户端身份验证|与发送端口相关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载发送端口，如每个主机实例的服务帐户，并导入到的客户端证书**当前用户 \ 个人 （我）**存储。|私人证书|指定的值**客户端证书的指纹**下列配置中的属性：<br /><br /> -**消息客户端凭据类型**或**传输客户端凭据类型**WCF BasicHttp 发送端口属性设置为**证书**。<br />-**消息客户端凭据类型**或**传输客户端凭据类型**WCF WSHttp 发送端口属性设置为**证书**。<br />-**消息客户端凭据类型**或**传输客户端凭据类型**WCF NetTcp 发送端口属性设置为**证书**。<br />-**消息客户端凭据类型**或**MSMQ 身份验证模式**WCF NetMsmq 发送端口属性设置为**证书**。|  
|服务验证、签名验证和加密取决于发送端口的安全设置|N/A|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载作为管理员，发送端口并导入到的服务证书**本地计算机 \ （通讯簿） 的其他人员**存储。 您还必须将服务证书的 CA 证书链安装到该计算机的“受信任的根证书颁发机构”证书存储中。|服务的公共证书<br />的服务证书 CA 证书链|指定的值**服务证书的指纹**下列配置中的属性：<br /><br /> -**消息客户端凭据类型**或**传输客户端凭据类型**WCF BasicHttp 发送端口属性设置为**证书**。<br />-**消息客户端凭据类型**WCF WSHttp 发送端口属性设置为**无**，**用户名**，或**证书**时**协商服务凭据**选项处于未选中状态。<br />-**安全模式**WCF NetMsmq 发送端口设置为**消息**或**同时**。|  
|服务验证、签名验证和加密取决于发送端口的安全设置|N/A|以管理员身份登录到将作为发送端口宿主的运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的每台计算机，将客户端 X.509 证书的 CA 证书链导入到该计算机的“受信任的根证书颁发机构”证书存储中，以便向此发送端口验证服务。|服务证书的 CA 证书链|如果你未显式指定的服务证书**服务证书的指纹**属性，安装 CA 证书链中的服务 X.509 证书向受信任的根证书颁发机构证书证书存储中的以下配置：<br /><br /> -**安全模式**WCF BasicHttp 发送端口设置为**传输**或**TransportWithMessageCredential**。<br />-**安全模式**WCF WSHttp 发送端口设置为**传输**或**TransportWithMessageCredential**。<br />-**安全模式**WCF NetTcp 发送端口设置为**TransportWithMessageCredential**。<br />-**传输客户端凭据类型**WCF NetTcp 发送端口属性设置为**无**或**证书**。<br />-**消息客户端凭据类型**WCF NetTcp 发送端口属性设置为**无**，**用户名**，或**证书**。|  
  
> [!NOTE]
>  因为标准 WCF 发送适配器使用[ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)模式下，若要验证服务证书，必须安装的服务 X.509 证书的 CA 证书链。 您可使用 WCF-Custom 或 WCF-CustomIsolated 适配器来更改此默认行为。  
  
> [!NOTE]
>  WCF 自定义和 WCF CustomIsolated 发送端口、 用户上下文、 证书存储位置和要安装证书的证书类型而异**serviceCredentials**和**clientCredentials**行为元素设置。  
  
> [!NOTE]
>  如果发送端口使用的证书元素**终结点标识**属性，你还必须将正确的服务标识的证书安装到中指定的证书存储区**终结点标识**属性。  
  
> [!NOTE]
>  除了使用主机实例服务帐户或管理员帐户登录到该计算机外，您还可使用适当的帐户通过“Run As”命令执行相同的操作。  
  
## <a name="displaying-the-certificates-management-console"></a>显示证书管理控制台  
 若要显示“本地计算机”和“当前用户”的“证书管理控制台”界面，请按下列步骤操作：  
  
1.  单击**启动**，单击**运行**，类型**MMC**，然后单击**确定**以打开 Microsoft 管理控制台。  
  
2.  上**文件**菜单上，单击**添加/删除管理单元中**以显示**添加/删除管理单元中**对话框。  
  
3.  单击**添加**以显示**添加独立管理单元中**对话框。  
  
4.  选择**证书**从管理单元，然后单击列表**添加**。  
  
5.  选择**计算机帐户**，单击**下一步**，然后单击**完成**。 这将为“本地计算机”添加“证书管理控制台”界面。  
  
6.  确保**证书**从管理单元的列表仍处于选中状态，然后单击**添加**试。  
  
7.  选择**我的用户帐户**，然后单击**完成**。 这将为“当前用户”添加“证书管理控制台”界面。  
  
    > [!NOTE]
    >  这将为您当前使用的登录帐户显示“证书管理控制台”。 如果您需要为某一服务帐户将证书导入个人存储，则应首先使用该服务帐户的凭据登录。  
  
8.  单击**关闭**中**独立管理单元中**对话框。  
  
9. 单击**确定**中**添加/删除管理单元中**对话框。