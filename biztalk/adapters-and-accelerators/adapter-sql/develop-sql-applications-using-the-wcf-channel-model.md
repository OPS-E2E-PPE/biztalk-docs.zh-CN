---
title: "开发 SQL 应用程序使用 WCF 通道模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a>开发 SQL 应用程序使用 WCF 通道模型
你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]通过直接通过使用 SQL Server 绑定创建的通道实例发送 XML 消息。  
  
 通过使用的强类型类和 WCF 服务模型公开的方法使用 WCF 通道模型的一个优点是通道模型提供的 SQL 数据库执行的操作的更好地细化控制。 此控件来自在 WCF 通道模型中，你直接控制通过通道发送的消息的内容的事实。  
  
 在某些情况下，此额外级别是控制的有益的。 例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。 仅有的列所需那些带有"nillable = false"WSDL 中。 由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。  
  
 本主题中的各节说明如何执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [运行 SQL 使用 WCF 通道模型中的表上的插入操作](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [通过使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)