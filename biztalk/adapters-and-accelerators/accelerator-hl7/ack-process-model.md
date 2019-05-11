---
title: ACK 进程模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4775605dc9b8eb41e60e39bee5a763913ce04901
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247706"
---
# <a name="ack-process-model"></a><span data-ttu-id="08c63-102">ACK 进程模型</span><span class="sxs-lookup"><span data-stu-id="08c63-102">ACK Process Model</span></span>
<span data-ttu-id="08c63-103">以下一系列步骤描述了确认 (ACK) 进程模型：</span><span class="sxs-lookup"><span data-stu-id="08c63-103">The following sequence of steps describes the acknowledgment (ACK) process model:</span></span>  
  
1. <span data-ttu-id="08c63-104">当招生人员登录患者入院信息到病人入院系统 (ADT) 时，系统将生成的触发器事件。</span><span class="sxs-lookup"><span data-stu-id="08c63-104">When the admissions personnel log patient admission information into the Admissions System (ADT), the system generates a trigger event.</span></span>  
  
2. <span data-ttu-id="08c63-105">ADT 系统生成 HL7 编码患者注册消息 (ADT ^ A04) 并将其传递到 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="08c63-105">The ADT system generates an HL7-encoded Patient Registration message (ADT^A04) and delivers it to BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
3. <span data-ttu-id="08c63-106">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统将 MLLP 包装应用上 ADT ^ A04 消息并将它路由到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="08c63-106">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system applies an MLLP wrapper on the ADT^A04 message and routes it to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   -   <span data-ttu-id="08c63-107">预配置的原始模式确认要求</span><span class="sxs-lookup"><span data-stu-id="08c63-107">Requirement of 'Original Mode' Acknowledgment is preconfigured</span></span>  
  
   -   <span data-ttu-id="08c63-108">MSH 15 和 16 具有 null 值</span><span class="sxs-lookup"><span data-stu-id="08c63-108">MSH 15 and 16 have null values</span></span>  
  
4. <span data-ttu-id="08c63-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证消息，并且如果验证成功发生，它将生成的确认消息的状态**MSA01 = AA**。</span><span class="sxs-lookup"><span data-stu-id="08c63-109">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the message and if successful validation occurs, it generates the ACK message with the status **MSA01 = AA**.</span></span>  
  
5. <span data-ttu-id="08c63-110">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎转换 ADT ^ A04 消息由与 MLLP 包装器将其括起来并将其路由到实验室的信息系统 (LIS)。</span><span class="sxs-lookup"><span data-stu-id="08c63-110">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine transforms the ADT^A04 message by enclosing it with MLLP wrappers and routing it to the Lab Information System (LIS).</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="08c63-111">增强型模式确认会预先配置</span><span class="sxs-lookup"><span data-stu-id="08c63-111">preconfigures 'Enhanced Mode' Acknowledgment</span></span>  
  
   - <span data-ttu-id="08c63-112">MSH 15 和 16 = AL</span><span class="sxs-lookup"><span data-stu-id="08c63-112">MSH 15 and 16 = AL</span></span>  
  
6. <span data-ttu-id="08c63-113">LIS 接口层验证标头： 提交消息，并生成状态为接受 ACK **MSA1 = CA**。</span><span class="sxs-lookup"><span data-stu-id="08c63-113">The LIS Interface Layer validates the header by committing the message and generating an ACCEPT ACK with the status **MSA1 = CA**.</span></span> <span data-ttu-id="08c63-114">接口层将与 MLLP 包装到消息路由[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="08c63-114">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
7. <span data-ttu-id="08c63-115">LIS 接口层验证整个消息并生成 ACK 应用程序状态**MSA1 = AA**。</span><span class="sxs-lookup"><span data-stu-id="08c63-115">The LIS Interface Layer validates the entire message and generates an APPLICATION ACK with the status **MSA1 = AA**.</span></span> <span data-ttu-id="08c63-116">接口层将与 MLLP 包装到消息路由[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。</span><span class="sxs-lookup"><span data-stu-id="08c63-116">The interface layer routes the message with the MLLP wrapper to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine.</span></span>  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="08c63-117">确认所需确认该确认会预先配置</span><span class="sxs-lookup"><span data-stu-id="08c63-117">preconfigures 'ACK Required' acknowledging the acknowledgment</span></span>  
  
   - <span data-ttu-id="08c63-118">MSH 15 = AL，指示接收系统必须确认并提交接受消息的确认</span><span class="sxs-lookup"><span data-stu-id="08c63-118">MSH 15 = AL, which indicates that the receiving system must acknowledge the ACK with a Commit Accept Message</span></span>  
  
8. <span data-ttu-id="08c63-119">LIS 接口层的消息传递到格式要求根据应用程序层。</span><span class="sxs-lookup"><span data-stu-id="08c63-119">The LIS Interface layer delivers the message to the Application Layer in accordance with the format requirement.</span></span>  
  
9. <span data-ttu-id="08c63-120">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证 LIS 接口层 （上述步骤 7 中） 从收到的确认，并返回到 LIS 接口层的状态的 ACK **MSA1 = CA**。</span><span class="sxs-lookup"><span data-stu-id="08c63-120">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine validates the ACK received from the LIS Interface Layer (in step 7 above) and responds with an ACK back to the LIS Interface Layer with the status **MSA1= CA**.</span></span>  
  
10. <span data-ttu-id="08c63-121">LIS 系统的用户查看患者信息。</span><span class="sxs-lookup"><span data-stu-id="08c63-121">A user of the LIS System reviews the Patient information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c63-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="08c63-122">See Also</span></span>  
 <span data-ttu-id="08c63-123">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="08c63-123">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="08c63-124">编程指南</span><span class="sxs-lookup"><span data-stu-id="08c63-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)