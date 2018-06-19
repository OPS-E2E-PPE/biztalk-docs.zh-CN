---
title: 将证书用于参与方解析 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4eb9b616-be1c-4b68-b3de-8721a344a423
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b157191e4004671a8b276f47d15a8589974dfbac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286909"
---
# <a name="using-certificates-for-party-resolution"></a><span data-ttu-id="203e4-102">将证书用于参与方解析</span><span class="sxs-lookup"><span data-stu-id="203e4-102">Using Certificates for Party Resolution</span></span>
<span data-ttu-id="203e4-103">A*方*是外部 BizTalk Server 业务流程交互的实体。</span><span class="sxs-lookup"><span data-stu-id="203e4-103">A *party* is an entity outside BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="203e4-104">在 BizTalk Server 接收某一消息时，它使用公钥证书确定该消息的发件人并且将该发件人解析为 BizTalk Server 环境中的已知参与方。</span><span class="sxs-lookup"><span data-stu-id="203e4-104">When BizTalk Server receives a message, it uses the public key certificate to determine who sent the message, and to resolve the sender to a known party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="203e4-105">本部分提供有关如何配置信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道，接收位置、 端口和参与方解析的 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="203e4-105">This section provides information about how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines, receive locations, ports, and the BizTalk Server environment for party resolution.</span></span>  
  
 <span data-ttu-id="203e4-106">有关消息的身份验证的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="203e4-106">For more information about authentication of a message, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="203e4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="203e4-107">In This Section</span></span>  
 [<span data-ttu-id="203e4-108">如何将 BizTalk Server 配置为参与方解析</span><span class="sxs-lookup"><span data-stu-id="203e4-108">How to Configure BizTalk Server for Party Resolution</span></span>](../core/how-to-configure-biztalk-server-for-party-resolution.md)