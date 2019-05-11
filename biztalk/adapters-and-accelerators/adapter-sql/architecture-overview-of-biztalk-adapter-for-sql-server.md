---
title: 用于 SQL Server 的 BizTalk 适配器的体系结构概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31eb73f-b73e-4cd3-8b62-207b806175ee
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f837105c816124163bacec0dc15e96544d294dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370279"
---
# <a name="architecture-overview-of-biztalk-adapter-for-sql-server"></a>用于 SQL Server 的 BizTalk 适配器的体系结构概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 此绑定包含一个自定义传输绑定元素，可实现与 SQL Server 数据库通信。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时和公开给应用程序可以通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与通过 ADO.NET 的 SQL Server 数据库进行通信。  


 下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/05e2a88c-a3cc-42a7-9c06-cfdb7c071e70.gif "05e2a88c-a3cc-42a7-9c06-cfdb7c071e70")  

  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开 SQL Server 数据库用作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行的操作和访问 SQL Server 数据库上的数据，客户端应用程序交换的 SOAP 消息具有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图中显示四种方法在其中[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以使用。  
  
- **通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序**。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序使用执行 SQL Server 数据库上的操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型来交换 SOAP 消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。
  
- **通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务应用程序模型**。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端上的 SQL Server 数据库执行操作。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为.NET 方法。 可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 WCF ServiceModel Metadata Utility Tool (svcutil.exe) 来创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开的元数据中的客户端类[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  请参阅[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。
  
- **通过 BizTalk 接收位置或发送端口配置为使用 Microsoft BizTalk Wcf-custom 适配器**。 WCF 自定义适配器，使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]可扩展性功能。 通过使用 WCF 自定义适配器可以选择和配置 SQL DB 绑定和行为的接收位置或发送端口。 有关如何使用详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。 
  
- **通过 IIS 托管的 Web 服务**。 在此方案中，使用标准的 WCF Http 绑定的 IIS 中承载 WCF 服务代理使用该适配器生成的。 这会为 Web 服务向外部用户公开的服务协定。 IIS 自动承载在运行时，这反过来，与 SQL Server 数据库进行通信的适配器。  
  
## <a name="the-sql-adapter-and-wcf"></a>SQL 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 显示基于客户端和服务之间的通道的 SOAP 消息交换的编程模型。 终结点公开的通信的客户端和服务之间发送这些消息。 终结点包括：  
  
- *终结点地址*，它指定接收消息的位置。  
  
- 一个*绑定*，它指定用于交换消息的通信协议。  
  
- 一个*协定*，它指定终结点公开的操作和数据类型。  
  
  一个绑定包含一个或多个绑定元素堆叠在一起以定义如何与终结点交换消息。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 终结点之间的消息交换的分组成一个或多个通道的通道堆栈。 每个通道是绑定的终结点配置中的绑定元素之一的具体实现。 

[WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，SQL DB 绑定 (**Microsoft.Adapters.SQLDB.SQLDBBinding**)。 默认情况下，此绑定包含一个单一的自定义传输绑定元素，SQL DB 适配器绑定元素 (**Microsoft.Adapters.SQLDB.SQLDBAdapter**)，这允许 SQL Server 数据库上的操作。  
  
 **Microsoft.Adapters.SQLDB.SQLDBBinding** （SQL DB 绑定） 和**Microsoft.Adapters.SQLDB.SQLDBAdapter** （SQL DB 适配器绑定元素） 为公共类，并向配置系统还公开。 因为 SQL DB 适配器绑定元素公开时公开，您可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定的扩展功能的支持[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 例如，可以实现自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型解决方案。 聚合数据库操作到单个多功能操作或执行架构操作实现的自定义应用程序和 SQL Server 数据库上的操作之间的转换是执行此操作的原因。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]构建的[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并运行的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时间。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个软件框架和工具基础结构的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于给用户和适配器客户端提供一套丰富的功能。  

## <a name="sql-adapter-and-the-wcf-lob-adapter-sdk"></a>SQL 适配器和 WCF LOB 适配器 SDK
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]实现了一组利用提供的功能的核心组件[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并提供与通过 ADO.NET 的 SQL Server 数据库的连接。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]充当通过它的软件层[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)];ADO.NET 用作通过其层[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 SQL Server 数据库的接口。 下图显示了的内部组件之间的关系[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以及这些组件和 ADO.NET 之间。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/0b15e33b-7f59-4228-bb50-0455f7ed3d85.gif "0b15e33b-7f59-4228-bb50-0455f7ed3d85")  
 
   
## <a name="adonet"></a>ADO.NET  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将与通过 ADO.NET 的 SQL Server 数据库连接。 ADO.NET 提供对 SQL Server 等数据源的一致访问，并帮助检索、 处理，以及修改数据源中的数据。 详细了解[ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx)。
  
 SQL 客户端提供连接到 SQL Server 数据库。 通过提供一个连接 URI 建立与 SQL Server 数据库的连接到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 此连接 URI 包含在其安装 SQL Server 的计算机的名称和数据库的名称。 有关连接 URI 的详细信息，请参阅[创建到 SQL Server 的连接](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)。  
  
## <a name="see-also"></a>请参阅  

 [了解用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)