---
title: 了解用于 Oracle E-business Suite 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77a3f0a8-fc64-42cd-bb7c-0a6f527622e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf84eef3d5e1ec4730926dd34b6533e1a7491f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980542"
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>了解用于 Oracle E-business Suite 的 BizTalk 适配器
## <a name="biztalk-adapter-pack-features"></a>BizTalk 适配器包功能
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
- **一致的设计时体验**。 适配器提供了常见用户友好设计时体验，用于浏览、 搜索和检索 LOB 项目的元数据。  
  
- **不同的编程选项**。 适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk Server 支持的模型。  
  
- **跨 Lob 的统一体验**。 使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获取访问权的任何 LOB 系统的统一的体验。  
  
  如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。 WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。 WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。 有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。

## <a name="overview-of-the-oracle-ebs-adapter"></a>Oracle EBS 适配器概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开为 WCF 服务的 Oracle E-business Suite。 适配器客户端可以通过该适配器与交换的 SOAP 消息执行对 Oracle E-business Suite 的操作。 适配器将使用 SOAP 消息并调用相应 ODP.NET 来执行该操作。 适配器从 Oracle E-business Suite 中返回的响应，返回到 SOAP 消息的窗体中的客户端。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示 Oracle E-business Suite 项目 （PL/SQL Api、 接口表/视图、 并发程序和请求集） 和描述基础 Oracle 数据库项目 （如表、 函数和过程） 的元数据窗体的 Web 服务描述语言 (WSDL) 中的 SOAP 消息的结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]启用适配器客户端来检索操作的元数据。 适配器还生成的编程项目，可以使用编程解决方案中。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，并[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET (ODP.NET) 11.1.0.7 使用 Oracle 数据提供程序与 Oracle E-business Suite 进行通信。 ODP.NET 11.1.0.7 是 Oracle 数据访问组件 (ODAC) 的组件之一。 可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以与 Oracle E-business Suite 中通过以下方式进行通信：  
  
- 通过开发 BizTalk 应用程序。 有关详细信息，请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。  
  
- 通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 有关详细信息，请参阅[开发 Oracle 数据库应用程序通过使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)。  
  
- 通过使用 WCF 通道模型。 有关详细信息，请参阅[通过使用 WCF 通道模型开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  

## <a name="access-to-oracle-e-business-suite"></a>对 Oracle E-business Suite 的访问
 若要执行 Oracle E-business Suite 中操作，适配器客户端必须 Oracle E-business Suite 中具有对相关项目的访问。 外部应用程序可以添加或删除 Oracle E-business Suite 界面表和数据库表中的数据，通过使用 SQL 语句。 应用程序还可以通过使用视图、 函数和过程访问的接口表和数据库表中的数据。 使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，适配器客户端可以浏览 Oracle E-business Suite 中的项目与基础数据库。 在 Oracle E-business Suite 适配器客户端可以浏览接口表、 界面视图、 并发程序，并请求集同时基础的 Oracle 数据库中，适配器客户端可以浏览表、 视图、 存储的过程、 函数、 PL/SQL Api和包。 适配器客户端可以选择他们需要为他们的解决方案和检索这些项目的元数据的项目。 这使用户可以访问和 Oracle E-business Suite 和基础的 Oracle 数据库中执行项目上的操作。  
  
 本部分中列出的功能[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="more-good-stuff"></a>更多有用内容  
  
-    [使用适配器连接到 Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [浏览、 搜索和获取 Oracle E-business Suite 元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [Oracle E-business Suite 适配器支持哪些操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [使用 Oracle 数据库适配器处理事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Oracle EBS 适配器客户端的功能](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [用于 Oracle E-business Suite 的 BizTalk 适配器的主要功能](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [用于 Oracle E-business Suite 的 BizTalk 适配器的限制](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>请参阅  
[入门](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)