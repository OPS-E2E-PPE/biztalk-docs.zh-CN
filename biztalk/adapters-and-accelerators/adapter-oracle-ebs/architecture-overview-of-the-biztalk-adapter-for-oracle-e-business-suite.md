---
title: 用于 Oracle E-business Suite 的 BizTalk Adapter 的体系结构概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f840ff23-4d68-4bd3-b115-aa87bc4c99f2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39c2353448a05747d94ae3128968182f428739ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216765"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-e-business-suite"></a>用于 Oracle E-business Suite 的 BizTalk Adapter 的体系结构概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 此绑定包含用于实现与 Oracle E-business Suite 进行通信的单个自定义传输绑定元素。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时，向应用程序可以通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET (ODP.NET) 和 Oracle 客户端，属于 Windows Oracle 数据访问组件 (ODAC) 与 Oracle E-business Suite 通过 Oracle 数据提供商进行通信。  
  
 下图显示了使用开发的解决方案的端到端体系结构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 ![Oracle 数据库适配器体系结构关系图](../../adapters-and-accelerators/adapter-oracle-ebs/media/967bc4a5-852b-479e-8ef0-941773f5991f.gif "967bc4a5-852b-479e-8ef0-941773f5991f")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开为 Oracle E-business Suite[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行的操作和访问 Oracle E-business Suite 上的数据，客户端应用程序交换使用 SOAP 消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图显示四种方式在其中[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可使用。 它们分别是：   
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序使用执行对 Oracle E-business Suite 操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型交换 SOAP 消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端执行对 Oracle E-business Suite 操作。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的运算[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]作为.NET 方法。 你可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 WCF ServiceModel 元数据实用工具 (svcutil.exe) 创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]从公开元数据的客户端类[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
-   通过 BizTalk 接收位置或发送配置为使用 Microsoft BizTalk WCF 自定义适配器的端口。 WCF 自定义适配器启用的使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]扩展性功能。 使用 WCF 自定义适配器中，你可以选择和配置 Oracle EBS 绑定和接收位置的行为或发送端口。 有关如何使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)。  
  
-   通过 IIS 托管的 Web 服务。 在此方案中，使用 basicHttpBinding WCF 绑定的 IIS 中承载 WCF 服务代理生成使用适配器。 这将作为 Web 服务向外部用户公开的服务协定。 IIS 自动托管在运行时，这反过来，与 Oracle E-business Suite 适配器。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]并且 ODAC 始终托管进程的应用程序或服务使用适配器。  
  
## <a name="oracle-ebs-adapter-and-wcf"></a>Oracle EBS 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供一个基于 SOAP 消息的交换对客户端和服务之间的通道的编程模型。 这些消息将由通信的客户端和服务公开的终结点之间发送。 终结点组成：  
  
-   *终结点地址*，它指定从该处接收消息的位置  
  
-   A*绑定*，它指定用于交换消息的通信协议  
  
-   A*协定*，它指定终结点公开的操作和数据类型。  
  
 绑定由一个或多个堆叠在一起以定义如何与终结点交换消息的绑定元素组成。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 会通过组成一个或多个通道的通道堆栈终结点之间的消息交换。 每个通道是一个终结点配置的绑定中的绑定元素的具体实现。 [WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，Oracle E-business Suite 绑定 (**Microsoft.Adapters.OracleEBS.OracleEBSBinding**)。 默认情况下，此绑定包含单个自定义传输绑定元素，Oracle E-business Suite 适配器绑定元素 (**Microsoft.Adapters.OracleEBS.OracleEBSAdapter**)，这样 Oracle 上的操作电子商务套件。  
  
 **Microsoft.Adapters.OracleEBS.OracleEBSBinding** （Oracle E-business Suite 绑定） 和**Microsoft.Adapters.OracleEBS.OracleEBSAdapter** （Oracle E-business Suite 适配器绑定元素） 都是公开的类和还公开给配置系统。 由于 Oracle E-business Suite 适配器绑定元素公开时公开，你可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定支持的扩展的功能[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 例如，可以实现一个自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型解决方案。 聚合数据库操作到单个多功能操作或执行由自定义应用程序实现的操作和对 Oracle E-business Suite 操作之间的架构转换是执行此操作的原因。  

## <a name="oracle-ebs-adapter-and-the-wcf-lob-sdk"></a>Oracle EBS 适配器和 WCF LOB SDK
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，和上运行[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。 


[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供的软件框架和工具可供基础结构，它[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于向用户和适配器客户端提供一组丰富的功能。  它还可以通过该软件层作为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接口与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 ODP.NET 用作通过其层[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Oracle 数据库的接口。 

下图显示的内部组件之间的关系[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，和 ODP.NET:  
  
 ![Oracle E &#45;业务适配器内部体系结构](../../adapters-and-accelerators/adapter-oracle-ebs/media/bts-oracleebs-architecture-internalc.gif "bts_OracleEBS_Architecture_Internalc")  
  
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将与 Oracle E-business Suite 通过 ODP.NET 和 Oracle 客户端连接。 这两个这些组件是一部分的 Oracle 数据访问组件 (ODAC)。  
  
 ODP.NET 实现的数据提供程序与 ADO.NET 界面一致 Oracle E-business Suite。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由 ODP.NET 公开的类用于对 Oracle E-business Suite 进行操作。  
  
 Oracle 客户端提供与 Oracle E-business Suite 的连接。 通过提供一个连接 URI 建立与 Oracle E-business Suite 的连接到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 你可以通过两种方式指定连接 URI:  
  
-   **使用 tnsnames.ora**。 在此方法中，连接由适配器客户端提供的 URI 包含在 tnsnames.ora 文件中指定的网络服务名称。 适配器从文件中的 net 服务名称条目中提取的连接参数，例如服务器名称、 服务名称、 端口号等。 若要使用此方法，必须配置运行 Oracle 客户端的计算机为 tnsnames.ora 文件中包括 Oracle 数据库的 net 服务名称。  
  
-   **而无需使用 tnsnames.ora**。 在此方法中，适配器客户端指定直接在连接 URI 中的连接参数。 这不需要的 net 服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。 此方法甚至不需要在客户端计算机上显示的 tnsnames.ora 文件。  
  
 有关连接 URI 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。  
  
## <a name="next"></a>Next
[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)