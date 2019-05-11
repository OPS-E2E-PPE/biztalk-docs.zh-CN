---
title: 监视 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fee5015-e818-459b-aeeb-a084ef355600
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf16b4998067d089a2fe0ecb6b05efa1ceed355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396695"
---
# <a name="monitoring-biztalk-server-databases"></a>监视 BizTalk Server 数据库
可以运行监视 BizTalk Server SQL 代理作业，以标识管理、 消息框中或 DTA 数据库中的任何已知的问题。 在 BizTalk Server 管理控制台中配置 BizTalk 组或从早期版本升级 BizTalk 时创建作业。  
  
## <a name="the-monitor-biztalk-server-job"></a>监视 BizTalk Server 作业  
 监视 BizTalk Server 作业扫描管理、 消息框和 DTA 数据库中的以下问题：  
  
> [!NOTE]  
>  监视 BizTalk Server 作业仅扫描问题。 它不能解决发现的问题。  
  
- 没有任何引用的消息  
  
- 没有引用计数的消息  
  
- 具有引用计数小于 0 的消息  
  
- 无后台行的消息引用  
  
- 没有实例的消息引用  
  
- 没有实例的实例状态  
  
- 没有相应的实例的实例订阅  
  
- 孤立的 DTA 服务实例  
  
- 孤立的 DTA 服务实例异常  
  
- TDDS 未运行任何主机实例上启用全局跟踪选项  
  
  监视 BizTalk Server 作业配置和自动运行一次在一周内。 由于是计算密集型作业，我们建议您计划的停机时间或低流量期间运行。  
  作业失败时如果遇到任何问题;返回的错误字符串包含找到的问题数。 否则，它将成功运行。 您可以看到作业历史记录中的详细信息。 如果使用管理员特权运行该作业，将向作业历史记录和 SQL Server 应用程序日志记录的错误字符串。  
  
> [!IMPORTANT]  
>  此作业的失败不一定是构成是关键问题，但而不是问题，应调查并解决的定期维护 BizTalk Server 数据库的一部分。 此作业失败按照设计，它会发现其中一个上面列出的问题的事件中。