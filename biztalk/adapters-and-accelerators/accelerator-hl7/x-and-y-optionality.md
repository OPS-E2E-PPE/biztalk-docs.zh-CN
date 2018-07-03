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
ms.openlocfilehash: aed5b87216bd2d8e127ff032e3773b3f740835c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981518"
---
# <a name="39x39-and-39y39-optionality"></a><span data-ttu-id="799b0-102">&#39;X&#39;和&#39;Y&#39;可选性</span><span class="sxs-lookup"><span data-stu-id="799b0-102">&#39;X&#39; and &#39;Y&#39; Optionality</span></span>
<span data-ttu-id="799b0-103">HL7 访问数据库中的 SegmentDataElements 表包含多个已设置为数据项 （字段）**请求/Opt = X**，这意味着 HL7 标准不会将此字段关联与此触发器事件，如中所示下表。</span><span class="sxs-lookup"><span data-stu-id="799b0-103">The SegmentDataElements table in the HL7 Access database contains several Data Items (fields) that have been set as **Req/Opt = X**, meaning that the HL7 standard does not associate this field with this trigger event, as shown in the following table.</span></span>  
  
|<span data-ttu-id="799b0-104">段</span><span class="sxs-lookup"><span data-stu-id="799b0-104">Segment</span></span>|<span data-ttu-id="799b0-105">版本</span><span class="sxs-lookup"><span data-stu-id="799b0-105">Version</span></span>|<span data-ttu-id="799b0-106">章节</span><span class="sxs-lookup"><span data-stu-id="799b0-106">Chapter</span></span>|<span data-ttu-id="799b0-107">数据项</span><span class="sxs-lookup"><span data-stu-id="799b0-107">Data Item</span></span>|<span data-ttu-id="799b0-108">所需 /</span><span class="sxs-lookup"><span data-stu-id="799b0-108">Required/</span></span><br /><br /> <span data-ttu-id="799b0-109">可选</span><span class="sxs-lookup"><span data-stu-id="799b0-109">Optional</span></span>|<span data-ttu-id="799b0-110">报告</span><span class="sxs-lookup"><span data-stu-id="799b0-110">Report</span></span>|<span data-ttu-id="799b0-111">Number</span><span class="sxs-lookup"><span data-stu-id="799b0-111">Number</span></span>|<span data-ttu-id="799b0-112">HTML 标准</span><span class="sxs-lookup"><span data-stu-id="799b0-112">HTML Standard</span></span>|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|<span data-ttu-id="799b0-113">OBX</span><span class="sxs-lookup"><span data-stu-id="799b0-113">OBX</span></span>|<span data-ttu-id="799b0-114">2.4</span><span class="sxs-lookup"><span data-stu-id="799b0-114">2.4</span></span>|<span data-ttu-id="799b0-115">7.4.2.9</span><span class="sxs-lookup"><span data-stu-id="799b0-115">7.4.2.9</span></span>|<span data-ttu-id="799b0-116">00577</span><span class="sxs-lookup"><span data-stu-id="799b0-116">00577</span></span>|<span data-ttu-id="799b0-117">X</span><span class="sxs-lookup"><span data-stu-id="799b0-117">X</span></span>|<span data-ttu-id="799b0-118">是</span><span class="sxs-lookup"><span data-stu-id="799b0-118">Y</span></span>|<span data-ttu-id="799b0-119">5</span><span class="sxs-lookup"><span data-stu-id="799b0-119">5</span></span>|<span data-ttu-id="799b0-120">ch07.htm#Heading113</span><span class="sxs-lookup"><span data-stu-id="799b0-120">ch07.htm#Heading113</span></span>|  
|<span data-ttu-id="799b0-121">OBX</span><span class="sxs-lookup"><span data-stu-id="799b0-121">OBX</span></span>|<span data-ttu-id="799b0-122">2.4</span><span class="sxs-lookup"><span data-stu-id="799b0-122">2.4</span></span>|<span data-ttu-id="799b0-123">7.4.2.8</span><span class="sxs-lookup"><span data-stu-id="799b0-123">7.4.2.8</span></span>|<span data-ttu-id="799b0-124">00576</span><span class="sxs-lookup"><span data-stu-id="799b0-124">00576</span></span>|<span data-ttu-id="799b0-125">X</span><span class="sxs-lookup"><span data-stu-id="799b0-125">X</span></span>||<span data-ttu-id="799b0-126">0</span><span class="sxs-lookup"><span data-stu-id="799b0-126">0</span></span>|<span data-ttu-id="799b0-127">ch07.htm#Heading112</span><span class="sxs-lookup"><span data-stu-id="799b0-127">ch07.htm#Heading112</span></span>|  
|<span data-ttu-id="799b0-128">OBX</span><span class="sxs-lookup"><span data-stu-id="799b0-128">OBX</span></span>|<span data-ttu-id="799b0-129">2.4</span><span class="sxs-lookup"><span data-stu-id="799b0-129">2.4</span></span>|<span data-ttu-id="799b0-130">7.4.2.6</span><span class="sxs-lookup"><span data-stu-id="799b0-130">7.4.2.6</span></span>|<span data-ttu-id="799b0-131">00574</span><span class="sxs-lookup"><span data-stu-id="799b0-131">00574</span></span>|<span data-ttu-id="799b0-132">X</span><span class="sxs-lookup"><span data-stu-id="799b0-132">X</span></span>||<span data-ttu-id="799b0-133">0</span><span class="sxs-lookup"><span data-stu-id="799b0-133">0</span></span>|<span data-ttu-id="799b0-134">ch07.htm#Heading107</span><span class="sxs-lookup"><span data-stu-id="799b0-134">ch07.htm#Heading107</span></span>|  
|<span data-ttu-id="799b0-135">OBX</span><span class="sxs-lookup"><span data-stu-id="799b0-135">OBX</span></span>|<span data-ttu-id="799b0-136">2.4</span><span class="sxs-lookup"><span data-stu-id="799b0-136">2.4</span></span>|<span data-ttu-id="799b0-137">7.4.2.17</span><span class="sxs-lookup"><span data-stu-id="799b0-137">7.4.2.17</span></span>|<span data-ttu-id="799b0-138">00936</span><span class="sxs-lookup"><span data-stu-id="799b0-138">00936</span></span>|<span data-ttu-id="799b0-139">X</span><span class="sxs-lookup"><span data-stu-id="799b0-139">X</span></span>|<span data-ttu-id="799b0-140">是</span><span class="sxs-lookup"><span data-stu-id="799b0-140">Y</span></span>|<span data-ttu-id="799b0-141">0</span><span class="sxs-lookup"><span data-stu-id="799b0-141">0</span></span>|<span data-ttu-id="799b0-142">ch07.htm#Heading121</span><span class="sxs-lookup"><span data-stu-id="799b0-142">ch07.htm#Heading121</span></span>|  
  
 <span data-ttu-id="799b0-143">由于 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]不指定触发事件，决定哪些必需/可选规则，或应为可选。</span><span class="sxs-lookup"><span data-stu-id="799b0-143">Since Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] does not specify trigger events, you decide what the required/optional rules, or optionality should be.</span></span> <span data-ttu-id="799b0-144">根据本地站点的条件，您可以决定以强制实施此规则。</span><span class="sxs-lookup"><span data-stu-id="799b0-144">Based on local site conditions, you may decide to enforce optionality rules.</span></span> <span data-ttu-id="799b0-145">默认情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供 23 字段列出为"X"为可选字段。</span><span class="sxs-lookup"><span data-stu-id="799b0-145">By default, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provides the 23 fields listed as "X" as optional fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="799b0-146">值"Y"是中的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="799b0-146">Value "Y" is an error in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access database.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="799b0-147"> 假定所有的值**Y**并**空白**都是可选的。</span><span class="sxs-lookup"><span data-stu-id="799b0-147"> assumes that all the values of **Y** and **Blank** are optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799b0-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="799b0-148">See Also</span></span>  
 [<span data-ttu-id="799b0-149">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="799b0-149">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)