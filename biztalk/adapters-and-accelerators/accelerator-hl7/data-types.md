---
title: 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a9c18f7178615c069afeed484fba32ae5a0977
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255565"
---
# <a name="data-types"></a><span data-ttu-id="6d7bd-102">数据类型</span><span class="sxs-lookup"><span data-stu-id="6d7bd-102">Data Types</span></span>
<span data-ttu-id="6d7bd-103">数据类型规范是分区的 HL7 标准复杂性的一个重要工具，了解 HL7 字段的数据内容的关键。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="6d7bd-104">某些数据类型是简单和包含只有一个组件，并且某些包含许多组件和子组件。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="6d7bd-105">例如，PID.5 患者名称具有键入 XPN 版本 2.4 中的数据。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="6d7bd-106">此数据类型支持的常见细分线的一个英语语言的名称，例如，姓氏、 名字、 中间名，以及后缀、 前缀、 名称类型代码和名称的有效性 (date) 范围。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="6d7bd-107">在新 HL7 版本中，您可以添加，但不是删除数据类型。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="6d7bd-108">如果您通过添加新组件或子组件为数据类型，添加内容，则只在其中它们所嵌套的结构末尾添加它们。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="6d7bd-109">在某些情况下，HL7 组织合并现有的数据类型，以形成新的。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="6d7bd-110">这就会导致需要支持先前在原始数据类型的子组件的项。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="6d7bd-111">Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="6d7bd-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="6d7bd-112">上支持所有 HL7 版本从 2.1 版的标准数据类型。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-112">supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
- <span data-ttu-id="6d7bd-113">在开发接口时，可以在适当的限制的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6d7bd-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d7bd-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="6d7bd-114">In This Section</span></span>  
  
-   [<span data-ttu-id="6d7bd-115">HL7 中的数据类型 ID 2.1</span><span class="sxs-lookup"><span data-stu-id="6d7bd-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)