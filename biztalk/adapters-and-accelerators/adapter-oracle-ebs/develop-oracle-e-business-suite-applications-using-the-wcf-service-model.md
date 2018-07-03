---
title: 开发 Oracle E-business Suite 应用程序使用 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cf3430d-12e9-437c-b398-d978faa4da2b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b290ef99349d970179b07ecfce45c72499d88c5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996014"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-service-model"></a>开发 Oracle E-business Suite 应用程序使用 WCF 服务模型
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] 提供编程模型调用 WCF 服务模型，连接到[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。 服务模型已添加到 WCF，若要解决，情况情况下，某些 WCF 通道编程模型的限制。  
  
 WCF 服务模型使用熟悉的.NET 范例来隐藏通过通道交换 SOAP 消息的复杂性。 服务模型通过读取到内存的整个 SOAP 消息，然后再将信息复制到.NET 数据结构来实现这种简化。 加载到内存中的长消息可能不可行的某些应用程序。 在这些情况下，开发人员应使用 WCF 通道模型。 有关使用 WCF 通道模型的详细信息，请参阅[通过使用 WCF 通道模型开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)。  
  
 最低级别[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]显示在其中客户端调用服务上的操作由客户端和服务终结点之间建立的通道通过交换 SOAP 消息的 WCF 通道模型。 WCF 通道模型公开的数据类型和方法，使你能够直接在 WCF 通道体系结构上运行。 WCF 通道模型为您提供直接控制对您创建的 SOAP 消息的内容和方式这两个应用程序和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用它们。 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。  
  
 WCF 服务模型使用的代理类调用将针对目标服务的操作或从客户端接收操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite 公开为 WCF 服务可在其调用操作。  
  
- 用于目标服务调用操作的代理类调用 WCF 客户端类。 此类模型由服务公开为强类型化参数使用的.NET 方法的操作。 通过使用 WCF 服务模型，可以调用公开的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。
  
  您可以使用以下工具之一生成 WCF 客户端类和关联的帮助程序代码从服务元数据的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开：  
  
- **ServiceModel Metadata Utility Tool (svcutil.exe)**，WCF 附带的。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** ，其中附带[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，并与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验。 此工具提供了一个标准的 Microsoft Windows 界面，可提供功能强大的浏览和搜索功能对该适配器公开的操作。 有关如何生成 WCF 客户端的详细信息，请参阅[为 Oracle E-business Suite 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
## <a name="in-this-section"></a>本节内容  
 以下主题提供有关如何开发使用 WCF 服务模型的应用程序的信息：  
  
-   [使用 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [元数据和具有 Oracle E-business Suite 的 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/metadata-and-the-wcf-service-model-with-oracle-e-business-suite.md)  
  
-   [为 Oracle E-business Suite 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)  
  
-   [用于 Oracle E-business Suite 中配置客户端绑定](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)  
  
-   [执行插入、 更新、 删除或对界面表和视图使用 WCF 服务模型的选择操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)  
  
-   [调用 Oracle E-business Suite 使用 WCF 服务模型中的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [调用请求集 Oracle E-business Suite 使用 WCF 服务模型中](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [在 Oracle E-business Suite 使用 WCF 服务模型中执行 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)  
  
-   [使用 WCF 服务模型轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)  
  
-   [Oracle E-business Suite 使用接收数据库更改通知 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)