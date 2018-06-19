---
title: 如何备份主密钥 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250993"
---
# <a name="how-to-back-up-the-master-secret"></a>如何备份主密钥
您可以将主密钥服务器中的主密钥备份到 NTFS 文件系统或可移动媒体（如软盘）上。  
  
 你必须是单一登录管理员和 Windows 管理员才能执行此任务。 单一登录 (SSO) 系统将提示你输入密码。 以后若要还原该密钥，则必须提供同一密码。  
  
> [!CAUTION]
>  如果主密钥服务器崩溃和您丢失了密钥，或如果密钥已损坏，你将不能检索凭据数据库中存储数据。 你必须备份的主密钥或风险从凭据数据库丢失数据。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>使用 MMC 管理单元备份主密钥  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO Microsoft 管理控制台 (MMC) 管理单元的作用域窗格中，展开**企业单一登录**节点。  
  
3.  右键单击**系统**，然后单击**备份主密钥**。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>使用命令行备份主密钥  
  
1.  上**启动**菜单上，单击**程序**，然后单击**附件**。 右键单击 **命令提示符**, ，然后单击 **运行另存为...**。  
  
2.  选择相应的管理员，然后单击 **确定**。  
  
3.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
4.  类型`ssoconfig –backupsecret <backup file>`，其中*\<备份文件 >* 是路径和其中主密钥将备份，例如，文件的名称`A:\ssobackup.bak`。  
  
5.  提供一个密码来帮助保护此文件。  
  
     然后，将提示您确认该密码并提供密码提示以帮助您记起此密码。  
  
> [!IMPORTANT]
>  您必须将该备份文件保存到安全的位置。  
  
## <a name="see-also"></a>另请参阅  
 [如何生成主密钥](../esso/how-to-generate-the-master-secret.md)   
 [如何还原主密钥](../esso/how-to-restore-the-master-secret.md)   
 [主密钥服务器](../esso/master-secret-server.md)   
 [管理主密钥](../esso/managing-the-master-secret.md)