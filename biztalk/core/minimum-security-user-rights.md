---
title: 最低安全用户权限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42f6a3ad04af27786c3b3379d00bfde12101971
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394431"
---
# <a name="minimum-security-user-rights"></a>最低安全用户权限
组和 BizTalk Server 使用的帐户具有执行大多数任务所需的最低用户权限。 因此，有一些任务下，可能需要更多的用户权限不是由 BizTalk Server 自动授予您所属的组。 本主题内容：  
  
 [组和角色成员身份](../core/minimum-security-user-rights.md#BKMK_GroupRole)  
  
 [用于执行管理任务的用户权限](../core/minimum-security-user-rights.md#BKMK_UserRights)  
  
 [社区补充内容 – 任务列表](../core/minimum-security-user-rights.md#BKMK_Community)  
  
##  <a name="BKMK_GroupRole"></a> 组和角色成员身份  
 下表描述了在 BizTalk Server 中执行任务所需的最低安全用户权限：  
  
|任务|组或角色|  
|----------|---------------------|  
|**安装程序**||  
|安装|-本地管理员|  
|配置|-BizTalk Server 管理员<br />-本地管理员<br />-sysadmin SQL Server 角色<br />SSO 管理员<br />OLAP 管理员|  
|加入 BizTalk Server 组|-本地管理员<br />-BizTalk Server 管理员|  
|**BizTalk 管理**||  
|创建 MessageBox 数据库|-BizTalk Server 管理员<br />-sysadmin SQL Server 角色|  
|创建或删除 BizTalk 主机|-BizTalk Server 管理员<br />-BizTalk MessageBox 数据库的 db_ddladmin SQL Server 数据库角色|  
|更改主机的主机跟踪属性|-BizTalk Server 管理员<br />BAM 主导入数据库、 BizTalk MessageBox 数据库和 BizTalk 跟踪数据库的 db_securityadmin SQL Server 数据库角色|  
|创建 （安装）、 删除或更改主机实例的凭据|<ul><li>BizTalk Server Administrators</li><li>本地管理员</li><li>以下数据库所在的服务器上的 securityadmin SQL Server 角色：<br /><br /> <ul><li>BizTalk MessageBox 数据库、 BizTalk 管理数据库、 规则引擎数据库、 BizTalk 跟踪数据库、 BAM 主导入数据库</li></ul></li><li>以下数据库的 db_securityadmin SQL Server 数据库角色：<br /><br /> <ul><li>BizTalk MessageBox 数据库、 BizTalk 管理数据库、 规则引擎数据库、 BizTalk 跟踪数据库、 BAM 主导入数据库</li></ul></li></ul>|  
|启动或停止主机实例|-BizTalk Server 管理员|  
|添加或删除服务器|-BizTalk Server 管理员<br />的添加或删除的计算机上本地管理员。|  
|添加或删除接收处理程序|-BizTalk Server 管理员<br />SSO 关联管理员|  
|启动或停止应用程序、 业务流程、 发送端口和发送端口组|BizTalk Server Operators|  
|启用或禁用接收位置|BizTalk Server Operators|  
|搜索项目|BizTalk Server Operators|  
|添加适配器|-BizTalk Server 管理员<br />SSO 关联管理员|  
|备份数据库|的数据库的 BTS_BACKUP_USERS 角色<br />-托管 BizTalk 管理数据库的 SQL Server 上的 sysadmin SQL Server 角色。 **注意：** 必须配置要映射的用户使用域帐户或本地帐户下运行每个 SQL Server 实例上的 SQL Server 代理服务。|  
|使用证书配置 BizTalk 组|-BizTalk Server 管理员|  
|所有其他任务 （包括 WMI）|-BizTalk Server 管理员|  
|**操作及消息和服务实例跟踪**||  
|查看组中心页上，执行查询、 保存和加载查询|BizTalk Server Operators|  
|查看查询结果|BizTalk Server Operators|  
|常规配置和跟踪配置|BizTalk Server 管理员 （读取和写入）<br />BizTalk Server Operators （读权限）|  
|浏览运行状况监视多维数据集|-BizTalk Server 管理员|  
|查看消息属性|-BizTalk Server 管理员|  
|保存消息正文|-BizTalk Server 管理员|  
|使用**查找消息**查询|-BizTalk Server 管理员|  
|使用**查询生成**|-BizTalk Server 管理员|  
|使用业务流程调试器|-BizTalk Server 管理员|  
|查看消息流，在组中心页中使用 BizTalk Server 管理控制台的消息事件。|BizTalk Server Operators|  
|挂起、 终止或恢复多个实例|BizTalk Server Operators|  
|存档或清除跟踪数据库中的消息|-对 BizTalk 跟踪数据库的 db_owner 角色|  
|所有其他任务|-BizTalk Server 管理员|  
|**跟踪配置文件编辑器**||  
|读取或写入到 BizTalk 管理数据库|-BizTalk Server 管理员|  
|**事件总线监视 MMC**||  
|所有任务|-BizTalk Server 管理员|  
|**BizTalk WCF 服务发布向导**||  
|所有任务|-本地管理员|  
|**BizTalk Web Services 发布向导**||  
|所有任务|-本地管理员|  
|**业务活动监视**||  
|运行 BM.exe|-在 BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 db_owner SQL Server 数据库角色|  
|如果有 Analysis Services 数据库，运行 BM.exe|-在 BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 db_owner SQL Server 数据库角色<br />BAM Analysis Services 数据库中的 OLAP 管理员|  
|为 BAM 视图创建帐户|-在 BAM 主导入数据库的 db_owner SQL Server 数据库角色<br />BAM Analysis Services 数据库中的 OLAP 管理员|  
|**规则引擎 （发布规则）**||  
|部署/取消部署策略，处理与安全相关项目|的规则引擎数据库中 RE_ADMIN_USERS SQL Server 数据库角色|  
  
##  <a name="BKMK_UserRights"></a> 用于执行管理任务的用户权限  
 若要执行管理任务，使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 执行管理任务的帐户需要不同级别的用户权限，具体取决于到任务执行。  
  
 下表描述了该帐户需要对其执行任务，从最低用户权限 （级别 1） 到最高用户权限 （级别 4） 的用户权限。  
  
|用户权限的级别|授予用户权限|“任务”|  
|--------------------------|-------------------------|-----------|  
|0|BizTalk Server Operators|-基本的管理和监视任务。 不是能更改配置设置。 消息属性或内容没有访问权限。|  
|1|-BizTalk Server 管理员|-所有管理任务，需要除外级别 2-4 用户权限|  
|2|授予级别 1 的用户权限<br />-所有 SQL Server 上的 securityadmin SQL Server 角色<br />-BizTalk 跟踪、 规则引擎、 BizTalk 管理、 BAM 主导入和 BizTalk MessageBox 数据库中的 db_securityadmin 和 db_accessadmin SQL Server 数据库角色<br />-所有 BizTalk MessageBox 数据库的 db_ddladmin SQL Server 数据库角色<br />SSO 关联管理员|-创建和删除 BizTalk 主机<br />更改主机跟踪属性<br />-添加和删除服务器<br />-添加和删除接收处理程序<br />-添加适配器|  
|3|授予级别 2 的用户权限<br />的所有 BizTalk Server 运行时计算机上本地管理员|-创建和删除主机实例|  
|4|用户权限授予为级别 3<br />-在所有包含 BizTalk MessageBox 数据库的 SQL 服务器上的 sysadmin SQL Server 角色|-创建 MessageBox 数据库|  
  
##  <a name="BKMK_Community"></a> 社区补充内容 – 任务列表  
 [BizTalk Server 2013 R2 的最低安全权限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)(http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)  
  
## <a name="see-also"></a>请参阅  
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
 [为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [在 BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)