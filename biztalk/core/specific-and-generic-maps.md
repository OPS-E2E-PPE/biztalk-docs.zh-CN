---
title: 特殊映射与通用映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b85658030540ae9b823a5eab32501a200f974c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243207"
---
# <a name="specific-and-generic-maps"></a><span data-ttu-id="0905c-102">特殊映射与通用映射</span><span class="sxs-lookup"><span data-stu-id="0905c-102">Specific and Generic Maps</span></span>
<span data-ttu-id="0905c-103">创建一个映射，以将数据转换时，可以创建*特定*或*泛型*映射。</span><span class="sxs-lookup"><span data-stu-id="0905c-103">When you create a map that transforms data, you can create either a *specific* or a *generic* map.</span></span>  
  
 <span data-ttu-id="0905c-104">使用特殊映射来满足特定贸易合作伙伴的需求。</span><span class="sxs-lookup"><span data-stu-id="0905c-104">You use a specific map to meet the needs of a particular trading partner.</span></span> <span data-ttu-id="0905c-105">当与贸易合作伙伴具有非常特定的业务需求或业务协议时，请使用特殊映射。</span><span class="sxs-lookup"><span data-stu-id="0905c-105">Use a specific map when you have very specific business needs or business agreements with your trading partner.</span></span> <span data-ttu-id="0905c-106">特殊映射的优点是，它自定义以满足您与特定贸易合作伙伴的业务功能的需求。</span><span class="sxs-lookup"><span data-stu-id="0905c-106">The advantage of a specific map is that it is customized to meet the needs of the business functions you have with specific trading partners.</span></span> <span data-ttu-id="0905c-107">特殊映射的缺点是它不能与多个贸易合作伙伴使用。</span><span class="sxs-lookup"><span data-stu-id="0905c-107">The disadvantage of a specific map is that it cannot be used with multiple trading partners.</span></span> <span data-ttu-id="0905c-108">如果乘贸易合作伙伴的与这些贸易合作伙伴交换的不同的消息类型的数目数必须分配足够的时间和资源来管理所有关联的映射。</span><span class="sxs-lookup"><span data-stu-id="0905c-108">If you multiply the number of trading partners by the number of different message types exchanged with those trading partners, you must allocate enough time and resources to manage all of the associated maps.</span></span>  
  
 <span data-ttu-id="0905c-109">通用映射，但是，旨在与多个贸易合作伙伴一起使用。</span><span class="sxs-lookup"><span data-stu-id="0905c-109">Generic maps, on the other hand, are designed to be used with multiple trading partners.</span></span> <span data-ttu-id="0905c-110">因此，而不是开发和维护多个特定的业务文档架构，创建一个用于每种类型的业务文档架构，然后将其用于所有贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0905c-110">Therefore, instead of developing and maintaining multiple schemas for a particular business document, you create one schema for each type of business document, and then use them with all of your trading partners.</span></span> <span data-ttu-id="0905c-111">虽然多个贸易合作伙伴使用一个映射可以节省时间和资源，这些映射未自定义，可能无法满足所有情况下的需要。</span><span class="sxs-lookup"><span data-stu-id="0905c-111">While using one map with multiple trading partners saves time and resources, these maps are not customized and may not be meet the needs of all cases.</span></span>  
  
 <span data-ttu-id="0905c-112">很可能您将创建特定和泛型的映射，具体取决于你的业务性质。</span><span class="sxs-lookup"><span data-stu-id="0905c-112">It is likely that you will create both specific and generic maps, depending on the nature of your business.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0905c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0905c-113">See Also</span></span>  
 <span data-ttu-id="0905c-114">[映射](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="0905c-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="0905c-115">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="0905c-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)