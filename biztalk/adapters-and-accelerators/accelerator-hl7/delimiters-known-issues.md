---
title: "分隔符已知的问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18168ade94eed99efff0a062904c14b387de6bcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="delimiters-known-issues"></a><span data-ttu-id="d9a5f-102">分隔符已知的问题</span><span class="sxs-lookup"><span data-stu-id="d9a5f-102">Delimiters Known Issues</span></span>
<span data-ttu-id="d9a5f-103">本节包含可以帮助您避免分隔符错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-103">This section contains useful information that may help you avoid delimiter errors.</span></span>  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a><span data-ttu-id="d9a5f-104">不建议用作分隔符的字符</span><span class="sxs-lookup"><span data-stu-id="d9a5f-104">Characters not recommended to be used as delimiters</span></span>  
 <span data-ttu-id="d9a5f-105">建议，你并不使用以下字符作为分隔符因为它们可能导致错误：</span><span class="sxs-lookup"><span data-stu-id="d9a5f-105">It is recommended that you do not use the following characters as delimiters as they might cause errors:</span></span>  
  
-   <span data-ttu-id="d9a5f-106">Null 字符</span><span class="sxs-lookup"><span data-stu-id="d9a5f-106">Null characters</span></span>  
  
-   <span data-ttu-id="d9a5f-107">空格</span><span class="sxs-lookup"><span data-stu-id="d9a5f-107">Spaces</span></span>  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a><span data-ttu-id="d9a5f-108">标头或正文字段中的额外分隔符导致多个错误</span><span class="sxs-lookup"><span data-stu-id="d9a5f-108">Extra delimiters in a header or body field cause multiple errors</span></span>  
 <span data-ttu-id="d9a5f-109">HL7 V2 中的字段中有额外的分隔符时。X 消息， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成两条错误消息，其中一个与 XML 验证和其他与结构化的验证。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-109">When you have an extra delimiter in a field in an HL7 V2.X message, the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser might generate two error messages, one related to XML validation and the other related to structural validation.</span></span>  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a><span data-ttu-id="d9a5f-110">HL7 批处理段中允许存在尾随分隔符</span><span class="sxs-lookup"><span data-stu-id="d9a5f-110">Trailing delimiters permitted in HL7 batch segments</span></span>  
 <span data-ttu-id="d9a5f-111">HL7 定义批处理段 FHS、 BHS、 BTS 和 FT 可以包含尾随分隔符，以及不受尾随分隔符标志，因为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证批处理段的尾随分隔符。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-111">HL7 defined batch segments such as FHS, BHS, BTS, and FTS can have trailing delimiters and are not constrained by the trailing delimiter flag, because [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate trailing delimiters for batching segments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a5f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9a5f-112">See Also</span></span>  
 [<span data-ttu-id="d9a5f-113">已知问题</span><span class="sxs-lookup"><span data-stu-id="d9a5f-113">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)