---
title: 词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b031e30bf1206b80d292458700b45470cb6cc7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285326"
---
# <a name="vocabulary"></a><span data-ttu-id="12fa3-102">词汇</span><span class="sxs-lookup"><span data-stu-id="12fa3-102">Vocabulary</span></span>
<span data-ttu-id="12fa3-103">HL7 版本 2 提供一些支持的编码元素的词汇，但大多数情况下，提供传输来自本地编码系统的代码的结构。</span><span class="sxs-lookup"><span data-stu-id="12fa3-103">HL7 Version 2 provides some support for vocabularies for coded elements, but for the most part, provides a structure that transmits codes drawn from local coding systems.</span></span>  
  
 <span data-ttu-id="12fa3-104">HL7 版本 2 中的段表链接所有编码的字段。</span><span class="sxs-lookup"><span data-stu-id="12fa3-104">In HL7 Version 2, a segment table links all coded fields.</span></span> <span data-ttu-id="12fa3-105">段表包含的字段将使用的表的标识符。</span><span class="sxs-lookup"><span data-stu-id="12fa3-105">The segment table includes the identifier of the table that the field uses.</span></span> <span data-ttu-id="12fa3-106">有三种类型的表：HL7 定义的外部定义和用户定义。</span><span class="sxs-lookup"><span data-stu-id="12fa3-106">There are three types of tables: HL7 defined, externally defined, and user-defined.</span></span> <span data-ttu-id="12fa3-107">在某些情况下，标准提供用户定义表的示例值。</span><span class="sxs-lookup"><span data-stu-id="12fa3-107">In some cases, the standard supplies example values for a user-defined table.</span></span> <span data-ttu-id="12fa3-108">如 HL7 标准具有标记它们所示，应将它们。</span><span class="sxs-lookup"><span data-stu-id="12fa3-108">You should treat these as the HL7 standard has labeled them.</span></span>  
  
 <span data-ttu-id="12fa3-109">在新版本中，不能从 HL7 定义的表，删除代码，但您可以添加新的代码。</span><span class="sxs-lookup"><span data-stu-id="12fa3-109">In new versions, you cannot remove codes from HL7 defined tables, but you can add new codes.</span></span> <span data-ttu-id="12fa3-110">你可以在将用户定义表。</span><span class="sxs-lookup"><span data-stu-id="12fa3-110">You can change user-defined tables at will.</span></span>  
  
 <span data-ttu-id="12fa3-111">Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="12fa3-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="12fa3-112">您可以使用所有 HL7 定义表。</span><span class="sxs-lookup"><span data-stu-id="12fa3-112">You can use all of the HL7 defined tables.</span></span>  
  
-   <span data-ttu-id="12fa3-113">可以导入和使用外部定义如 ICD9 和 LOINC 代码集。</span><span class="sxs-lookup"><span data-stu-id="12fa3-113">You can import and use externally defined code sets such as ICD9 and LOINC.</span></span>  
  
-   <span data-ttu-id="12fa3-114">对于用户定义表，可以提供的值。</span><span class="sxs-lookup"><span data-stu-id="12fa3-114">You can provide the values for user-defined tables.</span></span>  
  
-   <span data-ttu-id="12fa3-115">在系统的支持不同的代码的情况下，您可以设置允许不同的代码集以进行互操作的映射。</span><span class="sxs-lookup"><span data-stu-id="12fa3-115">In cases where systems are supporting different sets of codes, you can set up mappings that allow disparate code sets to interoperate.</span></span> <span data-ttu-id="12fa3-116">如有必要，可以定义单个用户定义表的中间映射随附的多个实例。</span><span class="sxs-lookup"><span data-stu-id="12fa3-116">If necessary, you can define multiple instances of a single user-defined table to go along with the intermediary mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fa3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="12fa3-117">See Also</span></span>  
 <span data-ttu-id="12fa3-118">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="12fa3-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="12fa3-119">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="12fa3-119">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="12fa3-120">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="12fa3-120">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)