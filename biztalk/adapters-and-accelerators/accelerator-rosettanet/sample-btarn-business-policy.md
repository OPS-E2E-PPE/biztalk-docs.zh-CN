---
title: 示例 BTARN 业务策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e055d039e323fb985d9650f6f105bb3b44e9581
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974902"
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="85c0d-102">BTARN 业务策略示例</span><span class="sxs-lookup"><span data-stu-id="85c0d-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="85c0d-103">此示例是与 Microsoft® 关联的 XML 代码[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="85c0d-103">This sample is the XML code associated with a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="85c0d-104">示例文件是中的 samplebtarnpolicy.xml \<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PIPAutomation\3A4。</span><span class="sxs-lookup"><span data-stu-id="85c0d-104">The sample file is samplebtarnpolicy.xml in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="85c0d-105">演示</span><span class="sxs-lookup"><span data-stu-id="85c0d-105">Demonstrates</span></span>  
 <span data-ttu-id="85c0d-106">此代码给出具有以下规则的业务规则策略：</span><span class="sxs-lookup"><span data-stu-id="85c0d-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="85c0d-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span><span class="sxs-lookup"><span data-stu-id="85c0d-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c0d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="85c0d-108">See Also</span></span>  
 [<span data-ttu-id="85c0d-109">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="85c0d-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)