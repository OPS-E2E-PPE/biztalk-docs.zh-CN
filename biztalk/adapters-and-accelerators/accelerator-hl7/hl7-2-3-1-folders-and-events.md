---
title: "HL7 2.3.1 文件夹和事件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: 5cab1b7e-fdce-4b4b-bbd6-1da67fcf6a74
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad51a024348c12c4097af29419698ced7c9c0c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-231-folders-and-events"></a><span data-ttu-id="96738-102">HL7 2.3.1 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="96738-102">HL7 2.3.1 Folders and Events</span></span>
<span data-ttu-id="96738-103">下表列出由安装向导在 HL7 编码消息的 HL7 版本 2.3.1 文件夹内创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="96738-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for HL7-encoded messages.</span></span> <span data-ttu-id="96738-104">这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="96738-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="96738-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="96738-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="96738-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="96738-106">Subfolder</span></span>|<span data-ttu-id="96738-107">事件</span><span class="sxs-lookup"><span data-stu-id="96738-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="96738-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="96738-108">Patient Administration</span></span>|<span data-ttu-id="96738-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="96738-109">A01-A51</span></span>|  
|<span data-ttu-id="96738-110">观察 Reporting</span><span class="sxs-lookup"><span data-stu-id="96738-110">Observation Reporting</span></span>|<span data-ttu-id="96738-111">C01 C12，P06 P09，R01 R06，W01 W02</span><span class="sxs-lookup"><span data-stu-id="96738-111">C01-C12,P06-P09,R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="96738-112">患者的引用</span><span class="sxs-lookup"><span data-stu-id="96738-112">Patient Referral</span></span>|<span data-ttu-id="96738-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="96738-113">I01-I15</span></span>|  
|<span data-ttu-id="96738-114">主文件</span><span class="sxs-lookup"><span data-stu-id="96738-114">Master Files</span></span>|<span data-ttu-id="96738-115">M01 M11 MFA</span><span class="sxs-lookup"><span data-stu-id="96738-115">M01-M11, MFA</span></span>|  
|<span data-ttu-id="96738-116">订单条目</span><span class="sxs-lookup"><span data-stu-id="96738-116">Order Entry</span></span>|<span data-ttu-id="96738-117">O01 O02、 Q06、 R0R、 RAR、 RDR、 RER、 RGR、 V01 V04</span><span class="sxs-lookup"><span data-stu-id="96738-117">O01-O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="96738-118">财务管理</span><span class="sxs-lookup"><span data-stu-id="96738-118">Financial Management</span></span>|<span data-ttu-id="96738-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="96738-119">P01-P06</span></span>|  
|<span data-ttu-id="96738-120">患者治疗</span><span class="sxs-lookup"><span data-stu-id="96738-120">Patient Care</span></span>|<span data-ttu-id="96738-121">PC1 PCH，PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="96738-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="96738-122">Query</span><span class="sxs-lookup"><span data-stu-id="96738-122">Query</span></span>|<span data-ttu-id="96738-123">CNQ，Q01 Q05，Q07 Q09，R07 R09</span><span class="sxs-lookup"><span data-stu-id="96738-123">CNQ, Q01-Q05, Q07-Q09, R07-R09</span></span>|  
|<span data-ttu-id="96738-124">计划</span><span class="sxs-lookup"><span data-stu-id="96738-124">Schedule</span></span>|<span data-ttu-id="96738-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="96738-125">S01-S26</span></span>|  
|<span data-ttu-id="96738-126">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="96738-126">Medical Records/Information Management</span></span>|<span data-ttu-id="96738-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="96738-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96738-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96738-128">See Also</span></span>  
 <span data-ttu-id="96738-129">[HL7 2.X 子文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="96738-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="96738-130">[HL7 2.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="96738-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="96738-131">[HL7 2.2 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="96738-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="96738-132">[HL7 2.3 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="96738-132">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="96738-133">[HL7 2.4 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="96738-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="96738-134">HL7 2.5 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="96738-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)