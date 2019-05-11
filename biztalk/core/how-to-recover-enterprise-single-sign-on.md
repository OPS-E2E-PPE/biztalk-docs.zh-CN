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
ms.openlocfilehash: 0e42139a9e286024487417a005963eb677b880a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384438"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>如何恢复企业单一登录
可以恢复 BizTalk Server 之前，必须先恢复企业单一登录 (SSO)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您必须登录为 Single Sign-on Administrators 组的成员和 Administrators 组的成员，才能执行此任务。  
  
-   您必须配置 SSO 时所用的密码。  
  
-   所有数据库都是在远程服务器上保持不变。  
  
-   备份主密钥文件在安全的位置保持不变，且保存。  
  
### <a name="to-recover-enterprise-single-sign-on"></a>若要恢复企业单一登录  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。  
  
2. 在 Microsoft BizTalk Server 配置，在控制台树中，单击**企业 SSO**。  
  
3. 在细节窗格中，选择**启用企业单一登录此计算机上**，然后单击**加入现有 SSO 系统**。  
  
4. 在中**数据存储区**，输入托管 SSO 数据库和 SSO 数据库的名称的 SQL server 的名称。  
  
5. 在中**Windows 服务**，最初安装和配置 BizTalk Server 时使用的 SSO 服务帐户输入用户名和密码。  
  
   > [!NOTE]
   >  可以使用不同的帐户，但它必须是 Single Sign-on Administrators 组的成员。  
  
6. 单击**应用配置**。  
  
    显示未检索到没有主密钥的警告。 您可以使用事件查看器来验证企业单一登录服务已经启动并运行在计算机上。  
  
7. 单击**文件**，然后单击**退出**。  
  
8. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，键入：  
  
     **cd Program Files\Common Files\Enterprise Single Sign-on**  
  
10. 在命令提示符下，键入：  
  
     **ssoconfig -restoreSecret**  *\<backupfile\>*  
  
     其中*\<backupfile\>* 是您备份主密钥文件的名称。  
  
     当**ssoconfig**提示您输入备份文件的密码，输入配置 SSO 时指定的密码。 如果密码正确无误， **ssoconfig**会显示以下消息：  
  
     **操作已成功完成**  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [配置企业 SSO 使用 BizTalk Server 配置](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)