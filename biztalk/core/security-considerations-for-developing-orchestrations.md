---
title: 有关开发业务流程的安全注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d159a96052871796c102dc628dae2a06d85046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280326"
---
# <a name="security-considerations-for-developing-orchestrations"></a><span data-ttu-id="ceef2-102">有关开发业务流程的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="ceef2-102">Security Considerations for Developing Orchestrations</span></span>
<span data-ttu-id="ceef2-103">在设计您的业务流程时，应考虑潜在的安全问题。</span><span class="sxs-lookup"><span data-stu-id="ceef2-103">When designing your orchestrations, you should consider potential security issues.</span></span>  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a><span data-ttu-id="ceef2-104">避免基于来自不可信消息的内容的订阅</span><span class="sxs-lookup"><span data-stu-id="ceef2-104">Avoid subscriptions based on content from untrusted messages</span></span>  
 <span data-ttu-id="ceef2-105">若要确保低权限的消息不会启动业务流程实例可能无法创建基于消息内容或上下文的订阅，强烈建议您的业务流程不会创建其消息订阅基于内容或不受信任的消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="ceef2-105">To ensure that a low-privilege message does not initiate an orchestration instance that could potentially create subscriptions based on the message content or context, it is highly recommended that your orchestrations do not create their message subscriptions based on the content or context of a message that is not trusted.</span></span>  
  
 <span data-ttu-id="ceef2-106">有关中的安全性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[保护 BizTalk Server](../core/securing-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ceef2-106">For information about security in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Securing BizTalk Server](../core/securing-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceef2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="ceef2-107">See Also</span></span>  
 <span data-ttu-id="ceef2-108">[创建业务流程](../core/creating-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="ceef2-108">[Creating Orchestrations](../core/creating-orchestrations.md) </span></span>  
 [<span data-ttu-id="ceef2-109">关于业务流程</span><span class="sxs-lookup"><span data-stu-id="ceef2-109">About Orchestrations</span></span>](../core/about-orchestrations.md)