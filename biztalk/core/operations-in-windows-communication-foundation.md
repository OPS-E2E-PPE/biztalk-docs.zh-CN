---
title: Windows Communication Foundation 中的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43e6eb64e73c072830072a1fdd11dcefef25e32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263035"
---
# <a name="operations-in-windows-communication-foundation"></a>Windows Communication Foundation 中的操作
本部分包含 BAM WCF 侦听器支持的自定义操作。  
  
 请注意，如果操作名称元素包含 Action 属性：  
  
1.  操作名称是由 name 属性标识的客户端和服务器，  
  
2.  对于答复路径 （回调答复），客户端答复和服务答复，操作名称由 name 属性标识。  
  
> [!NOTE]
>  答复消息有一个节点将名为后面附加单词"Result"由 name 属性指定的名称。 您必须确保 xpaths 遵从此命名约定。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AutoGenerateCorrelationToken](../core/autogeneratecorrelationtoken.md)  
  
-   [GetContextProperty](../core/getcontextproperty1.md)  
  
-   [GetEndpointName](../core/getendpointname.md)  
  
-   [GetOperationName](../core/getoperationname.md)  
  
-   [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)  
  
-   [XPath](../core/xpath.md)