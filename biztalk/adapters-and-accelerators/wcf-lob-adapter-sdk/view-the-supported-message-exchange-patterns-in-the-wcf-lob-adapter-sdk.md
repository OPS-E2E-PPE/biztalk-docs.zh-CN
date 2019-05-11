---
title: 在 WCF LOB 适配器 SDK 中查看支持的消息交换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6662f17-b4f8-45fe-a22f-5d027dc9f2ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eca67c0f5ebbb3220ebd6d1a836cc37f271df9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362652"
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a>在 WCF LOB 适配器 SDK 中查看支持的消息交换模式
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持多个消息传递模式支持由基础[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]包括请求-答复和单向通信。 不同的传输支持不同的消息传递模式，并因而会影响它们支持的交互的类型。  
  
 下表中列出的模式将由[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
|模式|Description|  
|-------------|-----------------|  
|单向入站|入站的消息业务线系统收到但无响应预期来自适配器。|  
|请求-响应入站|入站的消息接收从业务线系统需要来自适配器的相应响应。|  
|单向出站|出站消息发送到业务线系统，但无响应预期来自适配器。|  
|请求-响应出站|出站消息与预期来自适配器的响应发送到业务线系统。|  
|会话通道入站|唯一的会话中，从业务线系统接收入站的消息。 通过从适配器的业务线系统预期无响应。|  
|出站会话通道|出站消息发送到业务线系统内的唯一会话。 适配器从业务线系统预期无响应。|  
  
 所选的消息模式需要根据目标应用程序的功能。  
  
## <a name="planning-for-sessions"></a>规划的会话  
 消息传送模式可能会使用它时想要确保在适配器和业务线系统之间交换的所有消息都必须属于同一会话的会话。 通常使用会话时需要传递保证，但它们还可用于支持适配器开发人员可能有其他要求消息交换。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]依赖于[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]会话支持。 有关会话的详细信息，请参阅[会话、 实例存储功能和并发](https://msdn.microsoft.com/library/ms731193.aspx)。 
  
## <a name="see-also"></a>请参阅  
 [规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)