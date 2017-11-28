---
title: "有关 IIS 模拟的安全注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d10f460-29cf-49dc-9eef-b72bde4580cd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fdafc8668e5143cc43064690f7a14736fec4869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-iis-impersonation"></a><span data-ttu-id="47093-102">有关 IIS 模拟的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="47093-102">Security Considerations for IIS Impersonation</span></span>
<span data-ttu-id="47093-103">若要使用 BAM[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器与 IIS 模拟，请按照中的准则[如何确定和活动设置事件的编写器角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="47093-103">To use the BAM [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor with IIS impersonation, follow the guidelines in [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47093-104">你必须是 BizTalk 应用程序用户组的成员。</span><span class="sxs-lookup"><span data-stu-id="47093-104">You must be a member of the BizTalk Application Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47093-105">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47093-105">See Also</span></span>  
 [<span data-ttu-id="47093-106">BAM 拦截器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="47093-106">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)