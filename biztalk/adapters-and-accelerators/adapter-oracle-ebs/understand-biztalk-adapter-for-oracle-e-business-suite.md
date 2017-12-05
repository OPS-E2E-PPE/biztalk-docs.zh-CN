---
title: "了解有关 Oracle E-business Suite 的 BizTalk Adapter |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a3f0a8-fc64-42cd-bb7c-0a6f527622e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 342ffbd77434a470e3afdd10ae1c708c8734e85c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>了解有关 Oracle E-business Suite 的 BizTalk Adapter
## <a name="biztalk-adapter-pack-features"></a>BizTalk 适配器包功能
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
-   **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的设计时体验常见和用户友好。  
  
-   **各种编程选项**。 适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk Server 支持的模型。  
  
-   **跨 Lob 的统一体验**。 适配器标准化上使用 WCF 和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供统一的体验的获得对任何 LOB 系统的访问。  
  
 如前文所述，适配器均构建在之上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 此 SDK 提供用于生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器的通用基础。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开作为 WCF 通道的集成适配器结合适配器策略与 Microsoft 服务策略。 有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<*安装驱动器*\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。  

## <a name="overview-of-the-oracle-ebs-adapter"></a>Oracle EBS 适配器的概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开 Oracle E-business Suite 作为 WCF 服务。 适配器客户端可以通过交换 SOAP 消息与适配器执行对 Oracle E-business Suite 操作。 适配器使用 SOAP 消息，并且相应 ODP.NET 调用来执行该操作。 适配器回客户端的 SOAP 消息的形式返回从 Oracle E-business Suite 的响应。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示 Oracle E-business Suite 项目 （PL/SQL Api、 界面表/视图、 并发程序和请求集） 和描述基础 Oracle 数据库项目 （如表、 函数和过程） 的元数据在窗体的 Web 服务描述语言 (WSDL) 中 SOAP 消息的结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据。 适配器还编程解决方案中生成可用的编程项目。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET (ODP.NET) 11.1.0.7 使用 Oracle 数据提供程序与 Oracle E-business Suite 进行通信。 ODP.NET 11.1.0.7 是 Oracle 数据访问组件 (ODAC) 以下组件之一。 你可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Oracle E-business Suite 通信通过以下方式：  
  
-   通过开发 BizTalk 应用程序。 有关详细信息，请参阅[开发 BizTalk 服务器应用程序](../../core/developing-biztalk-server-applications.md)。  
  
-   通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 有关详细信息，请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)。  
  
-   通过使用 WCF 通道模型。 有关详细信息，请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  

## <a name="access-to-oracle-e-business-suite"></a>对 Oracle E-business Suite 的访问
 要在 Oracle E-business Suite 中执行操作，适配器客户端必须在 Oracle E-business Suite 中具有对相关项目的访问。 外部应用程序可以添加或删除 Oracle E-business Suite 接口表和数据库表中的数据，通过使用 SQL 语句。 应用程序还可以通过使用视图、 函数和过程访问接口表和数据库表中的数据。 与[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，适配器客户端可以浏览与基础数据库中 Oracle E-business Suite 的项目。 在 Oracle E-business Suite 适配器客户端可以浏览接口表、 界面视图、 并发程序，并请求集同时基础的 Oracle 数据库中，适配器客户端可以浏览表、 视图、 存储的过程、 函数、 PL/SQL Api和包。 适配器客户端可以选择他们需要用其解决方案和检索元数据的这些项目的项目。 这使用户能够访问和 Oracle E-business Suite 和基础的 Oracle 数据库中执行的操作的项目。  
  
 本部分列出的功能[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="more-good-stuff"></a>更多有用内容  
  
-    [使用适配器连接到 Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [浏览，搜索，并获得 Oracle E-business Suite 元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [Oracle E-business Suite 适配器支持何种操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [处理与 Oracle 数据库适配器的事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Oracle EBS 适配器客户端的功能](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [用于 Oracle E-business Suite 的 BizTalk Adapter 中的主要功能](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite 的 BizTalk 适配器的限制](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>另请参阅  
[入门](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)