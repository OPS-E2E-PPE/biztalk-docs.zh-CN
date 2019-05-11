---
title: CertWizard | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b028deda4ef180a4983e1c58fa7a9487804a0232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284776"
---
# <a name="certwizard"></a>CertWizard
使用 CertWizard 实用工具导入证书从.pfx 或.cer 文件到专用或公用存储区中，以用于 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\  
  
## <a name="running-certwizard"></a>运行 CertWizard  
  
#### <a name="to-run-certwizard"></a>若要运行 CertWizard  
  
1. 打开命令提示符。  
  
2. 将移动到\<*驱动器*\>\ Program Files (x86)\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
3. 在命令提示符处，键入**CertWizard**，键入必需的和适当的开关，，然后按 ENTER。  
  
## <a name="syntax-for-certwizard"></a>CertWizard 的语法  
 下面显示的语法，用于启动此命令行实用程序：  
  
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
  
|**语法**|**说明**|  
|----------------|---------------------|  
|**Privatekey**|用于导入私钥。|  
|**Publickey**|用于导入公钥。|  
|**Rootkey**|用于导入根钥 — 从证书颁发机构。|  
|**filename.pfx （或.cer）**|.Pfx （私钥） 或.cer （公钥） 文件的完整路径。|  
|**Filepassword**|若要解锁的.pfx 文件所需的密码。|  
|**Useridentity**|一个或多个 BizTalk 主机使用的服务标识。 如果不想指定主机，但想要导入用户帐户下的证书，请输入用户帐户。 **注意：** 如果不添加**Useridentity**切换，实用程序导入，并为所有用户设置的证书。 **注意：** 如果您将添加**Useridentity**开关，但不要输入一个值，WMI 会自动生成的用户标识。|  
|**密码**|服务标识用户的密码。|  
|**Thumbprint**|用例文件中的特定证书的指纹包含多个证书。 **注意：** 对于公共证书文件，如果该文件包含多个证书，并且不指定指纹，实用工具将导入该文件中的所有证书。 对于私用证书文件，该实用工具会提示您选择要导入的证书。|  
|**Usage**|导入私钥证书的预期使用情况。 可以为 sign （表示用作签名证书）、 decrypt （表示用作解密证书）、 both （表示为签名证书和解密证书的证书），或 none （也用于签名的证书和解密证书的证书). **注意：** 如果您设置 **/Usage**切换为无，该向导将 BizTalk 主机或 BizTalk 组上设置证书的指纹。|  
|**Exportable**|可以是`True`或`False`。 如果`True`，私钥可重新导出。|  
  
## <a name="remarks"></a>备注  
 CertWizard 将私钥从.pfx 文件导入到个人存储中，并将公钥从.cer 文件导入公共存储。 在导入私钥，证书可以是传入消息的解密证书或传出消息的签名证书。  
  
 如果您不要在命令提示符处提供完整的命令，CertWizard 会提示你提供所需的值。  
  
## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [使用 CertWizard 实用程序导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
