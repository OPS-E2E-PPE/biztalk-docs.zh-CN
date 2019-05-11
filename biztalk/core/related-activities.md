---
title: 相关活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef8cf9e4b73b4d2eda00c022270ba4cb2db8cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397988"
---
# <a name="related-activities"></a><span data-ttu-id="a0d52-102">相关的活动</span><span class="sxs-lookup"><span data-stu-id="a0d52-102">Related Activities</span></span>
<span data-ttu-id="a0d52-103">相关活动区域包含与查询所基于的活动相关的活动的列表。</span><span class="sxs-lookup"><span data-stu-id="a0d52-103">The Related Activities area contains a list of activities that are related to the activity on which the query is based.</span></span> <span data-ttu-id="a0d52-104">采购订单活动的相关活动的示例将多个发货活动，因为一个采购订单上的项可以提供在多个发货。</span><span class="sxs-lookup"><span data-stu-id="a0d52-104">An example of a related activity for a Purchase Order activity would be multiple Shipment activities, since items on a single purchase order can be delivered in multiple shipments.</span></span>  
  
## <a name="creating-related-activities"></a><span data-ttu-id="a0d52-105">创建相关的活动</span><span class="sxs-lookup"><span data-stu-id="a0d52-105">Creating related activities</span></span>  
 <span data-ttu-id="a0d52-106">有两种生成相关活动的列表：</span><span class="sxs-lookup"><span data-stu-id="a0d52-106">The list of related activities is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="a0d52-107">您定义两个活动，然后创建一个包含这两个值的单个视图。</span><span class="sxs-lookup"><span data-stu-id="a0d52-107">You define two activities and then create a single view that includes both of them.</span></span> <span data-ttu-id="a0d52-108">开发人员建立两个通过实现密钥、 字段和值在活动之间的关系之间的相关连接。</span><span class="sxs-lookup"><span data-stu-id="a0d52-108">Your developer makes a correlation connection between the two by implementing the key, field, and value relationships between the activities.</span></span>  
  
- <span data-ttu-id="a0d52-109">定义两个活动。</span><span class="sxs-lookup"><span data-stu-id="a0d52-109">You define two activities.</span></span> <span data-ttu-id="a0d52-110">开发人员通过调用 addrelationship （） 并定义密钥、 字段和值在活动之间的关系，在自定义应用程序中建立相关连接。</span><span class="sxs-lookup"><span data-stu-id="a0d52-110">Your developer makes a correlation connection in your custom application by calling AddRelationship() and defining the key, field, and value relationships between the activities.</span></span>  
  
  <span data-ttu-id="a0d52-111">在任一种方式中定义的活动关系将添加中的某一行\<activityname\>_Relationships 表。</span><span class="sxs-lookup"><span data-stu-id="a0d52-111">Defining the activity relationships in either of these ways adds a row in the \<activityname\>_Relationships table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0d52-112">仅在需要实时链接到每个其他的相关活动中定义的关系结果的第一种方法。</span><span class="sxs-lookup"><span data-stu-id="a0d52-112">Only the first method of defining relationships results in the related activities having live links to each other.</span></span> <span data-ttu-id="a0d52-113">第二种方法不会定义延伸视图，因此门户无法知道两个活动之间的关系。</span><span class="sxs-lookup"><span data-stu-id="a0d52-113">The second method does not define a spanning view and therefore the portal cannot know about the relationship between the two activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d52-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d52-114">See Also</span></span>  
 [<span data-ttu-id="a0d52-115">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="a0d52-115">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)