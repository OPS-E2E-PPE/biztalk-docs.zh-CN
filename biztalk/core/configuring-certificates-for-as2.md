---
title: 为 AS2 配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c160f294-7529-4e0a-876c-5827feaed067
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916f3f633e9311d970121cd3f41a03fbae8b8259
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011174"
---
# <a name="configuring-certificates-for-as2"></a>为 AS2 配置证书
若要使用加密和数字签名帮助确保 AS2 数据传输的安全，则除了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上相应地进行 AS2 配置之外，还必须安装适当的证书。 本主题介绍所需证书、证书的配置方式以及有关证书的常见问题。  

## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  

## <a name="certificates-required-for-as2-transport"></a>AS2 传输所需的证书  
 为了帮助确保 AS2 数据传输的安全，您必须将适当的证书添加到相应的证书存储区中，并将这些证书与相应的 BizTalk 项目关联。 使用以下证书可帮助确保 AS2 消息的安全：  


|        证书使用情况         |          证书类型           | 管道组件 |                              用户上下文                              |                                                                                           证书存储区                                                                                           |                                                                                                                                                                                                                                                                                                                                                            在此定义                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------|-------------------------------------|--------------------|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       签名（出站）       |       自己的私钥 (.pfx)        |    AS2 编码器     |  与发送处理程序相关联的主机实例使用的帐户。   |    每台承载 AS2 编码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“当前用户\个人”存储区    | -   **证书**页的**组属性**对话框。 发送已签名的文档时使用的默认签名证书。<br />-你可以重写默认证书设置，并改为使用不同的参与方的不同证书。 您可以通过选择做到这样**覆盖组签名证书**中**签名证书**的单向协议选项卡的页面**协议属性**对话框框中，并指定签名证书。 如果设置此属性，AS2 消息解析为协议将会使用签名中提供的证书**签名证书**页并不提供的证书为 BizTalk 组属性的一部分。 |
| 签名验证（入站） | 贸易合作伙伴的公钥 (.cer) |    AS2 解码器     | 与接收处理程序关联的主机实例使用的帐户。 | 每台承载 AS2 解码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“本地计算机\其他人”存储区 |                                                                                                                                                                                                                                                           **证书**页的**参与方属性**对话框中**注意：** 用于参与方必须是唯一的证书用于其他验证签名的证书验证签名的证书参与方。                                                                                                                                                                                                                                                            |
|      加密（出站）       | 贸易合作伙伴的公钥 (.cer) |    AS2 编码器     |  与发送处理程序相关联的主机实例使用的帐户。   |                    每台承载 AS2 编码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的“本地计算机\其他人”存储区                    |                                                                                                                                                                                                                                                                                                                                   **证书**页的**发送端口属性**对话框                                                                                                                                                                                                                                                                                                                                    |
|       解密（入站）       |       自己的私钥 (.pfx)        |    AS2 解码器     | 与接收处理程序关联的主机实例使用的帐户。 |    每台承载 AS2 解码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“当前用户\个人”存储区    |                                                                                                                                                                                                                        AS2 解码器将根据消息中的证书信息确定证书。<br /><br /> 对于 BizTalk MIME 解码器，该证书必须包含在**证书**页用于接收消息的主机。 对于 AS2 解码器，则不一定是这样。                                                                                                                                                                                                                        |

## <a name="certificate-signing-for-outgoing-messages"></a>为传出消息签名的证书  
 使用定义为 BizTalk 组属性一部分的默认证书，签名传出 AS2 消息。  但是，存在这样的情形，接收消息的参与方希望使用自己提供的私人证书签名消息，或签名传出消息时使用不同的证书。 如果选择启用此方案的签名传出消息使用其他证书**覆盖组签名证书**中**签名证书**的单向协议选项卡页**协议属性**对话框，然后指定签名证书。 如果证书指定为参与方 AS2 协议的一部分，则该证书用于签名传出消息。 如果无为参与方定义的证书，则使用指定为 BizTalk 组属性一部分的默认证书。  

## <a name="adding-certificates-to-the-certificate-stores"></a>将证书添加到证书存储  
 有关详细信息，请参阅的"显示证书管理控制台"部分[安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)，并将[证书向导实用工具](../core/certificate-wizard-utility.md)主题。  

> [!IMPORTANT]
>  只有在为登录凭据与主机实例关联的用户加载了用户配置文件时，个人证书存储区才可用于消息处理。 个人存储区用于签名证书和解密证书（用户自己的私钥）。 默认情况下，将为进程内主机实例加载用户配置文件；但默认情况下不会为独立主机实例加载用户配置文件。 您可以通过应用程序为独立主机加载用户配置文件。 另外，也可以通过对进程内主机实例和独立主机实例使用相同的登录名来解决此问题。  

## <a name="generating-certificates"></a>生成证书  
 证书可以从证书颁发机构 (CA) 获得；但是 CA 间请求证书的步骤不同。 在提交任何证书请求之前，请查阅证书颁发机构的网站上提供的信息。  

> [!IMPORTANT]
>  用于 AS2 传输的证书必须具有实现其用途所需的属性。 对于签名和签名验证，**密钥用法**属性的证书必须**数字签名**。 进行加密和解密**密钥用法**属性的证书必须**数据加密**或**密钥加密**。 你可以验证**密钥用法**特性通过双击证书，单击**详细信息**选项卡中**证书**对话框中，并检查**密钥用法**字段。  

 您还可以使用证书服务在 Windows Server 2008 中生成证书，但是您的参与方可能只能接受这些证书用于测试目的，因为其是自签名的，而不是公共 CA 签名。 使用证书服务请求证书的详细信息，请下载**Windows Server 2008 Active Directory 证书服务循序渐进指南**从[Windows Server 2008 循序渐进指南](http://go.microsoft.com/fwlink/?LinkId=187916) ([http://go.microsoft.com/fwlink/?LinkId=187916](http://go.microsoft.com/fwlink/?LinkId=187916)).  

### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages"></a>配置用于对传出 AS2 消息进行签名的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，，然后单击**属性**。  

2. 在控制台树中的**组属性**对话框中，单击**证书**。  

3. 在中**证书**窗格中，单击**浏览**，找到你想要用于签名的证书，然后单击**确定**。  

   > [!NOTE]
   >  不用输入证书的公用名，可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

4. 单击“确定” 。  

### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages-for-a-specific-party"></a>配置用于签署特定参与方传出 AS2 消息的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 从**参与方和业务配置文件**窗格中，从**协议**部分中，右键单击为交换特定参与方，消息创建的协议并单击**属性**。  

2. 在单向协议选项卡上，单击**签名证书**。  

3. 选择**覆盖组签名证书**复选框以使用此页中提供的签名传出 AS2 消息和 MDN 的证书。  

4. 单击**浏览**以显示**选择证书**对话框中，在其中选择要应用到由此参与方传输的消息的签名证书。  

5. **公用名**文本框显示所选证书的说明。  

6. **指纹**文本框将显示证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。  

7. 单击**删除证书**若要删除所选的证书。  

8. 单击**确定**以验证所做的更改，然后关闭对话框。  

### <a name="to-configure-a-certificate-for-verifying-the-digital-signature-of-an-incoming-as2-messages"></a>配置用于验证传入 AS2 消息的数字签名的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，，然后单击**方**节点。  

2. 在中**参与方和业务配置文件**窗格中，右键单击你将收到的参与方签名消息，然后单击**属性**。  

3. 在控制台树中，单击**证书**。  

4. 在中**证书**窗格中，单击**浏览**，找到你想要用于验证数字签名的证书，然后单击**确定**。  

   > [!NOTE]
   >  不用输入证书的公用名，可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

5. 单击“确定” 。  

### <a name="to-configure-a-certificate-for-encrypting-an-outgoing-as2-messages"></a>配置用于对传出 AS2 消息进行加密的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，打开**应用程序**节点，并打开的节点**应用程序**，其中包含发送端口，您将在发送加密的消息。  

2. 打开**发送端口**节点，右键单击该发送端口，然后依次**属性**。  

3. 在控制台树中，单击**证书**。  

4. 在中**证书**窗格中，单击**浏览**，找到你想要使用进行加密，然后单击该证书**确定**。  

   > [!NOTE]
   >  不用输入证书的公用名，可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [AS2 安全性](../core/as2-security.md)   
 [配置签名、 压缩和 AS2 传输中加密](../core/configuring-signing-compression-and-encryption-in-as2-transport.md)   
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)