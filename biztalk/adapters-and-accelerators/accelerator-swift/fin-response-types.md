---
title: FIN 响应类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 382e0e628d01903a6274dd3f0321379f71fc7a15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995398"
---
# <a name="fin-response-types"></a>FIN 响应类型
FIN 响应对帐 (FRR) 来协调对任何类别 0 到 9 SWIFT FIN 消息的响应。 其中一条 FIN 消息响应，SWIFT FIN 应用程序始终发送至少一个，可能是多个确认 (ACK) 或否定确认 (NAK)。 下表显示的消息类型的出站和入站 （响应） FRR 处理的消息。  


| 出站 /<br /><br /> 入站 |                                             消息类型                                              |                                                                                                                                                                                                                             消息状态                                                                                                                                                                                                                              |
|-------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           出站            |                              所有类别 0 到 9 SWIFT FIN 消息类型                              |                                                                                                                                                                                                                                   N/A                                                                                                                                                                                                                                   |
|            入站            |                         MQ 系列平移/NAN (MQ Series 传输级 ACK/NAK)                         |                                                                                                                                                                                                                    MQSeries 传输确认                                                                                                                                                                                                                    |
|                               |                                     MT010 （未送达警告）                                      |                                                                     SWIFT 成功发送原始消息到合作伙伴，但没有合作伙伴接收消息的指示。 如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收多个未送达警告 (NDW) 消息，它循环并等待下一个预期的消息。                                                                     |
|                               |                                     MT011 （送达通知）                                     |                                                                                                                                                                     SWIFT 成功发送原始消息到合作伙伴，并接收合作伙伴收到了消息，指示。                                                                                                                                                                      |
|                               |                                      MT012 （发件人通知）                                      |                                                                                                                                                            SWIFT 成功接收来自原始消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。                                                                                                                                                             |
|                               |                                      MT015 （DNK 或延迟的 NAK）                                      |                                                                                                                                                                                                  SWIFT 具有未成功发送原始消息到合作伙伴。                                                                                                                                                                                                   |
|                               |                                      MT019 （中止通知）                                       |                                                                                                                                                                                                                 在 SWIFT 中止消息传输。                                                                                                                                                                                                                  |
|                               | MTS21_FIN_ACKNAK （确认或否定确认 (ACK/NAK) LT 发送 FIN 消息） | SWIFT 成功或未成功接收到来自消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 此消息介绍这两种情况。 它是 ACK 或 NAK 已确定的消息 ("0"ACK) 和"1"为 NAK 451 字段中的值。 这将是第一个响应传递回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 |

## <a name="deployment-of-schemas-for-frr"></a>FRR 的架构部署  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 安装程序将部署 FrrSchemas.dll 中的所有系统级消息的架构 （如上面的表中所示）。 FRR 业务流程需要这些架构来进行部署。 因为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将部署 FrrSchemas.dll 这些架构，则不是必需的并不是，必须部署另一个项目中的这些架构。 执行此操作将生成错误。  

 FRRSchemas.dll 包括以下架构：  

-   TransportAck  

-   MT010  

-   MT011  

-   MT012  

-   MT015  

-   MT019  

-   MTS21_FIN_ACKNAK