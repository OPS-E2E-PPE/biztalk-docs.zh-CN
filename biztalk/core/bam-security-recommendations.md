---
title: BAM 安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- managing [BAM], security
- BAM, security
ms.assetid: 73613123-c1ed-477a-9f5c-342b2573c975
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60a844841eebe3e302b9b94f3d0c7e946522f6c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358430"
---
# <a name="bam-security-recommendations"></a>BAM 安全建议
我们建议您遵循这些准则以保护和环境中部署 BAM:  
  
- 如果使用的[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，管理计算机必须安装下列软件才能部署 BAM:  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 客户端工具  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 集成服务  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Analysis Services  
  
  - [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)]如果你将使用 BAM 警报  
  
    > [!NOTE]
    >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)] 包含[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]为 Notification Services [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]。  
  
  > [!NOTE]
  >  在其下运行分析 DTS 包的用户上下文必须是 db_owner 的成员[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]BAM 主导入和 BAM 星型架构数据库的角色。 此外，在其下运行 Analysis Services 的服务帐户必须是 OLAP 管理员并且必须是 BAM 星型架构数据库的 db_owner。 有关详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=22781 ](http://go.microsoft.com/fwlink/?LinkId=22781)。  
  
- 多个用户需要对实时和存档数据的访问： 顶尖销售员、 业务经理和其他人。 这些用户必须在 BAM 主导入和 BAM 分析数据库 （企业域），但其帐户不需要有权访问 BizTalk 资源的域中具有域帐户。  
  
- 用户可以访问 BAM 数据的视图必须使用 BAM 管理实用程序 (BM.exe) 授予用户权限到视图，并且，用户必须具有 SQL 登录名。 有关 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。  
  
- 若要将用户添加到 BAM 分析数据库中有权访问多维数据集的角色，必须在 BAM 数据库所在的域具有一台管理计算机。  
  
- 管理 BAM 的人员必须是 BAM 主导入、 星型架构和 BAM 存档数据库的 db_owner。 该用户还必须是 BAM 分析数据库的 OLAP 管理员。  
  
- 如果要部署 Microsoft Office Excel 工作簿 （.xls 文件），则必须在管理计算机上安装 Excel。 在部署某一工作簿之前，将其打开，并确保的宏安全性已设为高，不会出现任何警告。  
  
- 如果没有要分发到的用户 BAM Excel 工作簿连接到真实数据的业务需求，我们建议使用 XML 文件部署工作簿。 这样就无需在管理计算机上安装 Excel，并且需要验证宏安全级别。  
  
  > [!IMPORTANT]
  >  当您删除对视图的用户的权限时，您必须记得消除对该用户所设置的警报的任何订阅。 有关从警报删除订户的详细信息，请参阅[如何从警报删除订户](../core/how-to-remove-subscribers-from-an-alert.md)。  
  
## <a name="see-also"></a>请参阅  
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [针对 BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)