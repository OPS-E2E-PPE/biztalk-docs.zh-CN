---
title: "配置证书为 AS2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c160f294-7529-4e0a-876c-5827feaed067
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb2f9c22ddf41eec4133710de8a775bf8ff0b044
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-certificates-for-as2"></a>为 AS2 配置证书
若要使用加密和数字签名帮助确保 AS2 数据传输的安全，则除了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上相应地进行 AS2 配置之外，还必须安装适当的证书。 本主题介绍所需证书、证书的配置方式以及有关证书的常见问题。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
## <a name="certificates-required-for-as2-transport"></a>AS2 传输所需的证书  
 为了帮助确保 AS2 数据传输的安全，您必须将适当的证书添加到相应的证书存储区中，并将这些证书与相应的 BizTalk 项目关联。 使用以下证书可帮助确保 AS2 消息的安全：  
  
|证书使用情况|证书类型|管道组件|用户上下文|证书存储|在此定义|  
|-----------------------|----------------------|------------------------|------------------|-----------------------|-------------------|  
|签名（出站）|自己的私钥 (.pfx)|AS2 编码器|与发送处理程序相关联的主机实例使用的帐户。|每台承载 AS2 编码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“当前用户\个人”存储区|-   **证书**页**组属性**对话框。 发送已签名的文档时使用的默认签名证书。<br />-你可以重写默认证书设置，并改为不同方使用不同的证书。 你可以通过选择实现**覆盖组签名证书**中**签名证书**的单向协议选项卡页**协议属性**对话框框中，并指定签名证书。 如果设置此属性，无论 AS2 消息解析为协议将使用签名中提供的证书**签名证书**页上，不由证书提供作为 BizTalk 组属性的一部分。|  
|签名验证（入站）|贸易合作伙伴的公钥 (.cer)|AS2 解码器|与接收处理程序关联的主机实例使用的帐户。|每台承载 AS2 解码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“本地计算机\其他人”存储区|**证书**页**参与方属性**对话框**注意：**用于方必须是唯一从用于验证签名的证书验证签名的证书其他各方。|  
|加密（出站）|贸易合作伙伴的公钥 (.cer)|AS2 编码器|与发送处理程序相关联的主机实例使用的帐户。|每台承载 AS2 编码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的“本地计算机\其他人”存储区|**证书**页**发送端口属性**对话框|  
|解密（入站）|自己的私钥 (.pfx)|AS2 解码器|与接收处理程序关联的主机实例使用的帐户。|每台承载 AS2 解码器管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上针对每个主机实例服务帐户的“当前用户\个人”存储区|AS2 解码器将根据消息中的证书信息确定证书。<br /><br /> BizTalk MIME 解码器，该证书必须包含在**证书**页用于接收消息的主机。 对于 AS2 解码器，则不一定是这样。|  
  
## <a name="certificate-signing-for-outgoing-messages"></a>对传出消息进行签名的证书  
 使用定义为 BizTalk 组属性一部分的默认证书，签名传出 AS2 消息。  但是，存在这样的情形，接收消息的参与方希望使用自己提供的私人证书签名消息，或签名传出消息时使用不同的证书。 如果你选择启用对使用其他证书的传出消息进行签名的这种情况下**覆盖组签名证书**中**签名证书**单向协议选项卡页**协议属性**对话框框中，并指定签名证书。 如果证书指定为参与方 AS2 协议的一部分，则该证书用于签名传出消息。 如果无为参与方定义的证书，则使用指定为 BizTalk 组属性一部分的默认证书。  
  
## <a name="adding-certificates-to-the-certificate-stores"></a>将证书添加到证书存储  
 有关详细信息，请参阅的"显示证书管理控制台"部分[安装证书的 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)，以及[证书向导实用工具](../core/certificate-wizard-utility.md)主题。  
  
> [!IMPORTANT]
>  只有在为登录凭据与主机实例关联的用户加载了用户配置文件时，个人证书存储区才可用于消息处理。 个人存储区用于签名证书和解密证书（用户自己的私钥）。 默认情况下，将为进程内主机实例加载用户配置文件；但默认情况下不会为独立主机实例加载用户配置文件。 您可以通过应用程序为独立主机加载用户配置文件。 另外，也可以通过对进程内主机实例和独立主机实例使用相同的登录名来解决此问题。  
  
## <a name="generating-certificates"></a>生成证书  
 证书可以从证书颁发机构 (CA) 获得；但是 CA 间请求证书的步骤不同。 在提交任何证书请求之前，请查阅证书颁发机构的网站上提供的信息。  
  
> [!IMPORTANT]
>  用于 AS2 传输的证书必须具有实现其用途所需的属性。 进行签名和签名验证**密钥用法**证书属性必须为**数字签名**。 加密和解密，**密钥用法**证书属性必须为**数据加密**或**密钥加密**。 你可以验证**密钥用法**通过双击该证书，单击属性**详细信息**选项卡中**证书**对话框中，并检查**密钥用法**字段。  
  
 您还可以使用证书服务在 Windows Server 2008 中生成证书，但是您的参与方可能只能接受这些证书用于测试目的，因为其是自签名的，而不是公共 CA 签名。 有关使用请求证书的证书服务的详细信息，下载**Windows Server 2008 Active Directory 证书服务循序渐进指南**从[Windows Server 2008 分步指南](http://go.microsoft.com/fwlink/?LinkId=187916) ([http://go.microsoft.com/fwlink/?LinkId=187916](http://go.microsoft.com/fwlink/?LinkId=187916))。  
  
### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages"></a>配置用于对传出 AS2 消息进行签名的证书  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**节点，，然后单击**属性**。  
  
2.  在控制台树中的**组属性**对话框中，单击**证书**。  
  
3.  在**证书**窗格中，单击**浏览**，查找你想要使用进行签名的证书，然后单击**确定**。  
  
    > [!NOTE]
    >  不用输入证书的公用名，可以只输入其指纹。 你可以通过双击证书存储在 MMC 中或在文件系统中，单击中的证书获取指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  
  
4.  单击 **“确定”**。  
  
### <a name="to-configure-a-certificate-for-signing-outgoing-as2-messages-for-a-specific-party"></a>配置用于签署特定参与方传出 AS2 消息的证书  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 从**方和业务配置文件**窗格中，从**协议**部分中右键单击创建为与特定的当事方，交换消息的协议，单击**属性**。  
  
2.  单向协议选项卡上，单击**签名证书**。  
  
3.  选择**覆盖组签名证书**复选框以使用此页中提供用于对传出的 AS2 消息和 MDN 签名的证书。  
  
4.  单击**浏览**以显示**选择证书**对话框中，你在其中选择要应用于此方传输的消息的签名证书。  
  
5.  **公用名**文本框中显示所选证书的说明。  
  
6.  **指纹**文本框中显示证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。  
  
7.  单击**删除证书**若要删除所选的证书。  
  
8.  单击**确定**验证所做的更改，然后关闭对话框。  
  
### <a name="to-configure-a-certificate-for-verifying-the-digital-signature-of-an-incoming-as2-messages"></a>配置用于验证传入 AS2 消息的数字签名的证书  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，，然后单击**方**节点。  
  
2.  在**方和业务配置文件**窗格中，右键单击你将接收方签名消息，然后单击**属性**。  
  
3.  在控制台树中，单击**证书**。  
  
4.  在**证书**窗格中，单击**浏览**，查找你想要用于验证数字签名的证书，然后单击**确定**。  
  
    > [!NOTE]
    >  不用输入证书的公用名，可以只输入其指纹。 你可以通过双击证书存储在 MMC 中或在文件系统中，单击中的证书获取指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  
  
5.  单击 **“确定”**。  
  
### <a name="to-configure-a-certificate-for-encrypting-an-outgoing-as2-messages"></a>配置用于对传出 AS2 消息进行加密的证书  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**节点，打开**应用程序**节点，并打开的节点**应用程序**，其中包含发送端口，则将会在发送加密的消息。  
  
2.  打开**发送端口**节点，右键单击发送端口，再单击**属性**。  
  
3.  在控制台树中，单击**证书**。  
  
4.  在**证书**窗格中，单击**浏览**，查找你想要用于加密，然后单击该证书**确定**。  
  
    > [!NOTE]
    >  不用输入证书的公用名，可以只输入其指纹。 你可以通过双击证书存储在 MMC 中或在文件系统中，单击中的证书获取指纹**详细信息**选项卡上，单击**指纹**字段，并复制指纹.  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [AS2 安全](../core/as2-security.md)   
 [配置签名、 压缩和 AS2 传输中的加密](../core/configuring-signing-compression-and-encryption-in-as2-transport.md)   
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)