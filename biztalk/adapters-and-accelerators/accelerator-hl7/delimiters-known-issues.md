---
title: 分隔符已知的问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7a9c95318f3c95f65ef7b0fdfe616e71bfe3af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255517"
---
# <a name="delimiters-known-issues"></a><span data-ttu-id="a5654-102">分隔符已知的问题</span><span class="sxs-lookup"><span data-stu-id="a5654-102">Delimiters Known Issues</span></span>
<span data-ttu-id="a5654-103">本部分包含可帮助你避免分隔符错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="a5654-103">This section contains useful information that may help you avoid delimiter errors.</span></span>  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a><span data-ttu-id="a5654-104">不建议用作分隔符的字符</span><span class="sxs-lookup"><span data-stu-id="a5654-104">Characters not recommended to be used as delimiters</span></span>  
 <span data-ttu-id="a5654-105">建议您不要使用以下字符作为分隔符因为它们可能会导致错误：</span><span class="sxs-lookup"><span data-stu-id="a5654-105">It is recommended that you do not use the following characters as delimiters as they might cause errors:</span></span>  
  
-   <span data-ttu-id="a5654-106">Null 字符</span><span class="sxs-lookup"><span data-stu-id="a5654-106">Null characters</span></span>  
  
-   <span data-ttu-id="a5654-107">空格</span><span class="sxs-lookup"><span data-stu-id="a5654-107">Spaces</span></span>  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a><span data-ttu-id="a5654-108">标头或正文字段中的额外分隔符会导致多个错误</span><span class="sxs-lookup"><span data-stu-id="a5654-108">Extra delimiters in a header or body field cause multiple errors</span></span>  
 <span data-ttu-id="a5654-109">HL7 V2 中的字段中有额外分隔符时。消息，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成两条错误消息，其中一个与 XML 验证和其他与结构验证。</span><span class="sxs-lookup"><span data-stu-id="a5654-109">When you have an extra delimiter in a field in an HL7 V2.X message, the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser might generate two error messages, one related to XML validation and the other related to structural validation.</span></span>  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a><span data-ttu-id="a5654-110">HL7 batch 段中允许使用尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="a5654-110">Trailing delimiters permitted in HL7 batch segments</span></span>  
 <span data-ttu-id="a5654-111">HL7 定义批处理段如 FHS、 BHS、 BTS 和 FTS 可以具有尾部分隔符和不受尾随分隔符标志，因为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证批处理段的尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="a5654-111">HL7 defined batch segments such as FHS, BHS, BTS, and FTS can have trailing delimiters and are not constrained by the trailing delimiter flag, because [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate trailing delimiters for batching segments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5654-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5654-112">See Also</span></span>  
 [<span data-ttu-id="a5654-113">已知问题</span><span class="sxs-lookup"><span data-stu-id="a5654-113">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)