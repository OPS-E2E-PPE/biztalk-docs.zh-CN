---
title: "HL7 2.3.1 XML 文件夹和事件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-231-xml-folders-and-events"></a><span data-ttu-id="649b3-102">HL7 2.3.1 XML 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="649b3-102">HL7 2.3.1 XML Folders and Events</span></span>
<span data-ttu-id="649b3-103">下表列出由 XML 编码消息的 HL7 版本 2.3.1 文件夹中安装程序向导创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="649b3-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for XML-encoded messages.</span></span> <span data-ttu-id="649b3-104">这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="649b3-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="649b3-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="649b3-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="649b3-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="649b3-106">Subfolder</span></span>|<span data-ttu-id="649b3-107">事件</span><span class="sxs-lookup"><span data-stu-id="649b3-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="649b3-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="649b3-108">Patient Administration</span></span>|<span data-ttu-id="649b3-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="649b3-109">A01-A51</span></span>|  
|<span data-ttu-id="649b3-110">订单条目</span><span class="sxs-lookup"><span data-stu-id="649b3-110">Order Entry</span></span>|<span data-ttu-id="649b3-111">O01、 O02、 Q06、 R0R、 RAR、 RDR、 RER、 RGR、 V01 V04</span><span class="sxs-lookup"><span data-stu-id="649b3-111">O01,O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="649b3-112">Query</span><span class="sxs-lookup"><span data-stu-id="649b3-112">Query</span></span>|<span data-ttu-id="649b3-113">CNQ，Q01 Q03，Q05，Q07 Q09，R07，R08，R09</span><span class="sxs-lookup"><span data-stu-id="649b3-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07,R08,R09</span></span>|  
|<span data-ttu-id="649b3-114">财务管理</span><span class="sxs-lookup"><span data-stu-id="649b3-114">Financial Management</span></span>|<span data-ttu-id="649b3-115">P01 P06</span><span class="sxs-lookup"><span data-stu-id="649b3-115">P01-P06</span></span>|  
|<span data-ttu-id="649b3-116">观察 Reporting</span><span class="sxs-lookup"><span data-stu-id="649b3-116">Observation Reporting</span></span>|<span data-ttu-id="649b3-117">C01 C12、 P06、 P07、 P09、 R01 R06、 W01、 W02</span><span class="sxs-lookup"><span data-stu-id="649b3-117">C01-C12,P06,P07,P09,R01-R06, W01,W02</span></span>|  
|<span data-ttu-id="649b3-118">主文件</span><span class="sxs-lookup"><span data-stu-id="649b3-118">Master Files</span></span>|<span data-ttu-id="649b3-119">M01 M11 MFA</span><span class="sxs-lookup"><span data-stu-id="649b3-119">M01-M11, MFA</span></span>|  
|<span data-ttu-id="649b3-120">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="649b3-120">Medical Records/Information Management</span></span>|<span data-ttu-id="649b3-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="649b3-121">T01-T12</span></span>|  
|<span data-ttu-id="649b3-122">计划</span><span class="sxs-lookup"><span data-stu-id="649b3-122">Schedule</span></span>|<span data-ttu-id="649b3-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="649b3-123">S01-S26</span></span>|  
|<span data-ttu-id="649b3-124">患者的引用</span><span class="sxs-lookup"><span data-stu-id="649b3-124">Patient Referral</span></span>|<span data-ttu-id="649b3-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="649b3-125">I01-I15</span></span>|  
|<span data-ttu-id="649b3-126">患者治疗</span><span class="sxs-lookup"><span data-stu-id="649b3-126">Patient Care</span></span>|<span data-ttu-id="649b3-127">PC1 PCH，PCJ，PCK PCL</span><span class="sxs-lookup"><span data-stu-id="649b3-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="649b3-128">网络管理</span><span class="sxs-lookup"><span data-stu-id="649b3-128">Network Management</span></span>|<span data-ttu-id="649b3-129">N01 N02</span><span class="sxs-lookup"><span data-stu-id="649b3-129">N01,N02</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="649b3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="649b3-130">See Also</span></span>  
 [<span data-ttu-id="649b3-131">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="649b3-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)