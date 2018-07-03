---
title: 开发 SQL 应用程序使用 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afeb8d7aac2dd2a29f60c89cf54c86ef2e4519df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983974"
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a>开发 SQL 应用程序使用 WCF 服务模型
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] 提供编程模型调用 WCF 服务模型中，作为编程模型的 WCF 通道的替代方法。  
  
 WCF 服务模型使用熟悉的.NET 范例来隐藏通过通道交换 SOAP 消息的复杂性。 服务模型通过读取到内存的整个 SOAP 消息，然后再将信息复制到.NET 数据结构来实现这种简化。 加载到内存中的长消息，但是，可能不可行的某些应用程序。 在这些情况下，开发人员应使用 WCF 通道模型。 有关使用 WCF 通道模型的详细信息，请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  
  
 最低级别[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]显示 WCF 通道模型，在其中客户端调用服务上的操作由客户端和服务终结点之间建立的通道通过交换 SOAP 消息。 WCF 通道模型公开的数据类型和方法，使你能够直接在 WCF 通道体系结构上运行。 WCF 通道模型为您提供直接控制对您创建的 SOAP 消息的内容和方式这两个应用程序和[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使用它们。 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。  
  
 WCF 服务模型使用的代理类调用将针对目标服务的操作或从客户端接收操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开为 WCF 服务可在其调用操作的 SQL Server 数据库。  
  
- 用于目标服务调用操作的代理类调用 WCF 客户端类。 此类模型由服务公开为强类型化参数使用的.NET 方法的操作。 通过使用 WCF 服务模型，可以调用公开的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。
  
  您可以使用以下工具之一生成 WCF 客户端类和关联的帮助程序代码从服务元数据的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开：  
  
- **ServiceModel Metadata Utility Tool (svcutil.exe)**，WCF 附带的。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** ，其中附带[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，并与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验。 此工具提供了一个标准的 Microsoft Windows 界面，可提供功能强大的浏览和搜索功能对该适配器公开的操作。 有关如何生成 WCF 客户端应用程序的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
   在本部分中的主题包含信息、 步骤和示例来帮助你创建和使用 WCF 服务模型开发应用程序使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [元数据和具有 SQL 适配器的 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [包含 SQL 使用 WCF 服务模型中的大型数据类型运行操作表和视图](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [调用中使用 WCF 服务模型的 SQL 存储过程](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型中调用 SQL Server 中的标量函数](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型中调用 SQL Server 中的表值函数](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [在 SQL 中使用 WCF 服务模型的 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [SQL 适配器使用 WCF 服务模型轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [从使用 WCF 服务模型的 SQL 接收查询通知](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)