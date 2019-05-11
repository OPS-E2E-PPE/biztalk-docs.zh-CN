---
title: 用于发送到 SWIFT 消息的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0de25c96ec7d685fa68b1d2bd675d95dea0cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378074"
---
# <a name="frr-send-port-for-messages-to-swift"></a><span data-ttu-id="c01d4-102">用于发送到 SWIFT 消息的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="c01d4-102">FRR Send Port for Messages to SWIFT</span></span>
<span data-ttu-id="c01d4-103">若要启用 FIN 响应对帐 (FRR)，必须设置为 MQSeries 向 SAA 通过 BizTalk 适配器发送一条消息的 FRR 发送端口。</span><span class="sxs-lookup"><span data-stu-id="c01d4-103">To enable FIN response reconciliation (FRR), you must set up an FRR send port that sends a message to SAA through the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="c01d4-104">此发送端口路由任何消息通过自定义的 FRR 发送管道组件，则必须使用以下管道组件创建：</span><span class="sxs-lookup"><span data-stu-id="c01d4-104">This send port routes a message through a custom FRR send pipeline component that you must create with the following pipeline components:</span></span>  
  
- <span data-ttu-id="c01d4-105">SWIFT 汇编程序的组装阶段中</span><span class="sxs-lookup"><span data-stu-id="c01d4-105">The SWIFT assembler in the Assemble stage</span></span>  
  
- <span data-ttu-id="c01d4-106">SWIFTAsmFrrMQSeriesHelper 管道组件中的编码阶段</span><span class="sxs-lookup"><span data-stu-id="c01d4-106">The SWIFTAsmFrrMQSeriesHelper pipeline component in the Encode stage</span></span>  
  
  <span data-ttu-id="c01d4-107">SWIFTAsmFrrMQSeriesHelper 管道组件将传出消息的 MQMD_MsgID 属性设置为 FRRCorrelationToken 属性的值。</span><span class="sxs-lookup"><span data-stu-id="c01d4-107">The SWIFTAsmFrrMQSeriesHelper pipeline component sets the MQMD_MsgID property of the outgoing message to the value of the FRRCorrelationToken property.</span></span> <span data-ttu-id="c01d4-108">它还分配并升级开头"MQ"的值在管道设计时设置的任何其他所需的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c01d4-108">It also assigns and promotes any other required context properties starting with "MQ" with values set at the pipeline design time.</span></span> <span data-ttu-id="c01d4-109">发送管道包括用于 MQSeries 作为可配置属性定义每个属性。</span><span class="sxs-lookup"><span data-stu-id="c01d4-109">The send pipeline includes each property defined for MQSeries as a configurable property.</span></span> <span data-ttu-id="c01d4-110">每个值默认为"未使用"。</span><span class="sxs-lookup"><span data-stu-id="c01d4-110">Each value defaults to "Not Used".</span></span>  
  
  <span data-ttu-id="c01d4-111">发送端口处理的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True。</span><span class="sxs-lookup"><span data-stu-id="c01d4-111">The send port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="c01d4-112">传输机制是用于 MQSeries 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="c01d4-112">The transport mechanism is the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="c01d4-113">有关传输属性，例如碎片大小，请参阅 MQSeries 文档。</span><span class="sxs-lookup"><span data-stu-id="c01d4-113">For information about the transport properties, such as the fragmentation size, see the MQSeries documentation.</span></span>