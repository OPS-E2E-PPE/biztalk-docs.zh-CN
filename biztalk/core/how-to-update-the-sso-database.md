---
title: 如何更新 SSO 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbb7ea650a2845d8ebdcdcc2204f8346c5737c43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971315"
---
# <a name="how-to-update-the-sso-database"></a>如何更新 SSO 数据库
可以使用 MMC 管理单元或命令行来更改 SSO 数据库中诸如主密钥服务器标识、帐户名、数据库中的审核、票证超时和凭据缓存超时之类的全局信息。  
  
## <a name="changing-timeouts-for-the-sso-system"></a>更改 SSO 系统的超时  
 可以在企业单一登录 (SSO) 系统级别上修改两个超时：  
  
 **票证超时。** 此属性指定 SSO 颁发的票据的有效时长。 为满足企业中使用 SSO 的大部分情况，默认的票证超时为 2 分钟。 SSO 管理员可以根据应用程序要求来更改此属性。  
  
 **凭据缓存超时值。** 此属性可指定所有 SSO 服务器的凭据缓冲超时。 SSO 服务器在第一次查找后将对凭据进行缓存。 默认情况下，凭据缓存超时为 60 分钟。 SSO 管理员可以根据安全要求将此属性更改为适当的值。  
  
 通过更新 SSO 数据库，可以更改这两种超时。  
  
 更新 SSO 数据库的示例 XML 文件如下所示：  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
<secretServer>ComputerA</secretServer>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
<ticketTimeout>2</ticketTimeout>  
<credCacheTimeout>60</credCacheTimeout>  
</globalInfo>  
</sso>  
  
```  
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a>使用 MMC 管理单元更改超时  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  在“系统属性”  对话框上，单击“常规”  选项卡。  
  
5.  输入相应的设置，然后单击“确定” 。  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>使用 MMC 管理单元更新 SSO 数据库  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“升级数据库” 。  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a>使用命令行更新 SSO 数据库  
  
1.  依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-updatedb\<更新文件\>**，其中**\<更新文件\>** 是路径和文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)   
 [使用 SSO](../core/using-sso.md)