---
title: 部署进程 |Microsoft Docs
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
ms.openlocfilehash: 89b5e3640626ce63a58532568b08b7290bc40c4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389742"
---
# <a name="deployment-process"></a>部署过程
以下步骤进行安全的企业单一登录部署了高级概述。 要在 SQL Server 中执行的操作的详细过程，请参阅 SQL Server 文档。  
  
1.  在 SQL Server 域控制器上，使用新建信任向导来创建具有以下属性的信任：  
  
    -   **名称：** ORCH.com  
  
    -   **方向：** 双向  
  
    -   **信任方：** 仅限此域  
  
    -   **传出信任身份验证级别-本地域：** 选择性身份验证  
  
    -   **密码：** 选择的密码  
  
    -   **确认传出信任：** 是  
  
    -   **确认传入信任：** 否  
  
2.  在 ORCH.com 域控制器上，使用新建信任向导来创建具有以下属性的信任：  
  
    -   **名称：** SQL.com  
  
    -   **方向：** 双向  
  
    -   **信任方：** 仅限此域  
  
    -   **传出信任身份验证级别-本地域：** 选择性身份验证  
  
    -   **密码：** 必须为 ORCH.com 的密码相同  
  
    -   **确认传出信任：** 是  
  
    -   **确认传入信任：** 否  
  
3.  在 ORCH.com 域控制器上，从 SQL.COM 设置传入域范围信任。  
  
4.  在 SQL.com 域控制器设置从 ORCH.COM 的传出域范围信任。  
  
5.  在 ORCH.com 域控制器上，域功能级别提升到 Windows Server 2008 SP2 或 Windows Server 2008 R2。  
  
6.  在 ORCH 域中，创建以下新用户：  
  
    -   ORCH\SSOSvcUser  
  
    -   ORCH\TestAppUser  
  
    -   ORCH\AffAppUser  
  
7.  添加**充当操作系统的一部分**到 SSOSvcUser 和 TestAppUser。  
  
8.  添加**进行身份验证允许**到 ORCH\TestAdmin 特权。  
  
9. 将 ORCH\SSOSvcUser 添加到 SQL 域中的 SQL2 中。 （此步骤需要使用 Active Directory MMC 中的高级视图。）  
  
10. 在 SQL2 计算机上创建以下两个新登录名：  
  
    -   ORCH\TestAdmin  
  
    -   ORCH\SSOSvcUser  
  
11. 在 SQL2 域上创建两个域全局组：  
  
    -   ORCH\SSOAdminGroup  
  
    -   ORCH\SSOAffAdminGroup  
  
12. 添加**进行身份验证允许**到 ORCH\SSOAdminGroup 组的权限。  
  
13. 在 SQL2 数据库上创建以下新登录名：  
  
    -   ORCH\SSOAdminGroup  
  
14. 安装主密钥服务器，如下所示：  
  
    -   使用 ORCH\TestAdmin 登录到 NTS5。  
  
    -   安装 ESSO 将 SQL2 用作主密钥服务器。  
  
15. 使用 ORCH\TestAdmin，登录到 HIS1 并安装企业单一登录。 使用数据库服务器名称 SQL2 为 SSO 联接 HIS2，来将 ESSO 配置。  
  
16. 安装使用 ORCH\TestAdmin 在 HIS3 上的企业单一登录管理员实用程序。  
  
17. 将以下用户添加到以下组：  
  
    -   将 ORCH\TestAppUser 添加到 orch\ssoadmingroup 中  
  
    -   将 ORCH\AffAppUser 添加到 orch\testaffusergroup 中  
  
18. SQL Server Enterprise Edition HIS3 上安装，并添加登录名 ORCH\AffAppUser。  
  
19. 在 HIS1 计算机上打开命令提示符并使用以下命令设置约束委派和协议转换：  
  
    -   **setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**  
  
    -   **setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**  
  
20. 上**ORCH\SSOSvcUser**并**ORCH\TestAppUser**属性页中，通过选择以下选项设置为这两个用户帐户适当的委托：  
  
    -   **信任仅委派到指定服务的用户**  
  
    -   **使用任何身份验证协议**  
  
21. 在 HIS1 计算机上使用 ORCH\TestAdmin，执行以下操作：  
  
    -   将 ORCH\TestAppUser 添加到远程桌面用户组  
  
    -   授予**进行身份验证之后模拟**权限授予 ORCH\SSOSvcUser  
  
    -   授予**进行身份验证之后模拟**特权授予 ORCH\TestAppUser  
  
22. 通过登录到 HIS1 验证您的部署使用 ORCH\TestAppUser 并运行以下应用程序配置：  
  
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
  
## <a name="see-also"></a>请参阅  
 [SSO 部署概述](../core/sso-deployment-overview.md)