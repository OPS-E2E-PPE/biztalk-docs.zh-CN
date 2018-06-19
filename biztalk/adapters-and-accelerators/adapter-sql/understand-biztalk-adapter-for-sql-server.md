---
title: 理解 SQL Server 的 BizTalk Adapter |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fc14b7d9da40edd56c4c4cc4fa6b795386518db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965299"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>理解 SQL Server 的 BizTalk Adapter
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]实现使其可能与外部系统交互的面向服务的编程访问。 适配器向客户端提供以下优势：  
  
-   **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的设计时体验常见和用户友好。  
  
-   **各种编程选项**。 适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk 支持模型。  
  
-   **跨 Lob 的统一体验**。 适配器标准化上使用 WCF 和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供统一的体验的获得对任何 LOB 系统的访问。  
  
 如前文所述，适配器均构建在之上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。 有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。  
  
 若要执行 SQL Server 数据库上的操作，适配器客户端必须有权访问相关的表、 过程、 视图、 标量函数和表值的函数。 数据库表是 SQL Server 数据库中存储的基本单元。 外部应用程序可以选择、 插入、 删除和使用 SQL 语句更新表中的数据。 应用程序还可以通过使用过程、 视图、 标量函数和表值函数访问表中的数据。 与[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，适配器客户端可以浏览如表、 过程、 视图和其他此类项 SQL Server 数据库中的项目。 适配器客户端可以选择其解决方案，它们需要的项目，并检索这些项目的元数据。 这使用户可以访问和 SQL Server 数据库中执行的操作的项目。  
  
 本部分列出的功能[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 SQL Server 的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [用于 SQL Server 的 BizTalk Adapter 中的主要功能](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [BizTalk Adapter for SQL Server 的限制](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>另请参阅  
[开始使用 BizTalk adapter for SQL](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)