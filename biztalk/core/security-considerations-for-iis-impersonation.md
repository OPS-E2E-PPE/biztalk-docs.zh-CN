---
title: 有关 IIS 模拟的安全注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d10f460-29cf-49dc-9eef-b72bde4580cd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f69fed91a7110e88c034d2adc5050e9d2ac690f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280367"
---
# <a name="security-considerations-for-iis-impersonation"></a><span data-ttu-id="8a820-102">有关 IIS 模拟的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="8a820-102">Security Considerations for IIS Impersonation</span></span>
<span data-ttu-id="8a820-103">若要使用 BAM[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器和 IIS 模拟，请按照中的准则[如何确定和活动中设置事件写入者角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="8a820-103">To use the BAM [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor with IIS impersonation, follow the guidelines in [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a820-104">必须是 BizTalk Application Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="8a820-104">You must be a member of the BizTalk Application Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a820-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a820-105">See Also</span></span>  
 [<span data-ttu-id="8a820-106">BAM 侦听器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="8a820-106">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)