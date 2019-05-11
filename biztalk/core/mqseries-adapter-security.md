---
title: MQSeries 适配器安全性 |Microsoft Docs
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
ms.openlocfilehash: 2cf8d0b960f09ef3ba955da9996aa858595688f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323658"
---
# <a name="security-with-the-mqseries-adapter"></a><span data-ttu-id="ed0f8-102">使用 MQSeries 适配器的安全</span><span class="sxs-lookup"><span data-stu-id="ed0f8-102">Security with the MQSeries adapter</span></span>

<span data-ttu-id="ed0f8-103">MQSeries 适配器安全性始于保护你的 BizTalk 和 MQSeries 服务器。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-103">MQSeries adapter security begins with securing your BizTalk and MQSeries servers.</span></span> <span data-ttu-id="ed0f8-104">有关保护 BizTalk Server 的信息，请参阅[安全和保护你的数据](secure-and-protect-your-biztalk-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-104">For information about securing BizTalk Server, see [Secure and protect your data](secure-and-protect-your-biztalk-messages.md).</span></span> <span data-ttu-id="ed0f8-105">有关 MQSeries 服务器安全性的信息，请参阅 IBM MQSeries 服务器文档。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-105">For information about MQSeries Server security, see the IBM MQSeries Server documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed0f8-106">适配器会自动使用数据包隐私性发送和接收 BizTalk Server 和 MQSeries 服务器之间的消息。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-106">The adapter automatically uses packet privacy for sending and receiving messages between BizTalk Server and MQSeries Server.</span></span>  

## <a name="adapter-security"></a><span data-ttu-id="ed0f8-107">适配器安全性</span><span class="sxs-lookup"><span data-stu-id="ed0f8-107">Adapter security</span></span>  
 <span data-ttu-id="ed0f8-108">安全地使用适配器本身需要注意以下四个方面：</span><span class="sxs-lookup"><span data-stu-id="ed0f8-108">Using the adapter itself securely requires attention to four areas:</span></span>  
  
- <span data-ttu-id="ed0f8-109">选择应用程序标识和 MQSAgent 的成员</span><span class="sxs-lookup"><span data-stu-id="ed0f8-109">Choosing the application identity and members for MQSAgent</span></span>  
  
- <span data-ttu-id="ed0f8-110">控制使用的适配器的 BizTalk Server 帐户</span><span class="sxs-lookup"><span data-stu-id="ed0f8-110">Controlling the BizTalk Server accounts using the adapter</span></span>  
  
- <span data-ttu-id="ed0f8-111">保护队列创建脚本</span><span class="sxs-lookup"><span data-stu-id="ed0f8-111">Securing the queue creation scripts</span></span>  
  
- <span data-ttu-id="ed0f8-112">进行适当利用**SSO 关联应用程序**属性</span><span class="sxs-lookup"><span data-stu-id="ed0f8-112">Making appropriate use of the **SSO Affiliate Application** property</span></span>  
  
  <span data-ttu-id="ed0f8-113">在配置期间分配给应用程序标识的帐户不应是管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-113">The account assigned to the application identity during configuration should not be an administrator account.</span></span> <span data-ttu-id="ed0f8-114">相反，该帐户应具有所需的最小权限 — 读取和写入访问权限向 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-114">Rather, the account should have the minimum required privileges—read and write access to the MQSeries queues.</span></span>  
  
  <span data-ttu-id="ed0f8-115">请确保分配仅使用 MQSAgent 角色到适配器的 BizTalk Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-115">Make sure that you assign only BizTalk Server accounts using the adapter to the MQSAgent role.</span></span>  
  
  <span data-ttu-id="ed0f8-116">当使用导出队列定义过程中创建的脚本时，应将脚本置于安全区域。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-116">When using exported scripts created during the queue definition process, keep the scripts in a secure area.</span></span> <span data-ttu-id="ed0f8-117">只有使用脚本的管理员才具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-117">Only administrators using the scripts should have access.</span></span>  
  
  <span data-ttu-id="ed0f8-118">如果你的应用程序使用 MQCIH 和 MQIIH 标头属性将用户凭据置于出站消息中，使用**SSO 关联应用程序**上的属性**传输属性**页。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-118">If your application uses MQCIH and MQIIH header properties to put user credentials in outbound messages, use the **SSO Affiliate Application** property on the **Transport Properties** page.</span></span> <span data-ttu-id="ed0f8-119">有关此属性的详细信息，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="ed0f8-119">For more information about this property, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0f8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed0f8-120">See Also</span></span>  
 <span data-ttu-id="ed0f8-121">[MQSeries 适配器的结构](../core/structure-of-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed0f8-121">[Structure of the MQSeries Adapter](../core/structure-of-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="ed0f8-122">MQSeries 适配器概述</span><span class="sxs-lookup"><span data-stu-id="ed0f8-122">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)