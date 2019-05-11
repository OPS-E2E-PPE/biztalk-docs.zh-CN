---
title: 如何为 BizTalk Server 安装的证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70a89595-8828-4872-b78b-77e9b0b048b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1a7f605f94c415909fcd8d5f023ddcfd6c1b1f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400381"
---
# <a name="how-to-install-certificates-for-biztalk-server"></a>如何为 BizTalk Server 安装证书
若要帮助保护数据传输上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须将相应的证书添加到相应的证书存储中，并将证书与相应的 BizTalk 项目相关联。 本主题介绍如何显示证书管理控制台界面，以便本地计算机和当前用户证书存储，以及如何在适当的存储中安装相应的证书。  

 下表中显示的证书用于帮助登录、 验证的签名、 加密和解密消息。  

|证书使用情况|证书类型|证书存储区|  
|-----------------------|----------------------|-----------------------|  
|签名 （出站）|自己的私钥 (.pfx)|当前用户\\<br />每个托管每个主机实例服务帐户的 MIME/SMIME 编码器管道的 BizTalk 服务器的个人存储区|  
|签名验证 （入站）|贸易合作伙伴的公钥 (.cer)|本地计算机 \ 其他人将存储的每个 BizTalk server 用于承载 MIME/SMIME 解码器管道为每个主机实例服务帐户|  
|加密 （出站）|贸易合作伙伴的公钥 (.cer)|本地计算机 \ 其他人将存储的每个 BizTalk server 用于承载 MIME/SMIME 编码器管道|  
|解密 （入站）|自己的私钥 (.pfx)|当前用户 \ 个人存储的每个 BizTalk server 用于承载 MIME/SMIME 解码器管道为每个主机实例服务帐户|  

## <a name="prerequisites"></a>先决条件  
 若要执行必须作为的成员身份登录此主题中的过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

### <a name="to-display-the-certificates-management-console"></a>若要显示证书管理控制台  

1.  单击**启动**，单击**运行**，类型**MMC**，然后单击**确定**打开**Microsoft 管理控制台**.  

2.  单击**文件**菜单，并单击**管理单元中添加或删除**以显示**添加或删除管理单元中**对话框。  

3.  单击**外**按钮以显示**添加独立管理单元中**对话框。  

4.  选择**证书**从列表中的管理单元，然后单击**添加**。  

5.  选择**计算机帐户**，单击**下一步**，然后单击**完成**。 这将添加**证书管理控制台**接口**本地计算机**。  

6.  絋粄**证书**从管理单元的列表仍处于选中状态，然后单击**添加**试。  

7.  选择**我的用户帐户**，然后单击**完成**。 这将添加**证书管理控制台**接口**当前用户**。  

    > [!NOTE]  
    >  这将显示**证书管理控制台**当前以登录的帐户。 如果你需要将证书导入的服务帐户的个人存储然后您应该登录使用服务帐户凭据第一次。  

8.  单击**关闭**按钮**独立管理单元中**对话框。  

9. 单击**确定**按钮**管理单元中添加或删除**对话框。  

### <a name="to-install-a-certificate-for-receiving-encrypted-messages"></a>若要安装证书以便接收加密的消息  

1. 为请求用于从证书颁发机构 (CA) 的数字签名的私钥 / 公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  

2. 向合作伙伴发送加密的公钥。  

3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，运行该处理程序的主机实例的服务帐户将从合作伙伴接收消息的身份登录。 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书用于解密消息的服务帐户的个人存储中。  

   > [!NOTE]
   >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何为加密消息安装证书](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关用来将证书导入的证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  

4. 已安装的合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书以便在适当的存储中的消息进行加密。 如果合作伙伴使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，他们应在其他人存储中安装公钥。  

### <a name="to-install-a-certificate-for-sending-encrypted-messages"></a>若要为发送加密的消息安装证书  

1. 具有证书颁发机构 (CA) 请求用于加密的私钥 / 公钥对的合作伙伴。  

2. 已向你发送其公钥用于加密消息发送到合作伙伴的合作伙伴。  

3. 具有安装私钥证书用于解密在适当的存储中的消息的合作伙伴。 如果合作伙伴使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，他们应在个人证书存储中安装私钥。  

   > [!NOTE]
   >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何为加密消息安装证书](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关用来将证书导入的证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  

4. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到具有主机实例运行将向合作伙伴发送消息的处理程序的服务器。 安装合作伙伴的公钥证书用于加密发送到其他人存储中的合作伙伴的消息。  

### <a name="to-install-a-certificate-for-receiving-signed-messages"></a>若要安装证书以便接收签名的消息  

1. 具有证书颁发机构 (CA) 请求用于数字签名的私钥 / 公钥对的合作伙伴。  

2. 已向你发送其公钥数字签名的合作伙伴。  

3. 必须安装适当的存储的消息进行签名的私钥证书的合作伙伴。 如果用户正在使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，让他们会对发送到的消息进行签名的帐户的个人存储中安装私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

   > [!NOTE]
   >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何为加密消息安装证书](http://go.microsoft.com/fwlink/?LinkId=155156)([http://go.microsoft.com/fwlink/?LinkId=155156](http://go.microsoft.com/fwlink/?LinkId=155156)) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关用来将证书导入的证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155156>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  

4. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到具有主机实例运行将从合作伙伴接收消息的处理程序的服务器。 安装合作伙伴的公钥证书以验证其签名中其他人存储。  

### <a name="to-install-a-certificate-for-sending-signed-messages"></a>若要安装证书以便发送签名的消息  

1. 为请求用于从证书颁发机构 (CA) 的数字签名的私钥 / 公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  

2. 向合作伙伴发送数字签名的公钥。  

3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，运行该处理程序的主机实例的服务帐户将向合作伙伴发送消息的身份登录。 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书的服务帐户的个人存储中的消息进行签名。  

   > [!NOTE]
   >  有关用于安装用于加密的证书的过程的详细信息，请参阅[如何为加密消息安装证书](http://go.microsoft.com/fwlink/?LinkId=155156)(<http://go.microsoft.com/fwlink/?LinkId=155156>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 有关用来将证书导入的证书存储区的工具的详细信息，请参阅[证书向导实用工具](http://go.microsoft.com/fwlink/?LinkId=155157)(<http://go.microsoft.com/fwlink/?LinkId=155157>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  

4. 已安装的合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书以验证适当的存储其数字签名。 如果合作伙伴使用 Windows 2000 Server、 Windows Server 2003 或 Windows Server 2008，他们应在其他人存储中安装公钥。
