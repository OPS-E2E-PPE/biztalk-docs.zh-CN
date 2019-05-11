---
title: 配置 A4SWIFT 站点组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56eb836ffde957244b5ca80e6d7491f9e8c207c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378958"
---
# <a name="configuring-a4swift-site-groups"></a>配置 A4SWIFT 站点组
您需要创建相应的网站用户组，可以锁定消息修复和新提交配置过程中创建的文档库上的权限。 若要执行此操作与在上一部分中的示例，A4SWIFT 管理员会转到 MRSR 站点并设置以下站点组：  
  
- Payments_Creators  
  
- Payments_Repairers  
  
- Payments_Approvers  
  
  对于每个站点组应应用以下权限：  
  
- **查看项。** 查看列表、 文档库中的文档中的项，查看 Web 讨论评论，并设置列表的电子邮件通知。  
  
- **视图页。** 查看 Web 站点中的页面。  
  
  需要为每个用户都参与付款部门的角色，以创建新的站点用户并为该用户分配到站点组对应于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MMC 配置期间创建的角色。