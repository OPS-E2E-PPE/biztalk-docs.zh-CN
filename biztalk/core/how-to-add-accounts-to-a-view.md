---
title: 如何将帐户添加到视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53e1811e30ed1c74023b4402bcfc0f0d86b2c516
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343323"
---
# <a name="how-to-add-accounts-to-a-view"></a>如何将帐户添加到视图
管理员使用**添加帐户**命令以将用户与 BAM 视图相关联，以防止未经授权的访问 BAM Excel 电子表格视图。 当用户保存 BAM 视图时，视图将引用隐藏工作簿中的 SQL 连接字符串。 工作簿保护，但必须确保已保护文档。  
  
 将用户与 BAM 视图相关联，当你到视图的用户或组向其授予访问权限限制访问。  
  
> [!IMPORTANT]
>  如果使用的实时聚合 (Rta)，使用添加用户**添加帐户**不会自动授予登录到运行 SQL Server 的计算机的权限。 如果使用 Rta，请考虑建立一个包含的所有用户需要查看的 Rta 视图的 Windows 用户组。 授予该组显式上托管 BAM 主导入数据库的 SQL server 的 SQL Server 登录权限。  
  
 有关查看 BAM 视图的信息，请参阅[如何列出 BAM 视图](../core/how-to-list-bam-views.md)。  
  
### <a name="to-add-an-account-to-a-view"></a>若要将帐户添加到视图  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。 按 **Enter**。  
  
3. 类型**bm 添加帐户-AccountName:\<帐户名称\>的视图：\<视图名称\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)