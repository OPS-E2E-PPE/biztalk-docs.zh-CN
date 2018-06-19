---
title: 如何将帐户添加到视图 |Microsoft 文档
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
ms.openlocfilehash: 808d5395452733d43337e0883b306b7757a7da08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968667"
---
# <a name="how-to-add-accounts-to-a-view"></a>如何将帐户添加到视图
管理员使用**添加帐户**命令以将用户与 BAM 视图关联，以防止未经授权的访问的 BAM Excel 电子表格视图。 当用户保存 BAM 视图时，视图将引用隐藏工作簿中的 SQL 连接字符串。 工作簿受到保护，但你必须确保已保护文档。  
  
 将用户与 BAM 视图关联，限制访问权限向用户或向其授予访问权限的组视图。  
  
> [!IMPORTANT]
>  如果你使用的实时聚合 (Rta)，与添加用户**添加帐户**不会自动授予登录权限运行 SQL Server 的计算机。 如果你使用的 Rta，考虑建立包含所有需要查看的 Rta 视图的用户的 Windows 用户组。 组托管 BAM 主导入数据库的 SQL 服务器上的显式 SQL Server 登录权限的 Grant。  
  
 有关查看 BAM 视图的信息，请参阅[如何列表 BAM 视图](../core/how-to-list-bam-views.md)。  
  
### <a name="to-add-an-account-to-a-view"></a>若要将帐户添加到视图  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。 按 **Enter**。  
  
3.  类型**bm 添加帐户 AccountName:\<帐户名称\>的视图：\<视图名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)