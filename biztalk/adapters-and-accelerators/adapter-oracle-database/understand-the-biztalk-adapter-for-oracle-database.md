---
title: 了解用于 Oracle 数据库的 BizTalk 适配器 |Microsoft Docs
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
ms.openlocfilehash: 97fda25d77571a3c0128317a557e5f9d15bbc472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994614"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>了解用于 Oracle 数据库的 BizTalk 适配器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
- **一致的设计时体验**。 适配器提供了常见用户友好设计时体验，用于浏览、 搜索和检索 LOB 项目的元数据。  
  
- **不同的编程选项**。 适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。  
  
- **跨 Lob 的统一体验**。 使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获取访问权的任何 LOB 系统的统一的体验。  
  
  如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。 WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。 WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。 有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。
  
  若要对 Oracle 数据库执行操作，适配器客户端必须有权相关表、 函数和过程。 数据库表是在 Oracle 数据库中存储的基本单位。 外部应用程序可以添加或通过使用 SQL 语句从表中删除数据。 应用程序还可以通过使用视图、 函数和过程访问表中的数据。 使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]，适配器客户端可以浏览的项目，例如表、 过程、 包、 视图和 Oracle 数据库中的其他此类项。 适配器客户端可以选择他们需要为他们的解决方案和检索这些项目的元数据的项目。 这使用户可以访问和 Oracle 数据库中执行项目上的操作。  
  
  本部分中列出的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [用于 Oracle 数据库的 BizTalk 适配器的主要功能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [用于 Oracle 数据库的 BizTalk 适配器的限制](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>请参阅  
[BizTalk Server 入门](../../core/getting-started-with-biztalk-server.md)