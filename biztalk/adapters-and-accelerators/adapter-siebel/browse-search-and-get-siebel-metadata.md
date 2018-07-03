---
title: 浏览、 搜索和获取 Siebel 元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- metadata, surfacing
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- searching, metadata
ms.assetid: 48fc3bb1-b949-4b8d-ab62-a41cd8c2f0a0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a02e62bcea6a1647859b8578279ee97f2349d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980534"
---
# <a name="browse-search-and-get-siebel-metadata"></a>浏览、 搜索和获取 Siebel 元数据
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]从 Siebel 系统描述与使用该适配器的 Siebel 系统进行通信的消息结构的图面元数据。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持两个接口用于检索元数据。  
  
- 通过提供 MetadataExchange [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 Siebel 系统获取元数据。  
  
- 通过提供 IMetadataRetrievalContract [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持的元数据浏览和搜索功能的适配器。  
  
  目标[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是公开为 WCF 服务的 Siebel 系统。 该适配器显示为适配器客户端可以调用的操作的 Siebel 项目 （业务对象和业务服务）。  
  
  适配器客户端可以浏览、 搜索，并通过使用 WCF 服务模型，使用 WCF 通道模型，检索元数据或通过创建 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 使用 WCF 服务模型时，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成在 Siebel 系统上执行操作的代理类。 在使用 BizTalk 项目，您必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成你想要在 Siebel 系统中执行的操作的元数据。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]允许浏览的业务对象和业务服务公开的 Siebel 系统的适配器客户端。 作为元数据浏览操作的一部分，适配器将项目分类到多个逻辑级别并公开到适配器客户端的元数据的分层视图。 从 Siebel 系统的元数据进行分类的以下节点：  
  
- **业务对象**。 此节点包含业务对象在 Siebel 系统中，这是业务组件的逻辑集合。 业务对象进一步归类为业务组件。 在层次结构的最低级别是可以在业务组件调用的操作。  
  
- **业务服务**。 此节点包含业务服务公开的 Siebel 系统。 Siebel 业务服务是一套业务服务方法或可以直接调用 Siebel 系统中的函数。  
  
  有关元数据的分类方式的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端能够在 Siebel 系统中搜索元数据。 使用有效的 Siebel 搜索表达式与 Siebel 兼容的 LIKE 运算符 [名称] 字段用于元数据浏览的 Siebel 存储库业务组件上执行此操作。 下表列出了 Siebel 项目和他们可以在其下进行搜索的元数据层次结构。  
  
|项目|在 GUI 中的节点下的搜索|  
|--------------|----------------------------------------|  
|业务对象|/ 业务对象|  
|业务组件|/ 业务对象/业务对象名称|  
|业务服务|/ 业务服务|  
  
 下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|? （问号）|匹配一个字符。<br /><br /> 例如，一个？匹配 AB，交流，AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，ABC 匹配。|  
  
## <a name="retrieving-metadata"></a>检索元数据  
 在检索元数据，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以提取在架构包括全部或部分的业务对象或使用相应的操作参数的业务服务的元数据。 它显示从 Siebel 系统的实体，并且在 XML 中的元素名称。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端能够检索 Siebel 系统中，包括详细的元数据特征的元数据：  
  
- 作为业务组件[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]检索此类项作为业务对象名称、 业务组件名称、 字段名称、 数据类型、 字段长度、 必填字段，可选字段，并选择列表字段。 适配器还将检索如 INSERT、 UPDATE、 DELETE 和查询在业务组件上可能的操作。  
  
- 业务服务方法的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]检索业务服务名称、 方法名称 （与操作相同）、 方法参数和参数数据类型等项目。  
  
  检索元数据的详细信息，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)