---
title: 计划创建地图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, planning
ms.assetid: e86af976-b989-4e24-80d5-3a9a3ac4e443
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72dde6b09b7777204547d00d26af571c9998d73f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="planning-to-create-maps"></a><span data-ttu-id="5e931-102">计划创建地图</span><span class="sxs-lookup"><span data-stu-id="5e931-102">Planning to Create Maps</span></span>
<span data-ttu-id="5e931-103">使用映射可以将符合某种架构的输入消息转换为符合另一种架构的输出消息。</span><span class="sxs-lookup"><span data-stu-id="5e931-103">You use maps to convert input messages conforming to one schema into output messages conforming to a different schema.</span></span> <span data-ttu-id="5e931-104">这些转换可能很简单也可能相当复杂，涉及到信息的计算与合并。</span><span class="sxs-lookup"><span data-stu-id="5e931-104">These conversions may be simple or quite complex, involving calculations and consolidation of information.</span></span>  
  
 <span data-ttu-id="5e931-105">下表列出了在规划创建映射时需要回答的一些问题。</span><span class="sxs-lookup"><span data-stu-id="5e931-105">The following table lists some of the questions that you need to answer when you plan to create maps.</span></span>  
  
|<span data-ttu-id="5e931-106">规划问题</span><span class="sxs-lookup"><span data-stu-id="5e931-106">Planning question</span></span>|<span data-ttu-id="5e931-107">建议</span><span class="sxs-lookup"><span data-stu-id="5e931-107">Recommendation</span></span>|  
|-----------------------|--------------------|  
|<span data-ttu-id="5e931-108">需要创建哪些映射？</span><span class="sxs-lookup"><span data-stu-id="5e931-108">What maps do I need to create?</span></span>|<span data-ttu-id="5e931-109">列出要使用 Microsoft® [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理的业务文档的列表。</span><span class="sxs-lookup"><span data-stu-id="5e931-109">Make a list of the business documents that you will process with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5e931-110">此列表中应包括如采购订单、发票、发货确认等信息。</span><span class="sxs-lookup"><span data-stu-id="5e931-110">Such a list might include, for example, a purchase order, an invoice, a shipping confirmation, and so on.</span></span> <span data-ttu-id="5e931-111">列表也可能包含多个此类每个业务文档，如你从一个贸易合作伙伴接收采购订单的结构不同于采购订单的结构时收到来自另一个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="5e931-111">The list might also include more than one of each such business document, such as when the structure of a purchase order you receive from one trading partner is different than the structure of a purchase order you receive from another trading partner.</span></span><br /><br /> <span data-ttu-id="5e931-112">检查列表并决定哪些文档需要使用不同的格式，哪些文档最适合转换为通用格式。</span><span class="sxs-lookup"><span data-stu-id="5e931-112">Go through the list and decide which of the documents need to be in a different format, or which documents are best handled by conversion to a common format.</span></span>|  
|<span data-ttu-id="5e931-113">需要在何处使用映射？</span><span class="sxs-lookup"><span data-stu-id="5e931-113">Where do I need maps?</span></span>|<span data-ttu-id="5e931-114">可以在发送端口、接收端口和代表业务程序的业务流程中使用映射。</span><span class="sxs-lookup"><span data-stu-id="5e931-114">You can use maps in send ports, receive ports, and in orchestrations representing business processes.</span></span> <span data-ttu-id="5e931-115">请考虑希望或需要在何处转换文档。</span><span class="sxs-lookup"><span data-stu-id="5e931-115">Consider where you want or need to convert documents.</span></span>|  
|<span data-ttu-id="5e931-116">是否有旧的映射要转换？</span><span class="sxs-lookup"><span data-stu-id="5e931-116">Do I have old maps to convert?</span></span>|<span data-ttu-id="5e931-117">[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 中创建的映射应在未修改的情况下进行迁移。</span><span class="sxs-lookup"><span data-stu-id="5e931-117">Maps created in [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 should migrate without modification.</span></span> <span data-ttu-id="5e931-118">应分配足够的时间来测试所迁移的映射。</span><span class="sxs-lookup"><span data-stu-id="5e931-118">Allocate enough time to test the migrated maps.</span></span> <span data-ttu-id="5e931-119">但是，在较旧版本的 BizTalk 中创建的地图可能不一定打开在 BizTalk Server 中。</span><span class="sxs-lookup"><span data-stu-id="5e931-119">However, maps created in older versions of BizTalk may not necessarily open in BizTalk Server.</span></span> <span data-ttu-id="5e931-120">**注意：**以前的版本中创建映射[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]可能准确地在工作[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年。</span><span class="sxs-lookup"><span data-stu-id="5e931-120">**Note:**  Maps created in the versions prior to [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] may work accurately in [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span> <span data-ttu-id="5e931-121">但是，映射可能无法打开 BizTalk Server 中。</span><span class="sxs-lookup"><span data-stu-id="5e931-121">But, those maps may not open in BizTalk Server.</span></span> <br /><br /> <span data-ttu-id="5e931-122">映射包含**脚本**functoid 或自定义 functoid 可能需要额外的工作。</span><span class="sxs-lookup"><span data-stu-id="5e931-122">Maps containing **Scripting** functoids or custom functoids may require additional work.</span></span> <span data-ttu-id="5e931-123">有关详细信息，请参阅[迁移 Functoid](../core/migrating-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="5e931-123">For more information, see [Migrating Functoids](../core/migrating-functoids.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e931-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e931-124">See Also</span></span>  
 <span data-ttu-id="5e931-125">[有关映射](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="5e931-125">[About Maps](../core/about-maps.md) </span></span>  
 [<span data-ttu-id="5e931-126">“迁移”Functoid</span><span class="sxs-lookup"><span data-stu-id="5e931-126">Migrating Functoids</span></span>](../core/migrating-functoids.md)