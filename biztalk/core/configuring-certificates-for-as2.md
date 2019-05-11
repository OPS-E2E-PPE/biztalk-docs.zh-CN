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
ms.openlocfilehash: fafa91e99ef58cbb083b6815924f78ffb1715574
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356182"
---
# <a name="configuring-certificates-for-as2"></a>为 AS2 配置证书
若要帮助确保 AS2 数据传输使用加密和数字签名，你必须安装，除了相应的 AS2 配置上的相应证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本主题介绍了证书必需的如何使用它们配置方式以及常见的问题。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

## <a name="certificates-required-for-as2-transport"></a>为 AS2 传输所需证书  
 若要帮助确保 AS2 数据传输，必须将相应的证书添加到相应的证书存储中，并将证书与相应的 BizTalk 项目相关联。 以下证书用于帮助确保 AS2 消息：  


|        证书使用情况         |          证书类型           | 管道组件 |                              用户上下文                              |                                                                                           证书存储区                                                                                           |                                                                                                                                                                                                                                                                                                                                                            在此定义                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------|-------------------------------------|--------------------|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       签名 （出站）       |       自己的私钥 (.pfx)        |    AS2 编码器     |  与发送处理程序关联的主机实例使用的帐户。   |    当前用户 \ 个人存储区的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载 AS2 编码器管道为每个主机实例服务帐户    | -   **证书**页的**组属性**对话框。 这是默认签名发送已签名的文档时使用的证书。<br />-你可以重写默认证书设置，并改为使用不同的参与方的不同证书。 您可以通过选择做到这样**覆盖组签名证书**中**签名证书**的单向协议选项卡的页面**协议属性**对话框框中，并指定签名证书。 如果设置此属性，AS2 消息解析为协议将会使用签名中提供的证书**签名证书**页并不提供的证书为 BizTalk 组属性的一部分。 |
| 签名验证 （入站） | 贸易合作伙伴的公钥 (.cer) |    AS2 解码器     | 与接收处理程序关联的主机实例使用的帐户。 | 每个本地计算机 \ 其他人存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载 AS2 解码器管道为每个主机实例服务帐户 |                                                                                                                                                                                                                                                           **证书**页的**参与方属性**对话框的**注意：** 用于验证参与方签名的证书必须是唯一的证书用于验证其他参与方签名的证书。                                                                                                                                                                                                                                                            |
|      加密 （出站）       | 贸易合作伙伴的公钥 (.cer) |    AS2 编码器     |  与发送处理程序关联的主机实例使用的帐户。   |                    每个本地计算机 \ 其他人存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载 AS2 编码器管道的                    |                                                                                                                                                                                                                                                                                                                                   **证书**页的**发送端口属性**对话框                                                                                                                                                                                                                                                                                                                                    |
|       解密 （入站）       |       自己的私钥 (.pfx)        |    AS2 解码器     | 与接收处理程序关联的主机实例使用的帐户。 |    当前用户 \ 个人存储区的每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载 AS2 解码器管道为每个主机实例服务帐户    |                                                                                                                                                                                                                        AS2 解码器将确定基于消息中的证书信息的证书。<br /><br /> 对于 BizTalk MIME 解码器，该证书必须包含在**证书**页用于接收消息的主机。 这不是必需的 AS2 解码器。                                                                                                                                                                                                                        |

## <a name="certificate-signing-for-outgoing-messages"></a>为传出消息签名的证书  
 使用作为 BizTalk 组属性的一部分定义的默认证书进行签名传出 AS2 消息。 但是，可能是接收消息的参与方，希望它们提供或希望为其签名传出消息时使用的不同证书的私人证书签名的消息的方案。 如果选择启用此方案的签名传出消息使用其他证书**覆盖组签名证书**中**签名证书**的单向协议选项卡页**协议属性**对话框，然后指定签名证书。 如果证书指定为参与方的 AS2 协议的一部分，该证书使用传出消息进行签名。 如果没有证书的参与方定义，则使用指定的 BizTalk 组属性一部分的默认证书。  

## <a name="adding-certificates-to-the-certificate-stores"></a>将证书添加到证书存储  
 有关详细信息，请参阅的"显示证书管理控制台"部分[安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)，并将[证书向导实用工具](../core/certificate-wizard-utility.md)主题。  

> [!IMPORTANT]
>  个人证书存储区都可用于消息处理仅在用户配置文件加载为用户的登录凭据与主机实例相关联。 个人存储区用于签名和解密证书 （用户自己的私有密钥）。 对于进程内主机实例中; 默认情况下加载用户配置文件但是，默认情况下为独立的主机实例未加载用户配置文件。 为独立的主机，可以有一个应用程序加载用户配置文件。 或者，您可以解决此问题的进程内主机实例和独立主机实例使用相同的登录名。  

## <a name="generating-certificates"></a>生成证书  
 可以获取证书从证书颁发机构 (CA);但是请求证书的步骤会有所不同的 Ca。 查看提交的任何证书请求之前在证书颁发机构的网站上提供的信息。  

> [!IMPORTANT]
>  用于 AS2 传输的证书必须具有实现其用途所需的属性。 对于签名和签名验证，**密钥用法**属性的证书必须**数字签名**。 进行加密和解密**密钥用法**属性的证书必须**数据加密**或**密钥加密**。 你可以验证**密钥用法**特性通过双击证书，单击**详细信息**选项卡中**证书**对话框中，并检查**密钥用法**字段。  

 您还可以生成证书在 Windows Server 2008 中使用证书服务，但你的合作伙伴可能仅接受这些证书用于测试目的而不是自签名时由公共 CA 签名。 使用证书服务请求证书的详细信息，请下载**Windows Server 2008 Active Directory 证书服务循序渐进指南**从[Windows Server 2008 循序渐进指南](http://go.microsoft.com/fwlink/?LinkId=187916) ([http://go.microsoft.com/fwlink/?LinkId=187916](http://go.microsoft.com/fwlink/?LinkId=187916)).  

### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages"></a>若要配置用于签名传出 AS2 消息的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，，然后单击**属性**。  

2. 在控制台树中的**组属性**对话框中，单击**证书**。  

3. 在中**证书**窗格中，单击**浏览**，找到你想要用于签名的证书，然后单击**确定**。  

   > [!NOTE]
   >  而不是输入证书的公用名，您可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

4. 单击“确定” 。  

### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages-for-a-specific-party"></a>若要配置用于特定参与方签名传出 AS2 消息的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 从**参与方和业务配置文件**窗格中，从**协议**部分中，右键单击为交换特定参与方，消息创建的协议并单击**属性**。  

2. 在单向协议选项卡上，单击**签名证书**。  

3. 选择**覆盖组签名证书**复选框以使用此页中提供的签名传出 AS2 消息和 MDN 的证书。  

4. 单击**浏览**以显示**选择证书**对话框中，在其中选择要应用到由此参与方传输的消息的签名证书。  

5. **公用名**文本框显示所选证书的说明。  

6. **指纹**文本框将显示证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。  

7. 单击**删除证书**若要删除所选的证书。  

8. 单击**确定**以验证所做的更改，然后关闭对话框。  

### <a name="to-configure-a-certificate-for-verifying-the-digital-signature-of-an-incoming-as2-messages"></a>若要配置用于验证传入的 AS2 消息的数字签名的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，，然后单击**方**节点。  

2. 在中**参与方和业务配置文件**窗格中，右键单击你将收到的参与方签名消息，然后单击**属性**。  

3. 在控制台树中，单击**证书**。  

4. 在中**证书**窗格中，单击**浏览**，找到你想要用于验证数字签名的证书，然后单击**确定**。  

   > [!NOTE]
   >  而不是输入证书的公用名，您可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

5. 单击“确定” 。  

### <a name="to-configure-a-certificate-for-encrypting-an-outgoing-as2-messages"></a>若要配置传出的 AS2 消息进行加密的证书  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，打开**应用程序**节点，并打开的节点**应用程序**，其中包含发送端口，您将在发送加密的消息。  

2. 打开**发送端口**节点，右键单击该发送端口，然后依次**属性**。  

3. 在控制台树中，单击**证书**。  

4. 在中**证书**窗格中，单击**浏览**，找到你想要使用进行加密，然后单击该证书**确定**。  

   > [!NOTE]
   >  而不是输入证书的公用名，您可以只输入其指纹。 可以通过双击 MMC 中或在文件系统中，单击证书存储中的证书获取的指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  

5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [AS2 安全性](../core/as2-security.md)   
 [配置签名、 压缩和 AS2 传输中加密](../core/configuring-signing-compression-and-encryption-in-as2-transport.md)   
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)