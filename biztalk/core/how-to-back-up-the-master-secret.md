---
title: 如何备份主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e38ebeb861d26bfdb31819ea1d94d830bf58fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387095"
---
# <a name="how-to-back-up-the-master-secret"></a>如何备份主密钥
你可以备份中的主密钥对主密钥服务器到 NTFS 文件系统或可移动媒体，如软盘。  
  
 您必须是单一登录管理员和 Windows 管理员才能执行此任务。 SSO 系统将提示您输入密码。 若要还原该密钥更高版本，必须指定相同的密码。  
  
> [!CAUTION]
>  如果主密钥服务器失败，并且丢失了密钥，或者密钥损坏，您将不能检索存储在 SSO 数据库中的数据。 您必须备份主密钥或风险会丢失 SSO 数据库中的数据。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>若要备份主密钥使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**备份密钥**。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>若要备份主密钥使用命令行  
  
1. 上**启动**菜单上，单击**所有程序**，然后单击**附件**。 右键单击**命令提示符**，然后单击**运行方式...**.  
  
2. 选择合适的管理员，然后单击**确定**。  
  
3. 在命令行中，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4. 类型 * * ssoconfig-backupSecret *\<备份文件\>**<em>，其中 *\<备份文件\></em>是路径和要备份主密钥的文件的名称。 例如，A:\ssobackup.bak  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5. 提供一个密码来保护此文件。 若要确认该密码并提供密码提示，以帮助您记住此密码，系统将提示您。  
  
> [!IMPORTANT]
>  必须保存并将备份文件存储在安全的位置。  
  
## <a name="see-also"></a>请参阅  
 [如何生成主密钥](../core/how-to-generate-the-master-secret.md)   
 [如何还原主密钥](../core/how-to-restore-the-master-secret.md)   
 [主密钥服务器](../core/master-secret-server.md)   
 [管理主密钥](../core/managing-the-master-secret.md)