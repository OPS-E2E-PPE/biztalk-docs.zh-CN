---
title: 使用 MMC 导入证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d813adad739f7843308bcd3c53aa242ff97520c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283597"
---
# <a name="importing-certificates-using-mmc"></a>使用 MMC 导入证书
本主题介绍如何导入的数字证书，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]用于验证贸易合作伙伴、 解密传入消息，或加密或签名传出消息。  
  
 此过程使用证书管理单元中的 Microsoft 管理控制台 (MMC)。 这一手动流程将证书导入证书存储中，无需单独配置证书的使用。 此外可以通过使用自动配置为证书使用 CertWizard 实用工具导入证书。  
  
 若要导入私用证书，必须使用 BizTalk 主机在其下运行的用户帐户。  
  
### <a name="to-import-a-public-key-certificate"></a>若要导入公钥证书  
  
1. 复制到硬盘上的位置服务器正在向其复制证书的公钥 (.cer) 证书文件。  
  
2. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
3. 在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开**证书 （本地计算机）**。 登录的用户必须具有计算机的管理权限。  
  
4. 右键单击**其他人**，依次指向**的所有任务**，然后单击**导入**。  
  
5. 上**证书导入向导欢迎**页上，单击**下一步**。  
  
6. 上**导入的文件**页上，单击**浏览**并找到包含证书文件的文件夹。 选择想要导入证书，然后单击的文件**打开**。  
  
7. 上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**. 如果选择**将所有证书都放入下列存储**，单击**浏览**，选择证书存储区，单击**确定**，然后单击**下一步**.  
  
8. 单击 **“完成”**。  
  
### <a name="to-import-a-private-key-certificate"></a>若要导入私钥证书  
  
1. 复制私钥 (.pfx) 证书文件复制到硬盘上的服务器正在向其复制证书的位置。  
  
2. 单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。  
  
   > [!NOTE]
   >  有关\<*承载服务*\>，键入你在安装时自动为主机服务中选择的服务名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
3. 键入的密码\<*承载服务*\>，然后按**Enter**。  
  
4. 在 Microsoft 管理控制台中，在**文件**菜单上，单击**添加/删除管理单元中**。  
  
5. 在添加/删除管理单元对话框中，单击**添加**。  
  
6. 在添加独立管理单元对话框中，选择**证书**，单击**添加**，单击**关闭**，然后单击**确定**。  
  
7. 在 Microsoft 管理控制台中，展开**证书-当前用户**，右键单击**个人**，指向**所有任务**，然后单击**导入**.  
  
8. 上**证书导入向导欢迎**页上，单击**下一步**。  
  
9. 上**导入的文件**页上，单击**浏览**并找到包含您要导入的证书的.pfx 证书文件的文件夹。 选择相应的文件，然后单击**打开**。  
  
10. 上**密码**页上，在**密码**框中，键入私钥文件的密码。  
  
11. 选择**启用强私钥保护**或**标志此密钥为可导出**，然后单击**下一步**。  
  
12. 上**证书存储区**页上，选择**自动选择基于证书的类型的证书**或**将所有证书都放入下列存储**. 如果选择**将所有证书都放入下列存储**，单击**浏览**，选择在存储区，单击**确定**，然后单击**下一步**。  
  
13. 上**正在完成证书导入向导**页上，单击**完成**。  
  
## <a name="see-also"></a>请参阅  
 [配置使用 MMC 导入的证书](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md)   
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)