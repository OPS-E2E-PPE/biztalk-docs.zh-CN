---
title: "开始使用 BizTalk adapter for SQL |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a2ecd7ae8020865dff7b67fbc57388d1f15af6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a>开始使用 BizTalk adapter for SQL

  
 本部分提供的适配器、 先决条件和主题概述的用户的不熟悉 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 它讨论的功能[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和可以使用该适配器执行的 SQL Server 数据库的不同运算。  
  
 什么是适配器？ 适配器是一个软件组件，使您能够发送和接收消息传入和传出的业务线 (LOB) 系统。 适配器的主要设计目标是便于贸易合作伙伴之间的业务文档的交换。 由于每个业务系统可能符合特定的文档格式和协议，适配器必须使用符合公认的标准和协议，以向用户提供统一的接口的传递机制。  
  
 中的适配器[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]可以分为两大类：  
  
-   **LOB 适配器**。 提供面向服务的访问 LOB 系统的编程模型，该类型的适配器-例如，为 SAP 或 Siebel 适配器。  
  
-   **数据适配器**。 提供的 access 数据库面向服务的编程模型，该类型的适配器-例如，Oracle 数据库或 SQL Server 的适配器。  
  
 有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]之外还有[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]作为一个单独的适配器。  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不可用于 64 位平台。  
  
 如果你不已知道你想要在贵公司使用的 SQL 适配器，建议你首先探索功能和中所述的适配器的功能[了解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [理解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [SQL 适配器教程](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [常见问题](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)