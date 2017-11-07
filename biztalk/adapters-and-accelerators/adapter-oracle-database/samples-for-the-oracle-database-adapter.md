---
title: "Oracle 数据库适配器示例 |Microsoft 文档"
description: "可以用于 BizTalk Server、 WCF 服务模型和 WCF 通道模型的 oracle DB WCF 适配器示例"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bfef9fcfce65d8aede1cd905a53469c565977f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a>Oracle 数据库适配器的的示例
示例[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  

  
这些示例位于[BizTalk 适配器包 2010年: Oracle 数据库适配器示例](https://www.microsoft.com/download/details.aspx?id=4675)。 用于创建表和在这些示例中使用的包的 SQL 脚本是包含。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
以下列表介绍这些示例。
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|Func_RecordTypes|演示如何使用记录类型参数和返回值函数和过程使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|Func_RefCursor|演示如何使用函数和使用的过程中的 REF CURSOR 参数[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|InvokeFunction|演示如何调用在 Oracle 数据库中使用函数[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|InvokeOverloadedProc|演示如何使用重载的函数和在 Oracle 数据库中使用的过程调用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|Operate_BFILE|演示如何使用 Oracle 过程中使用 Oracle BFILE 类型[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|Operate_LOB|演示如何 ReadLOB 和 UpdateLOB 对表执行操作的 LOB 数据类型使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|PollingQuery|演示如何配置轮询查询和接收使用对结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|SelectAccTable|演示如何在使用 Oracle 数据库表上执行 select 查询[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
|SqlExec|演示如何执行参数化的查询使用在上 Oracle 数据库通过 SQLEXECUTE 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|  
  
## <a name="wcf-service-model-samples"></a>WCF 服务模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|OracleBfileTypeSM|演示如何提供给 Oracle 过程的 Oracle 表和作为参数的基本 SQL 操作中使用 Oracle BFILE 类型。|  
|OracleOverloadsSM|演示如何调用重载的函数和包中的过程。|  
|OraclePollingSM|演示如何配置轮询查询和接收的结果。|  
|OracleRecordTypesSM|演示如何使用记录类型参数和函数和过程中返回值。|  
|OracleRefCursorsSM|演示如何使用 REF CURSOR 参数在函数和过程|  
|OracleTransactedDmlSM|演示如何在使用 WCF 服务模型在某个事务中执行对 Oracle 数据库的操作。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|OraclePollingCM|演示如何配置轮询查询和接收的结果。|  
|OracleStreamingDemo|演示如何执行端到端对使用 UpdateLOB 和表选择操作的 LOB 数据进行流式处理|  
|OracleTransactedDmlCM|演示如何在使用 WCF 通道模型在某个事务中执行对 Oracle 数据库的操作。|  
  

## <a name="see-also"></a>另请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)