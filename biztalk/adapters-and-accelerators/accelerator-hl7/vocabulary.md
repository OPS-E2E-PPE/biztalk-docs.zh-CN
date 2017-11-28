---
title: "词汇 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c77247054914097131103fe33d86fc78551d8cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="vocabulary"></a><span data-ttu-id="350bd-102">词汇</span><span class="sxs-lookup"><span data-stu-id="350bd-102">Vocabulary</span></span>
<span data-ttu-id="350bd-103">HL7 版本 2 的词汇对于编码的元素，提供了一些支持，但大多数情况下，提供了传输绘制从本地编码系统的代码的结构。</span><span class="sxs-lookup"><span data-stu-id="350bd-103">HL7 Version 2 provides some support for vocabularies for coded elements, but for the most part, provides a structure that transmits codes drawn from local coding systems.</span></span>  
  
 <span data-ttu-id="350bd-104">在 HL7 版本 2 中，段表链接编码的所有字段。</span><span class="sxs-lookup"><span data-stu-id="350bd-104">In HL7 Version 2, a segment table links all coded fields.</span></span> <span data-ttu-id="350bd-105">段表包含的字段将使用的表的标识符。</span><span class="sxs-lookup"><span data-stu-id="350bd-105">The segment table includes the identifier of the table that the field uses.</span></span> <span data-ttu-id="350bd-106">有三种类型的表： HL7 定义，外部定义和用户定义。</span><span class="sxs-lookup"><span data-stu-id="350bd-106">There are three types of tables: HL7 defined, externally defined, and user-defined.</span></span> <span data-ttu-id="350bd-107">在某些情况下，标准提供用户定义表的示例值。</span><span class="sxs-lookup"><span data-stu-id="350bd-107">In some cases, the standard supplies example values for a user-defined table.</span></span> <span data-ttu-id="350bd-108">你应方式 HL7 标准具有标记为它们来处理这些信息。</span><span class="sxs-lookup"><span data-stu-id="350bd-108">You should treat these as the HL7 standard has labeled them.</span></span>  
  
 <span data-ttu-id="350bd-109">在新版本中，您不能取消代码 HL7 定义表，但你可以添加新的代码。</span><span class="sxs-lookup"><span data-stu-id="350bd-109">In new versions, you cannot remove codes from HL7 defined tables, but you can add new codes.</span></span> <span data-ttu-id="350bd-110">你可以更改将在用户定义的表。</span><span class="sxs-lookup"><span data-stu-id="350bd-110">You can change user-defined tables at will.</span></span>  
  
 <span data-ttu-id="350bd-111">下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="350bd-111">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="350bd-112">你可以使用的所有定义的 HL7 表。</span><span class="sxs-lookup"><span data-stu-id="350bd-112">You can use all of the HL7 defined tables.</span></span>  
  
-   <span data-ttu-id="350bd-113">你可以导入和使用外部定义 ICD9 等 LOINC 代码集。</span><span class="sxs-lookup"><span data-stu-id="350bd-113">You can import and use externally defined code sets such as ICD9 and LOINC.</span></span>  
  
-   <span data-ttu-id="350bd-114">你可以为用户定义的表中提供的值。</span><span class="sxs-lookup"><span data-stu-id="350bd-114">You can provide the values for user-defined tables.</span></span>  
  
-   <span data-ttu-id="350bd-115">在系统其中支持不同的代码集的情况下，你可以设置允许进行互操作的不同代码集的映射。</span><span class="sxs-lookup"><span data-stu-id="350bd-115">In cases where systems are supporting different sets of codes, you can set up mappings that allow disparate code sets to interoperate.</span></span> <span data-ttu-id="350bd-116">如有必要，你可以定义单个用户定义表转以及中间的映射的多个实例。</span><span class="sxs-lookup"><span data-stu-id="350bd-116">If necessary, you can define multiple instances of a single user-defined table to go along with the intermediary mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350bd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="350bd-117">See Also</span></span>  
 <span data-ttu-id="350bd-118">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="350bd-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="350bd-119">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="350bd-119">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="350bd-120">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="350bd-120">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)