---
title: HL7 2.3 文件夹和事件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: 555a8620-a714-4102-80ba-1424d60387bf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a396fca582defb8601bdda23280f92d0acbd90be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205205"
---
# <a name="hl7-23-folders-and-events"></a><span data-ttu-id="65adc-102">HL7 2.3 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="65adc-102">HL7 2.3 Folders and Events</span></span>
<span data-ttu-id="65adc-103">下表列出由安装向导在 HL7 编码消息的 HL7 版本 2.3 文件夹内创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="65adc-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3 folder for HL7-encoded messages.</span></span> <span data-ttu-id="65adc-104">这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="65adc-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="65adc-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="65adc-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="65adc-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="65adc-106">Subfolder</span></span>|<span data-ttu-id="65adc-107">事件</span><span class="sxs-lookup"><span data-stu-id="65adc-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="65adc-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="65adc-108">Patient Administration</span></span>|<span data-ttu-id="65adc-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="65adc-109">A01-A51</span></span>|  
|<span data-ttu-id="65adc-110">观察 Reporting</span><span class="sxs-lookup"><span data-stu-id="65adc-110">Observation Reporting</span></span>|<span data-ttu-id="65adc-111">C01 C12，P07 P09，R01 R06，W01 W02</span><span class="sxs-lookup"><span data-stu-id="65adc-111">C01-C12, P07-P09, R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="65adc-112">患者的引用</span><span class="sxs-lookup"><span data-stu-id="65adc-112">Patient Referral</span></span>|<span data-ttu-id="65adc-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="65adc-113">I01-I15</span></span>|  
|<span data-ttu-id="65adc-114">主文件</span><span class="sxs-lookup"><span data-stu-id="65adc-114">Master File</span></span>|<span data-ttu-id="65adc-115">M01 M11</span><span class="sxs-lookup"><span data-stu-id="65adc-115">M01-M11</span></span>|  
|<span data-ttu-id="65adc-116">订单条目</span><span class="sxs-lookup"><span data-stu-id="65adc-116">Order Entry</span></span>|<span data-ttu-id="65adc-117">O01 O02、 Q06、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04</span><span class="sxs-lookup"><span data-stu-id="65adc-117">O01-O02,Q06, RAR,RDR,RER,RGR,ROR, V01-V04</span></span>|  
|<span data-ttu-id="65adc-118">财务管理</span><span class="sxs-lookup"><span data-stu-id="65adc-118">Financial Management</span></span>|<span data-ttu-id="65adc-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="65adc-119">P01-P06</span></span>|  
|<span data-ttu-id="65adc-120">患者治疗</span><span class="sxs-lookup"><span data-stu-id="65adc-120">Patient Care</span></span>|<span data-ttu-id="65adc-121">PC1 PCH，PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="65adc-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="65adc-122">Query</span><span class="sxs-lookup"><span data-stu-id="65adc-122">Query</span></span>|<span data-ttu-id="65adc-123">CNQ，Q01 Q03，Q05</span><span class="sxs-lookup"><span data-stu-id="65adc-123">CNQ, Q01-Q03, Q05</span></span>|  
|<span data-ttu-id="65adc-124">计划</span><span class="sxs-lookup"><span data-stu-id="65adc-124">Scheduling</span></span>|<span data-ttu-id="65adc-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="65adc-125">S01-S26</span></span>|  
|<span data-ttu-id="65adc-126">医疗记录和信息管理</span><span class="sxs-lookup"><span data-stu-id="65adc-126">Medical Records and Information Management</span></span>|<span data-ttu-id="65adc-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="65adc-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65adc-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65adc-128">See Also</span></span>  
 <span data-ttu-id="65adc-129">[HL7 2.X 子文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="65adc-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="65adc-130">[HL7 2.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="65adc-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="65adc-131">[HL7 2.2 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="65adc-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="65adc-132">[HL7 2.3.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="65adc-132">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="65adc-133">[HL7 2.4 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="65adc-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="65adc-134">HL7 2.5 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="65adc-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)