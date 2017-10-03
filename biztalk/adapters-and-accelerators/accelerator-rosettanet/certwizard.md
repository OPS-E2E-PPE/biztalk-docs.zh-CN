---
title: "CertWizard |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d9daf4ea1ea996680088c7a7a1333e9d26906b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="certwizard"></a>CertWizard
CertWizard 实用程序用于从.pfx 或.cer 文件的证书导入到的与一起使用的私有或公用存储区[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*> \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\ 快捷键  
  
## <a name="running-certwizard"></a>运行 CertWizard  
  
#### <a name="to-run-certwizard"></a>运行 CertWizard  
  
1.  打开命令提示符。  
  
2.  将移动到\<*驱动器*> \ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > Accelerator for RosettaNet\SDK\\。  
  
3.  在命令提示符处，键入**CertWizard**，键入必选和相应的交换机，然后按 enter 键。  
  
## <a name="syntax-for-certwizard"></a>CertWizard 的语法  
 下面给出了用于启动此命令行实用工具的语法：  
  
### <a name="syntax-for-importing-a-private-key"></a>导入私钥的语法  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a>导入公钥的语法  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a>导入根钥的语法  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a>语法说明  
 下表介绍了 CertWizard 实用工具使用的语法的每个部分。  
  
|**语法**|**Description**|  
|----------------|---------------------|  
|**Privatekey**|用于导入私钥。|  
|**Publickey**|用于导入公钥。|  
|**根主键**|用于导入根钥（来自证书颁发机构）。|  
|**filename.pfx （或.cer）**|.pfx（私钥）或 .cer（公钥）文件的完整路径。|  
|**Filepassword**|对 .pfx 文件进行解锁所需的密码。|  
|**用户身份**|一个或多个 BizTalk 主机使用的服务标识。 如果不想指定主机，而想以用户帐户导入证书，请输入一个用户帐户。 **注意：**如果不希望添加**用户身份**开关，实用程序导入，并且将证书设置的所有用户。 **注意：**如果添加**用户身份**开关，但不是输入一个值，WMI 自动生成的用户标识。|  
|**密码**|服务标识用户的口令。|  
|**指纹**|特定证书的指纹（如果证书文件包含多个证书）。 **注意：**对于公共证书文件，如果该文件包含多个证书且未指定指纹，该实用程序导入文件中的所有证书。 对于私用证书文件，实用工具会提示你选择要导入的证书。|  
|**用法**|导入的私用证书的预期用途。 可以为 sign（表示用作签名证书）、decrypt（表示用作解密证书）、both（表示既用作签名证书也用作解密证书）或者 none（同样表示既用作签名证书也用作解密证书）。 **注意：**如果你设置**/Usage**交换机为 none，向导将 BizTalk 主机或 BizTalk 组上设置证书的指纹。|  
|**可导出**|可以为 `True` 或 `False`。 如果`True`，可以重新导出私钥。|  
  
## <a name="remarks"></a>注释  
 CertWizard 将私钥从 .pfx 文件导入到个人存储区中，将公钥从 .cer 文件导入到公用存储区中。 导入私钥时，证书可为传入消息的解密证书或传出消息的签名证书。  
  
 如果在命令提示符处提供的命令不完整，CertWizard 会提示你提供必需的值。  
  
## <a name="see-also"></a>另请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [导入证书使用 CertWizard 实用工具](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)