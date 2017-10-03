---
title: "开发在 BizTalk 应用程序 Oracle E-business Suite |Microsoft 文档"
description: "创建 Oracle EBS 应用程序使用 WCF，或在 BizTalk Server 中使用 BizTalk 适配器包 (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7b1ebff-b3f8-4e07-a089-d1d5bfb78d56
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc72e5adbef300115189119ba77821a08883999a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-oracle-e-business-suite-applications"></a>开发 Oracle E-business Suite 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]绑定。 客户端应用程序可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]来调用 Oracle E-business Suite 项目上的操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可使用：  
  
-   通过中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   通过调用客户端代理的一个实例上的方法。  
  
-   通过使用 WCF 通道模型的代码中的通道实例发送 SOAP 消息。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk vs WCF 服务与 WCF 通道 
  
 下表中：  
  
-   列出可以对 Oracle E-business Suite 执行的不同运算使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
-   提供指向包含有关执行任务使用选的方法的信息的主题 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型)。  
  
|运算|BizTalk Server|WCF 服务模型|WCF 通道模型|  
|---|---|---|---|  
|对接口表和视图执行操作 | [插入、 更新、 删除或选择上的接口表以及与 Oracle E-business Suite 的界面视图](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-or-select-on-interface-tables-and-views-with-oracle-ebs.md) |[插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)|  
|执行对表和视图较大的数据类型的操作 | [完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md) |[完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)||  
|执行对 Oracle 数据库的复合操作 | [完成对 Oracle E-business Suite 的复合操作](../../adapters-and-accelerators/adapter-oracle-ebs/complete-composite-operations-on-oracle-e-business-suite.md)|||  
|调用在 Oracle E-business Suite 的并发程序 | [调用在 Oracle E-business Suite 的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-concurrent-programs-in-oracle-e-business-suite.md) | [调用中使用 WCF 服务模型的 Oracle E-business Suite 的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|在 Oracle E-business Suite 中设置调用请求 | [调用在 Oracle E-business Suite 中的请求集](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite.md) | [调用中使用 WCF 服务模型的 Oracle E-business Suite 请求集](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|执行 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作| [在 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-or-executenonquery-in-oracle-e-business-suite.md) |[在使用 WCF 服务模型的 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)||  
|轮询 Oracle 数据库使用 BizTalk Server|[使用 BizTalk Server 轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)|[使用 WCF 服务模型的轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|从 Oracle E-business Suite 接收数据库更改通知|[接收使用 BizTalk Server 的 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[接收使用 WCF 服务模型的 Oracle E-business Suite 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)|[轮询 Oracle E-business Suite SELECT 语句中使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)|  

## <a name="next-steps"></a>后续步骤  
 本部分中的主题提供信息、 过程和示例来帮助你开发的应用程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和.NET 编程解决方案。 
  
-   [创建与 Oracle EBS 的连接](create-a-connection-to-oracle-e-business-suite.md)
-   [获取 Visual Studio 中的 Oracle EBS 操作的元数据](get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
-   [使用绑定属性](read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)
-   [接收基于轮询的数据更改消息](receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)
-   [启用使用 MSDTC 的事务](enable-ms-dtc-to-allow-transactions-for-oracle-e-business-suite-adapter.md)
-   [开发使用 Oracle EBS 适配器的 BizTalk 应用程序](develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)
-   [使用 WCF 服务模型开发应用程序](develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)
-   [使用 WCF 通道模型开发应用程序](develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
-   [使用带有 SharePoint Oracle EBS 适配器](use-the-oracle-e-business-suite-adapter-with-sharepoint.md)
-   [示例](samples-for-the-oracle-ebs-adapter.md)
-   [配置事务属性和应用程序上下文](configure-transaction-properties-and-application-context-in-oracle-ebs-adapter.md)
  
