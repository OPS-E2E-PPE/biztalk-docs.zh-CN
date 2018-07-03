---
title: 浏览、 搜索和获取 SAP 元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata
- adapters, surfacing metadata
- TRFC
- RFC
- metadata, browsing, searching, retrieving
- adapters, operations
- BAPI
- IDOC
ms.assetid: 5f0d7c1f-d6e1-4c56-8d8e-1f5d537aa3ce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa942786cda8c5e1070b3fa1c66e3300ffd16d4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984054"
---
# <a name="browse-search-and-get-sap-metadata"></a>浏览、 搜索和获取 SAP 元数据
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面元数据从 SAP 系统。 此元数据描述用于与 SAP 系统使用的适配器进行通信的消息结构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持两个接口用于检索元数据。  
  
- **MetadataExchange**提供的[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 SAP 系统中获取元数据。  
  
- **IMetadataRetrievalContract**提供的[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持的元数据浏览和搜索功能的适配器。  
  
  目标之一[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开为 WCF 服务的 SAP 系统。 该适配器显示 SAP 项目 （Rfc、 Bapi 和 Idoc） 作为适配器客户端可以调用的操作。 适配器还显示可用于发送或接收来自 SAP 系统的 Idoc 某些特定操作。 在本主题后面列出这些操作。  
  
  可以浏览、 搜索，并通过使用 WCF 服务模型，使用 WCF 通道模型，检索元数据或通过创建 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
  使用 WCF 服务模型时，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成在 SAP 系统上执行操作的代理类。 在使用 BizTalk 项目，您必须使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成你想要在 SAP 系统上执行的操作的元数据。  
  
  有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端能够浏览 Rfc、 Trfc、 Bapi 和公开的 SAP 系统的 Idoc。 作为元数据浏览操作的一部分，适配器可呈现 Rfc 和 Bapi 的操作。 为 Idoc，适配器可呈现用于发送和接收 Idoc 的操作。 这些操作是可从[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 SAP 元数据进行分类的以下节点：  
  
- **RFC**。 此节点包含公开的 SAP 系统的 Rfc，表示在 SAP 中的函数模块。 该适配器将 Rfc 分类到多个逻辑级别并公开到适配器客户端的层次结构视图。 RFC 是在此层次结构的最低级别，并公开为可由外部应用程序调用操作。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 RFC SDK 为 Rfc 生成元数据。 该适配器可以调用它可为其生成元数据这些 Rfc。  
  
   非公开作为操作 Rfc，适配器还会呈现某些特定操作如**RfcGetAttributes**。 有关这些操作的详细信息，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  
  
- **TRFC**。 此节点包含由 SAP 系统公开 Trfc。 Trfc 不是在 SAP 系统，但而不是一种机制来调用 Rfc 传统项目。 Trfc 归在单独的节点，因为它们的元数据的特征是不同于 Rfc。 具体而言，Rfc 还包括导出参数。 该适配器将 Trfc 分类到多个逻辑级别并公开到适配器客户端的层次结构视图。 TRFC 是在此层次结构的最低级别，并公开为可由外部应用程序调用操作。  
  
   非公开作为操作 Trfc，适配器还会呈现某些特定操作如**RfcConfirmTransID**。 有关这些操作的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
- **BAPI**。 此节点包含公开 SAP 系统的 Bapi。 该适配器将 Bapi 分类到多个逻辑级别并公开到适配器客户端的层次结构视图。 BAPI 是在此层次结构的最低级别，并公开为可由外部应用程序调用操作。  
  
- **IDOC**。 此节点包含公开的 SAP 系统的 Idoc。 适配器对 Idoc 进行分类到多个逻辑级别并公开到适配器客户端的层次结构视图。 该适配器公开 idoc 的操作包括：  
  
  - **发送**并**接收**。 适配器客户端可以使用这些操作来发送和接收来自 SAP 系统使用强类型架构的 Idoc。  
  
  - **SendIdoc**并**ReceiveIdoc**。 适配器客户端可以使用这些操作来发送和接收来自 SAP 系统使用弱类型的架构的 Idoc。  
  
    有关这些操作的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  
  
  有关元数据的分类方式的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 在中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器客户端可以通过使用依赖于基础 Rfc 的搜索表达式 SAP 系统中搜索元数据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用。 下表列出了 SAP 项目和适配器客户端可以搜索在其下的元数据层次结构。  
  
|项目|在 GUI 中的节点下的搜索|  
|--------------|------------------------------------|  
|RFC|-/RFC<br />-   /RFC/[Application Group]|  
|tRFC|-/TRFC<br />-   /TRFC/[Application Group]|  
|BAPI|-   /BAPI|  
|IDOC|-   /IDOC|  
  
 下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+（加号）|匹配一个字符。<br /><br /> 例如，A + 匹配 AB，交流，AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，ABC 匹配。|  
  
## <a name="retrieving-metadata"></a>检索元数据  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端能够检索 SAP 系统，包括详细的元数据特征的元数据：  
  
- Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 RFC 名称以及导入、 导出、 更改和表参数。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还对必需和可选参数，此外会检索参数，参数的字段长度的数据类型。  
  
- Trfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索类似于 RFC，除了导出参数的详细信息。 TRFC 调用是异步的因为不检索任何输出参数。  
  
- Bapi，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索业务对象名称、 业务对象方法名称和其他类似于 Rfc 的特定信息。  
  
- 为 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 IDOC 类型、 发行版号、 版本、 IDOC 控制记录、 IDOC 数据记录和 IDOC 段的其他信息。  
  
  > [!NOTE]
  >  如果 IDOC 的元数据包含下限和上限值 （范围） 的数据类型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以字符串形式公开的。 如果元数据仅包含低值，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开，作为枚举。  
  
> [!NOTE]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开 SAP 函数参数中按字母顺序，而不考虑 SAP 函数定义中参数的排序方式。 这是由于以下原因：  
> 
> - 不同版本的 SAP RFC SDK 以不同的顺序返回 SAP 函数参数。 因此，以便在向适配器用户提供一致的体验[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开按字母顺序的参数。  
>   - 不同的 SAP 服务器上的相同 Rfc 可能有不同的公开函数参数的顺序。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使这种差异对透明用户通过公开一致的字母顺序中的参数。  
> 
> [!NOTE]
>  从 SAP 系统中使用检索数据时[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不具有多个 65536 节点的消息反序列化。 请确保响应消息具有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[进行故障排除操作问题](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)。  
  
 有关浏览的详细信息，搜索和检索元数据，请参阅[获取 SAP 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)