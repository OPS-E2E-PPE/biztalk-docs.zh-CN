---
title: 浏览、 搜索和获取 SAP 元数据 |Microsoft 文档
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
ms.openlocfilehash: 40cc1bd6592b38dbda9c9bff3ad01d6cdaf8a707
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22218437"
---
# <a name="browse-search-and-get-sap-metadata"></a>浏览、 搜索和获取 SAP 元数据
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面从 SAP 系统的元数据。 此元数据描述与使用适配器的 SAP 系统通信的消息结构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为检索元数据支持两个接口。  
  
-   **MetadataExchange**由[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它使客户端从 SAP 系统获取元数据。  
  
-   **IMetadataRetrievalContract**由[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持浏览和搜索功能的适配器的元数据。  
  
 目标之一[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开 SAP 系统作为 WCF 服务。 该适配器显示为适配器客户端可以调用的操作的 SAP 项目 （Rfc、 BAPIs 和 Idoc）。 适配器还显示用于发送或接收到的 Idoc SAP 系统从某些特定操作。 此主题后面部分中列出了这些操作。  
  
 可以浏览、 搜索，并通过使用 WCF 服务模型中，通过使用 WCF 通道模型，检索元数据或通过创建 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
 在使用 WCF 服务模型，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成代理类在 SAP 系统上执行操作。 在使用 BizTalk 项目，你必须使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成你想要在 SAP 系统上执行的操作的元数据。  
  
 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]允许浏览 Rfc、 tRFCs、 BAPIs 和 Idoc 公开的 SAP 系统的适配器客户端。 作为元数据浏览操作的一部分，该适配器显示为操作的 Rfc 和 BAPIs。 为 Idoc，该适配器显示用于发送和接收到的 Idoc 的操作。 这些操作仅从可用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 在以下节点下，SAP 元数据进行分类：  
  
-   **RFC**. 此节点包含公开的 SAP 系统的 Rfc 并表示 SAP 中的函数模块。 适配器到多个逻辑级别分类 Rfc 并公开到适配器客户端的层次结构视图。 RFC 是在此层次结构的最低级别，并作为外部应用程序可以调用的操作公开。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 RFC SDK 为 Rfc 生成元数据。 该适配器可以调用它可为其生成元数据这些 Rfc。  
  
     非公开作为操作 Rfc，适配器还显示某些特定操作如**RfcGetAttributes**。 有关这些操作的详细信息，请参阅[操作中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  
  
-   **TRFC**。 此节点包含公开的 SAP 系统 tRFCs。 tRFCs 不是一个常规的项目的 SAP 系统，但而是一种机制来调用 Rfc。 tRFCs 分为在单独的节点下，因为其元数据特征 Rfc 不同。 具体而言，Rfc 还包括导出参数。 适配器到多个逻辑级别分类 tRFCs 并公开到适配器客户端的层次结构视图。 TRFC 是在此层次结构的最低级别，并作为外部应用程序可以调用的操作公开。  
  
     非公开作为操作 tRFCs，适配器还显示某些特定操作如**RfcConfirmTransID**。 有关这些操作的详细信息，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
-   **BAPI**. 此节点包含公开的 SAP 系统 BAPIs。 适配器到多个逻辑级别分类 BAPIs 并公开到适配器客户端的层次结构视图。 BAPI 是在此层次结构的最低级别，并作为外部应用程序可以调用的操作公开。  
  
-   **IDOC**. 此节点包含 SAP 系统公开 Idoc。 适配器到多个逻辑级别分类 Idoc 并公开到适配器客户端的层次结构视图。 适配器公开的 Idoc 的操作如下：  
  
    -   **发送**和**接收**。 适配器客户端可以使用这些操作来发送和接收到的 Idoc 从 SAP 系统使用强类型的架构。  
  
    -   **SendIdoc**和**ReceiveIdoc**。 适配器客户端可以使用这些操作来发送和接收到的 Idoc 从 SAP 系统使用弱类型的架构。  
  
     有关这些操作的详细信息，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  
  
 有关元数据的分类方式的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 在[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器客户端可以通过使用依赖于基础 Rfc 的搜索表达式中的 SAP 系统搜索元数据，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用。 下表列出的 SAP 项目和适配器客户端可以搜索依据元数据层次结构。  
  
|项目|在 GUI 中的节点下的搜索|  
|--------------|------------------------------------|  
|RFC|-   /RFC<br />-   /RFC/[Application Group]|  
|tRFC|-   /TRFC<br />-   /TRFC/[Application Group]|  
|BAPI|-   /BAPI|  
|IDOC|-   /IDOC|  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+（加号）|完全匹配一个字符。<br /><br /> 例如，A + 匹配 AB、 AC、 AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，与 ABC 匹配。|  
  
## <a name="retrieving-metadata"></a>检索元数据  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使适配器客户端能够检索对于 SAP 系统，包括详细的元数据特性的元数据：  
  
-   有关 RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 RFC 名称以及导入、 导出、 更改和表参数。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还检索的数据类型的参数，字段长度的参数，此外必需和可选参数。  
  
-   Trfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索类似于 RFC，除了导出参数的详细信息。 由于 tRFC 调用都是异步的会不检索任何输出参数。  
  
-   有关 BAPI[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索业务对象名称、 业务对象方法名称和类似于 Rfc 其他特定信息。  
  
-   为 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 IDOC 类型、 发行版号、 版本、 IDOC 控制记录、 IDOC 数据记录，以及其他 IDOC 段信息。  
  
    > [!NOTE]
    >  如果 IDOC 的元数据包含下限和上限值 （范围） 为数据类型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开，以字符串形式。 如果元数据仅包含低值，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开，作为枚举。  
  
> [!NOTE]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开 SAP 函数参数按字母顺序，而不考虑参数 SAP 函数定义中的排序方式。 这是由于以下原因：  
>   
>  -   不同版本的 SAP RFC SDK 按不同顺序返回 SAP 函数参数。 因此，以便向适配器用户提供一致的体验[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开按字母顺序的参数。  
> -   在不同的 SAP 服务器上的相同 Rfc 可能具有不同的公开函数参数的顺序。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]进行这种差异透明向用户公开中一致的字母顺序的参数。  
  
> [!NOTE]
>  从 SAP 系统使用检索数据时[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不具有多个 65536 节点的消息反序列化。 请确保响应消息有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[故障排除操作问题](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)。  
  
 浏览有关的详细信息，搜索和检索元数据，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
## <a name="see-also"></a>另请参阅  
 [为 mySAP Business Suite 的 BizTalk Adapter 的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)