---
title: 如何还原主密钥 |Microsoft 文档
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
ms.openlocfilehash: 9241c8d9c5f6e41f47199211d0215c16526951d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970907"
---
# <a name="how-to-restore-the-master-secret"></a>如何还原主密钥
在数据恢复过程中，可能需要还原主密钥以重新使用现有的数据。 若要执行此任务，必须使用同时作为 Windows 管理员和 SSO 管理员的帐户登录主密钥服务器。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>使用 MMC 管理单元还原主密钥  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击 **系统**, ，然后单击 **还原机密**。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>使用命令行还原主密钥  
  
1.  上 **启动** 菜单上，单击 **所有程序**, ，然后单击 **附件**。 右键单击 **命令提示符**, ，然后单击 **运行另存为...**。  
  
2.  选择相应的管理员，然后单击 **确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
4.  类型**ssoconfig-restoreSecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [如何生成主密钥](../core/how-to-generate-the-master-secret.md)   
 [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)   
 [主密钥服务器](../core/master-secret-server.md)   
 [管理主密钥](../core/managing-the-master-secret.md)