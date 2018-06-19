---
title: 特定和泛型映射 |Microsoft 文档
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
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276301"
---
# <a name="specific-and-generic-maps"></a><span data-ttu-id="8c3f5-102">特殊映射与通用映射</span><span class="sxs-lookup"><span data-stu-id="8c3f5-102">Specific and Generic Maps</span></span>
<span data-ttu-id="8c3f5-103">在创建转换数据的映射时，你可以创建*特定*或*泛型*映射。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-103">When you create a map that transforms data, you can create either a *specific* or a *generic* map.</span></span>  
  
 <span data-ttu-id="8c3f5-104">可以使用特殊映射来满足特定贸易合作伙伴的需求。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-104">You use a specific map to meet the needs of a particular trading partner.</span></span> <span data-ttu-id="8c3f5-105">当与贸易合作伙伴之间有特殊业务需求或业务协议时，可以使用特殊映射。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-105">Use a specific map when you have very specific business needs or business agreements with your trading partner.</span></span> <span data-ttu-id="8c3f5-106">特殊映射的优点是：可以对其进行自定义以满足与特定贸易合作伙伴之间的业务功能需求。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-106">The advantage of a specific map is that it is customized to meet the needs of the business functions you have with specific trading partners.</span></span> <span data-ttu-id="8c3f5-107">特殊映射的缺点是：无法用于多个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-107">The disadvantage of a specific map is that it cannot be used with multiple trading partners.</span></span> <span data-ttu-id="8c3f5-108">如果将贸易合作伙伴的数量乘以与这些贸易伙伴交换的不同消息类型的数量，您必须分配足够的时间和资源来管理所有关联的映射。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-108">If you multiply the number of trading partners by the number of different message types exchanged with those trading partners, you must allocate enough time and resources to manage all of the associated maps.</span></span>  
  
 <span data-ttu-id="8c3f5-109">另一方面，通用映射设计用于多个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-109">Generic maps, on the other hand, are designed to be used with multiple trading partners.</span></span> <span data-ttu-id="8c3f5-110">因此，您只需为每种类型的业务文档创建一个架构，然后对所有贸易合作伙伴使用这些架构即可，而无需为特定业务文档开发和维护多个架构。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-110">Therefore, instead of developing and maintaining multiple schemas for a particular business document, you create one schema for each type of business document, and then use them with all of your trading partners.</span></span> <span data-ttu-id="8c3f5-111">虽然对多个贸易合作伙伴使用一个映射可以节省时间和资源，但无法对这些映射进行自定义，而且可能无法满足所有情况下的需求。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-111">While using one map with multiple trading partners saves time and resources, these maps are not customized and may not be meet the needs of all cases.</span></span>  
  
 <span data-ttu-id="8c3f5-112">根据业务的性质，您所创建的映射可能既有特殊映射也有通用映射。</span><span class="sxs-lookup"><span data-stu-id="8c3f5-112">It is likely that you will create both specific and generic maps, depending on the nature of your business.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3f5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c3f5-113">See Also</span></span>  
 <span data-ttu-id="8c3f5-114">[地图](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="8c3f5-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="8c3f5-115">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="8c3f5-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)