---
title: "开发 SQL 应用程序使用 WCF 服务模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645b783ad23d79b4f6be177f6d38287e62abab1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a>开发 SQL 应用程序使用 WCF 服务模型
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供作为编程模型的 WCF 通道的替代方法调用 WCF 服务模型编程模型。  
  
 WCF 服务模型使用熟悉的.NET 范例来隐藏通过通道交换 SOAP 消息的复杂性。 服务模型完成这种简化读取到内存的整个的 SOAP 消息，然后将信息复制到.NET 数据结构。 加载到内存长消息，但是，可能不可行对于某些应用程序。 在这些情况下，开发人员应使用 WCF 通道模型。 有关使用 WCF 通道模型的详细信息，请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  
  
 在最低级别，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了 WCF 通道模型，在其中客户端调用服务上的操作通过在客户端和服务终结点之间建立信道交换 SOAP 消息。 WCF 通道模型公开数据类型和方法，您可以直接对 WCF 通道体系结构进行操作。 WCF 通道模型为您提供通过你创建的 SOAP 消息的内容和方式这两个应用程序的直接控制和[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使用它们。 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。  
  
 WCF 服务模型使用代理类来调用针对目标服务的操作或从客户端接收操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开 SQL Server 数据库作为 WCF 服务可以在其调用操作。  
  
-   用于调用操作将针对目标服务的代理类调用 WCF 客户端类。 此类模型作为使用强类型参数的.NET 方法由服务公开的操作。 通过使用 WCF 服务模型，你可以调用公开的运算[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。
  
 可以使用以下工具之一生成 WCF 客户端类和关联的服务元数据中的帮助器代码，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开：  
  
-   **ServiceModel 元数据实用工具 (svcutil.exe)**，其中附带了 WCF。  
  
-   **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** ，其中附带[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]并与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验。 此工具提供的标准的 Microsoft Windows 界面提供功能强大的浏览和搜索适配器公开的操作的功能。 有关如何生成一个 WCF 客户端应用程序的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
     本部分中的主题包含信息、 过程和示例来帮助你创建并使用 WCF 服务模型来开发应用程序使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [元数据和 WCF 服务模型与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [调用中使用 WCF 服务模型的 SQL 存储过程](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用 SQL Server 中的标量函数](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用 SQL Server 中的表值函数](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [从使用 WCF 服务模型的 SQL 接收查询通知](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)