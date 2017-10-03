---
title: "配置 A4SWIFT 站点组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0070f10819ebbde18cdeab9c3bd534ca74bfbcd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a4swift-site-groups"></a>配置 A4SWIFT 站点组
你需要创建相应的网站用户组，来锁定消息修复和新提交配置过程中创建的文档库的权限。 若要执行此操作与在上一部分中的示例，A4SWIFT 管理员将转到 MRSR 站点并设置以下站点组：  
  
-   Payments_Creators  
  
-   Payments_Repairers  
  
-   Payments_Approvers  
  
 对于每个站点组应应用以下权限：  
  
-   **查看项。** 查看列表，在文档库中的文档中的项、 查看 Web 讨论评论和设置列出的电子邮件通知。  
  
-   **视图的页数。** 查看网站中的页面。  
  
 对于每个用户都参与付款部门的角色，你需要创建一个新的站点用户并将该用户分配给对应的站点组[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MMC 配置过程中创建的角色。