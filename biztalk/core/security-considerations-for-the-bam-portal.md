---
title: "BAM 门户的安全注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-the-bam-portal"></a>BAM 门户的安全注意事项
遵循最小权限原则，用户帐户在 BAM 门户中应使用受限制的权限来执行日常的任务。 在设置 BAM 的用户帐户时请记住以下几点，通过适当的用户访问权限来平衡安全性。  
  
## <a name="user-accounts"></a>用户帐户  
 使用最小权限的用户帐户不能使用 BAM 门户分布式的 navigationfeature。 要使用此功能，必须授予这些帐户足够的权限，使其不仅可以访问本地计算机上的 Web Services，也能够访问远程计算机上的 Web Services。  
  
 BAM Web Services 的用户帐户必须具有访问所有引用的数据库的权限，并且在引用的数据库中必须是 BAM_ManagementWS 角色的成员。  
  
 对于下面的用户类型，应注意以下事项：  
  
-   域用户必须具有对要访问的主导入数据库的宿主远程计算机的访问权限。  
  
-   指定为“本地用户”角色的用户无法使用分布式导航。  
  
## <a name="administrator-accounts"></a>管理员帐户  
 管理员必须是 securityadmin 或 sysadmin 组的成员，才能授予域用户权限。  
  
 要运行 BAM 管理实用程序，您必须至少是 BAM 数据库的数据库操作员。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户](../core/bam-portal.md)