---
title: 实现消息安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971977a0-b74e-4408-8a07-ad327658f2bc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae25a8e09b6e9aa8f4b5cef7b6dc5365a601e7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001182"
---
# <a name="implementing-message-security"></a><span data-ttu-id="7c77c-102">实现消息安全性</span><span class="sxs-lookup"><span data-stu-id="7c77c-102">Implementing Message Security</span></span>
<span data-ttu-id="7c77c-103">可以配置 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境以使用证书来发送和接收签名消息和加密消息。</span><span class="sxs-lookup"><span data-stu-id="7c77c-103">You can configure your Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment to use certificates for sending and receiving signed and encrypted messages.</span></span> <span data-ttu-id="7c77c-104">通过使用证书来进行加密和数字签名，BizTalk Server 可以：</span><span class="sxs-lookup"><span data-stu-id="7c77c-104">By using certificates for encryption and digital signatures, BizTalk Server can:</span></span>  
  
- <span data-ttu-id="7c77c-105">发送和接收可信任的数据。</span><span class="sxs-lookup"><span data-stu-id="7c77c-105">Send and receive data that can be trusted.</span></span>  
  
- <span data-ttu-id="7c77c-106">确保它所处理的数据是安全的。</span><span class="sxs-lookup"><span data-stu-id="7c77c-106">Make sure that the data it processes is secure.</span></span>  
  
- <span data-ttu-id="7c77c-107">确保经授权的参与方收到其消息。</span><span class="sxs-lookup"><span data-stu-id="7c77c-107">Make sure that authorized parties receive its messages.</span></span>  
  
- <span data-ttu-id="7c77c-108">确保它收到来自授权参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="7c77c-108">Make sure that it receives messages from authorized parties.</span></span>  
  
  <span data-ttu-id="7c77c-109">本部分提供有关如何配置 BizTalk Server 管道、接收位置、端口和 BizTalk Server 环境以实施消息安全性的信息。</span><span class="sxs-lookup"><span data-stu-id="7c77c-109">This section provides information about how to configure BizTalk Server pipelines, receive locations, ports, and the BizTalk Server environment to implement message security.</span></span>  
  
  <span data-ttu-id="7c77c-110">有关消息安全性的详细信息，请参阅[规划消息安全性](../core/planning-message-security.md)。</span><span class="sxs-lookup"><span data-stu-id="7c77c-110">For more information about message security, see [Planning Message Security](../core/planning-message-security.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c77c-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="7c77c-111">In This Section</span></span>  
  
-   [<span data-ttu-id="7c77c-112">发送和接收加密消息</span><span class="sxs-lookup"><span data-stu-id="7c77c-112">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)  
  
-   [<span data-ttu-id="7c77c-113">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="7c77c-113">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)  
  
-   [<span data-ttu-id="7c77c-114">为参与方解析使用证书</span><span class="sxs-lookup"><span data-stu-id="7c77c-114">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)