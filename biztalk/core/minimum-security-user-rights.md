---
title: "最低安全用户权限 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, user accounts
- permissions, user accounts
- permissions, roles
- administrator accounts, permissions
- roles, permissions
- permissions, administrator accounts
- user accounts, permissions
- user accounts, access control
- security, permissions
ms.assetid: 44b6e7da-8e6c-40c0-a250-52ab422c0adf
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ad405afd1f69b4499b8c4650586411957a2ca3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="minimum-security-user-rights"></a>最低安全用户权限
BizTalk Server 使用的组和帐户具有执行大多数任务所需的最低用户权限。 因此，对于某些任务，你需要具有的用户权限可能高于 BizTalk Server 自动授予你所在的组的权限。 本主题内容：  
  
 [组和角色成员身份](../core/minimum-security-user-rights.md#BKMK_GroupRole)  
  
 [执行管理任务的用户权限](../core/minimum-security-user-rights.md#BKMK_UserRights)  
  
 [社区加码-任务列表](../core/minimum-security-user-rights.md#BKMK_Community)  
  
##  <a name="BKMK_GroupRole"></a>组和角色成员身份  
 下表说明了在 BizTalk Server 中执行任务需要具有的最低安全用户权限：  
  
|任务|组或角色|  
|----------|---------------------|  
|**安装程序**||  
|安装|-本地管理员|  
|配置|-BizTalk Server 管理员<br />-本地管理员<br />-sysadmin SQL Server 角色<br />-SSO 管理员<br />OLAP 管理员|  
|加入 BizTalk Server 组|-本地管理员<br />-BizTalk Server 管理员|  
|**BizTalk 管理**||  
|创建 MessageBox 数据库|-BizTalk Server 管理员<br />-sysadmin SQL Server 角色|  
|创建或删除 BizTalk 主机|-BizTalk Server 管理员<br />-BizTalk MessageBox 数据库上的 db_ddladmin SQL Server 数据库角色|  
|更改主机的“主机跟踪”属性|-BizTalk Server 管理员<br />-db_securityadmin 上 BAM 主导入数据库、 BizTalk MessageBox 数据库和 BizTalk 跟踪数据库的 SQL Server 数据库角色|  
|创建（安装）、删除或更改主机实例的凭据|<ul><li>BizTalk Server Administrators</li><li>本地 Administrators</li><li>以下数据库所在的服务器上的 securityadmin SQL Server 角色：<br /><br /> <ul><li>BizTalk MessageBox 数据库、BizTalk 管理数据库、规则引擎数据库、BizTalk 跟踪数据库和 BAM 主导入数据库</li></ul></li><li>以下数据库的 db_securityadmin SQL Server 数据库角色：<br /><br /> <ul><li>BizTalk MessageBox 数据库、BizTalk 管理数据库、规则引擎数据库、BizTalk 跟踪数据库和 BAM 主导入数据库</li></ul></li></ul>|  
|启动或停止主机实例|-BizTalk Server 管理员|  
|添加或删除服务器|-BizTalk Server 管理员<br />的在计算机上本地管理员可添加或删除。|  
|添加或删除接收处理程序|-BizTalk Server 管理员<br />-SSO Affiliate administrators|  
|启动或停止应用程序、业务流程、发送端口和发送端口组|-BizTalk Server Operators|  
|启用或禁用接收位置|-BizTalk Server Operators|  
|搜索项目|-BizTalk Server Operators|  
|将适配器添加|-BizTalk Server 管理员<br />-SSO Affiliate administrators|  
|备份数据库|-BTS_BACKUP_USERS 角色的数据库<br />-托管 BizTalk 管理数据库的 SQL Server 上的 sysadmin SQL Server 角色。 **注意：**必须配置要映射的用户使用域帐户或本地帐户下运行在每个 SQL Server 实例上的 SQL Server 代理服务。|  
|使用证书配置 BizTalk 组|-BizTalk Server 管理员|  
|所有其他任务（包括 WMI）|-BizTalk Server 管理员|  
|**操作和消息和跟踪的服务实例**||  
|查看“组中心”页、执行查询、保存并加载查询|-BizTalk Server Operators|  
|查看查询结果|-BizTalk Server Operators|  
|常规配置和跟踪配置|-BizTalk Server Administrators （读取和写入）<br />-BizTalk Server Operators （读取）|  
|浏览监视运行状况的多维数据集|-BizTalk Server 管理员|  
|查看消息属性|-BizTalk Server 管理员|  
|保存消息正文|-BizTalk Server 管理员|  
|使用**查找消息**查询|-BizTalk Server 管理员|  
|使用**查询生成**|-BizTalk Server 管理员|  
|使用业务流程调试器|-BizTalk Server 管理员|  
|使用 BizTalk Server 管理控制台查看“组中心”页中的消息流、消息事件。|-BizTalk Server Operators|  
|挂起、终止或恢复实例|-BizTalk Server Operators|  
|存档或清除跟踪数据库中的消息|-上 BizTalk 跟踪数据库的 db_owner 角色|  
|所有其他任务|-BizTalk Server 管理员|  
|**跟踪配置文件编辑器**||  
|读取或写入 BizTalk 管理数据库|-BizTalk Server 管理员|  
|**事件总线监视 MMC**||  
|所有任务|-BizTalk Server 管理员|  
|**发布向导的 BizTalk WCF 服务**||  
|所有任务|-本地管理员|  
|**发布向导的 BizTalk Web 服务**||  
|所有任务|-本地管理员|  
|**业务活动监视**||  
|运行 BM.exe|-db_owner BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 SQL Server 数据库角色|  
|如果有 Analysis Services 数据库，请运行 BM.exe|-db_owner BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 SQL Server 数据库角色<br />BAM Analysis Services 数据库中的 OLAP 管理员|  
|为 BAM 视图创建帐户|-db_owner BAM 主导入数据库中的 SQL Server 数据库角色<br />BAM Analysis Services 数据库中的 OLAP 管理员|  
|**规则引擎 （发布规则）**||  
|部署/取消部署策略，处理与安全相关的项目|-规则引擎数据库中的 RE_ADMIN_USERS SQL Server 数据库角色|  
  
##  <a name="BKMK_UserRights"></a>执行管理任务的用户权限  
 若要使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 来执行管理任务，则执行管理任务所用的帐户需要具有不同级别的用户权限，具体取决于要执行的任务。  
  
 下表说明了帐户执行各任务所需的用户权限，从最低用户权限（级别 1）到最高用户权限（级别 4）。  
  
|用户权限的级别|授予的用户权限|“任务”|  
|--------------------------|-------------------------|-----------|  
|0|-BizTalk Server Operators|-基本管理和监视任务。 无法更改配置设置。 无权访问消息属性或内容。|  
|1|-BizTalk Server 管理员|-所有管理任务，需要除外级别 2-4 的用户权限|  
|2|级别 1 授予用户权限<br />-securityadmin 所有 SQL 服务器上的 SQL Server 角色<br />-db_securityadmin 和 db_accessadmin BizTalk 跟踪、 规则引擎、 BizTalk 管理、 BAM 主导入和 BizTalk MessageBox 数据库中的 SQL Server 数据库角色<br />-所有 BizTalk MessageBox 数据库上的 db_ddladmin SQL Server 数据库角色<br />-SSO Affiliate administrators|-创建和删除 BizTalk 主机<br />更改主机跟踪属性<br />添加和删除服务器<br />添加和删除接收处理程序<br />-添加适配器|  
|3|授予为级别 2 的用户权限<br />的在 BizTalk Server 运行时的所有计算机上本地管理员|-创建和删除主机实例|  
|4|级别 3 授予用户权限<br />-包含 BizTalk MessageBox 数据库的所有 SQL Server 上的 sysadmin SQL Server 角色|-创建 MessageBox 数据库|  
  
##  <a name="BKMK_Community"></a>社区加码-任务列表  
 [BizTalk Server 2013 R2 的最低安全权限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)(http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)  
  
## <a name="see-also"></a>另请参阅  
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
 [BizTalk server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)   
 [BizTalk Server 中的 Windows 组和用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)