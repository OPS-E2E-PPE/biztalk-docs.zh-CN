---
title: 了解用于 Oracle 数据库的 BizTalk Adapter |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb2d3603bb6d7c64d355c88420167344f564ddd8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961171"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>了解 BizTalk 适配器用于 Oracle 数据库
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
-   **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的设计时体验常见和用户友好。  
  
-   **各种编程选项**。 适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk 支持模型。  
  
-   **跨 Lob 的统一体验**。 适配器标准化上使用 WCF 和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供统一的体验的获得对任何 LOB 系统的访问。  
  
 如前文所述，适配器均构建在之上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。 有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。  
  
 要对 Oracle 数据库执行操作，适配器客户端必须具有对相关表、 函数和过程的访问。 数据库表是 Oracle 数据库中存储的基本单元。 外部应用程序可以添加或从表中删除数据，通过使用 SQL 语句。 应用程序还可以通过使用视图、 函数和过程访问表中的数据。 与[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]，适配器客户端可以浏览如表、 过程、 包、 视图和其他此类项 Oracle 数据库中的项目。 适配器客户端可以选择他们需要用其解决方案和检索元数据的这些项目的项目。 这使用户可以访问和 Oracle 数据库中执行的操作的项目。  
  
 本部分列出的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [用于 Oracle 数据库的 BizTalk Adapter 中的主要功能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [用于 Oracle 数据库的 BizTalk Adapter 限制](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>另请参阅  
[BizTalk Server 入门](../../core/getting-started-with-biztalk-server.md)