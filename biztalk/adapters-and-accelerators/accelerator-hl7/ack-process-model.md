---
title: "ACK 进程模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846ecf4d8eee4eca0e8a75a3444a1478b7db5910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ack-process-model"></a><span data-ttu-id="d0435-102">ACK 进程模型</span><span class="sxs-lookup"><span data-stu-id="d0435-102">ACK Process Model</span></span>
<span data-ttu-id="d0435-103">下面的步骤序列描述的确认 (ACK) 进程模型：</span><span class="sxs-lookup"><span data-stu-id="d0435-103">The following sequence of steps describes the acknowledgment (ACK) process model:</span></span>  
  
1.  <span data-ttu-id="d0435-104">当许可人员登录患者许可信息到许可系统 (ADT) 时，系统将生成的触发器事件。</span><span class="sxs-lookup"><span data-stu-id="d0435-104">When the admissions personnel log patient admission information into the Admissions System (ADT), the system generates a trigger event.</span></span>  
  
2.  <span data-ttu-id="d0435-105">ADT 系统生成 HL7 编码患者注册消息 (ADT ^ A04) 并将其传递给 BizTalk 快捷键的 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="d0435-105">The ADT system generates an HL7-encoded Patient Registration message (ADT^A04) and delivers it to BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
3.  <span data-ttu-id="d0435-106">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统上 ADT 适用的 MLLP 包装 ^ A04 消息并将它路由到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="d0435-106">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system applies an MLLP wrapper on the ADT^A04 message and routes it to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
    -   <span data-ttu-id="d0435-107">预先配置的原始模式确认的要求</span><span class="sxs-lookup"><span data-stu-id="d0435-107">Requirement of 'Original Mode' Acknowledgment is preconfigured</span></span>  
  
    -   <span data-ttu-id="d0435-108">MSH 15 和 16 具有 null 值</span><span class="sxs-lookup"><span data-stu-id="d0435-108">MSH 15 and 16 have null values</span></span>  
  
4.  <span data-ttu-id="d0435-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎来验证消息，如果成功验证时，它将生成状态的 ACK 消息**MSA01 = AA**。</span><span class="sxs-lookup"><span data-stu-id="d0435-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the message and if successful validation occurs, it generates the ACK message with the status **MSA01 = AA**.</span></span>  
  
5.  <span data-ttu-id="d0435-110">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎转换 ADT ^ A04 条消息所使用 MLLP 包装器将其括起来，并将其路由到实验室信息系统 (LIS)。</span><span class="sxs-lookup"><span data-stu-id="d0435-110">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine transforms the ADT^A04 message by enclosing it with MLLP wrappers and routing it to the Lab Information System (LIS).</span></span>  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="d0435-111">以增强型模式确认预先配置</span><span class="sxs-lookup"><span data-stu-id="d0435-111"> preconfigures 'Enhanced Mode' Acknowledgment</span></span>  
  
    -   <span data-ttu-id="d0435-112">MSH 15 和 16 = AL</span><span class="sxs-lookup"><span data-stu-id="d0435-112">MSH 15 and 16 = AL</span></span>  
  
6.  <span data-ttu-id="d0435-113">LIS 接口层验证标头： 提交消息，并生成状态为接受 ACK **MSA1 = CA**。</span><span class="sxs-lookup"><span data-stu-id="d0435-113">The LIS Interface Layer validates the header by committing the message and generating an ACCEPT ACK with the status **MSA1 = CA**.</span></span> <span data-ttu-id="d0435-114">接口层将路由到 MLLP 包装的消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="d0435-114">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
7.  <span data-ttu-id="d0435-115">LIS 接口层验证整个消息并生成 ACK 应用程序状态**MSA1 = AA**。</span><span class="sxs-lookup"><span data-stu-id="d0435-115">The LIS Interface Layer validates the entire message and generates an APPLICATION ACK with the status **MSA1 = AA**.</span></span> <span data-ttu-id="d0435-116">接口层将路由到 MLLP 包装的消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="d0435-116">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="d0435-117">以 ACK 所需确认该确认预先配置</span><span class="sxs-lookup"><span data-stu-id="d0435-117"> preconfigures 'ACK Required' acknowledging the acknowledgment</span></span>  
  
    -   <span data-ttu-id="d0435-118">MSH 15 = AL，指示接收的系统必须确认并提交接受消息的确认</span><span class="sxs-lookup"><span data-stu-id="d0435-118">MSH 15 = AL, which indicates that the receiving system must acknowledge the ACK with a Commit Accept Message</span></span>  
  
8.  <span data-ttu-id="d0435-119">LIS 接口层将邮件传递到应用程序层根据格式要求。</span><span class="sxs-lookup"><span data-stu-id="d0435-119">The LIS Interface layer delivers the message to the Application Layer in accordance with the format requirement.</span></span>  
  
9. <span data-ttu-id="d0435-120">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证从 LIS 界面层 （在步骤 7 上面） 接收到 ACK，并回状态 LIS 接口层的 ACK **MSA1 = CA**。</span><span class="sxs-lookup"><span data-stu-id="d0435-120">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the ACK received from the LIS Interface Layer (in step 7 above) and responds with an ACK back to the LIS Interface Layer with the status **MSA1= CA**.</span></span>  
  
10. <span data-ttu-id="d0435-121">LIS 系统的用户查看患者信息。</span><span class="sxs-lookup"><span data-stu-id="d0435-121">A user of the LIS System reviews the Patient information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0435-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0435-122">See Also</span></span>  
 <span data-ttu-id="d0435-123">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="d0435-123">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="d0435-124">编程指南</span><span class="sxs-lookup"><span data-stu-id="d0435-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)