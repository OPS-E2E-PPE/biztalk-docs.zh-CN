---
title: 规划和设计您的适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: 82d907cdc2538bb4ed024f0aaf38bf04cf80cf59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363434"
---
# <a name="plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="05d11-102">规划和设计您的适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="05d11-102">Plan and design your adapter using the WCF LOB Adapter SDK</span></span>

## <a name="overview"></a><span data-ttu-id="05d11-103">概述</span><span class="sxs-lookup"><span data-stu-id="05d11-103">Overview</span></span>
<span data-ttu-id="05d11-104">规划是任何开发工作，包括与开发的适配器的一个重要部分[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05d11-104">Planning is an important part of any development effort, including adapters developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="05d11-105">做好充分规划时开发适配器可能会导致您的适配器出现意外行为，缺少 API 提供的某些关键功能与业务线系统和所涉及的不同的实现细节进行交互的策略和预期用户，或需要频繁更新和修复。</span><span class="sxs-lookup"><span data-stu-id="05d11-105">Failure to adequately plan strategies for interacting with the line-of-business system and the different implementation details involved when developing an adapter could cause your adapter to behave unexpectedly, to lack certain key features provided by the API and expected by the user, or to require frequent update and repair.</span></span>  
  
 <span data-ttu-id="05d11-106">本部分包含地设计您的适配器所需的信息。</span><span class="sxs-lookup"><span data-stu-id="05d11-106">This section contains the information needed to design your adapter.</span></span> <span data-ttu-id="05d11-107">使用此信息，您可以计划可满足用户需求的设计。</span><span class="sxs-lookup"><span data-stu-id="05d11-107">Using this information, you can plan a design that meets the needs of your users.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="05d11-108">入门</span><span class="sxs-lookup"><span data-stu-id="05d11-108">Get started</span></span>
  
-   [<span data-ttu-id="05d11-109">认识和了解 LOB 系统</span><span class="sxs-lookup"><span data-stu-id="05d11-109">Know and understand your LOB system</span></span>](understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="05d11-110">在 WCF LOB 适配器 SDK 中查看支持的消息交换模式</span><span class="sxs-lookup"><span data-stu-id="05d11-110">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>](view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="05d11-111">使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式</span><span class="sxs-lookup"><span data-stu-id="05d11-111">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>](select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="05d11-112">了解使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全性</span><span class="sxs-lookup"><span data-stu-id="05d11-112">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>](understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="05d11-113">了解 WCF 中的事务</span><span class="sxs-lookup"><span data-stu-id="05d11-113">Understand transactions in WCF</span></span>](atomic-consistent-isolated-durable-transactions-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="05d11-114">有关元数据搜索和浏览使用 WCF LOB 适配器 SDK 适配器</span><span class="sxs-lookup"><span data-stu-id="05d11-114">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>](about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter.md)
  
## <a name="see-also"></a><span data-ttu-id="05d11-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="05d11-115">See Also</span></span>  
[<span data-ttu-id="05d11-116">计划和构建适配器</span><span class="sxs-lookup"><span data-stu-id="05d11-116">Plan and architect your adapter</span></span>](plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)