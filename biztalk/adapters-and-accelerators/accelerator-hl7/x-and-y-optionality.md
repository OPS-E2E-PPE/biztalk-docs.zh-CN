---
title: '&#39;X&#39;和&#39;Y&#39;可选性 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82507c8c6d6f57c4fa85c4e20599b4fc79802e76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285292"
---
# <a name="39x39-and-39y39-optionality"></a><span data-ttu-id="c52cd-102">&#39;X&#39;和&#39;Y&#39;可选性</span><span class="sxs-lookup"><span data-stu-id="c52cd-102">&#39;X&#39; and &#39;Y&#39; Optionality</span></span>
<span data-ttu-id="c52cd-103">HL7 访问数据库中的 SegmentDataElements 表包含多个已设置为数据项 （字段）**请求/Opt = X**，这意味着 HL7 标准不会将此字段关联与此触发器事件，如中所示下表。</span><span class="sxs-lookup"><span data-stu-id="c52cd-103">The SegmentDataElements table in the HL7 Access database contains several Data Items (fields) that have been set as **Req/Opt = X**, meaning that the HL7 standard does not associate this field with this trigger event, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c52cd-104">段</span><span class="sxs-lookup"><span data-stu-id="c52cd-104">Segment</span></span>|<span data-ttu-id="c52cd-105">版本</span><span class="sxs-lookup"><span data-stu-id="c52cd-105">Version</span></span>|<span data-ttu-id="c52cd-106">一章</span><span class="sxs-lookup"><span data-stu-id="c52cd-106">Chapter</span></span>|<span data-ttu-id="c52cd-107">数据项</span><span class="sxs-lookup"><span data-stu-id="c52cd-107">Data Item</span></span>|<span data-ttu-id="c52cd-108">所需 /</span><span class="sxs-lookup"><span data-stu-id="c52cd-108">Required/</span></span><br /><br /> <span data-ttu-id="c52cd-109">可选</span><span class="sxs-lookup"><span data-stu-id="c52cd-109">Optional</span></span>|<span data-ttu-id="c52cd-110">报告</span><span class="sxs-lookup"><span data-stu-id="c52cd-110">Report</span></span>|<span data-ttu-id="c52cd-111">Number</span><span class="sxs-lookup"><span data-stu-id="c52cd-111">Number</span></span>|<span data-ttu-id="c52cd-112">HTML 标准</span><span class="sxs-lookup"><span data-stu-id="c52cd-112">HTML Standard</span></span>|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|<span data-ttu-id="c52cd-113">OBX</span><span class="sxs-lookup"><span data-stu-id="c52cd-113">OBX</span></span>|<span data-ttu-id="c52cd-114">2.4</span><span class="sxs-lookup"><span data-stu-id="c52cd-114">2.4</span></span>|<span data-ttu-id="c52cd-115">7.4.2.9</span><span class="sxs-lookup"><span data-stu-id="c52cd-115">7.4.2.9</span></span>|<span data-ttu-id="c52cd-116">00577</span><span class="sxs-lookup"><span data-stu-id="c52cd-116">00577</span></span>|<span data-ttu-id="c52cd-117">X</span><span class="sxs-lookup"><span data-stu-id="c52cd-117">X</span></span>|<span data-ttu-id="c52cd-118">Y</span><span class="sxs-lookup"><span data-stu-id="c52cd-118">Y</span></span>|<span data-ttu-id="c52cd-119">5</span><span class="sxs-lookup"><span data-stu-id="c52cd-119">5</span></span>|<span data-ttu-id="c52cd-120">ch07.htm#Heading113</span><span class="sxs-lookup"><span data-stu-id="c52cd-120">ch07.htm#Heading113</span></span>|  
|<span data-ttu-id="c52cd-121">OBX</span><span class="sxs-lookup"><span data-stu-id="c52cd-121">OBX</span></span>|<span data-ttu-id="c52cd-122">2.4</span><span class="sxs-lookup"><span data-stu-id="c52cd-122">2.4</span></span>|<span data-ttu-id="c52cd-123">7.4.2.8</span><span class="sxs-lookup"><span data-stu-id="c52cd-123">7.4.2.8</span></span>|<span data-ttu-id="c52cd-124">00576</span><span class="sxs-lookup"><span data-stu-id="c52cd-124">00576</span></span>|<span data-ttu-id="c52cd-125">X</span><span class="sxs-lookup"><span data-stu-id="c52cd-125">X</span></span>||<span data-ttu-id="c52cd-126">0</span><span class="sxs-lookup"><span data-stu-id="c52cd-126">0</span></span>|<span data-ttu-id="c52cd-127">ch07.htm#Heading112</span><span class="sxs-lookup"><span data-stu-id="c52cd-127">ch07.htm#Heading112</span></span>|  
|<span data-ttu-id="c52cd-128">OBX</span><span class="sxs-lookup"><span data-stu-id="c52cd-128">OBX</span></span>|<span data-ttu-id="c52cd-129">2.4</span><span class="sxs-lookup"><span data-stu-id="c52cd-129">2.4</span></span>|<span data-ttu-id="c52cd-130">7.4.2.6</span><span class="sxs-lookup"><span data-stu-id="c52cd-130">7.4.2.6</span></span>|<span data-ttu-id="c52cd-131">00574</span><span class="sxs-lookup"><span data-stu-id="c52cd-131">00574</span></span>|<span data-ttu-id="c52cd-132">X</span><span class="sxs-lookup"><span data-stu-id="c52cd-132">X</span></span>||<span data-ttu-id="c52cd-133">0</span><span class="sxs-lookup"><span data-stu-id="c52cd-133">0</span></span>|<span data-ttu-id="c52cd-134">ch07.htm#Heading107</span><span class="sxs-lookup"><span data-stu-id="c52cd-134">ch07.htm#Heading107</span></span>|  
|<span data-ttu-id="c52cd-135">OBX</span><span class="sxs-lookup"><span data-stu-id="c52cd-135">OBX</span></span>|<span data-ttu-id="c52cd-136">2.4</span><span class="sxs-lookup"><span data-stu-id="c52cd-136">2.4</span></span>|<span data-ttu-id="c52cd-137">7.4.2.17</span><span class="sxs-lookup"><span data-stu-id="c52cd-137">7.4.2.17</span></span>|<span data-ttu-id="c52cd-138">00936</span><span class="sxs-lookup"><span data-stu-id="c52cd-138">00936</span></span>|<span data-ttu-id="c52cd-139">X</span><span class="sxs-lookup"><span data-stu-id="c52cd-139">X</span></span>|<span data-ttu-id="c52cd-140">Y</span><span class="sxs-lookup"><span data-stu-id="c52cd-140">Y</span></span>|<span data-ttu-id="c52cd-141">0</span><span class="sxs-lookup"><span data-stu-id="c52cd-141">0</span></span>|<span data-ttu-id="c52cd-142">ch07.htm#Heading121</span><span class="sxs-lookup"><span data-stu-id="c52cd-142">ch07.htm#Heading121</span></span>|  
  
 <span data-ttu-id="c52cd-143">由于 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]不指定触发事件，决定哪些必需/可选规则，或应为可选。</span><span class="sxs-lookup"><span data-stu-id="c52cd-143">Since Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] does not specify trigger events, you decide what the required/optional rules, or optionality should be.</span></span> <span data-ttu-id="c52cd-144">根据本地站点的条件，您可以决定以强制实施此规则。</span><span class="sxs-lookup"><span data-stu-id="c52cd-144">Based on local site conditions, you may decide to enforce optionality rules.</span></span> <span data-ttu-id="c52cd-145">默认情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供 23 字段列出为"X"为可选字段。</span><span class="sxs-lookup"><span data-stu-id="c52cd-145">By default, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provides the 23 fields listed as "X" as optional fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c52cd-146">值"Y"是中的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="c52cd-146">Value "Y" is an error in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access database.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] <span data-ttu-id="c52cd-147">假定所有的值**Y**并**空白**都是可选的。</span><span class="sxs-lookup"><span data-stu-id="c52cd-147">assumes that all the values of **Y** and **Blank** are optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52cd-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="c52cd-148">See Also</span></span>  
 [<span data-ttu-id="c52cd-149">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="c52cd-149">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)