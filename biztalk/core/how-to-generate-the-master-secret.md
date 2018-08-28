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
ms.openlocfilehash: 41e7f000dbb53a054259ba18f5c1d118531c8138
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978334"
---
# <a name="how-to-generate-the-master-secret"></a>如何生成主密钥
必须具有对主密钥服务器的管理员权限才能执行此任务。 此外，您还必须从主密钥服务器执行此任务。  
  
 安装企业单一登录的第一台服务器就是主密钥服务器。  
  
> [!IMPORTANT]
>  在 SSO 系统中只能有一台主密钥服务器。  
> 
> [!NOTE]
>  当企业单一登录安装的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装中，主密钥生成配置向导的一部分。 如果希望生成新的主密钥，则只需要执行此任务。  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a>使用 MMC 管理单元生成主密钥  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**生成机密**。  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a>使用命令行生成主密钥  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoconfig-generateSecret \<*备份文件*\>**，其中\<*备份文件*\>的名称使用包含主密钥的文件。  
  
     此时，系统将提示您输入密码以保护刚刚创建的文件。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)   
 [主密钥服务器](../core/master-secret-server.md)   
 [管理主密钥](../core/managing-the-master-secret.md)