---
title: 开发 BizTalk Server 中的 SQL 应用程序 |Microsoft Docs
description: 创建使用 WCF，SQL 适配器的应用程序或 BizTalk Server 使用 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac4b5b0-2980-4784-a081-e795654292ed
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b003010ae8cb9394dd956a97bd3e05ef855d3e73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978454"
---
# <a name="develop-your-sql-applications"></a>开发 SQL 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]绑定。 客户端应用程序可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来调用 SQL Server 项目上的操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可使用：  
  
- 通过中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 通过调用客户端代理的实例上的方法。  
  
- 为托管 WCF 服务。  
  
- 通过在使用 WCF 通道模型的代码中某个通道实例发送 SOAP 消息。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk 与 WCF 服务与 WCF 通道    
 下表中：  
  
- 列出了可在 SQL Server 执行的不同操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 提供了指向包含有关执行任务使用所选的方法的信息的主题 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型，WCF 通道模型)。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|  
|----------|--------------------|-----------------------|-----------------------|  
|执行基本的 Insert、 Update、 Delete 和表和视图的 Select 操作|[插入、 更新、 删除或选择将 BizTalk Server 与 SQL 适配器的操作](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)|[插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[在 SQL 中使用 WCF 通道模型运行上一个表的插入操作](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)|  
|表和视图处理大型数据上执行的操作类型的列<br /><br /> （还包括有关使用适配器的 FILESTREAM 操作的信息）|[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)|[包含 SQL 使用 WCF 服务模型中的大型数据类型运行操作表和视图](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)|-|  
|执行存储的过程|[在 SQL Server 使用 BizTalk Server 中执行存储的过程](execute-stored-procedures-in-sql-server-using-biztalk-server.md)|[调用中使用 WCF 服务模型的 SQL 存储过程](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)|-|  
|使用单个参数而无需使用 BizTalk 业务流程为正在执行存储的过程|[在 SQL Server 使用 BizTalk Server 中执行使用单个 XML 参数的存储的过程](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)|-|-|  
|执行包含 FOR XML 子句中定义的存储的过程|[执行存储的过程中使用 BizTalk Server 的 SQL Server 具有 FOR XML 子句](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)|-|-|  
|执行 SQL Server 上的复合操作|[运行 SQL Server 使用 BizTalk Server 上的复合操作](run-composite-operations-on-sql-server-using-biztalk-server.md)|-|-|  
|调用 SQL Server 中的标量函数|[调用 SQL Server 使用 BizTalk Server 中的标量函数](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)|[通过使用 WCF 服务模型中调用 SQL Server 中的标量函数](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|调用 SQL Server 中的表值函数|[调用 SQL Server 使用 BizTalk Server 中的表值函数](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)|[通过使用 WCF 服务模型中调用 SQL Server 中的表值函数](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|执行**ExecuteReader**， **ExecuteScalar**，或**ExecuteNonQuery**操作|[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)|[在 SQL 中使用 WCF 服务模型的 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)|-|  
|接收基于轮询的数据更改消息|[使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)|[SQL 适配器使用 WCF 服务模型轮询 SQL Server](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)|[使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)|  
|SQL Server 通知的接收|[接收使用 BizTalk Server 的 SQL 查询通知](receive-sql-query-notifications-using-biztalk-server.md)|[从使用 WCF 服务模型的 SQL 接收查询通知](receive-query-notifications-from-sql-using-the-wcf-service-model.md)|-|  

## <a name="next-steps"></a>后续步骤  
 在本部分中的主题提供信息、 步骤和示例，以帮助您开发使用的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在这种[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和.NET 编程解决方案。 

- [创建与 SQL Server 的连接](create-a-connection-to-sql-server.md)
- [在 Visual Studio 中获取 SQL Server 操作的元数据](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
- [元数据节点 ID](metadata-node-ids2.md)
- [使用绑定属性](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
- [先决条件：配置 MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)
- [使用 SQL 适配器开发 BizTalk 应用程序](develop-biztalk-applications-using-the-sql-adapter.md)
- [使用 WCF 服务模型开发应用程序](develop-sql-applications-using-the-wcf-service-model.md)
- [使用 WCF 通道模型开发应用程序](develop-sql-applications-using-the-wcf-channel-model.md)
- [示例](samples-for-the-sql-adapter.md)
- [配置事务隔离级别和事务超时](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
  
