---
title: 如何删除孤立的跟踪配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, orphans
- tracking profiles, activities
- tracking profiles, deleting
- activities, tracking profiles
ms.assetid: e8923dab-5d02-41a3-840b-104b20624e6c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e61365e5677b81fd48a655ba553cd44108d5a0fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384310"
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a><span data-ttu-id="5671f-102">如何删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="5671f-102">How to Remove Orphaned Tracking Profiles</span></span>
<span data-ttu-id="5671f-103">跟踪配置文件是与活动关联。</span><span class="sxs-lookup"><span data-stu-id="5671f-103">Tracking profiles are associated with an activity.</span></span> <span data-ttu-id="5671f-104">如果某个活动是取消部署，关联的跟踪配置文件可能会变得孤立用户，这意味着它们不再与活动关联。</span><span class="sxs-lookup"><span data-stu-id="5671f-104">If an activity is undeployed, the associated tracking profiles can become orphaned, which means they are no longer associated with an activity.</span></span> <span data-ttu-id="5671f-105">可以使用以下过程删除跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="5671f-105">You can use the following procedure to remove the tracking profile.</span></span>  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a><span data-ttu-id="5671f-106">若要删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="5671f-106">To remove an orphaned tracking profile</span></span>  
  
1.  <span data-ttu-id="5671f-107">重新部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="5671f-107">Redeploy the BAM definition.</span></span> <span data-ttu-id="5671f-108">有关部署 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="5671f-108">For information about deploying BAM definitions, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
2.  <span data-ttu-id="5671f-109">使用跟踪配置文件编辑器 (TPE) 来删除跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="5671f-109">Use the Tracking Profile Editor (TPE) to remove the tracking profile.</span></span> <span data-ttu-id="5671f-110">有关删除跟踪配置文件的信息，请参阅[如何应用和删除跟踪配置文件](../core/how-to-apply-and-remove-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="5671f-110">For information about removing tracking profiles, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
3.  <span data-ttu-id="5671f-111">取消部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="5671f-111">Undeploy the BAM definition.</span></span> <span data-ttu-id="5671f-112">有关删除 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="5671f-112">For information about removing BAM definitions, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5671f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5671f-113">See Also</span></span>  
 <span data-ttu-id="5671f-114">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="5671f-114">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="5671f-115">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="5671f-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)