---
title: 开发使用 WCF 服务模型的 Oracle 数据库应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performing operations, by using the WCF service model
- developing applications, by using the WCF service model
- WCF service model, using to develop applications
ms.assetid: 3f2c60b2-4835-492d-8c3c-ed35d3e4c517
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 548ca256d4395aefd67681229e9669ef2afcc2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215637"
---
# <a name="develop-oracle-database-applications-using-the-wcf-service-model"></a>开发使用 WCF 服务模型的 Oracle 数据库应用程序
在最低级别，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供一个在其中客户端调用服务上的操作通过在客户端和服务终结点之间建立信道交换 SOAP 消息的编程模型。 此模型中，称为 WCF 通道模型，公开数据类型和方法，您可以直接对 WCF 通道体系结构进行操作。 WCF 通道模型为您提供通过你创建的 SOAP 消息的内容和方式这两个应用程序的直接控制和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用它们; 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回答复消息可以是详细、 更严格的任务。  
  
 为此，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供另一个调用 WCF 服务模型的编程模型。 WCF 服务模型涉及使用代理类来调用针对目标服务的操作或从客户端接收操作。  
  
-   用于调用操作将针对目标服务的代理类调用 WCF 客户端类。 此类模型作为使用强类型参数的.NET 方法由服务公开的操作。 通过使用 WCF 服务模型，你可以调用公开的运算[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅"WCF 客户端概述"在[http://go.microsoft.com/fwlink/?LinkId=91458](http://go.microsoft.com/fwlink/?LinkId=91458)。  
  
-   在 WCF 服务模型中，由服务公开的服务协定表示由接口。 此托管的代码表示形式的服务协定中调用 WCF 服务协定。 WCF 服务协定建模为使用强类型参数的方法的操作。 若要从客户端接收操作，则实现类，WCF 服务，请从此接口。 然后可以托管在此类的实例**System.ServiceModel.ServiceHost**使客户端以调用你的代码上的操作。 可以通过使用 WCF 服务模型和指向 POLLINGSTMT 操作的 WCF 服务协定，接收对 Oracle 数据库使用的轮询操作的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 使用工具来生成 WCF 客户端类或 WCF 服务协定和关联的服务元数据中的帮助器代码，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开。 你可以使用以下工具之一：  
  
-   ServiceModel 元数据实用工具 (svcutil.exe)，其中附带 WCF  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，其中附带[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验和显示标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能公开的适配器操作。 有关如何生成 WCF 客户端或 WCF 服务约定的详细信息，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
 因为它提供的模型，可为.NET 程序员所熟悉和，以通过通道隐藏基础 SOAP 消息交换的复杂性，WCF 服务模型通常是最佳选择，以编程的开发解决方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 但是，有一些的情形，WCF 通道模型可能是更好的选择。 例如，WCF 服务模型仅支持用于 ReadLOB 操作的流式处理。 这是因为序列化和反序列化的 XML 表示形式在 SOAP 消息的对象和用于表示它们的服务模型中的.NET 类型之间涉及到读取到内存的整个消息。 （ReadLOB 操作的结果是此规则的例外。）  
  
 WCF 通道模型适合 XML 节点级别上的所有操作流式传输和数据级流 ReadLOB 和 UpdateLOB 操作提供支持。 如果你处理的查询中返回大型结果集，或尝试更新表中的 LOB 字段，WCF 通道模型可能是更好的选择。 有关使用 WCF 通道模型的详细信息，请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。  
  
 本部分中的主题包含信息、 过程和示例来帮助你创建并使用 WCF 服务模型来开发应用程序使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)  
  
-   [元数据和 WCF 服务模型与 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/metadata-and-the-wcf-service-model-with-oracle-database.md)  
  
-   [为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)  
  
-   [用于 Oracle 数据库配置客户端绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)  
  
-   [通过使用 WCF 服务模型中执行基本的插入、 更新、 删除和选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)  
  
-   [使用 WCF 服务模型完成对表具有 Oracle 数据库中的大数据类型的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)  
  
-   [通过使用 WCF 服务模型中调用函数和 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型的 Oracle 数据库中执行操作使用 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型的 Oracle 数据库中执行操作使用的记录类型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [在 Oracle 数据库中执行 SQLEXECUTE 操作，通过使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [接收基于轮询的数据更改消息 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)  
  
-   [使用 WCF 服务模型的接收 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)