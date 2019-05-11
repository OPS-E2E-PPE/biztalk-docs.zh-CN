---
title: RosettaNet 和 CIDX 消息传送标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messaging standards
- CIDX, messaging standards
- RosettaNet, messaging standards
ms.assetid: 3e9c090b-9425-41ae-ae86-d39ca2abfb63
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67e914c7ac6a80a1d00b6c3bb5a240aba4ea4e87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282105"
---
# <a name="rosettanet-and-cidx-messaging-standards"></a><span data-ttu-id="76722-102">RosettaNet 和 CIDX 消息传送标准</span><span class="sxs-lookup"><span data-stu-id="76722-102">RosettaNet and CIDX Messaging Standards</span></span>
<span data-ttu-id="76722-103">Microsoft® 的主要用途[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]旨在处理符合 RosettaNet 或化工行业数据交换 (CIDX) 消息传递标准的消息。</span><span class="sxs-lookup"><span data-stu-id="76722-103">The primary purpose of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] is to process messages that conform to the RosettaNet or Chemical Industry Data Exchange (CIDX) messaging standards.</span></span> <span data-ttu-id="76722-104">本部分提供有关两个主要的 RosettaNet 标准的信息： RosettaNet 实现框架 (RNIF) 与合作伙伴接口流程 (Pip)。</span><span class="sxs-lookup"><span data-stu-id="76722-104">This section provides information about the two major RosettaNet standards: the RosettaNet Implementation Framework (RNIF) and Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="76722-105">它还提供有关 CIDX Chem eStandards 的信息。</span><span class="sxs-lookup"><span data-stu-id="76722-105">It also provides information about the CIDX Chem eStandards.</span></span>  
  
 <span data-ttu-id="76722-106">RosettaNet 标准是一套新兴的并被广泛接受的标准，用于在高科技方案中实现自动的消息交换。</span><span class="sxs-lookup"><span data-stu-id="76722-106">The RosettaNet standards are an emerging, widely accepted set of standards for implementing automated message exchange in high-technology scenarios.</span></span> <span data-ttu-id="76722-107">RosettaNet 组织的目的是创建、 实施和提升电子商务流程标准。</span><span class="sxs-lookup"><span data-stu-id="76722-107">The purpose of the RosettaNet organization is to create, implement, and promote eBusiness process standards.</span></span> <span data-ttu-id="76722-108">这些标准广泛高科技制造业和供应链应用程序中。</span><span class="sxs-lookup"><span data-stu-id="76722-108">These standards are widely used in high-technology manufacturing and supply-chain applications.</span></span> <span data-ttu-id="76722-109">管理 RosettaNet 组织的六个不同行业委员会演示应用程序的范围：</span><span class="sxs-lookup"><span data-stu-id="76722-109">The six different industry councils that govern the RosettaNet organization demonstrate the breadth of the application:</span></span>  
  
- <span data-ttu-id="76722-110">电子组件</span><span class="sxs-lookup"><span data-stu-id="76722-110">Electronic components</span></span>  
  
- <span data-ttu-id="76722-111">半导体制造商</span><span class="sxs-lookup"><span data-stu-id="76722-111">Semiconductor manufacturers</span></span>  
  
- <span data-ttu-id="76722-112">信息技术</span><span class="sxs-lookup"><span data-stu-id="76722-112">Information technology</span></span>  
  
- <span data-ttu-id="76722-113">电信</span><span class="sxs-lookup"><span data-stu-id="76722-113">Telecommunications</span></span>  
  
- <span data-ttu-id="76722-114">物流</span><span class="sxs-lookup"><span data-stu-id="76722-114">Logistics</span></span>  
  
- <span data-ttu-id="76722-115">解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="76722-115">Solution providers</span></span>  
  
  <span data-ttu-id="76722-116">CIDX Chem eStandards 是一套被广泛接受的用于在化工行业方案中实现自动的消息交换的标准。</span><span class="sxs-lookup"><span data-stu-id="76722-116">The CIDX Chem eStandards are a widely accepted set of standards for implementing automated message exchange in chemical-industry scenarios.</span></span>  
  
  <span data-ttu-id="76722-117">有关标准的详细信息，请参阅 RosettaNet 网站下载，网址[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)和 CIDX 网站上的[ http://go.microsoft.com/FWLink/?LinkID=34540 ](http://go.microsoft.com/FWLink/?LinkID=34540)。</span><span class="sxs-lookup"><span data-stu-id="76722-117">For more information about standards, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) and the CIDX Web site at [http://go.microsoft.com/FWLink/?LinkID=34540](http://go.microsoft.com/FWLink/?LinkID=34540).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76722-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="76722-118">In This Section</span></span>  
  
-   [<span data-ttu-id="76722-119">RNIF 标准</span><span class="sxs-lookup"><span data-stu-id="76722-119">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)  
  
-   [<span data-ttu-id="76722-120">RosettaNet PIP</span><span class="sxs-lookup"><span data-stu-id="76722-120">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)  
  
-   [<span data-ttu-id="76722-121">CIDX 消息传送标准</span><span class="sxs-lookup"><span data-stu-id="76722-121">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)