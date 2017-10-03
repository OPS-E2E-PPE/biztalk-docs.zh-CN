---
title: "Oracle E-business Suite 适配器支持哪些操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7236c21f1e298f2ccd4cbb97db481cbd3626d186
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite 适配器支持何种操作
## <a name="overview"></a>概述
适配器客户端可以在通过 Oracle E-business Suite 执行操作：  
  
-   创建 BizTalk 项目  
  
-   使用 WCF 通道模型  
  
-   使用 WCF 服务模型  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。 有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。  
  
 本部分提供有关在 Oracle E-business Suite 中使用支持的操作的信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [对接口表和接口视图的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [PL/SQL api 的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [对并发程序操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [对请求设置的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [对接口表、 界面视图、 表和视图包含 LOB 数据的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [对函数和存储的过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [对函数和过程与 REF CURSOR 参数的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [对函数和过程的记录类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [对同义词的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [接收数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [使用轮询的入站调用的支持](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [对复合操作的支持](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [对 Oracle 用户定义类型的支持](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a>另请参阅  
[了解有关 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)