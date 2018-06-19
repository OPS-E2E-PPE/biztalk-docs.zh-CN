---
title: 开发 BizTalk Server 中的 Oracle 数据库应用程序 |Microsoft 文档
description: 创建 Oracle DB 应用程序使用 WCF，或在 BizTalk Server 中使用 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a685b2-ac17-4949-bc77-001f56450847
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b0da5ae6691e3cca4a844d037e4714bd09ec146
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215621"
---
# <a name="develop-your-oracle-database-applications"></a>开发 Oracle 数据库应用程序

## <a name="overview"></a>概述
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 客户端应用程序可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]来调用上 Oracle 数据库项目的操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可使用：  
  
-   通过中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   通过调用方法的实例上[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]客户端代理。  
  
-   作为一个承载[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务。  
  
-   通过在代码中使用的通道实例发送 SOAP 消息通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk vs WCF 服务与 WCF 通道  
 下表中：  
  
-   列出可以对使用 Oracle 数据库执行的不同运算[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   提供指向包含有关执行任务使用选的方法的信息的主题 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型)。  
  
|任务|BizTalk Server|WCF 服务模型|WCF 通道模型|  
|----------|--------------------|-----------------------|-----------------------|  
|基本 Insert、 Update、 Delete 和对表和视图的 Select 操作|[插入、 更新、 删除或选择 BizTalk Server 使用 Oracle 数据库的操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)|[插入、 更新、 删除或使用 WCF 服务模型的 Oracle 数据库中选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)|[使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|对表和视图包含 LOB 数据的操作|[运行与 Oracle 数据库中的大型对象数据类型对表的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)|[完成对表使用 WCF 服务模型的 Oracle 数据库中的较大的数据类型的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)||  
|对函数和存储的过程的操作|[调用函数和 Oracle 数据库使用 BizTalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)|[调用中使用 WCF 通道模型的 Oracle 数据库的函数](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)|  
|调用重载的函数和过程|[调用重载函数和 Oracle 数据库使用 BizTalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)||  
|对函数和过程与 REF CURSOR 参数的操作|[调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)|[使用 WCF 服务模型的 Oracle 数据库中运行操作使用 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)||  
|对函数和过程的记录类型操作|[调用函数和过程与使用 BizTalk Server 的 Oracle 数据库中的记录类型](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)|[使用 WCF 服务模型的 Oracle 数据库中运行操作使用的记录类型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)||  
|对表和视图 BFILE 数据类型的操作|[使用 BFILE 数据类型，使用 BizTalk Server 的 Oracle 数据库中运行对表的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)|||  
|SQLEXECUTE 操作|[使用 BizTalk Server 的 Oracle 数据库中运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)|[使用 WCF 服务模型的 Oracle 数据库中运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)|[使用 WCF 通道模型的 Oracle 数据库中运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|接收基于轮询的数据更改消息|[使用 BizTalk Server 轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)|[使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)|[使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)|  
|执行对 Oracle 数据库的复合操作|[运行 Oracle 数据库使用 BizTalk Server 上的复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)|||  
|接收的数据库更改通知|[接收使用 BizTalk Server 的 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[接收使用 WCF 服务 Model1 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)||  
  

  
## <a name="next-steps"></a>后续步骤
 本部分中的主题提供信息、 过程和示例来帮助你开发的应用程序使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]解决方案编程。 
  
-   [创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)
  
-   [获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) 
  
-   [用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)
  
-   [Oracle 数据库适配器中的流式处理大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)
  
-   [Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)
  
-   [开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)
  
-   [开发使用 WCF 服务模型的 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)  
  
-   [开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
  
-   [从 Oracle 数据库以编程方式获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)  
  
-   [将用于 SharePoint 的 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/use-the-oracle-database-adapter-with-sharepoint.md)
  
-   [适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)  
  
-   [配置与 Oracle 数据库的事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)

- [使用 svcutil.exe](use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)