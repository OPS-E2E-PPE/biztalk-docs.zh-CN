---
title: "如何为 BizTalk Server 中安装证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d799956d25bfe8e494fcbc2fbc6cbea770a92fdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>如何为 BizTalk Server 中安装证书
若要帮助保护数据，将传输上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须将适当的证书添加到适当的证书存储中，并将证书与相应的 BizTalk 项目相关联。 本主题介绍如何显示本地计算机和当前用户证书存储，证书管理控制台接口以及如何在合适的存储区中安装适当的证书。  
  
 下表中所示的证书用于帮助标志、 验证的签名、 加密和解密消息。  
  
|证书使用情况|证书类型|证书存储|  
|-----------------------|----------------------|-----------------------|  
|签名（出站）|自己的私钥 (.pfx)|当前用户\\<br />每个承载为每个主机实例的服务帐户的 MIME/SMIME 编码器管道的 BizTalk server 的个人存储区|  
|签名验证（入站）|贸易合作伙伴的公钥 (.cer)|本地 computer\Other 人将存储的每个 BizTalk server 用于承载 MIME/SMIME 解码器管道为每个主机实例的服务帐户|  
|加密（出站）|贸易合作伙伴的公钥 (.cer)|本地 computer\Other 人员存储的每个 BizTalk server 用于承载 MIME/SMIME 编码器管道|  
|解密（入站）|自己的私钥 (.pfx)|当前用户 \ 个人存储的每个 BizTalk server 用于承载 MIME/SMIME 解码器管道为每个主机实例的服务帐户|  
  
## <a name="prerequisites"></a>先决条件  
 若要执行过程中必须作为的成员身份登录此主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-display-the-certificates-management-console"></a>若要显示证书管理控制台  
  
1.  单击**启动**，单击**运行**，类型**MMC**，然后单击**确定**以打开**Microsoft 管理控制台**.  
  
2.  单击**文件**菜单，，然后单击**添加或删除管理单元中**以显示**添加或删除管理单元中**对话框。  
  
3.  单击**添加**按钮以显示**添加独立管理单元中**对话框。  
  
4.  选择**证书**从管理单元，然后单击列表**添加**。  
  
5.  选择**计算机帐户**，单击**下一步**，然后单击**完成**。 这将添加**证书管理控制台**接口**本地计算机**。  
  
6.  确保**证书**从管理单元的列表仍处于选中状态，然后单击**添加**试。  
  
7.  选择**我的用户帐户**，然后单击**完成**。 这将添加**证书管理控制台**接口**当前用户**。  
  
    > [!NOTE]  
    >  此时将显示**证书管理控制台**当前作为登录的帐户。 如果您需要为某一服务帐户将证书导入个人存储，则应首先使用该服务帐户的凭据登录。  
  
8.  单击**关闭**按钮上**独立管理单元中**对话框。  
  
9. 单击**确定**按钮上**添加或删除管理单元中**对话框。  
  
### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>若要安装用于接收加密的消息的证书  
  
1.  请求中的证书颁发机构 (CA) 的数字签名的私钥-公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  
  
2.  向合作伙伴发送加密的公钥。  
  
3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，运行该处理程序中包含的主机实例的服务帐户将从合作伙伴接收消息的身份登录。 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书用于解密服务帐户的个人存储中的消息。  
  
    > [!NOTE]  
    >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何安装证书的加密消息](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关使用证书导入到证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
4.  已安装的合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书用于加密合适的存储区中的消息。 如果伙伴正在使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，他们应在其他人的存储中安装的公钥。  
  
### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>若要安装用于发送加密的消息的证书  
  
1.  已从证书颁发机构 (CA) 请求加密的专用公共密钥对的合作伙伴。  
  
2.  已向您发送其公钥来加密消息发送到合作伙伴的合作伙伴。  
  
3.  具有安装私钥证书用于解密的相应存储区中的消息的合作伙伴。 如果伙伴正在使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，它们应个人证书存储中安装的私钥。  
  
    > [!NOTE]  
    >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何安装证书的加密消息](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关使用证书导入到证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
4.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到了运行的处理程序将向合作伙伴发送消息的主机实例的服务器。 安装合作伙伴的公钥证书用于加密发送到合作伙伴的其他人员存储中的消息。  
  
### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>若要安装用于接收证书签名消息  
  
1.  已从证书颁发机构 (CA) 请求用于数字签名的私钥-公钥密钥对的合作伙伴。  
  
2.  已向您发送其数字签名的公钥的合作伙伴。  
  
3.  具有安装对相应的存储区中的消息进行签名对于其私钥证书的合作伙伴。 如果他们使用的 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，让他们将登录消息发送到的帐户的个人存储中安装的私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    > [!NOTE]  
    >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何安装证书的加密消息](http://go.microsoft.com/fwlink/?LinkId=155156)([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关使用证书导入到证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155156) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
4.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到了运行的处理程序将从合作伙伴接收消息的主机实例的服务器。 安装合作伙伴的公钥证书验证的其他人员存储中其签名。  
  
### <a name="to-install-a-certificate-for-sending-signed-messages"></a>若要安装发送签名的消息的证书  
  
1.  请求中的证书颁发机构 (CA) 的数字签名的私钥-公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  
  
2.  向合作伙伴发送数字签名的公钥。  
  
3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，运行该处理程序中包含的主机实例的服务帐户将向合作伙伴发送消息的身份登录。 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书进行签名的服务帐户的个人存储区中的消息。  
  
    > [!NOTE]  
    >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何安装证书的加密消息](http://go.microsoft.com/fwlink/?LinkId=155156)(http://go.microsoft.com/fwlink/?LinkId=155156) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关使用证书导入到证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(http://go.microsoft.com/fwlink/?LinkId=155157) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
4.  已安装的合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书用于验证相应的存储区中的数字签名。 如果伙伴正在使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，他们应在其他人的存储中安装的公钥。