---
title: 示例 BTARN 业务策略 |Microsoft 文档
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
ms.openlocfilehash: c85cbb7894f0d8bd1b61b7e7856865b49fd33859
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960619"
---
# <a name="sample-btarn-business-policy"></a><span data-ttu-id="37d0a-102">示例 BTARN 业务策略</span><span class="sxs-lookup"><span data-stu-id="37d0a-102">Sample BTARN Business Policy</span></span>
<span data-ttu-id="37d0a-103">此示例是与 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 业务规则策略相关联的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="37d0a-103">This sample is the XML code associated with a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] business-rules policy.</span></span>  
  
 <span data-ttu-id="37d0a-104">示例文件是在 samplebtarnpolicy.xml \<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK\ 快捷键PIPAutomation\3A4。</span><span class="sxs-lookup"><span data-stu-id="37d0a-104">The sample file is samplebtarnpolicy.xml in \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\PIPAutomation\3A4.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="37d0a-105">演示</span><span class="sxs-lookup"><span data-stu-id="37d0a-105">Demonstrates</span></span>  
 <span data-ttu-id="37d0a-106">此代码给出具有以下规则的业务规则策略：</span><span class="sxs-lookup"><span data-stu-id="37d0a-106">This code shows a business-rule policy with the following rule:</span></span>  
  
 <span data-ttu-id="37d0a-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span><span class="sxs-lookup"><span data-stu-id="37d0a-107">IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d0a-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37d0a-108">See Also</span></span>  
 [<span data-ttu-id="37d0a-109">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="37d0a-109">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)