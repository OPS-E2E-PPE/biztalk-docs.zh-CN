---
title: 以编程方式获取元数据从 SAP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IMetadataRetrievalContract endpoint
- metadata, retrieving programmatically
- WS-Metadata Exchange (MEX) endpoint
ms.assetid: 8d75332e-c103-4bd5-a9a2-56d21747a04e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e03b4ecaee949b3d8fbceeb4929a88b3d5ee004
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373363"
---
# <a name="get-metadata-programmatically-from-sap"></a>从 SAP 以编程方式获取元数据
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开为 WCF 服务将 SAP 系统的自定义 WCF 绑定。 该适配器将 SAP 系统公开为自描述的服务;也就是说，服务能够发布元数据，它支持的操作。 元数据描述的逻辑接口的 WCF 服务;也就是说，服务协定、 消息和消息架构，必须使用与服务进行交互。  
  
 如由工具使用此元数据：  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来生成服务协定的托管的代码表示形式和  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。  
  
  但是，您还可以检索元数据以编程方式从适配器。 例如，你可能想要执行此操作以创建要在现有的应用程序中使用的自定义元数据检索工具。  
  
  适配器会发布元数据通过两个终结点：  
  
- WS-元数据交换 (MEX) 终结点。 WCF 自动提供的所有 WCF 绑定的 MEX 终结点。 元数据交换可用于检索基础 SAP 系统上的适配器支持的操作的元数据。  
  
- **IMetadataRetrievalContract**终结点。 **IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 它对多个逻辑级别的 SAP 系统项目进行分类并将其表示为元数据节点的树。 可以使用公开的方法**IMetadataRetrievalContract**界面来浏览和搜索此树的节点，并返回你感兴趣的操作的元数据。  
  
  在本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**终结点，以从适配器以编程方式检索元数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [检索元数据在 SAP 中使用 WS-元数据交换](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [使用 IMetadataRetrievalContract SAP 中检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)