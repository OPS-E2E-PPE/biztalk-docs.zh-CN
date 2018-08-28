---
title: 如何恢复企业单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56953fcab29b53f23ba3097296a74aeb67a17c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973118"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>如何恢复企业单一登录
必须先恢复企业单一登录 (SSO)，然后才能恢复 BizTalk Server。  
  
## <a name="prerequisites"></a>必要條件  
  
-   若要执行此项任务，您必须以 Single Sign-On Administrators 组成员和 Administrators 组成员的身份登录。  
  
-   您必须拥有配置 SSO 时所使用的密码。  
  
-   远程服务器上所有数据库都保持不变。  
  
-   备份主密钥文件保持不变，且保存到一个安全的地方。  
  
### <a name="to-recover-enterprise-single-sign-on"></a>恢复企业单一登录  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
2. 在 Microsoft BizTalk Server 配置，在控制台树中，单击**企业 SSO**。  
  
3. 在细节窗格中，选择**启用企业单一登录此计算机上**，然后单击**加入现有 SSO 系统**。  
  
4. 在中**数据存储区**，输入托管 SSO 数据库和 SSO 数据库的名称的 SQL server 的名称。  
  
5. 在中**Windows 服务**，最初安装和配置 BizTalk Server 时使用的 SSO 服务帐户输入用户名和密码。  
  
   > [!NOTE]
   >  您也可使用其他帐户，但必须是 Single Sign-On Administrators 组的成员。  
  
6. 单击“应用配置”。  
  
    此时将显示未检索到主密钥的警告。 您可使用事件查看器来验证企业单一登录服务是否已经启动，并正在该计算机上运行。  
  
7. 单击**文件**，然后单击**退出**。  
  
8. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，键入：  
  
     **cd Program Files\Common Files\Enterprise Single Sign-on**  
  
10. 在命令提示符下，键入：  
  
     **ssoconfig-restoreSecret***\<backupfile  \>*  
  
     其中*\<backupfile\>* 是您备份主密钥文件的名称。  
  
     当**ssoconfig**提示您输入备份文件的密码，输入配置 SSO 时指定的密码。 如果密码正确无误， **ssoconfig**会显示以下消息：  
  
     **操作已成功完成**  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [配置企业 SSO 使用 BizTalk Server 配置](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)