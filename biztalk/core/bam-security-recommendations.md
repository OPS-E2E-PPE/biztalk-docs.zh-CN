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
ms.openlocfilehash: 4818540e6adaba2568226f353e7e025b8732655b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970638"
---
# <a name="bam-security-recommendations"></a>BAM 安全建议
我们建议您遵守以下准则，以便在您的环境中保护和部署 BAM。  
  
- 如果您使用的是 [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，则管理计算机必须安装下列软件以部署 BAM：  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 客户端工具  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 集成服务  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Analysis Services  
  
  - [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)]（如果您将使用 BAM 警报）  
  
    > [!NOTE]
    >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)] 包含 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的 [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 通知服务。  
  
  > [!NOTE]
  >  用于运行分析 DTS 包的用户上下文必须是 BAM 主导入数据库和 BAM 星型架构数据库的 db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 角色的成员。 此外，分析服务在其下运行的服务帐户必须为 OLAP 管理员并且必须为 BAM 星型架构数据库的 db_owner。 有关详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=22781 ](http://go.microsoft.com/fwlink/?LinkId=22781)。  
  
- 多个用户需要对实时和存档数据的访问： 顶尖销售员、 业务经理和其他人。 这些用户必须在 BAM 主导入数据库和 BAM 分析数据库所在的域（企业域）中具有域帐户，但他们的帐户不需要具有访问 BizTalk 资源的权限。  
  
- 为了让用户可以访问 BAM 数据的视图，必须使用 BAM 管理实用程序 (BM.exe) 授予用户对视图的访问权限，此外，用户必须具有 SQL 登录名。 有关 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。  
  
- 若要向可以访问 BAM 分析数据库中的多维数据集的角色添加用户，您必须在 BAM 数据库所在的域中有一台管理计算机。  
  
- 管理 BAM 的人员必须是 BAM 主导入数据库、星型架构数据库和 BAM 存档数据库的 db_owner。 该人还必须是 BAM 分析数据库的 OLAP 管理员。  
  
- 如果要部署 Microsoft Office Excel 工作簿（.xls 文件），则必须在管理计算机上安装 Excel。 部署某个工作簿之前，请打开它，并确保宏安全性设置为高，且没有任何警告。  
  
- 如果不需要将任何业务分发到与实际数据相连的用户 BAM Excel 工作簿中，我们建议您使用 XML 文件部署工作簿。 这样就不再需要在管理计算机上安装 Excel，也不再需要验证宏的安全性。  
  
  > [!IMPORTANT]
  >  当您删除对视图的用户的权限时，您必须记得消除对该用户所设置的警报的任何订阅。 有关从警报删除订户的详细信息，请参阅[如何从警报删除订户](../core/how-to-remove-subscribers-from-an-alert.md)。  
  
## <a name="see-also"></a>请参阅  
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [针对 BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)