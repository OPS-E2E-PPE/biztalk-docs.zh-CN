---
title: "使用 HL7 2.X 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas
- HL7, 2.X schemas
- schemas, 2.X schemas
ms.assetid: 7f2d7dd4-76f1-463e-b579-9839a74b9631
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 934ca60bb3d89e08c9e803813f3548f196c3d56d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="61216-102">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="61216-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="61216-103">本部分讨论支持的运行状况级别七 (HL7) 标准的 2.X 版本[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="61216-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="61216-104">你可能需要更新随 BTAHL7 以符合标准 HL7 一起安装的架构。</span><span class="sxs-lookup"><span data-stu-id="61216-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="61216-105">若要执行此操作，请参阅[解决数据库错误](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="61216-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61216-106">BTAHL7 引擎无法处理消息实例符合具有不明确的架构结构的 HL7 架构。</span><span class="sxs-lookup"><span data-stu-id="61216-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="61216-107">不明确的架构结构是指 HL7 标准尚未完全定义。</span><span class="sxs-lookup"><span data-stu-id="61216-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="61216-108">此类架构包括与消息类型 CSU 和 SUR.</span><span class="sxs-lookup"><span data-stu-id="61216-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61216-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="61216-109">In This Section</span></span>  
  
-   [<span data-ttu-id="61216-110">HL7 2.X 版</span><span class="sxs-lookup"><span data-stu-id="61216-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="61216-111">HL7 2.X 子文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="61216-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="61216-112">HL7 2.X 公共架构文件</span><span class="sxs-lookup"><span data-stu-id="61216-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="61216-113">扩展 HL7 2.X 架构具有 Z 对象</span><span class="sxs-lookup"><span data-stu-id="61216-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="61216-114">解决数据库错误</span><span class="sxs-lookup"><span data-stu-id="61216-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="61216-115">X 和 Y Optionality</span><span class="sxs-lookup"><span data-stu-id="61216-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="61216-116">可重复字段段</span><span class="sxs-lookup"><span data-stu-id="61216-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)