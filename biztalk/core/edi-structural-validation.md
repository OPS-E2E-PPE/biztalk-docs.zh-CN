---
title: EDI 结构验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 422449a9720b78a65b4934fbf17d255e84678613
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350226"
---
# <a name="edi-structural-validation"></a><span data-ttu-id="034b9-102">EDI 结构验证</span><span class="sxs-lookup"><span data-stu-id="034b9-102">EDI Structural Validation</span></span>
<span data-ttu-id="034b9-103">X12 和 EDIFACT 编码的 EDI 规范定义的 EDI 交换结构的特定规则和约定。</span><span class="sxs-lookup"><span data-stu-id="034b9-103">EDI specifications for both X12 and EDIFACT encoding define specific rules and conventions for the structure of EDI interchanges.</span></span> <span data-ttu-id="034b9-104">EDIReceivePipeline 中的 EDI 拆装器将验证每个收到的消息的信封符合这些结构规则。</span><span class="sxs-lookup"><span data-stu-id="034b9-104">The EDI Disassembler in the EDIReceivePipeline verifies that the envelope of each received message complies with these structural rules.</span></span> <span data-ttu-id="034b9-105">EDISendPipeline 生成要发送这些规则根据每个消息，并在发送前验证信封。</span><span class="sxs-lookup"><span data-stu-id="034b9-105">The EDISendPipeline builds each message to be sent in accordance with these rules and validates the envelope before sending.</span></span>  
  
 <span data-ttu-id="034b9-106">结构验证确保存在必需的标头和尾部。</span><span class="sxs-lookup"><span data-stu-id="034b9-106">The structural validation ensures that the required headers and trailers are present.</span></span> <span data-ttu-id="034b9-107">结构完整性检查包括段、 循环排序和计数检查。</span><span class="sxs-lookup"><span data-stu-id="034b9-107">The structural integrity checks include segment and loop ordering and count checks.</span></span> <span data-ttu-id="034b9-108">始终执行这些检查以确保该文档将分析或正确序列化。</span><span class="sxs-lookup"><span data-stu-id="034b9-108">These checks are always performed to ensure that the document will parse or serialize correctly.</span></span> <span data-ttu-id="034b9-109">执行此验证，即使**EDI 类型验证**和/或**扩展验证**选项处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="034b9-109">This validation is performed even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span> <span data-ttu-id="034b9-110">未通过基本结构验证的交换将挂起，即使**EDI 类型验证**和/或**扩展验证**选项处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="034b9-110">An interchange that fails the basic structural validations will be suspended, even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span>  
  
 <span data-ttu-id="034b9-111">标头和尾部内的数据元素和如何分隔的标头/尾部与数据元素的值由协议确定。</span><span class="sxs-lookup"><span data-stu-id="034b9-111">The values of the data elements within the headers and trailers, and how the headers/trailers and data elements are separated, are determined by the agreement.</span></span> <span data-ttu-id="034b9-112">这些架构验证通过验证。</span><span class="sxs-lookup"><span data-stu-id="034b9-112">These are validated through schema validation.</span></span>  
  
 <span data-ttu-id="034b9-113">有关信封以及其中每个组标头和尾部的内容的详细信息，请参阅[EDI 消息结构](../core/edi-message-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="034b9-113">For more information about the envelope and the contents within each set of headers and trailers, see [EDI Message Structure](../core/edi-message-structure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034b9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="034b9-114">See Also</span></span>  
 [<span data-ttu-id="034b9-115">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="034b9-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)