---
title: 如何还原主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04852571be9294ee62733bd78c884b407f2fb5b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384130"
---
# <a name="how-to-restore-the-master-secret"></a>如何还原主密钥
作为数据恢复过程的一部分，您可能需要还原主密钥以重新使用现有数据。 若要执行此任务，您必须登录到主密钥服务器与 Windows 管理员和 SSO 管理员帐户。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>若要还原主密钥使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**还原机密**。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>若要还原主密钥使用命令行  
  
1.  上**启动**菜单上，单击**所有程序**，然后单击**附件**。 右键单击**命令提示符**，然后单击**运行方式...**.  
  
2.  选择合适的管理员，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssoconfig-restoreSecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何生成主密钥](../core/how-to-generate-the-master-secret.md)   
 [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)   
 [主密钥服务器](../core/master-secret-server.md)   
 [管理主密钥](../core/managing-the-master-secret.md)