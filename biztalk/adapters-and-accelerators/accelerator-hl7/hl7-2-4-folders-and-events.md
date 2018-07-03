---
title: HL7 2.4 文件夹和事件 |Microsoft Docs
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
ms.assetid: c8855311-40c7-4338-ba07-5112c253fafd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62747b5f1669026b3b1eaf7b2f48f87242947890
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992351"
---
# <a name="hl7-24-folders-and-events"></a><span data-ttu-id="992c8-102">HL7 2.4 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="992c8-102">HL7 2.4 Folders and Events</span></span>
<span data-ttu-id="992c8-103">下表列出了 HL7 编码的消息的 HL7 版本 2.4 文件夹中，安装向导创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="992c8-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for HL7-encoded messages.</span></span> <span data-ttu-id="992c8-104">这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="992c8-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="992c8-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="992c8-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="992c8-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="992c8-106">Subfolder</span></span>|<span data-ttu-id="992c8-107">事件</span><span class="sxs-lookup"><span data-stu-id="992c8-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="992c8-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="992c8-108">Patient Administration</span></span>|<span data-ttu-id="992c8-109">A01 A62，K21-K24 Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="992c8-109">A01-A62, K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="992c8-110">人员管理</span><span class="sxs-lookup"><span data-stu-id="992c8-110">Personnel Management</span></span>|<span data-ttu-id="992c8-111">B01 B06，K25，Q25</span><span class="sxs-lookup"><span data-stu-id="992c8-111">B01-B06, K25,Q25</span></span>|  
|<span data-ttu-id="992c8-112">观察报告</span><span class="sxs-lookup"><span data-stu-id="992c8-112">Observation Reporting</span></span>|<span data-ttu-id="992c8-113">C01 C12，P07-P09 R01 R02，R04，R21，W01 W02</span><span class="sxs-lookup"><span data-stu-id="992c8-113">C01-C12, P07-P09, R01-R02,R04, R21, W01-W02</span></span>|  
|<span data-ttu-id="992c8-114">患者的引用</span><span class="sxs-lookup"><span data-stu-id="992c8-114">Patient Referral</span></span>|<span data-ttu-id="992c8-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="992c8-115">I01-I15</span></span>|  
|<span data-ttu-id="992c8-116">查询</span><span class="sxs-lookup"><span data-stu-id="992c8-116">Query</span></span>|<span data-ttu-id="992c8-117">J01、 J02、 K11、 K13、 K15、 Q01 Q05、 Q07 Q09、 Q11、 Q13、 Q15 Q17、 R07 R09、 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="992c8-117">J01,J02,K11,K13,K15,  Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="992c8-118">主文件</span><span class="sxs-lookup"><span data-stu-id="992c8-118">Master Files</span></span>|<span data-ttu-id="992c8-119">M01 M12 MFA</span><span class="sxs-lookup"><span data-stu-id="992c8-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="992c8-120">订单录入</span><span class="sxs-lookup"><span data-stu-id="992c8-120">Order Entry</span></span>|<span data-ttu-id="992c8-121">O01 O22、 Q06、 Q26 Q30、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04、 Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="992c8-121">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73- Z74</span></span>|  
|<span data-ttu-id="992c8-122">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="992c8-122">Application Management</span></span>|<span data-ttu-id="992c8-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="992c8-123">N01-N02</span></span>|  
|<span data-ttu-id="992c8-124">财务管理</span><span class="sxs-lookup"><span data-stu-id="992c8-124">Financial Management</span></span>|<span data-ttu-id="992c8-125">P01 P06 P10</span><span class="sxs-lookup"><span data-stu-id="992c8-125">P01-P06, P10</span></span>|  
|<span data-ttu-id="992c8-126">病人护理</span><span class="sxs-lookup"><span data-stu-id="992c8-126">Patient Care</span></span>|<span data-ttu-id="992c8-127">PC1 PCH，PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="992c8-127">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="992c8-128">计划</span><span class="sxs-lookup"><span data-stu-id="992c8-128">Scheduling</span></span>|<span data-ttu-id="992c8-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="992c8-129">S01-S26</span></span>|  
|<span data-ttu-id="992c8-130">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="992c8-130">Medical Records/Information Management</span></span>|<span data-ttu-id="992c8-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="992c8-131">T01-T12</span></span>|  
|<span data-ttu-id="992c8-132">临床实验室自动化</span><span class="sxs-lookup"><span data-stu-id="992c8-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="992c8-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="992c8-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="992c8-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="992c8-134">See Also</span></span>  
 <span data-ttu-id="992c8-135">[HL7 2.X 子文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="992c8-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="992c8-136">[HL7 2.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="992c8-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="992c8-137">[HL7 2.2 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="992c8-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="992c8-138">[HL7 2.3 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="992c8-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="992c8-139">[HL7 2.3.1 文件夹和事件](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="992c8-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 [<span data-ttu-id="992c8-140">HL7 2.5 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="992c8-140">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)