---
title: 用于 SQL Server 的 BizTalk Adapter 的体系结构概述 |Microsoft 文档
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
ms.openlocfilehash: 841f07bfb8c027ab2bfc1b98e23b225af42b449c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225245"
---
# <a name="architecture-overview-of-biztalk-adapter-for-sql-server"></a>用于 SQL Server 的 BizTalk Adapter 的体系结构概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 此绑定包含用于实现与 SQL Server 数据库进行通信的单个自定义传输绑定元素。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时，向应用程序可以通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与通过 ADO.NET 的 SQL Server 数据库进行通信。  


 下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/05e2a88c-a3cc-42a7-9c06-cfdb7c071e70.gif "05e2a88c-a3cc-42a7-9c06-cfdb7c071e70")  

  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开 SQL Server 数据库作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行操作并访问 SQL Server 数据库上的数据，客户端应用程序交换使用 SOAP 消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图显示四种方式在其中[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可使用。  
  
-   **通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序**。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序使用执行 SQL Server 数据库上的操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型交换 SOAP 消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。
  
-   **通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序**。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端在 SQL Server 数据库上执行操作。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的运算[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为.NET 方法。 你可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 WCF ServiceModel 元数据实用工具 (svcutil.exe) 创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]从公开元数据的客户端类[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  请参阅[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。
  
-   **通过 BizTalk 接收位置或发送配置为使用 Microsoft BizTalk WCF 自定义适配器的端口**。 WCF 自定义适配器启用的使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]扩展性功能。 使用 WCF 自定义适配器中，你可以选择和配置 SQL DB 绑定和接收位置的行为或发送端口。 有关如何使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 服务器应用程序](../../core/developing-biztalk-server-applications.md)。 
  
-   **通过 IIS 托管的 Web 服务**。 在此方案中，使用标准的 WCF Http 绑定的 IIS 中承载 WCF 服务代理生成使用适配器。 这将作为 Web 服务向外部用户公开的服务协定。 IIS 自动托管在运行时，这，反过来，与 SQL Server 数据库进行通信的适配器。  
  
## <a name="the-sql-adapter-and-wcf"></a>SQL 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供一个基于 SOAP 消息的交换对客户端和服务之间的通道的编程模型。 这些消息将由通信的客户端和服务公开的终结点之间发送。 终结点组成：  
  
-   *终结点地址*，它指定从该处接收消息的位置。  
  
-   A*绑定*，它指定用于交换消息的通信协议。  
  
-   A*协定*，它指定终结点公开的操作和数据类型。  
  
 绑定由一个或多个堆叠在一起以定义如何与终结点交换消息的绑定元素组成。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 会通过组成一个或多个通道的通道堆栈终结点之间的消息交换。 每个通道是一个终结点配置的绑定中的绑定元素的具体实现。 

[WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，SQL DB 绑定 (**Microsoft.Adapters.SQLDB.SQLDBBinding**)。 默认情况下，此绑定包含单个自定义传输绑定元素，SQL DB 适配器绑定元素 (**Microsoft.Adapters.SQLDB.SQLDBAdapter**)，从而使 SQL Server 数据库上的操作。  
  
 **Microsoft.Adapters.SQLDB.SQLDBBinding** （SQL DB 绑定） 和**Microsoft.Adapters.SQLDB.SQLDBAdapter** （SQL DB 适配器绑定元素） 为公共类，并还公开给配置系统。 由于 SQL DB 适配器绑定元素公开时公开，你可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定支持的扩展的功能[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 例如，可以实现一个自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型解决方案。 聚合数据库操作到单个多功能操作或执行由自定义应用程序实现的操作和 SQL Server 数据库上的操作之间的架构转换是执行此操作的原因。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，和上运行[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时间。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供的软件框架和工具可供基础结构，它[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于向用户和适配器客户端提供一组丰富的功能。  

## <a name="sql-adapter-and-the-wcf-lob-adapter-sdk"></a>SQL 适配器和 WCF LOB 适配器 SDK
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]实现利用提供的功能的核心组件的一组[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和提供与通过 ADO.NET 的 SQL Server 数据库的连接。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]用作通过其软件层[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接口与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)];ADO.NET 用作通过其层[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 SQL Server 数据库的接口。 下图显示的内部组件之间的关系[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以及这些组件和 ADO.NET 之间。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/0b15e33b-7f59-4228-bb50-0455f7ed3d85.gif "0b15e33b-7f59-4228-bb50-0455f7ed3d85")  
 
   
## <a name="adonet"></a>ADO.NET  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将与通过 ADO.NET 的 SQL Server 数据库连接。 ADO.NET 提供一致地访问数据源，如 SQL Server，并帮助检索、 处理，以及修改数据源中的数据。 阅读更多有关[ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx)。
  
 SQL 客户端提供与 SQL Server 数据库的连接。 通过提供一个连接 URI 建立与 SQL Server 数据库的连接到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 此连接 URI 包含在其安装 SQL Server 的计算机的名称和数据库的名称。 有关连接 URI 的详细信息，请参阅[创建与 SQL Server 的连接](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)。  
  
## <a name="see-also"></a>另请参阅  

 [理解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)