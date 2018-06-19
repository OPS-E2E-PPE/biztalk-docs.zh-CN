---
title: 步骤 3： 导入公共和私有证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46d087c44cac350df2d58c880303668b5c3e0c24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966947"
---
# <a name="step-3-importing-public-and-private-certificates"></a>步骤 3： 导入公共和私有证书
在此步骤中，你在中创建将证书导入[步骤 2： 创建公钥和私有证书和 #91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)到 Contoso 和 Fabrikam 计算机。 每台计算机将导入自己的私用证书和对方组织的公用证书。  
  
> [!NOTE]
>  你必须将 Fabrikam 私用证书和 Contoso 公用证书传输至 Fabrikam 计算机以导入它们。 此步骤假设你将这些证书存放在 Fabrikam 计算机的 C:\Certs 文件夹中。  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>在 Contoso 计算机上导入 Contoso 私用证书  
  
1.  Contoso 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到 **\<** *驱动器***\>: files\microsoft BizTalk\<版本\>快捷键RosettaNet\SDK**然后按**Enter**。  
  
3.  在命令提示符处，键入**CertWizard /Privatekey"\<***驱动器***\>: \Certs\Contoso 私有 Encryption.pfx"**，然后按**输入**。  
  
4.  在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。  
  
5.  在**Enter 密码标识 < contoso_machine > \HostSvc**提示，并键入 HostSvc 帐户密码，然后按**Enter**。  
  
    > [!NOTE]
    >  如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。  
  
6.  在**此主证书将用于**提示符下，键入**D**，然后按**Enter**。  
  
     CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。  
  
7.  重复步骤 3-6 用于指定它签名证书，通过键入 Contoso 私有 Signature.pfx 证书**S**在**此主证书将用于**在第 6 步中记下的提示。  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>在 Contoso 计算机上导入 Fabrikam 公用证书  
  
1.  Contoso 计算机上，单击**启动**，单击**运行，** 类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到*\<驱动器\>***: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK** ，然后按**Enter**。  
  
3.  在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Fabrikam 公共 Encryption.cer"**，然后按**输入**。  
  
4.  为 Fabrikam Public Signature.cer 证书重复步骤 3。  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>在 Fabrikam 计算机上导入 Fabrikam 私用证书  
  
1.  复制以下文件从 Contoso 的计算机向\<驱动器\>: Fabrikam 计算机上的 \Certs 文件夹： Contoso 公共 Encryption.cer、 Contoso 公共 Signature.cer、 Fabrikam 私有 Encryption.pfx 和 Fabrikam 私有Signature.pfx。  
  
2.  Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
3.  在命令提示符下，将移到*\<驱动器\>***: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK** ，然后按**Enter**。  
  
4.  在命令提示符处，键入**CertWizard /Privatekey"***\<驱动器\>***: \Certs\Fabrikam 私有 Encryption.pfx"**，然后按**输入**。  
  
5.  在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。  
  
6.  在**Enter 密码标识 < fabrikam_machine > \HostSvc**提示，并键入 HostSvc 帐户密码，然后按**Enter**。  
  
    > [!NOTE]
    >  如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。  
  
7.  在**此主证书将用于**提示符下，键入**D**，然后按**Enter**。  
  
     CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。  
  
8.  重复步骤 4-7 用于指定它签名证书，通过键入 Fabrikam 私有 Signature.pfx 证书**S**在**此主证书将用于**提示在步骤 6 中。  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>在 Fabrikam 计算机上导入 Contoso 公用证书  
  
1.  Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到*\<驱动器\>***: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK** ，然后按**Enter**。  
  
3.  在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Contoso 公共 Encryption.cer"**，然后按**输入**。  
  
4.  为 Contoso Public Signature.cer 证书重复步骤 3。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4：在 IIS 中启用安全套接字层](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)