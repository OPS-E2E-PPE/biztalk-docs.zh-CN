---
title: 开发 SQL 应用程序使用 WCF 通道模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf7b12a076e88cd59dcc463dd8c10bd0817e612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369869"
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a>开发 SQL 应用程序使用 WCF 通道模型
可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]通过直接通过使用 SQL Server 绑定创建通道实例发送 XML 消息。  
  
 通过使用强类型化类和方法，WCF 服务模型公开了使用 WCF 通道模型的一个优点是通道模型提供更精细地控制在 SQL 数据库执行的操作。 此控件的来源的事实，在 WCF 通道模型中，您可以直接控制在通道上发送的消息的内容。  
  
 在某些情况下，此额外级别的控制可能有益。 例如时使用的 WCF 通道模型以执行更新操作的表，将有选择地可以忽略传入的消息更新模板中的列，从而更新目标行中的列。 仅有的列所需的那些带有"nillable = false"的 WSDL 中。 公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于包括表架构中的每个列的模板使用强类型的记录参数。  
  
 本主题中的各节说明如何执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [在 SQL 中使用 WCF 通道模型运行上一个表的插入操作](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)