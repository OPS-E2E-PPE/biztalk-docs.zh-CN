---
title: 构建基块的贸易合作伙伴管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0dabb562-7065-44b8-a26f-658d70b126eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c29ec45b6ed7a8a7b5e3911794aa936a78c586ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357787"
---
# <a name="building-blocks-of-a-trading-partner-management-solution"></a><span data-ttu-id="c5a8f-102">贸易合作伙伴管理解决方案的构建基块</span><span class="sxs-lookup"><span data-stu-id="c5a8f-102">Building Blocks of a Trading Partner Management Solution</span></span>
## <a name="overview"></a><span data-ttu-id="c5a8f-103">概述</span><span class="sxs-lookup"><span data-stu-id="c5a8f-103">Overview</span></span>
<span data-ttu-id="c5a8f-104">核心价值主张之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是使客户能够与其业务合作伙伴的企业到企业 (B2B) 通信。</span><span class="sxs-lookup"><span data-stu-id="c5a8f-104">One of the core value propositions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to empower customers to enable business-to-business (B2B) communication with their business partners.</span></span> <span data-ttu-id="c5a8f-105">为了满足此类业务需求，企业需要的模型、 存储和管理有关的信息：</span><span class="sxs-lookup"><span data-stu-id="c5a8f-105">To fulfill such business needs, enterprises need to model, store, and manage information about:</span></span>  
  
- <span data-ttu-id="c5a8f-106">合作伙伴和业务</span><span class="sxs-lookup"><span data-stu-id="c5a8f-106">Partners and their businesses</span></span>  
  
- <span data-ttu-id="c5a8f-107">参与规则与合作伙伴 – 其中包括详细信息的消息编码协议 （EDI 标准），如传输协议 (AS2) 使用，等等。</span><span class="sxs-lookup"><span data-stu-id="c5a8f-107">Rules of engagement with the partners – These include details such as which message encoding protocol to use (EDI standards), which transport protocol to use (AS2), etc.</span></span>  
  
  <span data-ttu-id="c5a8f-108">虽然[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]继续提供支持 EDI 和 AS2，它将添加到的基本概念，围绕如何管理和存储有关合作伙伴及其业务的信息。</span><span class="sxs-lookup"><span data-stu-id="c5a8f-108">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] continues to provide support for EDI and AS2, it adds to the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="c5a8f-109">EDI 标准、 AS2 消息传送和概念组合到一起形成了 B2B 通信或贸易合作伙伴管理 (TPM) 解决方案的构建基块。</span><span class="sxs-lookup"><span data-stu-id="c5a8f-109">EDI standards, AS2 messaging, and the concepts put together form the building blocks of a B2B communication or a Trading Partner Management (TPM) solution.</span></span> <span data-ttu-id="c5a8f-110">本部分提供有关这些概念的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="c5a8f-110">This section provides detailed explanation about these concepts.</span></span> 
 
  <span data-ttu-id="c5a8f-111">有关如何信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持 EDI 和 AS2，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c5a8f-111">For information about how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supports EDI and AS2, see:</span></span>
 
  - [<span data-ttu-id="c5a8f-112">BizTalk Server EDI 功能</span><span class="sxs-lookup"><span data-stu-id="c5a8f-112">BizTalk Server EDI functionality</span></span>](../core/biztalk-server-edi-functionality.md)
  - [<span data-ttu-id="c5a8f-113">BizTalk Server AS2 功能</span><span class="sxs-lookup"><span data-stu-id="c5a8f-113">BizTalk Server AS2 functionality</span></span>](../core/biztalk-server-as2-functionality.md)
  
## <a name="in-this-section"></a><span data-ttu-id="c5a8f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="c5a8f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c5a8f-115">贸易合作伙伴和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="c5a8f-115">Trading partners and business profiles</span></span>](../core/trading-partners-and-business-profiles.md)
  
-   [<span data-ttu-id="c5a8f-116">协议设置</span><span class="sxs-lookup"><span data-stu-id="c5a8f-116">Protocol settings</span></span>](../core/protocol-settings.md)  
  
-   [<span data-ttu-id="c5a8f-117">贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c5a8f-117">Trading partner agreement</span></span>](../core/trading-partner-agreement.md)  
  
-   [<span data-ttu-id="c5a8f-118">将所有组合在一起：定义贸易合作伙伴管理解决方案</span><span class="sxs-lookup"><span data-stu-id="c5a8f-118">Putting it all together: Defining a trading partner management solution</span></span>](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5a8f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5a8f-119">See Also</span></span>  
 [<span data-ttu-id="c5a8f-120">使用 BizTalk Server 贸易合作伙伴管理</span><span class="sxs-lookup"><span data-stu-id="c5a8f-120">Trading Partner Management Using BizTalk Server</span></span>](../core/trading-partner-management-using-biztalk-server.md)