---
title: 规划和设计你的适配器使用 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dfbfa6c-2f87-40bb-93d4-6fbb37a235c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4ff4e0263c5b652d9422324ea176496bc555aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225021"
---
# <a name="plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="673ba-102">规划和设计你使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="673ba-102">Plan and design your adapter using the WCF LOB Adapter SDK</span></span>

## <a name="overview"></a><span data-ttu-id="673ba-103">概述</span><span class="sxs-lookup"><span data-stu-id="673ba-103">Overview</span></span>
<span data-ttu-id="673ba-104">规划是任何开发工作，包括适配器使用的开发的重要部分[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="673ba-104">Planning is an important part of any development effort, including adapters developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="673ba-105">做好充分规划用于开发适配器可能会导致您要按预期方式运行，缺少 API 提供的某些主要功能的适配器时，与业务线系统和所涉及的不同的实现细节交互的策略和预期用户，或需要频繁更新和修复。</span><span class="sxs-lookup"><span data-stu-id="673ba-105">Failure to adequately plan strategies for interacting with the line-of-business system and the different implementation details involved when developing an adapter could cause your adapter to behave unexpectedly, to lack certain key features provided by the API and expected by the user, or to require frequent update and repair.</span></span>  
  
 <span data-ttu-id="673ba-106">本部分包含地设计你的适配器所需的信息。</span><span class="sxs-lookup"><span data-stu-id="673ba-106">This section contains the information needed to design your adapter.</span></span> <span data-ttu-id="673ba-107">使用此信息，你可以计划可满足用户需求的设计。</span><span class="sxs-lookup"><span data-stu-id="673ba-107">Using this information, you can plan a design that meets the needs of your users.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="673ba-108">要开始</span><span class="sxs-lookup"><span data-stu-id="673ba-108">Get started</span></span>
  
-   [<span data-ttu-id="673ba-109">了解，以及了解你 LOB 系统</span><span class="sxs-lookup"><span data-stu-id="673ba-109">Know and understand your LOB system</span></span>](understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="673ba-110">在 WCF LOB 适配器 SDK 中查看受支持的消息交换模式</span><span class="sxs-lookup"><span data-stu-id="673ba-110">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>](view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="673ba-111">使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式</span><span class="sxs-lookup"><span data-stu-id="673ba-111">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>](select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="673ba-112">了解在使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全</span><span class="sxs-lookup"><span data-stu-id="673ba-112">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>](understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="673ba-113">了解 WCF 中的事务</span><span class="sxs-lookup"><span data-stu-id="673ba-113">Understand transactions in WCF</span></span>](atomic-consistent-isolated-durable-transactions-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="673ba-114">有关元数据搜索和浏览与 WCF LOB 适配器 SDK 适配器</span><span class="sxs-lookup"><span data-stu-id="673ba-114">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>](about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter.md)
  
## <a name="see-also"></a><span data-ttu-id="673ba-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="673ba-115">See Also</span></span>  
[<span data-ttu-id="673ba-116">规划和设计你的适配器</span><span class="sxs-lookup"><span data-stu-id="673ba-116">Plan and architect your adapter</span></span>](plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)