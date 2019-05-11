---
title: 定义数据库的自动增长设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c2070ae827136a5b03cb51ef0697db0180fe5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305949"
---
# <a name="define-auto-growth-settings-for-databases"></a>定义数据库的自动增长设置
您应设置为固定数量的兆字节而不是百分比，尤其是对于 MessageBox 和 BizTalk 跟踪数据库的数据库自动增长。 具体取决于您的 BizTalk 应用程序和吞吐量，MessageBox 和跟踪数据库可能会非常大。 如果将自动增长设置为百分比，则自动增长可能是重大。  
  
## <a name="how-instant-file-initialization-works"></a>如何即时文件初始化的工作原理  
 SQL Server 会增加文件的大小，它必须先初始化新的空间，然后才能使用。 这是涉及使用空页填充新的空间的阻塞操作。 Windows 上的 SQL Server 支持"即时文件初始化"。 这可以大大减少文件增长操作的性能影响。 有关详细信息，请参阅 [数据库文件初始化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)。 本主题概述了必须执行，以便启用即时文件初始化的步骤。  
  
## <a name="enable-instant-file-initialization"></a>启用即时文件初始化  
 有关步骤启用即时文件初始化，请参阅[数据库文件初始化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)。 创建文件组并将 BizTalk Server 数据库表、 索引和日志文件移动到相应的文件组，请按照中的建议[BizTalk 性能优化指南](../technical-guides/biztalk-server-2013-performance-optimization-guide.md)。 理想情况下支持的文件组的文件的大小应为预分配和如果可能，请设置为静态的大小。  
  
 如果系统为新并且没有已明确建立静态大小，然后配置文件**启用自动增长**选项，并指定文件的增长**中兆字节为单位**。 增长增量应通常不能大于 100 MB （对于大型文件）、 （适用于中型文件），10 MB 或 1 MB （对于小文件）。
