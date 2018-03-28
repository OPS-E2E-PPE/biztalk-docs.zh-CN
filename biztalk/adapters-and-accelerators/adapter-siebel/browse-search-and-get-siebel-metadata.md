---
title: 浏览、 搜索和获取 Siebel 元数据 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1ed7d74b4e69f56c53beda8273533bb6891a55
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-siebel-metadata"></a>浏览、 搜索和获取 Siebel 元数据
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面从 Siebel 系统，用于描述与使用适配器 Siebel 系统进行通信的消息结构的元数据。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]为检索元数据支持两个接口。  
  
-   MetadataExchange 由[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它使客户端从 Siebel 系统获取元数据。  
  
-   IMetadataRetrievalContract 由[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持浏览和搜索功能的适配器的元数据。  
  
 目标[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是公开 Siebel 系统作为 WCF 服务。 该适配器显示为适配器客户端可以调用的操作 Siebel 项目 （业务对象和业务服务）。  
  
 适配器客户端可以浏览、 搜索，并通过使用 WCF 服务模型中，通过使用 WCF 通道模型，检索元数据或通过创建 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 在使用 WCF 服务模型，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成代理类在 Siebel 系统上执行操作。 在使用 BizTalk 项目，你必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成你想要在 Siebel 系统上执行的操作的元数据。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]允许浏览的业务对象和业务服务公开的 Siebel 系统的适配器客户端。 作为元数据浏览操作的一部分，适配器分类到多个逻辑级别的项目，并公开到适配器客户端的元数据的层次结构视图。 在以下节点下，从 Siebel 系统的元数据进行分类：  
  
-   **业务对象**。 此节点包含业务对象在 Siebel 系统中，这是业务组件的逻辑集合。 业务对象进一步分为业务组件。 在层次结构的最低级别是你可以在业务组件调用的操作。  
  
-   **业务服务**。 此节点包含公开 Siebel 系统的业务服务。 Siebel 业务服务是一套业务服务方法或可以在 Siebel 系统中直接调用的函数。  
  
 有关元数据的分类方式的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端要在 Siebel 系统中搜索元数据。 通过使用搜索表达式与 Siebel 兼容的 LIKE 运算符用于元数据浏览 Siebel 存储库在业务组件的 [名称] 字段上的有效 Siebel 来执行此操作。 下表列出 Siebel 项目和在其下可以搜索的元数据层次结构。  
  
|项目|在 GUI 中的节点下的搜索|  
|--------------|----------------------------------------|  
|业务对象|/ 业务对象|  
|在业务组件|/ 企业对象/业务对象名称|  
|业务服务|/ 业务服务|  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|? （问号）|完全匹配一个字符。<br /><br /> 例如，A？匹配 AB、 AC、 AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，与 ABC 匹配。|  
  
## <a name="retrieving-metadata"></a>检索元数据  
 检索元数据时,[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以提取在架构包括所有数据或业务对象或与相应的操作参数的业务服务的子集的元数据。 XML 中用作元素名称，它显示从 Siebel 系统的实体。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端能够检索 Siebel 系统，包括详细的元数据特性的元数据：  
  
-   对于业务组件，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]检索此类的项作为业务对象名称、 业务组件名称、 字段名称、 数据类型、 字段长度，必填字段，可选字段，以及选择列表字段。 适配器还会检索例如插入、 更新、 删除和查询在业务组件上可能的操作。  
  
-   业务服务方法的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]检索此类的项作为业务服务名称、 方法名称 （与操作相同）、 方法参数和参数数据类型。  
  
 有关检索元数据的详细信息，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
## <a name="see-also"></a>另请参阅  
 [用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)