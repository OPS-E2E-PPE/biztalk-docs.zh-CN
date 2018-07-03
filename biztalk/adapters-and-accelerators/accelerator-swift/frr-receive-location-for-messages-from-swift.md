---
title: 从 SWIFT 的 FRR 接收位置消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc4666e90510e7076a3f901ce6fc95b07ef16c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002078"
---
# <a name="frr-receive-location-for-messages-from-swift"></a><span data-ttu-id="c23f0-102">FRR 从 SWIFT 接收的消息的位置</span><span class="sxs-lookup"><span data-stu-id="c23f0-102">FRR Receive Location for Messages from SWIFT</span></span>
<span data-ttu-id="c23f0-103">若要启用 FIN 响应对帐 (FRR)，必须设置 FRR 接收管道组件以从 SAA 收到一条消息并准备将其以供处理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c23f0-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive pipeline component to receive a message from SAA and prepare it for processing by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="c23f0-104">接收管道将包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="c23f0-104">The receive pipeline contains the following components:</span></span>  
  
- <span data-ttu-id="c23f0-105">SWIFT 反汇编程序中的拆装阶段</span><span class="sxs-lookup"><span data-stu-id="c23f0-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
- <span data-ttu-id="c23f0-106">解码器阶段中的 SWIFT 的 FRR 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="c23f0-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
- <span data-ttu-id="c23f0-107">SWIFT FRR CorrelationSet 冲突解决程序管道组件中的参与方解析阶段</span><span class="sxs-lookup"><span data-stu-id="c23f0-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
  <span data-ttu-id="c23f0-108">当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收平移/NAN、 SWIFT 的 FRR 解码器读取 MQ 反馈上下文属性以确定响应是否为平移或为 NAN。</span><span class="sxs-lookup"><span data-stu-id="c23f0-108">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives a PAN/NAN, SWIFT FRR Decoder reads the MQ Feedback context property to determine whether the response is a PAN or a NAN.</span></span> <span data-ttu-id="c23f0-109">设置传输不可知[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck 布尔值为平移或 nan false 值为 true。</span><span class="sxs-lookup"><span data-stu-id="c23f0-109">It sets the transport-agnostic [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck Boolean values to true for a PAN or false for a NAN.</span></span>  
  
  <span data-ttu-id="c23f0-110">SWIFT FRR CorrelationSet 冲突解决程序管道组件将覆盖与响应消息的 FRRCorrelationToken 属性，FRR 业务流程使用，与 MQMD 中的值。CorrelId 属性。</span><span class="sxs-lookup"><span data-stu-id="c23f0-110">The SWIFT FRR CorrelationSet Resolver pipeline component overwrites the response message's FRRCorrelationToken property, which the FRR orchestration uses, with the value in the MQMD.CorrelId property.</span></span>