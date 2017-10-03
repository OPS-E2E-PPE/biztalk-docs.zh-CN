---
title: "FIN 响应类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-types"></a>FIN 响应类型
FIN 响应对帐 (FRR) 来协调对任何类别 0 到 9 SWIFT FIN 消息的响应。 SWIFT FIN 应用程序始终将至少一个，并且可能不只一个，确认 (ACK) 发送响应这些 FIN 消息之一，或否定确认 （否认）。 下表显示的消息类型的出站和入站 （响应） FRR 所处理的消息。  
  
|出站 /<br /><br /> 入站|消息类型|消息状态|  
|----------------------------|------------------|--------------------|  
|出站|所有类别 0 到 9 SWIFT FIN 消息类型|N/A|  
|入站|MQ 系列平移/NAN （MQ 系列传输级 ACK/否认）|MQSeries 传输确认|  
||MT010 （未送达警告）|SWIFT 成功发送原始消息到合作伙伴，但不合作伙伴接收消息会指示。 如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收多个未送达警告 (NDW) 消息，它循环并等待下一步的预期消息。|  
||MT011 （传递通知）|已成功发送原始 SWIFT 向合作伙伴，发送消息，以及接收合作伙伴接收消息的指示。|  
||MT012 （发件人通知）|SWIFT 成功接收来自的原始消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。|  
||MT015 （DNK 或延迟的否认）|SWIFT 尚未成功发送原始消息到合作伙伴。|  
||MT019 （中止通知）|在 SWIFT 中止消息传输。|  
||MTS21_FIN_ACKNAK （确认消息或否定确认 （ACK/否认） LT 发送的 FIN 消息的）|SWIFT 成功或失败收到来自的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 此消息介绍这两种情况。 它是一个 ACK 还是否认已确定消息 ("0"ACK) 和"1"的否认 451 字段中的值。 这将是第一个响应发送回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。|  
  
## <a name="deployment-of-schemas-for-frr"></a>FRR 架构的部署  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将部署 FrrSchemas.dll 中的所有系统级消息的架构 （如上面的表中所示）。 FRR 业务流程要求要部署这些架构。 因为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将部署中 FrrSchemas.dll 这些架构，你不是必需的并且不是，必须部署在其他项目中的这些架构。 执行此操作将生成错误。  
  
 FRRSchemas.dll 包括以下架构：  
  
-   TransportAck  
  
-   MT010  
  
-   MT011  
  
-   MT012  
  
-   MT015  
  
-   MT019  
  
-   MTS21_FIN_ACKNAK