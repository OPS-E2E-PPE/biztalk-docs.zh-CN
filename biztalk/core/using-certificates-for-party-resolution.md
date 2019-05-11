---
title: 为参与方解析使用证书 |Microsoft Docs
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
ms.openlocfilehash: 5b8ebd7023b687cd66ab0de082079330b20c2ac8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401635"
---
# <a name="using-certificates-for-party-resolution"></a><span data-ttu-id="e8111-102">为参与方解析使用证书</span><span class="sxs-lookup"><span data-stu-id="e8111-102">Using Certificates for Party Resolution</span></span>
<span data-ttu-id="e8111-103">一个*参与方*是与业务流程交互的 BizTalk Server 外部的实体。</span><span class="sxs-lookup"><span data-stu-id="e8111-103">A *party* is an entity outside BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="e8111-104">在 BizTalk Server 接收一条消息，它使用公钥证书，以确定谁发送的消息，并将发件人解析为 BizTalk Server 环境中的已知参与方。</span><span class="sxs-lookup"><span data-stu-id="e8111-104">When BizTalk Server receives a message, it uses the public key certificate to determine who sent the message, and to resolve the sender to a known party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="e8111-105">本部分提供有关如何配置信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道、 接收位置、 端口和参与方解析为 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="e8111-105">This section provides information about how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines, receive locations, ports, and the BizTalk Server environment for party resolution.</span></span>  
  
 <span data-ttu-id="e8111-106">有关消息的身份验证的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="e8111-106">For more information about authentication of a message, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8111-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="e8111-107">In This Section</span></span>  
 [<span data-ttu-id="e8111-108">如何为参与方解析配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e8111-108">How to Configure BizTalk Server for Party Resolution</span></span>](../core/how-to-configure-biztalk-server-for-party-resolution.md)