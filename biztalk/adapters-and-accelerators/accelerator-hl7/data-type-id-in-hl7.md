---
title: "数据类型中 HL7 ID |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5778e772d21cb5f9c6759c127c92ebe74b6f5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-id-in-hl7"></a><span data-ttu-id="3a886-102">HL7 中的数据类型 ID</span><span class="sxs-lookup"><span data-stu-id="3a886-102">Data Type ID in HL7</span></span>
<span data-ttu-id="3a886-103">对于 HL7 2.1 版，数据类型 ID 是未定义的数据类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="3a886-103">In the case of HL7 V2.1, the data type ID is a placeholder for undefined data types.</span></span> <span data-ttu-id="3a886-104">其使用情况的示例如下：</span><span class="sxs-lookup"><span data-stu-id="3a886-104">The following are examples of its usage:</span></span>  
  
-   <span data-ttu-id="3a886-105">ST 字段的窗体中的数据类型是 SI (序列 ID)。</span><span class="sxs-lookup"><span data-stu-id="3a886-105">The data type in the form of an ST field is SI (Sequence ID).</span></span>  
  
-   <span data-ttu-id="3a886-106">NM 字段的窗体中的数据类型是复合字段。</span><span class="sxs-lookup"><span data-stu-id="3a886-106">The data type in the form of an NM field is composite fields.</span></span>  
  
 <span data-ttu-id="3a886-107">专门定义的复合数据类型的示例如下：</span><span class="sxs-lookup"><span data-stu-id="3a886-107">The following are examples of specifically defined composite data types:</span></span>  
  
-   <span data-ttu-id="3a886-108">带校验位 CK： 复合 ID。</span><span class="sxs-lookup"><span data-stu-id="3a886-108">CK: Composite ID with check digit.</span></span> <span data-ttu-id="3a886-109">例如：</span><span class="sxs-lookup"><span data-stu-id="3a886-109">For example:</span></span>  
  
    ```  
    |128952^6^M11|  
    ```  
  
-   <span data-ttu-id="3a886-110">CN： 复合 ID 号和名称。</span><span class="sxs-lookup"><span data-stu-id="3a886-110">CN: Composite ID number and name.</span></span> <span data-ttu-id="3a886-111">例如：</span><span class="sxs-lookup"><span data-stu-id="3a886-111">For example:</span></span>  
  
    ```  
    |12372^RIGGINS^JOHN^""^MD|  
    |12372|  
    |^RIGGINS^JOHN^""^MD|  
    ```  
  
-   <span data-ttu-id="3a886-112">使用的单位 CQ： 复合数量。</span><span class="sxs-lookup"><span data-stu-id="3a886-112">CQ: Composite quantity with units.</span></span> <span data-ttu-id="3a886-113">例如：</span><span class="sxs-lookup"><span data-stu-id="3a886-113">For example:</span></span>  
  
    ```  
    |123.7^ML|  
    ```  
  
-   <span data-ttu-id="3a886-114">CE： 编码的元素。</span><span class="sxs-lookup"><span data-stu-id="3a886-114">CE: Coded element.</span></span> <span data-ttu-id="3a886-115">例如：</span><span class="sxs-lookup"><span data-stu-id="3a886-115">For example:</span></span>  
  
    ```  
    |54.21^Laparoscopy^I9C^42112^^AS4|  
    ```  
  
 <span data-ttu-id="3a886-116">此数据类型是本地化，且站点定义。</span><span class="sxs-lookup"><span data-stu-id="3a886-116">This data type is localized and site-defined.</span></span> <span data-ttu-id="3a886-117">此外，HL7 2.1 版不提供此 HL7 访问数据库中的数据类型则覆盖率。</span><span class="sxs-lookup"><span data-stu-id="3a886-117">Additionally, HL7 V2.1 does not provide the coverage for this data type in the HL7 Access database.</span></span> <span data-ttu-id="3a886-118">用于生成你的架构， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 假定 HL7 V2.2 数据类型有效，并使用此信息生成架构。</span><span class="sxs-lookup"><span data-stu-id="3a886-118">For generating your schemas, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) assumes that the HL7 V2.2 data types are valid, and uses this information to build the schemas.</span></span> <span data-ttu-id="3a886-119">具体取决于架构中使用，相应的数据类型必须使用，这意味着，必须使用 CK、 CQ、 CE、 ST 替换的数据类型 ^ SI，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3a886-119">Depending on the usage in the schema, an appropriate data type must be used, meaning that the data type must be replaced with CK, CQ, CE, ST^SI, and so on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a886-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a886-120">See Also</span></span>  
 <span data-ttu-id="3a886-121">[数据类型](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3a886-121">[Data Types](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span></span>  
 <span data-ttu-id="3a886-122">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3a886-122">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3a886-123">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="3a886-123">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="3a886-124">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="3a886-124">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)