---
title: "监视 BizTalk Server 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f137fc5-0e95-4952-8465-008771a1a377
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0ad2f450a859bc7c56a4829ba5315745fbf80a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitor-the-biztalk-server-databases"></a>监视 BizTalk Server 数据库
你可以运行的监视器 BizTalk Server SQL 代理作业来标识管理、 消息框中或 DTA 数据库中的所有已知的问题。 在 BizTalk Server 管理控制台中配置 BizTalk 组或从以前的版本升级 BizTalk 时创建该作业。  
  
## <a name="the-monitor-biztalk-server-job"></a>监视器 BizTalk Server 作业  
 监视 BizTalk 服务器作业扫描管理、 消息框中，和 DTA 数据库中的以下问题：  
  
> [!NOTE]  
>  监视 BizTalk 服务器作业仅扫描的问题。 它不能解决找到的问题。  
  
-   没有任何引用的消息  
  
-   而无需引用计数的消息  
  
-   引用计数小于 0 的消息  
  
-   无后台行的消息引用  
  
-   无实例的消息引用  
  
-   不包含实例的实例状态  
  
-   实例不包含相应的实例的订阅  
  
-   孤立的 DTA 服务实例  
  
-   孤立的 DTA 服务实例异常  
  
-   启用全局跟踪选项不在任何主机实例上运行 TDDS  
  
 “监视 BizTalk Server”作业已配置为每周自动运行一次。 由于该作业是计算密集型，我们建议你计划的停机时间或低流量期间运行。  
作业失败时，如果遇到任何问题;返回的错误字符串包含发现的问题数。 否则，它将成功运行。 您可以在作业历史中查看详细信息。 如果您使用管理员特权运行该作业，将作业历史记录和 SQL Server 应用程序日志记录的错误字符串。  
  
> [!IMPORTANT]  
>  此作业的失败不一定构成的严重问题，但而是应调查和解决 BizTalk Server 数据库的定期维护的一部分的问题。 此作业失败设计使然，它发现上面列出的问题之一的事件中。 上面列出的问题的详细信息，并访问通常用于 Microsoft 产品支持服务解决这些问题的实用程序，请参阅[使用 BizTalk 终止符，若要解决标识 BizTalk 的问题MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)。