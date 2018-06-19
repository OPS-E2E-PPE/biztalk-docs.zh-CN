---
title: 部署过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240661"
---
# <a name="deployment-process"></a>部署过程
以下步骤对企业单一登录的安全部署进行了高级概述。 有关在 SQL Server 中执行操作的详细过程，请参阅 SQL Server 文档。  
  
1.  在 SQL Server 域控制器上，使用新建信任向导可创建具有以下属性的信任：  
  
    -   **名称：** ORCH.com  
  
    -   **方向：** 双向  
  
    -   **边：** 仅限于此域  
  
    -   **传出信任身份验证级别的本地域：** 选择性身份验证  
  
    -   **密码：** 选择一个密码  
  
    -   **确认传出信任：** 是  
  
    -   **确认传入信任：** 否  
  
2.  在 ORCH.com 域控制器上，使用新建信任向导可创建具有以下属性的信任：  
  
    -   **名称：** SQL.com  
  
    -   **方向：** 双向  
  
    -   **边：** 仅限于此域  
  
    -   **传出信任身份验证级别的本地域：** 选择性身份验证  
  
    -   **密码：** 必须是与密码相同的 ORCH.com  
  
    -   **确认传出信任：** 是  
  
    -   **确认传入信任：** 否  
  
3.  在 ORCH.com 域控制器上，为从 SQL.COM 的传入通信设置域范围信任。  
  
4.  在 SQL.com 域控制器上，为从 ORCH.COM 的传出通信设置域范围信任。  
  
5.  在 ORCH.com 域控制器上，将域功能级别提升到 Windows Server 2008 SP2 或 Windows Server 2008 R2。  
  
6.  在 ORCH 域中，创建以下新用户：  
  
    -   ORCH\SSOSvcUser  
  
    -   ORCH\TestAppUser  
  
    -   ORCH\AffAppUser  
  
7.  添加**充当操作系统的一部分**SSOSvcUser 和 TestAppUser。  
  
8.  添加**以进行身份验证允许**ORCH\TestAdmin 特权。  
  
9. 将 ORCH\SSOSvcUser 添加到 SQL 域的 SQL2 中。 （此步骤需要使用 Active Directory MMC 中的高级视图。）  
  
10. 在 SQL2 计算机上，创建以下两个新登录名：  
  
    -   ORCH\TestAdmin  
  
    -   ORCH\SSOSvcUser  
  
11. 在 SQL2 域上，创建两个域全局组：  
  
    -   ORCH\SSOAdminGroup  
  
    -   ORCH\SSOAffAdminGroup  
  
12. 添加**以进行身份验证允许**ORCH\SSOAdminGroup 组特权。  
  
13. 在 SQL2 数据库上，创建以下新登录名：  
  
    -   ORCH\SSOAdminGroup  
  
14. 按照以下步骤安装主密钥服务器：  
  
    -   使用 ORCH\TestAdmin 登录到 NTS5。  
  
    -   将 SQL2 用作主密钥服务器以安装 ESSO。  
  
15. 使用 ORCH\TestAdmin 登录到 HIS1，然后安装企业单一登录。 使用数据库服务器名称 SQL2 来将 ESSO 配置为 SSO 联接 HIS2。  
  
16. 使用 ORCH\TestAdmin 在 HIS3 上安装企业单一登录管理实用工具。  
  
17. 将以下用户添加到以下组中：  
  
    -   将 ORCH\TestAppUser 添加到 ORCH\SSOAdminGroup 中  
  
    -   将 ORCH\AffAppUser 添加到 ORCH\TestAffUserGroup 中  
  
18. 在 HIS3 上安装 SQL Server Enterprise Edition，并添加登录名 ORCH\AffAppUser。  
  
19. 在 HIS1 计算机上，打开命令提示符，使用以下命令设置约束委托和协议转换：  
  
    -   **setspn-A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**  
  
    -   **setspn-A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**  
  
20. 上**ORCH\SSOSvcUser**和**ORCH\TestAppUser**属性页中，通过选择以下选项来设置这两个用户帐户的正确委派：  
  
    -   **信任仅委派到指定服务的用户**  
  
    -   **使用任何身份验证协议**  
  
21. 在 HIS1 计算机上使用 ORCH\TestAdmin，执行以下操作：  
  
    -   将 ORCH\TestAppUser 添加到远程桌面用户组中  
  
    -   授予**模拟身份验证后**ORCH\SSOSvcUser 特权  
  
    -   授予**模拟身份验证后**ORCH\TestAppUser 特权  
  
22. 通过使用 ORCH\TestAppUser 登录到 HIS1 并运行以下应用程序配置，以验证您的部署：  
  
     运行 LogonExternalUser 测试。  
  
    ```  
    <SSO>  
       <application name="TestApp">  
          <description>An SSO Test Affiliate Application</description>  
          <contact>AffAppUser@ESSOV2.EBiz.Com</contact>  
          <appUserAccount>ORCH\TestAffAdminGroup</appUserAccount>  
          <appAdminAccount>ORCH\TestAffUserGroup</appAdminAccount>  
          <field ordinal="0" label="User ID" masked="no" />  
          <field ordinal="1" label="Password" masked="yes" />  
          <flags   
             groupApp="no"   
             configStoreApp="no"   
             allowTickets="no"   
             validateTickets="yes"   
             allowLocalGroups="yes"   
             ticketTimeout="yes"   
             adminGroupSame="no"   
             enableApp="yes"   
             hostInitiatedSSO="yes"   
             validatePassword="yes"/>  
       </application>  
    </SSO>  
  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [SSO 部署概述](../core/sso-deployment-overview.md)