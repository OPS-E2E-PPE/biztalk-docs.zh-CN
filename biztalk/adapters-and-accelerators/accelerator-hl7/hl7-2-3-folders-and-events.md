---
title: HL7 2.3 文件夹和事件 |Microsoft Docs
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
ms.openlocfilehash: 6f5df624fa1de08844fb1076adbc5e6d2ff08720
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992046"
---
# <a name="hl7-23-folders-and-events"></a><span data-ttu-id="b2199-102">HL7 2.3 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="b2199-102">HL7 2.3 Folders and Events</span></span>
<span data-ttu-id="b2199-103">下表列出了 HL7 编码的消息的 HL7 2.3 版文件夹中，安装向导创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2199-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3 folder for HL7-encoded messages.</span></span> <span data-ttu-id="b2199-104">这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="b2199-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="b2199-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b2199-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="b2199-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="b2199-106">Subfolder</span></span>|<span data-ttu-id="b2199-107">事件</span><span class="sxs-lookup"><span data-stu-id="b2199-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="b2199-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="b2199-108">Patient Administration</span></span>|<span data-ttu-id="b2199-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="b2199-109">A01-A51</span></span>|  
|<span data-ttu-id="b2199-110">观察报告</span><span class="sxs-lookup"><span data-stu-id="b2199-110">Observation Reporting</span></span>|<span data-ttu-id="b2199-111">C01 C12，P07-P09 R01-R06 W01 W02</span><span class="sxs-lookup"><span data-stu-id="b2199-111">C01-C12, P07-P09, R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="b2199-112">患者的引用</span><span class="sxs-lookup"><span data-stu-id="b2199-112">Patient Referral</span></span>|<span data-ttu-id="b2199-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="b2199-113">I01-I15</span></span>|  
|<span data-ttu-id="b2199-114">主文件</span><span class="sxs-lookup"><span data-stu-id="b2199-114">Master File</span></span>|<span data-ttu-id="b2199-115">M01 M11</span><span class="sxs-lookup"><span data-stu-id="b2199-115">M01-M11</span></span>|  
|<span data-ttu-id="b2199-116">订单录入</span><span class="sxs-lookup"><span data-stu-id="b2199-116">Order Entry</span></span>|<span data-ttu-id="b2199-117">O01 O02、 Q06、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04</span><span class="sxs-lookup"><span data-stu-id="b2199-117">O01-O02,Q06, RAR,RDR,RER,RGR,ROR, V01-V04</span></span>|  
|<span data-ttu-id="b2199-118">财务管理</span><span class="sxs-lookup"><span data-stu-id="b2199-118">Financial Management</span></span>|<span data-ttu-id="b2199-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="b2199-119">P01-P06</span></span>|  
|<span data-ttu-id="b2199-120">病人护理</span><span class="sxs-lookup"><span data-stu-id="b2199-120">Patient Care</span></span>|<span data-ttu-id="b2199-121">PC1 PCH，PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="b2199-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="b2199-122">查询</span><span class="sxs-lookup"><span data-stu-id="b2199-122">Query</span></span>|<span data-ttu-id="b2199-123">CNQ，Q01-Q03 Q05</span><span class="sxs-lookup"><span data-stu-id="b2199-123">CNQ, Q01-Q03, Q05</span></span>|  
|<span data-ttu-id="b2199-124">计划</span><span class="sxs-lookup"><span data-stu-id="b2199-124">Scheduling</span></span>|<span data-ttu-id="b2199-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="b2199-125">S01-S26</span></span>|  
|<span data-ttu-id="b2199-126">医疗记录和信息管理</span><span class="sxs-lookup"><span data-stu-id="b2199-126">Medical Records and Information Management</span></span>|<span data-ttu-id="b2199-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="b2199-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2199-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2199-128">See Also</span></span>  
 <span data-ttu-id="b2199-129">[HL7 2.X 子文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b2199-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="b2199-130">[HL7 2.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b2199-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="b2199-131">[HL7 2.2 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b2199-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="b2199-132">[HL7 2.3.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b2199-132">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="b2199-133">[HL7 2.4 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b2199-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="b2199-134">HL7 2.5 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="b2199-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)