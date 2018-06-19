---
title: 如何还原主密钥 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250945"
---
# <a name="how-to-restore-the-master-secret"></a>如何还原主密钥
作为数据恢复过程的一部分，你可能需要还原主密钥可以重复使用现有数据。 若要执行此任务，你必须使用的是 Windows 管理员和单一登录 (SSO) 管理员的帐户登录到的主密钥服务器。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>使用 MMC 管理单元还原主密钥  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO Microsoft 管理控制台 (MMC) 管理单元的作用域窗格中，展开**企业单一登录**节点。  
  
3.  右键单击**系统**，然后单击**还原主密钥**。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>使用命令行还原主密钥  
  
1.  上**启动**菜单上，单击**程序**，然后单击**附件**。 右键单击 **命令提示符**, ，然后单击 **运行另存为...**。  
  
2.  选择相应的管理员，然后单击 **确定**。  
  
3.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
4.  类型`ssoconfig –restoresecret <restore file>`，其中*\<还原文件 >* 是路径和主密钥的存储位置的文件的名称。  
  
## <a name="see-also"></a>另请参阅  
 [如何生成主密钥](../esso/how-to-generate-the-master-secret.md)   
 [如何备份主密钥](../esso/how-to-back-up-the-master-secret.md)   
 [主密钥服务器](../esso/master-secret-server.md)   
 [管理主密钥](../esso/managing-the-master-secret.md)