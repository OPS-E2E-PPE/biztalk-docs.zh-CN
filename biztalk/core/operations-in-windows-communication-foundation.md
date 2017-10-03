---
title: "Windows Communication Foundation 中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-in-windows-communication-foundation"></a>Windows Communication Foundation 中的操作
本部分包含 BAM WCF 侦听器支持的自定义操作。  
  
 注意，如果操作名称元素包含 Action 属性：  
  
1.  操作名称是由客户端和服务器的名称属性共同标识的。  
  
2.  对于答复路径（回调答复）、客户端答复和服务答复，操作名称由 name 属性标识。  
  
> [!NOTE]
>  答复消息中有一个节点将通过在由 name 属性指定的名称后面附加单词“Result”来命名。 您必须确保 XPaths 遵从此命名约定。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AutoGenerateCorrelationToken](../core/autogeneratecorrelationtoken.md)  
  
-   [GetContextProperty](../core/getcontextproperty1.md)  
  
-   [GetEndpointName](../core/getendpointname.md)  
  
-   [GetOperationName](../core/getoperationname.md)  
  
-   [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)  
  
-   [XPath](../core/xpath.md)