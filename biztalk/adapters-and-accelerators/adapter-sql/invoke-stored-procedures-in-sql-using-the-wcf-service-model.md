---
title: 调用中使用 WCF 服务模型的 SQL 存储过程 |Microsoft 文档
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
ms.openlocfilehash: 7e2d707c37ba92fb6f1d1608ae43d02d1e964cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222285"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 SQL 存储过程
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现的存储的过程作为适配器客户端可以调用 WCF 客户端来调用存储的过程上的操作。 根据如何存储的过程返回结果集，该适配器将分类为所有存储的过程：  
  
-   **过程**。 调用存储的过程从**过程**节点返回数据集的数组。  
  
-   **强类型的过程**。 调用存储的过程从**Strongly-Typed 过程**节点返回一个强类型化结果集。  
  
 请注意，相同的存储过程中连接到的数据库集将列出不足**过程**和**Strongly-Typed 过程**节点。 根据所需的结果集的类型，必须调用存储的过程从相关节点。 有关详细信息，如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持存储的过程，请参阅[中使用 BizTalk Server 的 SQL Server 执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。  
  
 本部分将说明了如何调用存储的过程从这两个**过程**和**Strongly-Typed 过程**使用 WCF 客户端的节点。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Involk 弱类型中使用 WCF 服务模型的 SQL 存储过程](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [调用 SQL 使用 WCF 服务模型中的强类型化存储的过程](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>另请参阅  
[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)