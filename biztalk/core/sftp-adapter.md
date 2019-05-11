---
title: SFTP 适配器 |Microsoft Docs
description: 创建或配置接收位置和发送端口在 BizTalk Server，包括使用 SFTP 适配器常见问题解答中使用 SFTP 适配器
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f64c4c8-64a0-4e43-9660-b5c2d75d28aa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 115eba0f61735ecaf361127c263c86b1bc518b59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393191"
---
# <a name="sftp-adapter"></a>SFTP 适配器
BizTalk Server 包含**SFTP**适配器来发送和接收消息，从安全 FTP 服务器使用 SSH 文件传输协议。 本主题包括配置的步骤**SFTP**接收位置，并配置 SFTP 发送端口以接收和从安全 FTP 服务器发送消息。 它还包括常见问题和解答。

## <a name="prerequisites"></a>先决条件
**从 BizTalk Server 2016 开始**，SFTP 适配器使用 WinSCP 连接到 SFTP，并因此支持更大范围的 SFTP 服务器。 **下载[WinSCP](http://winscp.net)** 在 BizTalk Server 运行时。 请务必检查中的受支持的 WinSCP 版本[硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)

BizTalk Server 2013 R2 和以前的版本不支持 WinSCP。
  
## <a name="configure-the-receive-location"></a>配置接收位置
  
> [!NOTE]
>  在创建接收位置之前, 您必须已添加单向接收端口。 请参阅[创建一个接收端口](../core/how-to-create-a-receive-port.md)的具体步骤。  
  
 
1.  在 BizTalk Server 管理控制台中，展开 BizTalk Server 中，展开**BizTalk 组**，展开**应用程序**，然后展开应用程序在你想要创建的接收位置。  
  
2.  在左窗格中，单击“接收端口”  节点，在右窗格中，右键单击你希望将新的接收位置与其关联的接收端口，然后单击“属性” 。  
  
3.  在“接收端口属性”  对话框的左窗格中，选择“接收位置” ，然后在右窗格中单击“新建”  以创建新的接收位置。  
  
4.  在中**接收位置属性**对话框中**传输**部分中，选择**SFTP**从**类型**下拉列表，然后单击**配置**以配置接收位置的传输属性。  
  
5.  在中**SFTP 传输属性**，执行以下操作：  
 
     **其他**
         
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |连接限制|指定的最大可以打开到服务器的并发连接数。<br /><br /> 此设置是每个服务器，并且每个接收位置。 请考虑下列情形：<br /><br /> -有两个接收位置具有相同的配置属性值，包括 ConnectionLimit 属性设置为相同的值。 例如，该属性设置为 6。 在这种情况下，没有一个连接池 （具有 6 个可用连接），供两个接收位置。<br /><br /> -有两个接收位置配置了相同的配置值，并将 ConnectionLimit 属性设置为不同的值。 例如，ReceiveLocation1 属性设置为 6，并且 ReceiveLocation2 属性设置为 5。 在此情况下，每个接收位置有其自己的连接池具有其自己可用的连接。 ReceiveLocation1 连接池具有 6 个可用连接。 ReceiveLocation2 连接池具有 5 个可用连接。|  
    |日志 | 从 BizTalk Server 2016 开始可用。 <br/><br/>输入要创建客户端的日志文件的完整路径。 使用此日志文件来解决任何错误。|
  
     **轮询**  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |轮询间隔|指定的适配器轮询服务器的时间间隔。 若要连续轮询，请将此值设置为零。<br /><br /> **默认值：** 5|  
    |单位|指定在其中轮询间隔指定的单元，例如、 秒、 分钟、 小时或天。<br /><br /> **默认值：** Seconds|  
  
     **代理**（从 BizTalk Server 2013 R2 开始可用）  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Address|指定的 DNS 名称或代理服务器的 IP 地址。|  
    |Password|指定代理服务器的密码。|  
    |Port|指定代理服务器的端口。|  
    |类型|指定代理服务器使用的协议。|  
    |UserName|指定代理服务器的用户名。|  
  
     **安全性**  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |接受任何 SSH 服务器主机密钥|当 **，则返回 True**，接收位置接受来自服务器的任何 SSH 公共主机密钥。 当**False**，接收位置使用服务器指纹进行身份验证。 输入中的指纹**SSHServerHostKeyFingerPrint**属性。<br /><br /> **默认值：** False|  
    |客户端身份验证模式|选择接收位置使用的 SSH 服务器到客户端身份验证的身份验证方法。 如果设置为**密码**，必须输入中的值**密码**属性。 如果设置为**PublicKeyAuthentication**，你必须输入中的用户的私钥**PrivateKey**属性。 如果设置为**MultiFactorAuthentication**必须输入**用户名**使用其**密码**并**PrivateKey**。 此外，如果私钥受密码保护，输入的密码也**PrivateKeyPassword**属性。<br /><br /> **默认值：** Password|  
    |强度的加密密码 |从 BizTalk Server 2013 R2 开始可用。 <br/><br/>输入加密密码类型。<br/><br/>BizTalk Server 2013 R2 选项：自动、 AES、 和 TripleDES<br/><br/>BizTalk Server 2016 选项：自动、 AES、 Arcfour、 Blowfish、 TripleDES 和 DES|  
    |Password|如果您设置，则指定 SFTP 用户密码**ClientAuthenticationMode**到**密码**。|  
    |私钥|如果您设置，则指定 SFTP 用户的私钥**ClientAuthenticationMode**到**PublicKeyAuthentication**。<br /><br /> **注意：** 私钥文件必须指定的.ppk 文件。|  
    |私钥密码|指定私钥密码，如果需要在指定的密钥**PrivateKey**属性。|  
    |SSH 服务器主机密钥指纹|指定 SSH 服务器的公共主机密钥的指纹。|  
    |用户名|指定的用户名登录到 SFTP 服务器上。|  
  
     **SSH Server**  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |文件掩码|指定从安全 FTP 服务器检索文件时要使用的文件掩码。|  
    |文件夹路径|从接收位置可在其中检索文件的安全 FTP 服务器上指定的文件夹路径。|  
    |Port|指定文件传输发生的安全 FTP 服务器的端口地址。|  
    |服务器地址|指定服务器名称或 IP 地址的安全 FTP 服务器。|  
  
6.  单击“确定” 。  
  
7.  在“接收位置属性”  对话框中输入相应的值，完成对接收位置的配置，然后单击“确定”  保存设置。 璝惠**接收位置属性**对话框中，请参阅[创建接收位置](../core/how-to-create-a-receive-location.md)。
 
## <a name="configure-the-send-port"></a>配置发送端口  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[创建一个发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项，并指定**SFTP**有关**类型**选项**传输**一部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮。  
  
3.  在中**SFTP 传输属性**，请输入以下命令：  
  
    **其他**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |连接限制|指定的最大可以打开到服务器的并发连接数。|  
    |日志 | 从 BizTalk Server 2016 开始可用。 <br/><br/>输入要创建客户端的日志文件的完整路径。 使用此日志文件来解决任何错误。|
    |临时文件夹 | 从 BizTalk Server 2013 R2 开始可用。 <br/><br/>要将上载大型文件，然后它们可以自动移动到所需位置在同一服务器上的 SFTP 服务器上的临时文件夹。|  
    
    **代理**（可从 BizTalk Server 2013 R2）
    
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Address|指定的 DNS 名称或代理服务器的 IP 地址。|  
    |Password|指定代理服务器的密码。|  
    |Port|指定代理服务器的端口。|  
    |类型|指定代理服务器使用的协议。|  
    |用户名|指定代理服务器的用户名。|  
    
    **安全性**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |访问任何 SSH 服务器主机密钥|当 **，则返回 True**，发送端口接受来自服务器的任何 SSH 公共主机密钥。 当**False**，为端口与该主机密钥与中指定的密钥匹配**SSHServerHostKey**属性。<br /><br /> **默认值：** False|  
    |客户端身份验证模式|指定发送端口使用的 SSH 服务器到客户端身份验证的身份验证方法。 如果设置为**密码**，必须输入中的值**密码**属性。 如果设置为**PublicKeyAuthentication**，你必须输入中的用户的私钥**PrivateKey**属性。 如果设置为**MultiFactorAuthentication**必须提供**用户名**使用其**密码**并**PrivateKey**。 此外，如果私钥受密码保护，输入的密码也**PrivateKeyPassword**属性。<br /><br /> **默认值：** Password|  
    |强度的加密密码 | 从 BizTalk Server 2013 R2 开始可用。<br/><br/>输入加密密码类型。<br/><br/>BizTalk Server 2013 R2 选项：自动、 AES、 和 TripleDES<br/><br/>BizTalk Server 2016 选项：自动、 AES、 Arcfour、 Blowfish、 TripleDES 和 DES|  
    |Password|如果您设置，则指定 SFTP 用户密码**ClientAuthenticationMode**到**密码**。|  
    |私钥|如果您设置，则指定 SFTP 用户的私钥**ClientAuthenticationMode**到**PublicKeyAuthentication**。|  
    |私钥密码|指定私钥密码，如果需要在指定的密钥**PrivateKey**属性。|  
    |SSH 服务器主机密钥指纹|指定适配器用于对服务器进行身份验证，如果服务器的指纹**AccessAnySSHServerHostKey**属性设置为**False**。 如果指纹不匹配，则连接将失败。|  
    |“用户名”|指定安全 FTP 服务器的用户名。|  
    
    **SSH Server**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |如果将存在|如果目标上存在已传输到安全 FTP 服务器的文件，此属性指定是否应将从正在传输的文件数据追加到现有文件。 如果设置为 **，则返回 True**，追加数据。 如果设置为**False**，覆盖目标服务器上的文件。<br /><br /> **默认值：** False|  
    |文件夹路径|该文件将复制的安全 FTP 服务器上指定的文件夹路径。|  
    |Port|指定文件传输发生的安全 FTP 服务器的端口地址。|  
    |服务器地址|指定服务器名称或 IP 地址的安全 FTP 服务器。|  
    |目标文件名|指定与该文件将传输到安全 FTP 服务器的名称。 此外可以为目标的文件名使用宏。|  
  
4.  单击**确定**并**确定**次以保存设置。  
  
## <a name="use-a-newer-winscp-version"></a>使用较新的 WinSCP 版本

若要使用 BizTalk Server 使用 WinSCP 的较新版本，请添加程序集重定向，以便 BizTalk 了解要加载的程序集。 在 BizTalk Server 配置文件中配置重定向：BTSNTSVC.exe.config （32 位主机实例） 和 BTSNTSVC64.exe.config （64 位主机实例）。

以下包含示例配置语法。 确保替换`%NEWVERSION%`与您的版本：

```
<configuration>
 <runtime>
  <assemblyBinding>
   <dependentAssembly>
    <assemblyIdentity name="WinSCPnet" publicKeyToken="2271ec4a3c56d0bf" culture="neutral" />
    <bindingRedirect oldVersion="1.2.10.6257" newVersion="%NEWVERSION%"/>
   </dependentAssembly>
  </assemblyBinding>
 </runtime>
</configuration>
```

完成后，你的配置类似于以下内容：  

![配置文件中的程序集重定向。](media/AssemblyRedirect.png)

## <a name="frequently-asked-questions"></a>常见问题解答  
  
|问题|答案|  
|--------------|------------|  
|支持哪些 SFTP 服务器？|请参阅[受支持的 SFTP 服务器](http://social.technet.microsoft.com/wiki/contents/articles/29940.biztalk-serverbiztalk-services-supported-sftp-servers.aspx)。 从 BizTalk Server 2016 开始，SFTP 适配器使用 WinSCP 连接到 SFTP。 因此，支持 WinSCP 的 SFTP 服务器应协同工作。|  
|SFTP 适配器是否可用于相互身份验证方法 （公钥和密码）|-使用起始**BizTalk Server 2013 R2**，答案为是。 如果设置为**MultiFactorAuthentication**必须提供**用户名**使用其**密码**并**PrivateKey**。 此外，如果私钥受密码保护，指定的密码也**PrivateKeyPassword**属性。<br /><br /> -对于**BizTalk Server 2013**、 任一**密码**或**PublicKeyAuthentication**可用。 **MultiFactorAuthentication** BizTalk Server 2013 附带的 SFTP 适配器不支持。|  
|支持哪些私钥格式？ 可以使用 OpenSSH 私钥格式？|SFTP 适配器支持仅 PuTTY 私钥文件格式。 可以使用 PuTTYgen 从 OpenSSH 转换为.ppk 格式。|  
|对于 SSHServerHostKeyFingerPrint，应使用哪种指纹算法和格式？|应采用格式使用服务器的密钥的 MD5 指纹： `ssh-rsa 2048 90:e4:9b:67:d9:22:a7:5f:6f:33:db:6a:b1:23:96:12`。|  
|SFTP 适配器是否支持 256 位加密？|是-SFTP 适配器支持 256 位加密。 支持的加密算法包括：<br /><br /> AES 加密：256 位、 192 位或 128 位 SDCTR 或 CBC<br /><br /> -3DES (三重 DES) 加密：168 位 SDCTR 或 CBC|  
|该适配器支持哪些 SSH 版本？|仅 SSH2。 不能与具有 SSH1 版本的 SFTP 服务器建立连接。|  
|文件掩码是否区分大小写？|否。 \*.txt 和 \*.TXT 同样适用。 请安装 BizTalk Server 2013 的最新累积更新。 BizTalk Server 2013 RTM 版本必须区分大小写的文件掩码。|  
|导出绑定提供了空密码字段。 尝试通过导入这些绑定创建接收位置时所有更改都是什么进行？|通过编辑密码字段编辑绑定文件。 此外，在`<Password vt="1">MySecretPassword</Password>`， **vt ="1"** 指示 null 值。 更改为**vt ="8"**，这指示一个字符串。 例如：<br /><br /> `<Password vt="8">MySecretPassword</Password>`<br /><br /> 有关更多详细信息，请参阅 [http://msdn.microsoft.com/library/system.runtime.interopservices.varenum(v=vs.100).aspx](http://msdn.microsoft.com/library/system.runtime.interopservices.varenum\(v=vs.100\).aspx)|  
|如何指定文件路径？|通常情况下，采用格式指定路径`/folder/pathname`。 但是，不同的服务器需要使用不同的格式，带或不带前导或尾随斜杠。 因此，您还可以尝试以下：<br /><br /> -                   `/folder/pathname`<br /><br /> -                   `/folder/pathname/`<br /><br /> -                   `folder/pathname`<br /><br /> -                   `folder/pathname/`|  
  

