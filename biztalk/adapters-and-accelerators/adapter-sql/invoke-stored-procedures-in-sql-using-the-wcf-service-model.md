---
title: 调用中使用 WCF 服务模型的 SQL 存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ce43db33101dfc3849743e8480e66a8fd76f53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023291"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 SQL 存储过程
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为操作适配器客户端可以调用来调用存储的过程在 WCF 客户端上发现的存储的过程。 如何存储的过程返回的结果集为基础，适配器将分类为所有存储的过程：  
  
- **过程**。 调用存储的过程从**过程**节点返回数据集的数组。  
  
- **强类型的过程**。 调用存储的过程从**Strongly-Typed 过程**节点返回强类型化结果集。  
  
  请注意，同一组中连接到的数据库的存储过程将列出下两者**过程**并**Strongly-Typed 过程**节点。 根据所需的结果集的类型，必须调用中的相关节点的存储的过程。 详细了解如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持存储的过程，请参阅[SQL Server 使用 BizTalk Server 中执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。  
  
  本部分说明如何调用存储的过程从这两个**过程**并**Strongly-Typed 过程**使用 WCF 客户端的节点。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Involk 弱类型中使用 WCF 服务模型的 SQL 存储过程](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [调用强类型化 SQL 使用 WCF 服务模型中的存储的过程](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)