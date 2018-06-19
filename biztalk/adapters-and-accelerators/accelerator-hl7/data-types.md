---
title: 数据类型 |Microsoft 文档
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
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204941"
---
# <a name="data-types"></a><span data-ttu-id="b8575-102">数据类型</span><span class="sxs-lookup"><span data-stu-id="b8575-102">Data Types</span></span>
<span data-ttu-id="b8575-103">数据类型规范是重要工具，用于分区的 HL7 标准，复杂性，并了解 HL7 字段的数据内容至关重要。</span><span class="sxs-lookup"><span data-stu-id="b8575-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="b8575-104">某些数据类型是简单和包含只有一个组件，并且一些包含许多组件和子组件。</span><span class="sxs-lookup"><span data-stu-id="b8575-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="b8575-105">例如，PID.5 患者名称具有数据类型在版本 2.4 的 XPN。</span><span class="sxs-lookup"><span data-stu-id="b8575-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="b8575-106">此数据类型支持常见的细分。 一个英语语言的名称，例如，姓氏、 名字、 中间名，以及后缀，前缀，名称类型代码和名称的有效性 （日期） 范围。</span><span class="sxs-lookup"><span data-stu-id="b8575-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="b8575-107">在新 HL7 版本中，则可以添加，但不是删除数据类型。</span><span class="sxs-lookup"><span data-stu-id="b8575-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="b8575-108">如果您通过添加新组件为数据类型，添加内容，你可以仅添加它们末尾的范围内，则它们嵌套的结构。</span><span class="sxs-lookup"><span data-stu-id="b8575-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="b8575-109">在某些情况下，HL7 组织合并现有数据类型，以形成新的。</span><span class="sxs-lookup"><span data-stu-id="b8575-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="b8575-110">这会导致需要支持作为以前个子组件中的原始数据类型的项。</span><span class="sxs-lookup"><span data-stu-id="b8575-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="b8575-111">下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：</span><span class="sxs-lookup"><span data-stu-id="b8575-111">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b8575-112">支持从 2.1 版的所有 HL7 版本的标准数据类型上。</span><span class="sxs-lookup"><span data-stu-id="b8575-112"> supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
-   <span data-ttu-id="b8575-113">在开发接口时，可以在适当的限制数据类型。</span><span class="sxs-lookup"><span data-stu-id="b8575-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8575-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="b8575-114">In This Section</span></span>  
  
-   [<span data-ttu-id="b8575-115">数据类型 ID 在 HL7 2.1</span><span class="sxs-lookup"><span data-stu-id="b8575-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)