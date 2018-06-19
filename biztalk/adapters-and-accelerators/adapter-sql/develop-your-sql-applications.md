---
title: 开发 BizTalk Server 中的 SQL 应用程序 |Microsoft 文档
description: 创建 SQL 适配器应用程序使用 WCF，或在 BizTalk Server 中使用 BizTalk 适配器包 (BAP)
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
ms.openlocfilehash: 5e5be1f01a9d8180dea60f508cba1c4ff7c0964f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224429"
---
# <a name="develop-your-sql-applications"></a>开发 SQL 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]绑定。 客户端应用程序可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来调用 SQL Server 项目上的操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可使用：  
  
-   通过中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   通过调用客户端代理的一个实例上的方法。  
  
-   作为承载的 WCF 服务。  
  
-   通过使用 WCF 通道模型的代码中的通道实例发送 SOAP 消息。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk vs WCF 服务与 WCF 通道    
 下表中：  
  
-   列出可以在 SQL Server 执行的不同运算使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   提供指向包含有关执行任务使用选的方法的信息的主题 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型，WCF 通道模型)。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|  
|----------|--------------------|-----------------------|-----------------------|  
|执行基本的插入、 更新、 删除和对表和视图的 Select 操作|[插入、 更新、 删除或选择 BizTalk Server 使用的 SQL 适配器的操作](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)|[插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[运行 SQL 使用 WCF 通道模型中的表上的插入操作](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)|  
|执行操作对表和视图对大型数据类型列<br /><br /> （还包括有关使用该适配器的 FILESTREAM 操作信息）|[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)|[在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)|-|  
|执行存储的过程|[在 SQL Server 使用 BizTalk Server 中执行存储的过程](execute-stored-procedures-in-sql-server-using-biztalk-server.md)|[调用中使用 WCF 服务模型的 SQL 存储过程](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)|-|  
|具有单个参数而无需使用 BizTalk 业务流程执行存储的过程|[在 SQL Server 使用 BizTalk Server 中执行存储的过程使用单个 XML 参数](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)|-|-|  
|执行包含在定义中的 FOR XML 子句的存储的过程|[执行具有 FOR XML 子句中使用 BizTalk Server 的 SQL Server 中的存储的过程](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)|-|-|  
|执行 SQL Server 上的复合操作|[运行 SQL Server 使用 BizTalk Server 上的复合操作](run-composite-operations-on-sql-server-using-biztalk-server.md)|-|-|  
|调用 SQL Server 中的标量函数|[调用 SQL Server 使用 BizTalk Server 中的标量函数](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)|[使用 WCF 服务模型调用 SQL Server 中的标量函数](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|调用 SQL Server 中的表值函数|[调用 SQL Server 使用 BizTalk Server 中的表值函数](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)|[使用 WCF 服务模型调用 SQL Server 中的表值函数](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|执行**ExecuteReader**， **ExecuteScalar**，或**ExecuteNonQuery**操作|[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 BizTalk Server 中的操作](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)|[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)|-|  
|接收基于轮询的数据更改消息|[与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)|[使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)|[通过使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)|  
|接收的 SQL Server 通知|[接收使用 BizTalk Server 的 SQL 查询通知](receive-sql-query-notifications-using-biztalk-server.md)|[从使用 WCF 服务模型的 SQL 接收查询通知](receive-query-notifications-from-sql-using-the-wcf-service-model.md)|-|  

## <a name="next-steps"></a>后续步骤  
 本部分中的主题提供信息、 过程和示例来帮助你开发的应用程序使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和.NET 编程解决方案。 

- [创建与 SQL Server 的连接](create-a-connection-to-sql-server.md)
- [获取 Visual Studio 中的 SQL Server 操作的元数据](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
- [元数据节点 Id](metadata-node-ids2.md)
- [使用绑定属性](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
- [先决条件： 配置 MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)
- [开发使用 SQL 适配器的 BizTalk 应用程序](develop-biztalk-applications-using-the-sql-adapter.md)
- [开发应用程序使用 WCF 服务模型](develop-sql-applications-using-the-wcf-service-model.md)
- [开发应用程序使用 WCF 通道模型](develop-sql-applications-using-the-wcf-channel-model.md)
- [示例](samples-for-the-sql-adapter.md)
- [配置事务隔离级别和事务超时](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
  
