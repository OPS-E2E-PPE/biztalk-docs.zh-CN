---
title: HL7 2.4 XML 文件夹和事件 |Microsoft Docs
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
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7665a5101f5b49abd9ba087bd07cf799384c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993286"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="b0e22-102">HL7 2.4 XML 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="b0e22-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="b0e22-103">下表列出了安装程序向导 XML 编码的消息的 HL7 版本 2.4 文件夹中创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0e22-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="b0e22-104">这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="b0e22-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="b0e22-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0e22-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="b0e22-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="b0e22-106">Sub folder</span></span>|<span data-ttu-id="b0e22-107">事件</span><span class="sxs-lookup"><span data-stu-id="b0e22-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="b0e22-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="b0e22-108">Patient Administration</span></span>|<span data-ttu-id="b0e22-109">A01 A62、 K21、 K22、 K23、 K24、 Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="b0e22-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="b0e22-110">订单录入</span><span class="sxs-lookup"><span data-stu-id="b0e22-110">Order Entry</span></span>|<span data-ttu-id="b0e22-111">O01 O22、 Q06、 Q26 Q30、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04、 Z73、 Z74</span><span class="sxs-lookup"><span data-stu-id="b0e22-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="b0e22-112">查询</span><span class="sxs-lookup"><span data-stu-id="b0e22-112">Query</span></span>|<span data-ttu-id="b0e22-113">J01、 J02、 K11、 K13、 K15、 Q01 Q05、 Q07 Q09、 Q11、 Q13、 Q15 Q17、 R07 R09、 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="b0e22-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="b0e22-114">财务管理</span><span class="sxs-lookup"><span data-stu-id="b0e22-114">Financial Management</span></span>|<span data-ttu-id="b0e22-115">P01 ~ P06、 P10</span><span class="sxs-lookup"><span data-stu-id="b0e22-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="b0e22-116">观察报告</span><span class="sxs-lookup"><span data-stu-id="b0e22-116">Observation Reporting</span></span>|<span data-ttu-id="b0e22-117">C01 C12、 P07、 P08、 P09、 R01、 R02、 R04、 R21、 W01、 W02</span><span class="sxs-lookup"><span data-stu-id="b0e22-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="b0e22-118">主文件</span><span class="sxs-lookup"><span data-stu-id="b0e22-118">Master Files</span></span>|<span data-ttu-id="b0e22-119">M01 M12 MFA</span><span class="sxs-lookup"><span data-stu-id="b0e22-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="b0e22-120">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="b0e22-120">Medical Records/Information Management</span></span>|<span data-ttu-id="b0e22-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="b0e22-121">T01-T12</span></span>|  
|<span data-ttu-id="b0e22-122">计划</span><span class="sxs-lookup"><span data-stu-id="b0e22-122">Scheduling</span></span>|<span data-ttu-id="b0e22-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="b0e22-123">S01-S26</span></span>|  
|<span data-ttu-id="b0e22-124">患者的引用</span><span class="sxs-lookup"><span data-stu-id="b0e22-124">Patient Referral</span></span>|<span data-ttu-id="b0e22-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="b0e22-125">I01-I15</span></span>|  
|<span data-ttu-id="b0e22-126">病人护理</span><span class="sxs-lookup"><span data-stu-id="b0e22-126">Patient Care</span></span>|<span data-ttu-id="b0e22-127">PC1 PCH，PCJ，这是 PCL</span><span class="sxs-lookup"><span data-stu-id="b0e22-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="b0e22-128">临床实验室自动化</span><span class="sxs-lookup"><span data-stu-id="b0e22-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="b0e22-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="b0e22-129">U01-U13</span></span>|  
|<span data-ttu-id="b0e22-130">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="b0e22-130">Application Management</span></span>|<span data-ttu-id="b0e22-131">N01 N02</span><span class="sxs-lookup"><span data-stu-id="b0e22-131">N01,N02</span></span>|  
|<span data-ttu-id="b0e22-132">人员管理</span><span class="sxs-lookup"><span data-stu-id="b0e22-132">Personnel Management</span></span>|<span data-ttu-id="b0e22-133">B01 B06，K25，Q25</span><span class="sxs-lookup"><span data-stu-id="b0e22-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0e22-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e22-134">See Also</span></span>  
 [<span data-ttu-id="b0e22-135">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="b0e22-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)