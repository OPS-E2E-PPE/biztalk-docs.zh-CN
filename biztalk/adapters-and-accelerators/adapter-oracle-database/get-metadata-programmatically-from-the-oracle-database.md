---
title: 以编程方式获取元数据从 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2380e58605cf401e7ed1138b078d19d5279144f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972870"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a>从 Oracle 数据库中以编程方式获取元数据
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是公开为 WCF 服务的 Oracle 数据库的自定义 WCF 绑定。 该适配器公开为自描述的服务; Oracle 数据库也就是说，服务能够发布元数据，它支持的操作。 元数据描述的逻辑接口的 WCF 服务;也就是说，服务协定、 消息和消息架构，必须使用与服务进行交互。  
  
 如由工具使用此元数据：  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来生成服务协定的托管的代码表示形式和  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。  
  
  但是，您还可以检索元数据以编程方式从适配器。 例如，你可能想要执行此操作以创建要在现有的应用程序中使用的自定义元数据检索工具。  
  
  适配器会发布元数据通过两个终结点：  
  
- WS-元数据交换 (MEX) 终结点。 WCF 自动提供的所有 WCF 绑定的 MEX 终结点。 元数据交换可用于检索元数据为基础的 Oracle 数据库适配器支持的操作。  
  
- **IMetadataRetrievalContract**终结点。 **IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 它对多个逻辑级别的 Oracle 数据库项目进行分类并将其表示为元数据节点的树。 可以使用公开的方法**IMetadataRetrievalContract**界面来浏览和搜索此树的节点，并返回你感兴趣的操作的元数据。  
  
  在本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**终结点，以从适配器以编程方式检索元数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 Oracle 数据库中使用 Ws-metadata Exchange 获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [在 Oracle 数据库中使用 IMetadataRetrievalContract 获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)