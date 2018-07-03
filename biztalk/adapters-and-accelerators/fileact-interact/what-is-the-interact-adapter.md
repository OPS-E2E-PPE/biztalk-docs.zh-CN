---
title: 什么是 InterAct 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc2f29f08edda2fb8d2b0cf05f3ba5b2b786e8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967078"
---
# <a name="what-is-the-interact-adapter"></a>什么是 InterAct 适配器？
SWIFTNet 交互适配器传输的消息提供 BizTalk Server 和 SWIFT Secure IP Network (SIPN) 之间的连接。 SIPN 互联金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。 InterAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。  
  
 SWIFTNet 交互提供了安全且可靠的单个结构化的财务消息的交换。 在客户之间，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。  
  
 它支持以下功能：  
  
- PKI 安全性  
  
- 消息验证  
  
- 可配置的中央路由  
  
- 消息优先级  
  
- 为存储和转发消息的送达通知  
  
- 不可否认性的回执和句子。  
  
  使用交互适配器为 SWIFTNet 与外部提供的应用程序使用的交互功能。 此适配器并不知道要传输，并将不审核也不会验证消息，除了 exchange 基元的内容的消息的内容。  
  
## <a name="interact-message-exchange"></a>InterAct 消息交换  
 SWIFTNet 交互提供了安全且可靠的单个结构化的财务消息的交换。 在客户之间，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。 SWIFTNet 交互提供了广泛的电信模式：  
  
- **存储和转发消息传递。** SWIFTNet 交互的存储和转发功能专为发送到大量的帖者，许多用户可能不处于联机状态时的传输的消息。 它删除的不确定性和的担心在帖者处于联机状态时将消息发送给您带来不便。 一旦接收方已准备好接收其传递消息。 因此，它提供了将单个指令、 确认和报告发送到大量的帖者，其中一些可能在不同时区的理想方法。  
  
- **实时消息传送。** 实时消息传送提供了低成本替代方法来存储和转发的消息的目标为帖者，在传输时处于联机状态。 因此，它非常适合于几个大型帖者或市场的基础结构将消息发送单个指令、 确认和报告、。  
  
  可选的 SWIFTNet 交互功能 （在消息由消息的基础） 包括：  
  
- **消息优先级。** 这些消息可以在消息中，以允许适当处理你的通讯对象标记为"紧急"。  
  
- **送达通知 （存储和转发模式）。** 提供对响应方返回收到您的消息的确认消息  
  
- **发出和接收的不可否认。** 争议，如果允许 SWIFT 确认的消息交换未进行，所声称的那个。  
  
  SWIFTNet 进行交互的标准功能包括 SWIFTNet PKI 安全性。 SWIFTNet FileAct SWIFTNet pki 保护，并提供消息身份验证和完整性控制。  
  
  所有消息以及交换 SWIFTNet 上的文件会都进行一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。 SWIFTAlliance 网关 （压降） 应用程序执行这些检查。  
  
## <a name="see-also"></a>请参阅  
 [开始使用 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet 是什么？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [FileAct 适配器概述](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)