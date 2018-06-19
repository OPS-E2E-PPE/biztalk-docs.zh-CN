---
title: MSH 替代 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MSH segments
- routing, messages
- subscriptions
- messages, routing
- routing, MSH segments
- send ports, subscriptions
- MSH segments
- send ports, multiple ports
ms.assetid: 4f5700bc-c8f4-40c9-9c9c-2220fa2627ba
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ed4111e2fdb925740d248c9f751f7a80b9f046f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205933"
---
# <a name="msh-override"></a><span data-ttu-id="630d8-102">MSH 替代</span><span class="sxs-lookup"><span data-stu-id="630d8-102">MSH Override</span></span>
<span data-ttu-id="630d8-103">之前[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将出站的 HL7 消息路由到发送端口，你可能想要替换 MSH 分段内的某些值。</span><span class="sxs-lookup"><span data-stu-id="630d8-103">Before [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) routes an outbound HL7 message to a send port, you may want to replace certain values within the MSH segment.</span></span> <span data-ttu-id="630d8-104">你可能想要执行此操作，当一条消息的订阅包含多个发送端口，并且每个发送端口应该会看到接收应用程序字段中的不同值。</span><span class="sxs-lookup"><span data-stu-id="630d8-104">You may want to do this when the subscription for a message contains multiple send ports, and each send port should see a different value in the receiving-application field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630d8-105">另请参阅</span><span class="sxs-lookup"><span data-stu-id="630d8-105">See Also</span></span>  
 <span data-ttu-id="630d8-106">[MSH 字段将覆盖](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md) </span><span class="sxs-lookup"><span data-stu-id="630d8-106">[MSH Field Overrides](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md) </span></span>  
 [<span data-ttu-id="630d8-107">确认</span><span class="sxs-lookup"><span data-stu-id="630d8-107">Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)