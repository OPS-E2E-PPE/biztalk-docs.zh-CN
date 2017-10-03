---
title: "EDI 结构验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-structural-validation"></a><span data-ttu-id="65d9e-102">EDI 结构验证</span><span class="sxs-lookup"><span data-stu-id="65d9e-102">EDI Structural Validation</span></span>
<span data-ttu-id="65d9e-103">X12 和 EDIFACT 编码的 EDI 规范为 EDI 交换的结构定义了特定规则和约定。</span><span class="sxs-lookup"><span data-stu-id="65d9e-103">EDI specifications for both X12 and EDIFACT encoding define specific rules and conventions for the structure of EDI interchanges.</span></span> <span data-ttu-id="65d9e-104">EDIReceivePipeline 中的 EDI 拆装器将验证每条接收的消息的信封是否符合这些结构规则。</span><span class="sxs-lookup"><span data-stu-id="65d9e-104">The EDI Disassembler in the EDIReceivePipeline verifies that the envelope of each received message complies with these structural rules.</span></span> <span data-ttu-id="65d9e-105">EDISendPipeline 根据这些规则生成要发送的每个消息并在发送前验证信封。</span><span class="sxs-lookup"><span data-stu-id="65d9e-105">The EDISendPipeline builds each message to be sent in accordance with these rules and validates the envelope before sending.</span></span>  
  
 <span data-ttu-id="65d9e-106">结构验证可确保存在所需的标头和尾部。</span><span class="sxs-lookup"><span data-stu-id="65d9e-106">The structural validation ensures that the required headers and trailers are present.</span></span> <span data-ttu-id="65d9e-107">结构完整性检查包括段检查、循环排序检查和计数检查。</span><span class="sxs-lookup"><span data-stu-id="65d9e-107">The structural integrity checks include segment and loop ordering and count checks.</span></span> <span data-ttu-id="65d9e-108">将始终执行这些检查以确保正确解析或序列化文档。</span><span class="sxs-lookup"><span data-stu-id="65d9e-108">These checks are always performed to ensure that the document will parse or serialize correctly.</span></span> <span data-ttu-id="65d9e-109">执行此验证即使**EDI 类型验证**和/或**扩展验证**将禁用这些选项。</span><span class="sxs-lookup"><span data-stu-id="65d9e-109">This validation is performed even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span> <span data-ttu-id="65d9e-110">将挂起的交换中失败的基本结构验证，即使**EDI 类型验证**和/或**扩展验证**将禁用这些选项。</span><span class="sxs-lookup"><span data-stu-id="65d9e-110">An interchange that fails the basic structural validations will be suspended, even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span>  
  
 <span data-ttu-id="65d9e-111">标头和尾部内数据元素的值以及标头/尾部与数据元素的分隔方式均由协议确定。</span><span class="sxs-lookup"><span data-stu-id="65d9e-111">The values of the data elements within the headers and trailers, and how the headers/trailers and data elements are separated, are determined by the agreement.</span></span> <span data-ttu-id="65d9e-112">它们是通过架构验证进行验证的。</span><span class="sxs-lookup"><span data-stu-id="65d9e-112">These are validated through schema validation.</span></span>  
  
 <span data-ttu-id="65d9e-113">有关信封和标头和拖车安排每个集内的内容的详细信息，请参阅[EDI 消息结构](../core/edi-message-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="65d9e-113">For more information about the envelope and the contents within each set of headers and trailers, see [EDI Message Structure](../core/edi-message-structure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d9e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65d9e-114">See Also</span></span>  
 [<span data-ttu-id="65d9e-115">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="65d9e-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)