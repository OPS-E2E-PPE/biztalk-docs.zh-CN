---
title: 如何生成主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2104dae9d01ef56d4e0d99a2af887db8c68131e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337708"
---
# <a name="how-to-generate-the-master-secret"></a>如何生成主密钥
若要执行此任务，必须在主服务器上具有管理员权限。 此外，你必须从主密钥服务器执行此任务。  
  
 安装企业单一登录的第一个服务器将成为在主密钥服务器。  
  
> [!IMPORTANT]
>  SSO 系统中可以有一个主密钥服务器。  
> 
> [!NOTE]
>  当企业单一登录安装的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装中，主密钥生成配置向导的一部分。 您只需要执行此任务，如果你想要生成新的主密钥。  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a>若要生成使用 MMC 管理单元中的主密钥  
  
1.  在“开始”  菜单上，依次单击“所有程序”  、“Microsoft Enterprise Single Sign-On”  和“SSO 管理”  。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**生成机密**。  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a>若要生成使用命令行的主密钥  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoconfig-generateSecret \<*备份文件*\>** ，其中\<*备份文件*\>的名称使用包含主密钥的文件。  
  
     系统将提示您输入密码以保护刚刚创建的文件。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)   
 [主密钥服务器](../core/master-secret-server.md)   
 [管理主密钥](../core/managing-the-master-secret.md)