---
title: 开发 BizTalk 中的 Oracle E-business Suite 应用程序 |Microsoft Docs
description: 创建 Oracle EBS 应用程序使用 WCF 或 BizTalk Server 使用 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7b1ebff-b3f8-4e07-a089-d1d5bfb78d56
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f756a983dcdd8753b55bca1844f1fea5527ee692
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375819"
---
# <a name="develop-your-oracle-e-business-suite-applications"></a>开发 Oracle E-business Suite 应用程序

## <a name="overview"></a>概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]绑定。 客户端应用程序可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]调用 Oracle E-business Suite 项目上的操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可使用：  
  
- 通过中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 通过调用客户端代理的实例上的方法。  
  
- 通过在使用 WCF 通道模型的代码中某个通道实例发送 SOAP 消息。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk 与 WCF 服务与 WCF 通道 
  
 下表中：  
  
- 列出了可对 Oracle E-business Suite 的不同操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
- 提供了指向包含有关执行任务使用所选的方法的信息的主题 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型)。  
  
|操作|BizTalk Server|WCF 服务模型|WCF 通道模型|  
|---|---|---|---|  
|对界面表和视图执行操作 | [插入、 更新、 删除或选择对界面表和界面视图与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-or-select-on-interface-tables-and-views-with-oracle-ebs.md) |[插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[Oracle E-business Suite 使用 WCF 通道模型中运行插入操作在界面表](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)|  
|执行对表和视图包含大型数据类型的操作 | [完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md) |[完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)||  
|执行对 Oracle 数据库的复合操作 | [完成对 Oracle E-business Suite 的复合操作](../../adapters-and-accelerators/adapter-oracle-ebs/complete-composite-operations-on-oracle-e-business-suite.md)|||  
|Oracle E-business Suite 中调用并发程序 | [调用 Oracle E-business Suite 中的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-concurrent-programs-in-oracle-e-business-suite.md) | [调用 Oracle E-business Suite 使用 WCF 服务模型中的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Oracle E-business Suite 中的调用请求集 | [调用 Oracle E-business Suite 中的请求集](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite.md) | [调用请求集 Oracle E-business Suite 使用 WCF 服务模型中](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|执行 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作| [Oracle E-business Suite 中的 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-or-executenonquery-in-oracle-e-business-suite.md) |[Oracle E-business Suite 使用 WCF 服务模型中的 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)||  
|轮询 Oracle 数据库使用 BizTalk Server|[使用 BizTalk Server 轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)|[使用 WCF 服务模型轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|从 Oracle E-business Suite 接收数据库更改通知|[接收使用 BizTalk Server 的 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[Oracle E-business Suite 使用接收数据库更改通知 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)|[SELECT 语句中使用 WCF 通道模型轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)|  

## <a name="next-steps"></a>后续步骤  
 在本部分中的主题提供信息、 步骤和示例，以帮助您开发使用的应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在这种[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和.NET 编程解决方案。 
  
-   [创建与 Oracle EBS 的连接](create-a-connection-to-oracle-e-business-suite.md)
-   [在 Visual Studio 中获取 Oracle EBS 操作的元数据](get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
-   [使用绑定属性](read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)
-   [接收基于轮询的数据更改消息](receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)
-   [使用 MSDTC 启用事务](enable-ms-dtc-to-allow-transactions-for-oracle-e-business-suite-adapter.md)
-   [使用 Oracle EBS 适配器开发 BizTalk 应用程序](develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)
-   [使用 WCF 服务模型开发应用程序](develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)
-   [使用 WCF 通道模型开发应用程序](develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
-   [使用包含 SharePoint 的 Oracle EBS 适配器](use-the-oracle-e-business-suite-adapter-with-sharepoint.md)
-   [示例](samples-for-the-oracle-ebs-adapter.md)
-   [配置事务属性和应用程序上下文](configure-transaction-properties-and-application-context-in-oracle-ebs-adapter.md)
  
