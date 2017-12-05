---
title: "证书向导实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b0341a11c45cd08f8476d48ea38cbf96bcc49c1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="certificate-wizard-utility"></a>证书向导实用工具
使用 CertWizard 实用工具可以将证书从 .pfx 或 .cer 文件导入到专用或公用存储区中，以用于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 在找不到证书向导的源代码**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。 使用 64 位操作系统和版本的 BizTalk Server，则将为**C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。 若要使用证书向导将首先需要生成使用 Visual Studio。  
  
 CertWizard 将私钥从 .pfx 文件导入到个人存储区中，将公钥从 .cer 文件导入到公用存储区中。 导入私钥时，证书可为传入消息的解密证书或传出消息的签名证书。  
  
 **语法说明**  
  
 下表介绍了 CertWizard 实用工具使用的语法的每个部分。  
  
|||  
|-|-|  
|语法|Description|  
|Privatekey|用于导入私钥。|  
|Publickey|用于导入公钥。|  
|Rootkey|用于导入根钥（来自证书颁发机构）。|  
|filename.pfx（或 .cer）|.pfx（私钥）或 .cer（公钥）文件的完整路径。|  
|Filepassword|对 .pfx 文件进行解锁所需的密码。|  
|Useridentity|一个或多个 BizTalk 主机使用的服务标识。 如果不想指定主机，而想以用户帐户导入证书，请输入一个用户帐户。 **注意：**如果不希望添加用户身份交换机，该实用程序导入，并为所有用户设置的证书。 **注意：** WMI 如果添加用户身份开关，但未输入值时，会自动生成的用户标识。|  
|密码|服务标识用户的口令。|  
|Thumbprint|特定证书的指纹（如果证书文件包含多个证书）。 **注意：**对于公共证书文件，如果该文件包含多个证书且未指定指纹，该实用程序导入文件中的所有证书。 对于私用证书文件，实用工具会提示你选择要导入的证书。|  
|用法|导入的私用证书的预期用途。 可以为以下各项之一：<br /><br /> **登录**（用于签名的证书）<br /><br /> **解密**（用于解密证书）<br /><br /> **同时**（用于解密证书和签名证书的证书）<br /><br /> **无**（还用于解密证书和签名证书的证书）。 **注意：**如果 /Usage 开关设置为 none 时，向导不会在 BizTalk 主机或 BizTalk 组上设置证书的指纹。|  
|Exportable|可以是**True**或**False**。 如果**True**，可以重新导出私钥。|  
  
 **用于导入私钥的语法**  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 **导入公钥的语法**  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 **用于导入的根项的语法**  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-run-the-certificate-wizard"></a>运行证书向导  
  
1.  打开命令提示符。  
  
2.  移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities。  
  
3.  在命令提示符处，键入**CertWizard**，键入必选和相应的交换机，然后按**Enter**。  
  
    > [!NOTE]
    >  如果在命令提示符处提供的命令不完整，CertWizard 会提示你提供必需的值。  
  
## <a name="see-also"></a>另请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)