---
title: 从 SAP 以编程方式获取元数据 |Microsoft 文档
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
ms.openlocfilehash: 4c856b3629d7d7dcd3f9aa5431c0406f6c822e54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216829"
---
# <a name="get-metadata-programmatically-from-sap"></a>从 SAP 以编程方式获取元数据
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开作为 WCF 服务的 SAP 系统的自定义 WCF 绑定。 适配器将作为自描述服务; 公开 SAP 系统即，它能够发布元数据，它支持的操作有关的服务。 元数据描述 WCF 服务; 的逻辑接口即，服务协定、 消息和消息架构，必须用于与服务交互。  
  
 此元数据是由工具中使用，如：  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成的服务协定中，托管的代码表示形式和  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。  
  
 但是，你还可以检索元数据以编程方式从适配器。 例如，你可能想要执行此操作可创建要在现有应用程序中使用一个自定义元数据检索工具。  
  
 适配器发布元数据通过两个终结点：  
  
-   WS 元数据交换 (MEX) 终结点。 WCF 自动提供的所有 WCF 绑定的 MEX 终结点。 可以使用元数据交换来检索元数据为基础的 SAP 系统上的适配器支持的操作。  
  
-   **IMetadataRetrievalContract**终结点。 **IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 它对多个逻辑级别的 SAP 系统项目进行分类并使它们表现为元数据节点树。 你可以使用公开的方法**IMetadataRetrievalContract**界面，用于浏览和搜索此树的节点和以返回你感兴趣的操作的元数据。  
  
 本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**要从适配器以编程方式检索元数据终结点。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 SAP 中使用 Ws-metadata Exchange 检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [SAP 使用 IMetadataRetrievalContract 中检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>另请参阅  
[开发您的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)