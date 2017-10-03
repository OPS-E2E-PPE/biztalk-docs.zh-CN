---
title: "为 MIME 或 SMIME 消息配置证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea6e5481-fc2e-4b17-b6c8-1ec5d2bfa2c3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72fb8677734cc5a3e87d9b3c90618f719430c553
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-certificates-for-mime-or-smime-messages"></a>为 MIME 或 SMIME 消息配置证书
若要帮助保护数据，将传输上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须将相应的 BizTalk 项目使用的证书存储中安装证书相关联。 这适用于 MIME/SMIME 编码消息。 它还适用于 AS2 传输，传输 MIME/SMIME 消息。  
  
 使用下表作为参考有关证书的使用方案和中可用的配置选项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在本主题末尾的"在此部分"标题列出的主题提供了详细的过程。  
  
|**证书使用情况**|**用户上下文**|**证书存储位置**|**证书类型**|**在 BizTalk 管理控制台中的配置参数**|  
|---------------------------|----------------------|------------------------------------|--------------------------|------------------------------------------------------------------------|  
|加密（发送）|与发送处理程序相关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 编码器管道并导入到的加密证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|-指定值的加密证书**公用名**和**指纹**上**证书**页**发送端口属性**对话框。<br />-指定管道**编码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**发送管道**上的下拉列表**常规**页**发送端口属性**对话框。|  
|解密（接收）|与接收处理程序关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 解码器管道，如每个主机实例的服务帐户，并导入到解密证书**当前用户 \ 个人**存储。 **注意：**进行管道解密，在运行 IIS 6.0 的计算机上成功或更高版本，确保为 IIS 应用程序池帐户和与接收处理程序关联的主机实例所使用的帐户是相同，并且此帐户是成员\< *machineName*> \IIS_WPG 组。 有关设置 IIS 进程标识有关 IIS，请参阅[解决 IIS 权限问题的指导原则](http://go.microsoft.com/fwlink/?LinkId=155161)(http://go.microsoft.com/fwlink/?LinkId=155161) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 这些进程必须以相同的帐户运行，以便确保加载的帐户配置文件还加载了在管道中执行解密所需的注册表项。 出于性能原因，IIS 不会加载将帐户配置文件启动关联的 w3wp.exe 进程时因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例必须使用相同的帐户进行配置以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将加载帐户配置文件和注册表项。|私人证书|-指定的解密证书值**公用名**和**指纹**上**证书**每个页**主机属性**对话框。<br />-指定管道**解码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。|  
|签名（发送）|与发送处理程序相关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 编码器管道，如每个主机实例的服务帐户，并导入到的签名证书**当前用户 \ 个人**存储。|私人证书|-指定值的签名证书**公用名**和**指纹**上**证书**页**BizTalk 组属性**对话框。 **注意：**可以按每个指定只有一个签名证书[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]组。<br />-指定管道**编码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**发送管道**上的下拉列表**常规**页**发送端口属性**对话框。|  
|签名验证（接收）|与接收处理程序关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 解码器管道并导入到的签名证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|-指定验证证书的值**公用名**和**指纹**上**证书**每个页**参与方属性**对话框。<br />-指定管道**解码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。 **注意：**用于方必须是唯一从用于的其他各方验证签名的证书验证签名的证书。 **注意：**配置**解码**选项需要部署与 MIME/SMIME 解码器组件的管道。|  
|参与方解析（接收）|与接收处理程序关联的主机实例使用的帐户|登录到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机从哪方解析为其配置，和导入证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|-指定证书的值**公用名**和**指纹**上**证书**每个页**主机属性**对话框.<br />-指定**ResolveParty**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。 **注意：**配置此选项需要包含的管道使用**方解析**组件。 **XMLReceive**管道包含**方解析**组件。|  
|HTTPS（发送）|与发送处理程序相关联的主机实例使用的帐户|SSL 通信无需客户端证书。 是否要求客户端证书由目标 Web 服务器管理员决定。 如果目标 Web 服务器要求客户端证书，则执行以下步骤：<br /><br /> -从贸易合作伙伴获取的公用证书。<br />-登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为发送处理程序与关联的主机实例所使用的帐户。<br />-导入证书**当前用户 \ 个人**存储。<br /><br /> 有关配置 IIS 以使用 SSL 的信息，请参阅知识库文章[HOW TO： 安装 Windows Server 2003 中的 Web 服务器上的导入证书](http://go.microsoft.com/fwlink/?LinkId=155162)(http://go.microsoft.com/fwlink/?LinkId=155162)。<br /><br /> 有关如何使用 Windows Server 2003 证书服务 Web pages 获取证书的信息，请参阅[使用 Windows Server 2003 证书服务 Web 页面](http://go.microsoft.com/fwlink/?LinkID=69975)(http://go.microsoft.com/fwlink/?LinkID=69975)。 **注意：**若要使用证书服务 Web 页从 Windows Server 2008 计算机获取证书，请参阅 Microsoft 知识库文章 922706， [http://go.microsoft.com/fwlink/?LinkId = 155317](http://go.microsoft.com/fwlink/?LinkId=155317) (http://go.microsoft.com/fwlink/?LinkId = 155317)。|贸易合作伙伴公共证书|-   **HTTP 传输**-设置**SSL 客户端证书指纹**选项**身份验证**选项卡**HTTP 传输属性**对话框. **HTTP 传输属性**对话框中将显示通过单击**配置**按钮上**常规**页**发送端口属性**对话框。<br />-   **SOAP 传输**-设置**客户端证书指纹**选项**常规**选项卡**SOAP 传输属性**对话框。 **SOAP 传输属性**对话框中将显示通过单击**配置**按钮上**常规**页**发送端口属性**对话框。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置 BizTalk Server 接收加密的 MIME 或 SMIME 消息](../technical-guides/how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages.md)  
  
-   [如何配置 BizTalk Server 发送加密的 MIME 或 SMIME 消息](~/technical-guides/how-to-configure-biztalk-server-to-send-encrypted-mime-smime-messages.md)  
  
-   [如何配置 BizTalk 服务器以接收注册 MIME 或 SMIME 消息](../technical-guides/how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages.md)  
  
-   [如何配置 BizTalk Server 发送签名 MIME 或 SMIME 消息](../technical-guides/how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages.md)