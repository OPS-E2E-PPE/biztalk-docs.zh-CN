---
title: 开发 Oracle 数据库应用程序使用 WCF 服务模型 |Microsoft Docs
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
ms.openlocfilehash: bdfb72f4901ce8c4ff10f4ff2e664c10e9f7726c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529216"
---
# <a name="develop-oracle-database-applications-using-the-wcf-service-model"></a>开发 Oracle 数据库应用程序使用 WCF 服务模型
最低级别[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]显示在其中客户端调用服务上的操作由客户端和服务终结点之间建立的通道通过交换 SOAP 消息的编程模型。 此模型中，名为 WCF 通道模型，公开的数据类型和方法，使你能够直接在 WCF 通道体系结构上运行。 WCF 通道模型为您提供直接控制对您创建的 SOAP 消息的内容和方式这两个应用程序和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用它们; 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回答复消息可以是详细、 更严格的任务。  
  
 出于此原因，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了另一个名为 WCF 服务模型的编程模型。 WCF 服务模型涉及到使用代理类来调用目标服务上的操作，或若要从客户端接收操作。  
  
- 用于目标服务调用操作的代理类调用 WCF 客户端类。 此类模型由服务公开为强类型化参数使用的.NET 方法的操作。 通过使用 WCF 服务模型，可以调用公开的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅"WCF Client Overview"处[ http://go.microsoft.com/fwlink/?LinkId=91458 ](http://go.microsoft.com/fwlink/?LinkId=91458)。  
  
- 在 WCF 服务模型中，由服务公开的服务协定接口由表示。 此托管的代码表示形式的服务约定调用 WCF 服务约定。 WCF 服务协定建模为具有强类型化参数的方法的操作。 若要从客户端接收操作您实现一个类，WCF 服务，此接口中。 然后可以托管在此类的实例**System.ServiceModel.ServiceHost**启用客户端以调用代码操作。 通过使用 WCF 服务模型和针对 POLLINGSTMT 操作的 WCF 服务协定，您都会收到对 Oracle 数据库使用的轮询操作的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
  使用工具来生成 WCF 客户端类或 WCF 服务协定和关联的服务元数据中的帮助器代码的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开。 您可以使用以下工具：  
  
- ServiceModel Metadata Utility Tool (svcutil.exe)，其中附带了 WCF  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，附带的 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验并提供标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能对由适配器公开的操作。 有关如何生成 WCF 客户端或 WCF 服务约定的详细信息，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
  因为它提供的模型，这就是.NET 程序员所熟悉的和，以通过通道隐藏基础 SOAP 消息交换的复杂性时，WCF 服务模型通常是最佳选择开发的编程解决方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 但是，有的方案中的 WCF 通道模型可能更好的选择。 例如，WCF 服务模型仅支持 ReadLOB 操作流式处理。 这是因为序列化和反序列化的 XML 表示形式中的 SOAP 消息的对象和用来表示它们的服务模型中的.NET 类型之间涉及到读取到内存中的整个消息。 （ReadLOB 操作的结果是此规则的例外。）  
  
  WCF 通道模型为 XML 节点级别上的所有操作流式处理和数据级别的流式处理 ReadLOB 和 UpdateLOB 操作提供支持。 如果处理的查询可返回大型结果集或尝试进行更新 LOB 表的字段中，WCF 通道模型可能是更好的选择。 有关使用 WCF 通道模型的详细信息，请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。  
  
  在本部分中的主题包含信息、 步骤和示例来帮助你创建和使用 WCF 服务模型开发应用程序使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)  
  
-   [元数据和具有 Oracle 数据库的 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/metadata-and-the-wcf-service-model-with-oracle-database.md)  
  
-   [为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)  
  
-   [为 Oracle 数据库配置客户端绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)  
  
-   [通过使用 WCF 服务模型中执行基本的 Insert、 Update、 Delete 和 Select 操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)  
  
-   [使用 WCF 服务模型完成对表具有 Oracle 数据库中的大数据类型的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)  
  
-   [通过使用 WCF 服务模型中调用函数和 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型的 Oracle 数据库中执行的操作使用 REF CURSOR](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型的 Oracle 数据库中执行的操作使用的记录类型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型在 Oracle 数据库中执行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型在 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)  
  
-   [使用 WCF 服务模型的接收 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)