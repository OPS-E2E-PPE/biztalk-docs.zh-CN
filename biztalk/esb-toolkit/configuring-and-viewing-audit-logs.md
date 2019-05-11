---
title: 配置和查看审核日志 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c725bf04-d59f-42c1-b327-b4268421689c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad02f6c54d1535c3580093d8c981b0e29731f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302111"
---
# <a name="configuring-and-viewing-audit-logs"></a>配置和查看审核日志
ESB 管理门户维护审核日志的操作，可帮助你监视使用情况并跟踪问题。 管理员可以指定该门户将写入审核日志的事件。  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a>若要查看在门户的审核日志  
  
1.  指向**管理员**在门户的主菜单上，选项卡，然后单击**管理审核日志**以打开[审核日志页](../esb-toolkit/audit-log-page.md)。  
  
2.  若要查看重新提交详细信息和重新提交消息的原始消息，请单击要打开审核日志 – 消息查看器页列表中的消息标识符。  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a>若要配置在门户的审核设置  
  
1.  请确保您登录到在门户中使用该帐户是 （门户管理员的自动成员） 的 BizTalk Server Administrators 帐户组的成员。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**容错设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。  
  
3.  若要更改的审核选项，选择中的复选框**AuditOptions**部分，了解每个想要审核的事件。 可用的事件。 保存修改的设置，编辑和失败后成功重新提交错误时重新提交错误