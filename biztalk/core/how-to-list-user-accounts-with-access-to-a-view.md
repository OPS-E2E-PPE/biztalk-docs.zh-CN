---
title: 如何列出用户帐户具有访问权限添加到视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e27f1f48846c1eb134c2ee71bf9c00c72d4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981702"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a>如何列出具有视图访问权限的用户帐户
管理员使用**get 帐户**BAM 管理实用程序命令，以获得某个视图角色，这意味着有权访问指定的视图的所有用户帐户列表的所有用户帐户。  
  
 有关查看 BAM 视图的信息，请参阅[如何列出 BAM 视图](../core/how-to-list-bam-views.md)。  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a>列出具有视图访问权限的用户帐户  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
3. 类型**bm 获取帐户的视图：\<视图名称\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)