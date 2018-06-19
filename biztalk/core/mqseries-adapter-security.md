---
title: MQSeries 适配器安全 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08d5228dab8463c2ad5dc7f9d9347899d4c41a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263197"
---
# <a name="security-with-the-mqseries-adapter"></a><span data-ttu-id="32d4b-102">安全与 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="32d4b-102">Security with the MQSeries adapter</span></span>

<span data-ttu-id="32d4b-103">MQSeries 适配器安全性首先是要确保 BizTalk 和 MQSeries 服务器的安全。</span><span class="sxs-lookup"><span data-stu-id="32d4b-103">MQSeries adapter security begins with securing your BizTalk and MQSeries servers.</span></span> <span data-ttu-id="32d4b-104">有关保护 BizTalk Server 的信息，请参阅[安全和保护数据](secure-and-protect-your-biztalk-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="32d4b-104">For information about securing BizTalk Server, see [Secure and protect your data](secure-and-protect-your-biztalk-messages.md).</span></span> <span data-ttu-id="32d4b-105">有关 MQSeries 服务器安全性的信息，请参阅 IBM MQSeries 服务器文档。</span><span class="sxs-lookup"><span data-stu-id="32d4b-105">For information about MQSeries Server security, see the IBM MQSeries Server documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32d4b-106">在 BizTalk Server 与 MQSeries 服务器之间发送和接收消息时，该适配器将自动使用数据包隐私性。</span><span class="sxs-lookup"><span data-stu-id="32d4b-106">The adapter automatically uses packet privacy for sending and receiving messages between BizTalk Server and MQSeries Server.</span></span>  

## <a name="adapter-security"></a><span data-ttu-id="32d4b-107">适配器安全</span><span class="sxs-lookup"><span data-stu-id="32d4b-107">Adapter security</span></span>  
 <span data-ttu-id="32d4b-108">安全地使用适配器本身需要注意以下四个方面：</span><span class="sxs-lookup"><span data-stu-id="32d4b-108">Using the adapter itself securely requires attention to four areas:</span></span>  
  
-   <span data-ttu-id="32d4b-109">选择 MQSAgent 的应用程序标识和成员</span><span class="sxs-lookup"><span data-stu-id="32d4b-109">Choosing the application identity and members for MQSAgent</span></span>  
  
-   <span data-ttu-id="32d4b-110">使用适配器控制 BizTalk Server 帐户</span><span class="sxs-lookup"><span data-stu-id="32d4b-110">Controlling the BizTalk Server accounts using the adapter</span></span>  
  
-   <span data-ttu-id="32d4b-111">确保队列创建脚本安全</span><span class="sxs-lookup"><span data-stu-id="32d4b-111">Securing the queue creation scripts</span></span>  
  
-   <span data-ttu-id="32d4b-112">使适合使用**SSO Affiliate 应用程序**属性</span><span class="sxs-lookup"><span data-stu-id="32d4b-112">Making appropriate use of the **SSO Affiliate Application** property</span></span>  
  
 <span data-ttu-id="32d4b-113">在配置过程中为应用程序标识指定的帐户不应为管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="32d4b-113">The account assigned to the application identity during configuration should not be an administrator account.</span></span> <span data-ttu-id="32d4b-114">相反，该帐户应具有所需的最小权限-读取和写入访问权限 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="32d4b-114">Rather, the account should have the minimum required privileges—read and write access to the MQSeries queues.</span></span>  
  
 <span data-ttu-id="32d4b-115">确保只将使用该适配器的 BizTalk Server 帐户分配给 MQSAgent 角色。</span><span class="sxs-lookup"><span data-stu-id="32d4b-115">Make sure that you assign only BizTalk Server accounts using the adapter to the MQSAgent role.</span></span>  
  
 <span data-ttu-id="32d4b-116">使用在队列定义过程中创建的导出脚本时，应将脚本置于安全区域中。</span><span class="sxs-lookup"><span data-stu-id="32d4b-116">When using exported scripts created during the queue definition process, keep the scripts in a secure area.</span></span> <span data-ttu-id="32d4b-117">只有使用这些脚本的管理员才具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="32d4b-117">Only administrators using the scripts should have access.</span></span>  
  
 <span data-ttu-id="32d4b-118">如果你的应用程序使用 MQCIH 和 MQIIH 标头属性放置在出站消息中的用户凭据，使用**SSO Affiliate 应用程序**属性**传输属性**页。</span><span class="sxs-lookup"><span data-stu-id="32d4b-118">If your application uses MQCIH and MQIIH header properties to put user credentials in outbound messages, use the **SSO Affiliate Application** property on the **Transport Properties** page.</span></span> <span data-ttu-id="32d4b-119">有关此属性的详细信息，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="32d4b-119">For more information about this property, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d4b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32d4b-120">See Also</span></span>  
 <span data-ttu-id="32d4b-121">[MQSeries 适配器的结构](../core/structure-of-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="32d4b-121">[Structure of the MQSeries Adapter](../core/structure-of-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="32d4b-122">什么是 MQSeries 适配器？</span><span class="sxs-lookup"><span data-stu-id="32d4b-122">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)