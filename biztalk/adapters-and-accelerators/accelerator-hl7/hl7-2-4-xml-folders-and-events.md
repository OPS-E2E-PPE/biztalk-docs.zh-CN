---
title: HL7 2.4 XML 文件夹和事件 |Microsoft 文档
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
ms.openlocfilehash: 10c9445a1d5c7978b526fd0347dc6defa3214640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204805"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="259f6-102">HL7 2.4 XML 文件夹和事件</span><span class="sxs-lookup"><span data-stu-id="259f6-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="259f6-103">下表列出由 XML 编码消息的 HL7 版本 2.4 文件夹中安装程序向导创建的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="259f6-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="259f6-104">这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。</span><span class="sxs-lookup"><span data-stu-id="259f6-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="259f6-105">子文件夹名称描述的这些架构支持的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="259f6-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="259f6-106">子文件夹</span><span class="sxs-lookup"><span data-stu-id="259f6-106">Sub folder</span></span>|<span data-ttu-id="259f6-107">事件</span><span class="sxs-lookup"><span data-stu-id="259f6-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="259f6-108">患者管理</span><span class="sxs-lookup"><span data-stu-id="259f6-108">Patient Administration</span></span>|<span data-ttu-id="259f6-109">A01 A62、 K21、 K22、 K23、 K24、 Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="259f6-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="259f6-110">订单条目</span><span class="sxs-lookup"><span data-stu-id="259f6-110">Order Entry</span></span>|<span data-ttu-id="259f6-111">O01 O22、 Q06、 Q26 Q30、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04、 Z73、 Z74</span><span class="sxs-lookup"><span data-stu-id="259f6-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="259f6-112">Query</span><span class="sxs-lookup"><span data-stu-id="259f6-112">Query</span></span>|<span data-ttu-id="259f6-113">J01、 J02、 K11、 K13、 K15、 Q01 Q05、 Q07 Q09、 Q11、 Q13、 Q15 Q17、 R07 R09、 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="259f6-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="259f6-114">财务管理</span><span class="sxs-lookup"><span data-stu-id="259f6-114">Financial Management</span></span>|<span data-ttu-id="259f6-115">P01 ~ P06、 P10</span><span class="sxs-lookup"><span data-stu-id="259f6-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="259f6-116">观察 Reporting</span><span class="sxs-lookup"><span data-stu-id="259f6-116">Observation Reporting</span></span>|<span data-ttu-id="259f6-117">C01 C12、 P07、 P08、 P09、 R01、 R02、 R04、 R21、 W01、 W02</span><span class="sxs-lookup"><span data-stu-id="259f6-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="259f6-118">主文件</span><span class="sxs-lookup"><span data-stu-id="259f6-118">Master Files</span></span>|<span data-ttu-id="259f6-119">M01 M12 MFA</span><span class="sxs-lookup"><span data-stu-id="259f6-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="259f6-120">医疗记录/信息管理</span><span class="sxs-lookup"><span data-stu-id="259f6-120">Medical Records/Information Management</span></span>|<span data-ttu-id="259f6-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="259f6-121">T01-T12</span></span>|  
|<span data-ttu-id="259f6-122">计划</span><span class="sxs-lookup"><span data-stu-id="259f6-122">Scheduling</span></span>|<span data-ttu-id="259f6-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="259f6-123">S01-S26</span></span>|  
|<span data-ttu-id="259f6-124">患者的引用</span><span class="sxs-lookup"><span data-stu-id="259f6-124">Patient Referral</span></span>|<span data-ttu-id="259f6-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="259f6-125">I01-I15</span></span>|  
|<span data-ttu-id="259f6-126">患者治疗</span><span class="sxs-lookup"><span data-stu-id="259f6-126">Patient Care</span></span>|<span data-ttu-id="259f6-127">PC1 PCH，PCJ，PCK PCL</span><span class="sxs-lookup"><span data-stu-id="259f6-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="259f6-128">临床实验室自动化</span><span class="sxs-lookup"><span data-stu-id="259f6-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="259f6-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="259f6-129">U01-U13</span></span>|  
|<span data-ttu-id="259f6-130">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="259f6-130">Application Management</span></span>|<span data-ttu-id="259f6-131">N01 N02</span><span class="sxs-lookup"><span data-stu-id="259f6-131">N01,N02</span></span>|  
|<span data-ttu-id="259f6-132">人员管理</span><span class="sxs-lookup"><span data-stu-id="259f6-132">Personnel Management</span></span>|<span data-ttu-id="259f6-133">B01 B06，K25，Q25</span><span class="sxs-lookup"><span data-stu-id="259f6-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="259f6-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="259f6-134">See Also</span></span>  
 [<span data-ttu-id="259f6-135">使用 HL7 2.XML 架构</span><span class="sxs-lookup"><span data-stu-id="259f6-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)