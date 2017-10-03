---
title: "流式处理 Oracle 数据库中的 LOB 数据类型支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3f052b5051e511179ed0a3b371a619b315a16af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a>Oracle 数据库中的 LOB 数据类型的流式处理支持
Oracle 数据库支持流式处理大型对象 (LOB) 数据类型。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持消息流式处理，这样就可以进行流式处理 LOB 数据端到端 Oracle 数据库和适配器客户端之间。 但是，流式处理不支持相同的方式跨所有的编程模型时使用适配器。  
  
 跨不同的编程模型，适配器支持如下所示方式端到端流式处理的 LOB 数据类型。  
  
|运算|WCF 通道模型|WCF 服务模型|BizTalk Server|  
|---------------|-----------------------|-----------------------|--------------------|  
|表/视图插入操作|不支持|不支持|不支持|  
|表/视图选择操作|是否支持|不支持|是否支持|  
|表/视图更新操作|不支持|不支持|不支持|  
|表/视图删除操作|不支持|不支持|不支持|  
|表/视图 ReadLOB 操作|支持;但是，主要是为了支持流式处理 WCF 服务模型中可以找出 ReadLOB 操作，建议不要在 WCF 通道模型中使用。 改为使用选择的操作或 SQLEXECUTE 操作。|是否支持|ReadLOB 操作不可用于 BizTalk Server。 请改用选择操作。|  
|表/视图 UpdateLOB 操作|是否支持|不支持|是否支持|  
|SQLEXECUTE 操作|在响应中受支持|不支持|在响应中受支持|  
|存储的过程和函数的操作|在响应中受支持|不支持|在响应中受支持|  
|POLLINGSTMT 操作|是否支持|不支持|是否支持|  
  
 有关如何对 LOB 数据类型进行流式处理适配器所支持的和如何支持它时随适配器一起使用各种编程模型的更全面信息，请参阅[流式处理大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle 数据库的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)