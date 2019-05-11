---
title: 用于 Oracle E-business Suite 的 BizTalk 适配器的体系结构概述 |Microsoft Docs
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
ms.openlocfilehash: e5360a26fc0df13548b7c0e6b26e5a59cb5eba50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375801"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-e-business-suite"></a>用于 Oracle E-business Suite 的 BizTalk 适配器的体系结构概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 此绑定包含可实现与 Oracle E-business Suite 的通信的单个自定义传输绑定元素。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时和公开给应用程序可以通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Oracle 数据提供程序通过 Oracle E-business Suite 的.NET (ODP.NET) 和 Oracle 客户端，这属于 Windows Oracle 数据访问组件 (ODAC) 进行通信。  
  
 下图显示了使用开发的解决方案的端到端体系结构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 ![Oracle 数据库适配器体系结构关系图](../../adapters-and-accelerators/adapter-oracle-ebs/media/967bc4a5-852b-479e-8ef0-941773f5991f.gif "967bc4a5-852b-479e-8ef0-941773f5991f")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开为 Oracle E-business Suite[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行的操作和访问 Oracle E-business Suite 的数据，客户端应用程序交换的 SOAP 消息具有[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图显示通过四种方式在其中[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以使用。 它们分别是：   
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序使用执行对 Oracle E-business Suite 操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型来交换 SOAP 消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
- 通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端执行对 Oracle E-business Suite 的操作。 一个[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]作为.NET 方法。 可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 WCF ServiceModel Metadata Utility Tool (svcutil.exe) 来创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开的元数据中的客户端类[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
- 通过 BizTalk 接收位置或发送端口配置为使用 Microsoft BizTalk Wcf-custom 适配器。 WCF 自定义适配器，使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]可扩展性功能。 通过使用 WCF 自定义适配器可以选择并配置 Oracle EBS 绑定和行为的接收位置或发送端口。 有关如何使用详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)。  
  
- 通过 IIS 托管的 Web 服务。 在此方案中，使用 basicHttpBinding WCF 绑定的 IIS 中承载 WCF 服务代理使用该适配器生成的。 这会为 Web 服务向外部用户公开的服务协定。 IIS 将自动托管在运行时，这反过来，与 Oracle E-business Suite 适配器。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和 ODAC 始终托管进程的应用程序或使用适配器服务。  
  
## <a name="oracle-ebs-adapter-and-wcf"></a>Oracle EBS 适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 显示基于客户端和服务之间的通道的 SOAP 消息交换的编程模型。 终结点公开的通信的客户端和服务之间发送这些消息。 终结点包括：  
  
- *终结点地址*，它指定接收消息的位置  
  
- 一个*绑定*，它指定用于交换消息的通信协议  
  
- 一个*协定*，它指定终结点公开的操作和数据类型。  
  
  一个绑定包含一个或多个绑定元素堆叠在一起以定义如何与终结点交换消息。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 终结点之间的消息交换的分组成一个或多个通道的通道堆栈。 每个通道是绑定的终结点配置中的绑定元素之一的具体实现。 [WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
  [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，Oracle E-business Suite 绑定 (**Microsoft.Adapters.OracleEBS.OracleEBSBinding**)。 默认情况下，此绑定包含一个单一的自定义传输绑定元素，Oracle E-business Suite 适配器绑定元素 (**Microsoft.Adapters.OracleEBS.OracleEBSAdapter**)，这样在 Oracle 上的操作电子商务套件。  
  
  **Microsoft.Adapters.OracleEBS.OracleEBSBinding** （Oracle E-business Suite 绑定） 和**Microsoft.Adapters.OracleEBS.OracleEBSAdapter** （Oracle E-business Suite 适配器绑定元素） 都是公共类和还向配置系统公开。 因为 Oracle E-business Suite 适配器绑定元素公开时公开，您可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定的扩展功能的支持[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 例如，可以实现自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型解决方案。 聚合数据库操作到单个多功能操作或执行架构由自定义应用程序实现的操作和对 Oracle E-business Suite 操作之间的转换是执行此操作的原因。  

## <a name="oracle-ebs-adapter-and-the-wcf-lob-sdk"></a>Oracle EBS 适配器和 WCF LOB SDK
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]构建的[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并运行的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。 


[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个软件框架和工具基础结构的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于给用户和适配器客户端提供一套丰富的功能。  它还可以通过该软件层作为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 ODP.NET 用作通过其层[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Oracle 数据库的接口。 

下图显示了的内部组件之间的关系[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，和 ODP.NET:  
  
 ![Oracle 电子&#45;业务适配器内部体系结构](../../adapters-and-accelerators/adapter-oracle-ebs/media/bts-oracleebs-architecture-internalc.gif "bts_OracleEBS_Architecture_Internalc")  
  
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 Oracle E-business Suite 通过 ODP.NET 和 Oracle 客户端连接。 这两个这些组件是一部分的 Oracle 数据访问组件 (ODAC)。  
  
 ODP.NET 实现与 ADO.NET 接口一致 Oracle E-business Suite 的数据提供程序。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 公开的类用于在 Oracle E-business Suite 上运行。  
  
 Oracle 客户端提供与 Oracle E-business Suite 的连接。 通过提供一个连接 URI 建立与 Oracle E-business Suite 的连接到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 您可以通过两种方式指定连接 URI:  
  
- **使用 tnsnames.ora**。 在此方法中，连接由适配器客户端提供的 URI 包含 tnsnames.ora 文件中指定的网络服务名称。 适配器从文件中的 net 服务名称条目中提取连接参数，例如服务器名称、 服务名称、 端口号等。 若要使用此方法，运行 Oracle 客户端的计算机必须配置为在 tnsnames.ora 文件中包含的 Oracle 数据库的 net 服务名称。  
  
- **而无需使用 tnsnames.ora**。 在此方法时，适配器客户端指定直接在连接 URI 中的连接参数。 这不需要网络服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。 这种方法甚至不需要在客户端计算机上显示的 tnsnames.ora 文件。  
  
  有关连接 URI 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。  
  
## <a name="next"></a>Next
[保护 Oracle EBS 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)