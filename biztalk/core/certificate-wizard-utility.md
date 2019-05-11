---
title: 证书向导实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff147004773bfb620898f5e381fd242a6416f158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357563"
---
# <a name="certificate-wizard-utility"></a>证书向导实用工具
使用 CertWizard 实用工具导入证书从.pfx 或.cer 文件到专用或公用存储区中，以用于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 证书向导的源代码可在**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。 使用 64 位操作系统和版本的 BizTalk Server，它位于**C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\SDK\Utilities\Certificate 向导**文件夹。 若要使用证书向导首先需要使用 Visual Studio 生成它。  
  
 CertWizard 将私钥从.pfx 文件导入到个人存储中，并将公钥从.cer 文件导入公共存储。 在导入私钥，证书可以是传入消息的解密证书或传出消息的签名证书。  
  
 **语法说明**  
  
 下表介绍了 CertWizard 实用工具使用的语法的每个部分。  
  
|||  
|-|-|  
|语法|Description|  
|Privatekey|用于导入私钥。|  
|公钥|用于导入公钥。|  
|Rootkey|用于导入根钥 — 从证书颁发机构。|  
|filename.pfx （或.cer）|.Pfx （私钥） 或.cer （公钥） 文件的完整路径。|  
|Filepassword|若要解锁的.pfx 文件所需的密码。|  
|Useridentity|一个或多个 BizTalk 主机使用的服务标识。 如果不想指定主机，但想要导入用户帐户下的证书，请输入用户帐户。 **注意：** 如果不添加 Useridentity 开关，该实用工具将导入，并为所有用户设置的证书。 **注意：** 如果添加 Useridentity 开关，但不要输入一个值，WMI 会自动生成的用户标识。|  
|Password|服务标识用户的密码。|  
|Thumbprint|用例文件中的特定证书的指纹包含多个证书。 **注意：** 对于公共证书文件，如果该文件包含多个证书，并且不指定指纹，实用工具将导入该文件中的所有证书。 对于私用证书文件，该实用工具会提示您选择要导入的证书。|  
|用法|导入私钥证书的预期使用情况。 可以为以下各项之一：<br /><br /> **登录**（适用于签名证书）<br /><br /> **解密**（用于解密证书）<br /><br /> **同时**（适用于签名证书和解密证书的证书）<br /><br /> **无**（也用于签名的证书和解密证书的证书）。 **注意：** 如果将 /Usage 开关设置为无，该向导不会在 BizTalk 主机或 BizTalk 组上设置证书的指纹。|  
|可导出|可以是 **，则返回 True**或**False**。 如果 **，则返回 True**，私钥可重新导出。|  
  
 **导入私钥的语法**  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 **导入公钥的语法**  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 **导入根钥的语法**  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a>先决条件  
 以下是执行本主题中的过程的先决条件：  
  
- 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-run-the-certificate-wizard"></a>若要运行证书向导  
  
1. 打开命令提示符。  
  
2. 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities。  
  
3. 在命令提示符处，键入**CertWizard**，键入必需的和适当的开关，，然后按**Enter**。  
  
   > [!NOTE]
   >  如果您不要在命令提示符处提供完整的命令，CertWizard 会提示你提供所需的值。  
  
## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)