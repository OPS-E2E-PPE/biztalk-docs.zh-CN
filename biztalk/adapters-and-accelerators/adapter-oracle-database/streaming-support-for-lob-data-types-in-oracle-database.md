---
title: Oracle 数据库中的 LOB 数据类型的流式处理支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a6e5f842efd8c5d4778d5920c82f99302c82ec7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375964"
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a>Oracle 数据库中的 LOB 数据类型的流支持
Oracle database 支持流式处理大型对象 (LOB) 数据类型。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持消息流式处理，这样就可以进行流式处理 LOB 数据端到端 Oracle 数据库和适配器客户端之间。 但是，流式处理不支持相同的方式跨所有编程模型时使用的适配器。  
  
 跨不同的编程模型，适配器支持以下显示了如何端到端 LOB 数据类型的流式处理。  
  
|操作|WCF 通道模型|WCF 服务模型|BizTalk Server|  
|---------------|-----------------------|-----------------------|--------------------|  
|表/视图插入操作|不支持|不支持|不支持|  
|表/视图中，选择操作|支持|不支持|支持|  
|表/视图更新操作|不支持|不支持|不支持|  
|表/视图删除操作|不支持|不支持|不支持|  
|表/视图 ReadLOB 操作|受支持;但是，主要用于支持 WCF 服务模型中的流式处理可以找出 ReadLOB 操作，建议不要在 WCF 通道模型中使用。 改为使用选择操作或 SQLEXECUTE 操作。|支持|为 BizTalk Server 不支持 ReadLOB 操作。 改为使用选择操作。|  
|表/视图 UpdateLOB 操作|支持|不支持|支持|  
|SQLEXECUTE 操作|在响应中受支持|不支持|在响应中受支持|  
|存储的过程和函数操作|在响应中受支持|不支持|在响应中受支持|  
|POLLINGSTMT 操作|支持|不支持|支持|  
  
 有关如何流式处理 LOB 数据类型的适配器是否支持和您的适配器使用各种编程模型时的支持方式的更全面信息，请参阅[流式处理大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)