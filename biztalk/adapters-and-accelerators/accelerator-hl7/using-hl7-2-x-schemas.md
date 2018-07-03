---
title: 使用 HL7 2.X 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas
- HL7, 2.X schemas
- schemas, 2.X schemas
ms.assetid: 7f2d7dd4-76f1-463e-b579-9839a74b9631
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155710a421eaaf98f551729a00d724cd9a29ce3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979558"
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="6847b-102">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="6847b-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="6847b-103">本部分讨论了 Microsoft 支持的运行状况级别 7 (HL7) 标准的 2.X 版本[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6847b-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6847b-104">您可能需要更新随 BTAHL7 以符合标准 HL7 架构。</span><span class="sxs-lookup"><span data-stu-id="6847b-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="6847b-105">若要执行此操作，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="6847b-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6847b-106">BTAHL7 引擎无法处理消息实例符合 HL7 架构具有不明确的架构结构。</span><span class="sxs-lookup"><span data-stu-id="6847b-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="6847b-107">不明确的架构结构是指 HL7 标准尚未完全定义。</span><span class="sxs-lookup"><span data-stu-id="6847b-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="6847b-108">此类架构包括为 CSU 和 SUR.消息类型</span><span class="sxs-lookup"><span data-stu-id="6847b-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6847b-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="6847b-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6847b-110">HL7 2.X 版本</span><span class="sxs-lookup"><span data-stu-id="6847b-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="6847b-111">HL7 2.X 子文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="6847b-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="6847b-112">HL7 2.X 通用架构文件</span><span class="sxs-lookup"><span data-stu-id="6847b-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="6847b-113">使用 Z 对象扩展 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="6847b-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="6847b-114">解决数据库错误</span><span class="sxs-lookup"><span data-stu-id="6847b-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="6847b-115">“X”和“Y”可选性</span><span class="sxs-lookup"><span data-stu-id="6847b-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="6847b-116">可重复字段段</span><span class="sxs-lookup"><span data-stu-id="6847b-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)