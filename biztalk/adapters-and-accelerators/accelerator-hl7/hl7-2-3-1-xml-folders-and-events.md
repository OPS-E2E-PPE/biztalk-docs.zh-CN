---
title: HL7 2.3.1 XML 文件夹和事件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b98dbc5b0b234d56984fc606d05dffcab7e6ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271174"
---
# <a name="hl7-231-xml-folders-and-events"></a><span data-ttu-id="68779-102">HL7 2.3.1 XML 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="68779-102">HL7 2.3.1 XML Folders and Events</span></span>
<span data-ttu-id="68779-103">下表列出了安装程序向导 XML 编码的消息的 HL7 2.3.1 文件夹中创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="68779-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for XML-encoded messages.</span></span> <span data-ttu-id="68779-104">这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="68779-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="68779-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="68779-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="68779-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="68779-106">Subfolder</span></span>|<span data-ttu-id="68779-107">事件</span><span class="sxs-lookup"><span data-stu-id="68779-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="68779-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="68779-108">Patient Administration</span></span>|<span data-ttu-id="68779-109">A01-A51</span><span class="sxs-lookup"><span data-stu-id="68779-109">A01-A51</span></span>|  
|<span data-ttu-id="68779-110">订单录入</span><span class="sxs-lookup"><span data-stu-id="68779-110">Order Entry</span></span>|<span data-ttu-id="68779-111">O01、 O02、 Q06、 R0R、 RAR、 RDR、 RER、 RGR、 V01 V04</span><span class="sxs-lookup"><span data-stu-id="68779-111">O01,O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="68779-112">查询</span><span class="sxs-lookup"><span data-stu-id="68779-112">Query</span></span>|<span data-ttu-id="68779-113">CNQ，Q01-Q03 Q05，Q07-Q09 R07，R08，R09</span><span class="sxs-lookup"><span data-stu-id="68779-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07,R08,R09</span></span>|  
|<span data-ttu-id="68779-114">财务管理</span><span class="sxs-lookup"><span data-stu-id="68779-114">Financial Management</span></span>|<span data-ttu-id="68779-115">P01-P06</span><span class="sxs-lookup"><span data-stu-id="68779-115">P01-P06</span></span>|  
|<span data-ttu-id="68779-116">观察报告</span><span class="sxs-lookup"><span data-stu-id="68779-116">Observation Reporting</span></span>|<span data-ttu-id="68779-117">C01 C12、 P06、 P07、 P09、 R01 R06、 W01、 W02</span><span class="sxs-lookup"><span data-stu-id="68779-117">C01-C12,P06,P07,P09,R01-R06, W01,W02</span></span>|  
|<span data-ttu-id="68779-118">主文件</span><span class="sxs-lookup"><span data-stu-id="68779-118">Master Files</span></span>|<span data-ttu-id="68779-119">M01 M11 MFA</span><span class="sxs-lookup"><span data-stu-id="68779-119">M01-M11, MFA</span></span>|  
|<span data-ttu-id="68779-120">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="68779-120">Medical Records/Information Management</span></span>|<span data-ttu-id="68779-121">T01-T12</span><span class="sxs-lookup"><span data-stu-id="68779-121">T01-T12</span></span>|  
|<span data-ttu-id="68779-122">“计划”</span><span class="sxs-lookup"><span data-stu-id="68779-122">Schedule</span></span>|<span data-ttu-id="68779-123">S01-S26</span><span class="sxs-lookup"><span data-stu-id="68779-123">S01-S26</span></span>|  
|<span data-ttu-id="68779-124">患者的引用</span><span class="sxs-lookup"><span data-stu-id="68779-124">Patient Referral</span></span>|<span data-ttu-id="68779-125">I01-I15</span><span class="sxs-lookup"><span data-stu-id="68779-125">I01-I15</span></span>|  
|<span data-ttu-id="68779-126">病人护理</span><span class="sxs-lookup"><span data-stu-id="68779-126">Patient Care</span></span>|<span data-ttu-id="68779-127">PC1 PCH，PCJ，这是 PCL</span><span class="sxs-lookup"><span data-stu-id="68779-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="68779-128">网络管理</span><span class="sxs-lookup"><span data-stu-id="68779-128">Network Management</span></span>|<span data-ttu-id="68779-129">N01,N02</span><span class="sxs-lookup"><span data-stu-id="68779-129">N01,N02</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68779-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="68779-130">See Also</span></span>  
 [<span data-ttu-id="68779-131">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="68779-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)