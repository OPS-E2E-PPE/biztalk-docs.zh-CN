---
title: "HL7 2.4 文件夹和事件 |Microsoft 文档"
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
ms.assetid: c8855311-40c7-4338-ba07-5112c253fafd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9196b0b69eb3730de8ad3ef383a1cde8564e5002
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-24-folders-and-events"></a><span data-ttu-id="1dafa-102">HL7 2.4 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="1dafa-102">HL7 2.4 Folders and Events</span></span>
<span data-ttu-id="1dafa-103">下表列出由安装向导在 HL7 编码消息的 HL7 版本 2.4 文件夹内创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="1dafa-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for HL7-encoded messages.</span></span> <span data-ttu-id="1dafa-104">这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="1dafa-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="1dafa-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="1dafa-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="1dafa-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="1dafa-106">Subfolder</span></span>|<span data-ttu-id="1dafa-107">事件</span><span class="sxs-lookup"><span data-stu-id="1dafa-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="1dafa-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="1dafa-108">Patient Administration</span></span>|<span data-ttu-id="1dafa-109">A01 A62，K21 K24，Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="1dafa-109">A01-A62, K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="1dafa-110">人员管理</span><span class="sxs-lookup"><span data-stu-id="1dafa-110">Personnel Management</span></span>|<span data-ttu-id="1dafa-111">B01 B06，K25，Q25</span><span class="sxs-lookup"><span data-stu-id="1dafa-111">B01-B06, K25,Q25</span></span>|  
|<span data-ttu-id="1dafa-112">观察 Reporting</span><span class="sxs-lookup"><span data-stu-id="1dafa-112">Observation Reporting</span></span>|<span data-ttu-id="1dafa-113">C01 C12，P07 P09，R01 R02，R04，R21，W01 W02</span><span class="sxs-lookup"><span data-stu-id="1dafa-113">C01-C12, P07-P09, R01-R02,R04, R21, W01-W02</span></span>|  
|<span data-ttu-id="1dafa-114">患者的引用</span><span class="sxs-lookup"><span data-stu-id="1dafa-114">Patient Referral</span></span>|<span data-ttu-id="1dafa-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="1dafa-115">I01-I15</span></span>|  
|<span data-ttu-id="1dafa-116">Query</span><span class="sxs-lookup"><span data-stu-id="1dafa-116">Query</span></span>|<span data-ttu-id="1dafa-117">J01、 J02、 K11、 K13、 K15、 Q01 Q05、 Q07 Q09、 Q11、 Q13、 Q15 Q17、 R07 R09、 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="1dafa-117">J01,J02,K11,K13,K15,  Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="1dafa-118">主文件</span><span class="sxs-lookup"><span data-stu-id="1dafa-118">Master Files</span></span>|<span data-ttu-id="1dafa-119">M01 M12 MFA</span><span class="sxs-lookup"><span data-stu-id="1dafa-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="1dafa-120">订单条目</span><span class="sxs-lookup"><span data-stu-id="1dafa-120">Order Entry</span></span>|<span data-ttu-id="1dafa-121">O01 O22、 Q06、 Q26 Q30、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04、 Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="1dafa-121">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73- Z74</span></span>|  
|<span data-ttu-id="1dafa-122">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="1dafa-122">Application Management</span></span>|<span data-ttu-id="1dafa-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="1dafa-123">N01-N02</span></span>|  
|<span data-ttu-id="1dafa-124">财务管理</span><span class="sxs-lookup"><span data-stu-id="1dafa-124">Financial Management</span></span>|<span data-ttu-id="1dafa-125">P01 P06 P10</span><span class="sxs-lookup"><span data-stu-id="1dafa-125">P01-P06, P10</span></span>|  
|<span data-ttu-id="1dafa-126">患者治疗</span><span class="sxs-lookup"><span data-stu-id="1dafa-126">Patient Care</span></span>|<span data-ttu-id="1dafa-127">PC1 PCH，PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="1dafa-127">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="1dafa-128">计划</span><span class="sxs-lookup"><span data-stu-id="1dafa-128">Scheduling</span></span>|<span data-ttu-id="1dafa-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="1dafa-129">S01-S26</span></span>|  
|<span data-ttu-id="1dafa-130">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="1dafa-130">Medical Records/Information Management</span></span>|<span data-ttu-id="1dafa-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="1dafa-131">T01-T12</span></span>|  
|<span data-ttu-id="1dafa-132">临床实验室自动化</span><span class="sxs-lookup"><span data-stu-id="1dafa-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="1dafa-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="1dafa-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dafa-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dafa-134">See Also</span></span>  
 <span data-ttu-id="1dafa-135">[HL7 2.X 子文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="1dafa-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="1dafa-136">[HL7 2.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="1dafa-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="1dafa-137">[HL7 2.2 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="1dafa-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="1dafa-138">[HL7 2.3 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="1dafa-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="1dafa-139">[HL7 2.3.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="1dafa-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 [<span data-ttu-id="1dafa-140">HL7 2.5 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="1dafa-140">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)