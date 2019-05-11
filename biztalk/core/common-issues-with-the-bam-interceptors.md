---
title: BAM 侦听器的常见问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 787ed9f5fd2f94f719e224db471bde8c2aad9829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357105"
---
# <a name="common-issues-with-the-bam-interceptors"></a>BAM 侦听器中的常见问题
本主题讨论使用 BAM 侦听器时，可能会出现的以下常见问题：  
  
-   为分布式事务相关的 SQL 异常  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a>收到 SQL 异常，就已完成的分布式的事务或事务描述符  
 运行 BAM Windows Communication Framework (WCF) 侦听器时，可能会看到以下异常之一：  
  
- 分布式事务已完成。 请将此会话登记到新事务或 NULL 事务中。  
  
- 新的请求不能启动，因为它应具有有效的事务描述符。  
  
  有关解决此问题的一些建议是：  
  
- 启用 BAM 跟踪。 此跟踪将包括所有相关的消息包括错误的根本原因。 有关 BAM 跟踪的详细信息，请参阅[如何在 BAM 中启用跟踪](../core/how-to-enable-tracing-in-bam.md)。  
  
- 当你看到此分布式的事务处理协调器 (DTC) 异常时，尝试重新运行不具有事务相同的方案。  
  
- 使用 SQL Server Profiler 并检查存在错误将导致事务中止的跟踪中。  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a>使用 WCF 侦听器时收到类似于"侦听器配置轮询间隔 '0' 必须至少 '5' 秒"的错误  
 未显式提供侦听器配置轮询间隔值在应用程序配置文件中，或提供一个值，但它是 5 秒内，需最小值时，可能会遇到此错误。  
  
 若要解决此问题，请为 PollingIntervalSec 提供有效的值所示：  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 侦听器疑难解答](../core/troubleshooting-bam-interceptors.md)