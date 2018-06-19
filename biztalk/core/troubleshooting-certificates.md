---
title: 证书疑难解答方面 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7013db6-ebf7-4294-a072-e9b5b0ad0de2
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963dfdd55937fd3e41fa50a5e2a609dd591f728f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975963"
---
# <a name="troubleshooting-certificates"></a>证书疑难解答
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以使用的公钥基础结构 (PKI) 数字证书进行文档加密和解密，文档签名和验证 （不可否认性），并参与方解析。 本主题介绍各种证书使用情况和配置选项，并提供有关使用与数字证书的一些通用准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="certificate-usage-scenarios-and-configuration-options"></a>证书使用方案和配置选项  
 使用证书时出现的大多数问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是不正确或不完整配置的结果。 例如，将正确的证书导入错误的证书存储、将错误的证书导入正确的证书存储或者未能将适当的信息输入 BizTalk 管理控制台都会导致在使用证书时发生运行时错误。  
  
 使用下表作为参考有关证书的使用方案和中可用的配置选项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**证书使用情况**|**用户上下文**|**证书存储位置**|**证书类型**|**使用的管道组件**|**BizTalk Server 管理控制台中配置参数**|  
|---------------------------|----------------------|------------------------------------|--------------------------|---------------------------------|-------------------------------------------------------------------------------|  
|加密（发送）|与发送处理程序相关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 编码器管道并导入到的加密证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|MIME/SMIME 编码器|-指定值的加密证书**公用名**和**指纹**上**证书**页**发送端口属性**对话框。<br />-指定管道**编码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**发送管道**上的下拉列表**常规**页**发送端口属性**对话框。|  
|解密（接收）|与接收处理程序关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 解码器管道，如每个主机实例的服务帐户，并导入到解密证书**当前用户 \ 个人**存储。 **注意：** 对于在 IIS 7.0 的计算机上成功的管道解密，请确保为 IIS 应用程序池帐户和与接收处理程序关联的主机实例所使用的帐户是相同，并且此帐户是的成员\<machineName\>\IIS_WPG 组。 关于设置的 IIS 7.0 的 IIS 进程标识的详细信息，请参阅[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)。 这些进程必须以相同的帐户运行，以便确保加载的帐户配置文件还加载了在管道中执行解密所需的注册表项。 出于性能原因，IIS 6.0 不会加载将帐户配置文件启动关联的 w3wp.exe 进程时因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例必须使用相同的帐户进行配置以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将加载帐户配置文件和注册表项。|私人证书|MIME/SMIME 解码器|-指定的解密证书值**公用名**和**指纹**上**证书**每个页**主机属性**对话框。<br />-指定管道**解码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。|  
|签名（发送）|与发送处理程序相关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 编码器管道，如每个主机实例的服务帐户，并导入到的签名证书**当前用户 \ 个人**存储。|私人证书|MIME/SMIME 编码器|-指定值的签名证书**公用名**和**指纹**上**证书**页**BizTalk 组属性**对话框。 **注意：** 可以按每个指定只有一个签名证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。<br />-指定管道**编码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**发送管道**上的下拉列表**常规**页**发送端口属性**对话框。|  
|签名验证（接收）|与接收处理程序关联的主机实例使用的帐户|登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它会承载 S/MIME 解码器管道并导入到的签名证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|MIME/SMIME 解码器|-指定验证证书的值**公用名**和**指纹**上**证书**每个页**参与方属性**对话框。<br />-指定管道**解码**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。 **注意：** 配置**解码**选项需要部署与 MIME/SMIME 解码器组件的管道。|  
|参与方解析（接收）|与接收处理程序关联的主机实例使用的帐户|登录到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机从哪方解析为其配置，和导入证书**本地计算机 \ 其他人**存储。|贸易合作伙伴公共证书|参与方解析|-指定证书的值**公用名**和**指纹**上**证书**每个页**主机属性**对话框.<br />-指定**ResolveParty**中的选项**配置管道**对话框。 **配置管道**对话框中将显示单击的按钮旁边**接收管道**上的下拉列表**常规**页**接收位置属性**对话框。 **注意：** 配置此选项需要包含的管道使用**方解析**组件。 **XMLReceive**管道包含**方解析**组件。|  
|HTTPS（发送）|与发送处理程序相关联的主机实例使用的帐户|SSL 通信无需客户端证书。 是否要求客户端证书由目标 Web 服务器管理员决定。 如果目标 Web 服务器要求客户端证书，则执行以下步骤：<br /><br /> -从贸易合作伙伴获取的公用证书。<br />-登录到运行每个计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为发送处理程序与关联的主机实例所使用的帐户。<br />-导入证书**当前用户 \ 个人**存储。<br /><br /> 有关如何使用 Windows Server 2008 证书服务 Web pages 获取证书的信息，请参阅[请求证书通过 Web](http://go.microsoft.com/fwlink/?LinkId=129628)。|贸易合作伙伴公共证书|不适用|-   **HTTP 传输**-设置**SSL 客户端证书指纹**选项**身份验证**选项卡**HTTP 传输属性**对话框. **HTTP 传输属性**对话框中将显示通过单击**配置**按钮上**常规**页**发送端口属性**对话框。<br />-   **SOAP 传输**-设置**客户端证书指纹**选项**常规**选项卡**SOAP 传输属性**对话框。 **SOAP 传输属性**对话框中将显示通过单击**配置**按钮上**常规**页**发送端口属性**对话框。|  
  
#### <a name="to-display-the-certificates-management-console-interface-for-local-computer-and-current-user"></a>显示“本地计算机”和“当前用户”的“证书管理控制台”界面  
  
1.  单击**启动**，单击**运行**，类型**MMC**，然后单击**确定**以打开**Microsoft 管理控制台**.  
  
2.  单击**文件**菜单，，然后单击**添加/删除管理单元中**以显示**添加/删除管理单元中**对话框。  
  
3.  选择**证书**从列表中可用的管理单元，然后单击**添加**。  
  
4.  选择**计算机帐户**，单击**下一步**，然后单击**完成**。 这将添加**证书管理控制台**接口**本地计算机**。  
  
5.  确保**证书**从管理单元的列表仍处于选中状态，然后单击**添加**试。  
  
6.  选择**我的用户帐户**，然后单击**完成**。 这将添加**证书管理控制台**接口**当前用户**。  
  
    > [!NOTE]
    >  此时将显示**证书管理控制台**当前作为登录的帐户。 如果您需要为某一服务帐户将证书导入个人存储，则应首先使用该服务帐户的凭据登录。  
  
7.  单击**确定**按钮上**添加/删除管理单元中**对话框。  
  
## <a name="general-guidelines"></a>通用指导原则  
  
-   **确保导入的证书针对预期用途使用**： 若要执行此操作，请双击中的证书**证书管理控制台**接口，然后单击**详细信息**选项卡**证书**对话框。 然后单击**所有**选项**显示**下拉列表，然后单击以选择**密钥用法**和/或**增强型密钥用法**字段若要验证的预期的用途。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会尝试使用证书为以外其预期用途的运行时错误。  
  
-   **测试目标 Web 站点的连接**： 如果你使用 SSL，确保你可以连接到目标 Web 站点使用 Internet Explorer 在尝试连接到目标 Web 站点使用的 HTTP 或 SOAP 传输之前。 验证连接到目标 Web 站点时，在 Internet Explorer 中显示任何对话框。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有任何机制进行连接与连接到目标 web 站点时，可能会显示任何对话框。 可能由 Internet Explorer 显示一个对话框，如果目标网站名称不匹配的 SSL 证书中的 web 站点为指定的名称或 SSL 证书的根证书颁发机构不在相应**受信任的根证书颁发机构**存储。  
  
-   **使用 SSL 诊断工具分析 SSL 连接问题：** SSL 诊断工具是 IIS 诊断工具包的可选组件。  下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkId=64426)。  
  
-   **请确保证书有效**。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果证书已过期，不会提示你。 但 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会挂起消息。  
  
## <a name="see-also"></a>另请参阅  
 [加密和签名证书](../core/encryption-and-signing-certificates.md)