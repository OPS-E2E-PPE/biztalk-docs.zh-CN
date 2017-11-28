---
title: "查询活动关系 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11570bbf42001ac11b5be61ff7b76d06f3df0889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="querying-activity-relationships"></a><span data-ttu-id="241ca-102">查询活动关系</span><span class="sxs-lookup"><span data-stu-id="241ca-102">Querying Activity Relationships</span></span>
<span data-ttu-id="241ca-103">在为每个活动动态创建的 SQL 视图中，可以找到活动关系信息。</span><span class="sxs-lookup"><span data-stu-id="241ca-103">The activity relationship information is available in a dynamically created SQL view for each activity.</span></span> <span data-ttu-id="241ca-104">此视图的名称是</span><span class="sxs-lookup"><span data-stu-id="241ca-104">The name of this view is</span></span>  
  
 <span data-ttu-id="241ca-105">**bam_\<**  *活动* **> _AllRelationships**</span><span class="sxs-lookup"><span data-stu-id="241ca-105">**bam_\<** *Activity* **>_AllRelationships**</span></span>  
  
 <span data-ttu-id="241ca-106">其中\<*活动*> 为 BAM 定义 XML 中的活动元素的名称属性即为 Excel BAM 外接程序使用输入的活动名称相同。</span><span class="sxs-lookup"><span data-stu-id="241ca-106">Where \<*Activity*> is the Name attribute of the Activity element in the BAM definition XML, which is the same as the Activity name entered using the BAM Add-in for Excel.</span></span>  
  
 <span data-ttu-id="241ca-107">关系事件发生在特定活动的上下文中。</span><span class="sxs-lookup"><span data-stu-id="241ca-107">The relationship events occur in the context of a specific activity.</span></span> <span data-ttu-id="241ca-108">例如，如果采购订单和装运之间的关系发生在采购订单活动的上下文中，关系记录将显示在**bam_PurchaseOrder_AllRelationships**，但未显示在**bam_Shipment_AllRelationships**。</span><span class="sxs-lookup"><span data-stu-id="241ca-108">For example, if the relationship between Purchase Order and Shipment occurs in the context of the Purchase Order activity, the Relationship record will show up in **bam_PurchaseOrder_AllRelationships**, but not in **bam_Shipment_AllRelationships**.</span></span> <span data-ttu-id="241ca-109">有关详细信息，请参阅[活动关系](../core/activity-relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="241ca-109">For more information, see [Activity Relationships](../core/activity-relationships.md).</span></span>  
  
 <span data-ttu-id="241ca-110">若要查找所有相关的活动与购买排序需要查询这两个视图**bam_PurchaseOrder_AllRelationships**以及所有视图**bam_\<***OtherActivity* **> _AllRelationships**，其中\< *OtherActivity*> 相同 BAM 视图中的活动。</span><span class="sxs-lookup"><span data-stu-id="241ca-110">To find all the related activities to a purchase order you need to query both the view **bam_PurchaseOrder_AllRelationships** as well as all views **bam_\<***OtherActivity***>_AllRelationships**, where \<*OtherActivity*> is the activity in the same BAM view.</span></span>  
  
 <span data-ttu-id="241ca-111">关系记录的活动实例的一部分，维护多维数据集与实例数据同步中所述[活动数据存储](../core/activity-data-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="241ca-111">The relationship records are part of the activity instance and they are maintained in synchronization with the instance data as described in [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241ca-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="241ca-112">See Also</span></span>  
 [<span data-ttu-id="241ca-113">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="241ca-113">Querying BAM Data</span></span>](../core/querying-bam-data.md)