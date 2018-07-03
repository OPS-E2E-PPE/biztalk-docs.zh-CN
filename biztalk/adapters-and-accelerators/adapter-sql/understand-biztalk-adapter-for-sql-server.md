---
title: 了解适用于 SQL Server 的 BizTalk 适配器 |Microsoft Docs
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
ms.openlocfilehash: ea21a06ad5d87e94118aaa45e2f6f541627aae9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996927"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>了解适用于 SQL Server 的 BizTalk 适配器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]实现面向服务的编程访问从而可以与外部系统进行交互。 适配器向客户端提供以下优势：  
  
- **一致的设计时体验**。 适配器提供了常见用户友好设计时体验，用于浏览、 搜索和检索 LOB 项目的元数据。  
  
- **不同的编程选项**。 适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。  
  
- **跨 Lob 的统一体验**。 使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获取访问权的任何 LOB 系统的统一的体验。  
  
  如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。 WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。 WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。 有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。
  
  若要执行的 SQL Server 数据库上的操作，适配器客户端必须有权访问相关的表、 过程、 视图、 标量函数和表值的函数。 数据库表是 SQL Server 数据库中存储的基本单位。 外部应用程序可以选择、 插入、 删除和使用 SQL 语句更新表中的数据。 应用程序还可以通过使用过程、 视图、 标量函数和表值函数访问表中的数据。 使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，适配器客户端可以浏览项目，例如表、 过程、 视图和 SQL Server 数据库中的其他此类项。 适配器客户端可以选择为他们的解决方案，它们需要的项目并检索这些项目的元数据。 这使用户可以访问和执行 SQL Server 数据库中的项目上的操作。  
  
  本部分中列出的功能[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 SQL Server 的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [用于 SQL Server 的 BizTalk 适配器的主要功能](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [适用于 SQL Server 的 BizTalk 适配器的限制](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>请参阅  
[开始使用的 BizTalk 适配器进行 SQL](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)