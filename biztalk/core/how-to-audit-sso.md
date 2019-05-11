---
title: 如何审核 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315ef88247d61e26056467232bf5a460c6c7fed1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387179"
---
# <a name="how-to-audit-sso"></a>如何审核 SSO
可以使用 MMC 管理单元或命令行设置这两个成功和失败审核级别。 审核的结果存储在事件日志和数据库的审核日志。  
  
 SSO 管理员可以设置适合其公司策略的成功和失败审核级别。 可以将成功和失败审核设置为以下级别之一：  
  
 0 = 无  
  
 1 = 低  
  
 2 = 中等  
  
 3 = 高。 此级别不发出多尽可能的审核消息。  
  
 正审核的默认值为 0 （无）、 和失败审核的默认值为 1 （低）。  
  
 若要更改数据库级别审核，必须更新 SSO 数据库使用的 XML 文件。 更新 SSO 数据库的示例 XML 文件如下所示：  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a>若要审核上单一登录使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  上**系统属性**对话框中，单击**审核**选项卡。  
  
5.  输入相应的设置，然后单击“确定” 。  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a>若要实现单一登录使用命令行审核  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoconfig-auditlevel\<正\>\<负\>**，其中**\<正\>** 的级别审核时操作都成功，并**\<负\>** 是操作失败时的审核级别。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-audit-the-sso-database"></a>若要审核 SSO 数据库  
  
1. 依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。  
  
2. 在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型**ssomanage – updatedb\<更新文件\>**，其中<strong>\<更新文件\></strong>是路径和文件的名称。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [使用 SSO](../core/using-sso.md)