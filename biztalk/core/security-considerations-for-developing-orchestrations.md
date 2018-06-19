---
title: 有关开发业务流程的安全注意事项 |Microsoft 文档
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
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269317"
---
# <a name="security-considerations-for-developing-orchestrations"></a><span data-ttu-id="60d99-102">有关开发业务流程的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="60d99-102">Security Considerations for Developing Orchestrations</span></span>
<span data-ttu-id="60d99-103">在设计业务流程时，应考虑潜在的安全问题。</span><span class="sxs-lookup"><span data-stu-id="60d99-103">When designing your orchestrations, you should consider potential security issues.</span></span>  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a><span data-ttu-id="60d99-104">避免基于来自不可信消息的内容的订阅</span><span class="sxs-lookup"><span data-stu-id="60d99-104">Avoid subscriptions based on content from untrusted messages</span></span>  
 <span data-ttu-id="60d99-105">为确保低权限的消息不会启动可能基于该消息内容或上下文创建订阅的业务流程实例，强烈建议您的业务流程不要基于不可信消息的内容或上下文来创建其消息订阅。</span><span class="sxs-lookup"><span data-stu-id="60d99-105">To ensure that a low-privilege message does not initiate an orchestration instance that could potentially create subscriptions based on the message content or context, it is highly recommended that your orchestrations do not create their message subscriptions based on the content or context of a message that is not trusted.</span></span>  
  
 <span data-ttu-id="60d99-106">有关中的安全信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[保护 BizTalk Server](../core/securing-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="60d99-106">For information about security in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Securing BizTalk Server](../core/securing-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d99-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60d99-107">See Also</span></span>  
 <span data-ttu-id="60d99-108">[创建业务流程](../core/creating-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="60d99-108">[Creating Orchestrations](../core/creating-orchestrations.md) </span></span>  
 [<span data-ttu-id="60d99-109">有关业务流程</span><span class="sxs-lookup"><span data-stu-id="60d99-109">About Orchestrations</span></span>](../core/about-orchestrations.md)