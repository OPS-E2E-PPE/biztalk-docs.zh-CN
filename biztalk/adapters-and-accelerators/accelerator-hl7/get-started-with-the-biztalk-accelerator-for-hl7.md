---
title: 开始使用 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14559d888bc020a5772fbbc6eddf3ba4fdb4beb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989598"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a><span data-ttu-id="39dc8-102">开始使用 BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="39dc8-102">Get started with the BizTalk Accelerator for HL7</span></span>
<span data-ttu-id="39dc8-103">使用 Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]，可以在医疗保健计算机系统之间开发业务流程。</span><span class="sxs-lookup"><span data-stu-id="39dc8-103">Using the Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)], you can develop business processes between your health care computer systems.</span></span> <span data-ttu-id="39dc8-104">通过使用[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，开发人员、 IT 专业人员和接口分析师可以在常见环境来开发跨保健应用程序的端到端集成基于 BTAHL7 的解决方案下工作。</span><span class="sxs-lookup"><span data-stu-id="39dc8-104">By using [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], developers, IT professionals, and interface analysts can work in a common environment to develop end-to-end integrated BTAHL7-based solutions across health care applications.</span></span>  
  
 <span data-ttu-id="39dc8-105">更具体地说，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]你可以：</span><span class="sxs-lookup"><span data-stu-id="39dc8-105">More specifically, with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] you can:</span></span>  
  
- <span data-ttu-id="39dc8-106">**简化卫生保健应用程序集成**。</span><span class="sxs-lookup"><span data-stu-id="39dc8-106">**Simplify health care application integration**.</span></span> <span data-ttu-id="39dc8-107">生成、 管理和跟踪分布式的业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]开发环境。</span><span class="sxs-lookup"><span data-stu-id="39dc8-107">Build, manage, and track distributed business processes using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development environment.</span></span>  
  
- <span data-ttu-id="39dc8-108">**标准化医疗应用程序之间的临床数据交换**。</span><span class="sxs-lookup"><span data-stu-id="39dc8-108">**Standardize clinical data interchange between medical applications**.</span></span> <span data-ttu-id="39dc8-109">转换到的应用程序之间的现有数据传输[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]标准。</span><span class="sxs-lookup"><span data-stu-id="39dc8-109">Transform existing data transmission between applications to the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] standard.</span></span>  
  
- <span data-ttu-id="39dc8-110">**提高效率**。</span><span class="sxs-lookup"><span data-stu-id="39dc8-110">**Increase efficiency**.</span></span> <span data-ttu-id="39dc8-111">自动执行最少的手动干预的医疗应用程序之间的所有通信流程。</span><span class="sxs-lookup"><span data-stu-id="39dc8-111">Automate all communication processes between medical applications with minimal manual intervention.</span></span>  

<span data-ttu-id="39dc8-112">本部分提供有关如何使用特定于角色的信息[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]便于企业应用程序集成 (EAI) 医院和医疗卫生领域来自动执行企业到企业医疗保健解决方案中.</span><span class="sxs-lookup"><span data-stu-id="39dc8-112">This section provides role-specific information about how you can use [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] to facilitate Enterprise Application Integration (EAI) within hospitals and the healthcare arena to automate business-to-business healthcare solutions.</span></span>  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="39dc8-113"> 为每种类型的解决方案提供四种不同方案教程格式。</span><span class="sxs-lookup"><span data-stu-id="39dc8-113"> provides four separate scenarios in tutorial format for each type of solution.</span></span> <span data-ttu-id="39dc8-114">在开始这些教程之前，应了解基本概念[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，以及工具和进程进行生成解决方案所需的[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39dc8-114">Before you begin these tutorials, you should understand the fundamental concepts in [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], and the tools and processes that are required to start building solutions with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].</span></span>  

> [!TIP] 
> <span data-ttu-id="39dc8-115">在开始这些课程之前[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc8-115">Before you begin these lessons, [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
 <span data-ttu-id="39dc8-116">以下说明提供每个有一个大致了解[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]教程。</span><span class="sxs-lookup"><span data-stu-id="39dc8-116">The following descriptions provide a general understanding of each [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial.</span></span>  
  
## <a name="end-to-end-tutorial"></a><span data-ttu-id="39dc8-117">端到端教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-117">End-to-End tutorial</span></span>  
 <span data-ttu-id="39dc8-118">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]端到端教程提供了详细步骤，以便在订阅服务器和发布服务器方案中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="39dc8-118">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] End-to-End tutorial provides you with detailed steps to facilitate business processes in a subscriber and publisher scenario.</span></span> <span data-ttu-id="39dc8-119">这种情况下是发布服务器，例如，一个病人入院出院事项和传输系统将一条消息发送到特定的订阅服务器的情况。</span><span class="sxs-lookup"><span data-stu-id="39dc8-119">This scenario is a situation in which a publisher, for example, an Admissions Discharge and Transfer system sends a message to specific subscribers.</span></span>  
  
 <span data-ttu-id="39dc8-120">该消息将路由到[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎，又接收进程，验证，将重新格式化，并随后将消息路由到订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="39dc8-120">The message routes to the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to the subscribers.</span></span> <span data-ttu-id="39dc8-121">在此方案中的订阅服务器是医院信息系统和药房系统。</span><span class="sxs-lookup"><span data-stu-id="39dc8-121">The subscribers in this scenario are a Hospital Information System and a Pharmacy System.</span></span>  
  
 <span data-ttu-id="39dc8-122">此方案使用文件和最小的较低层协议 (MLLP) 适配器类型。</span><span class="sxs-lookup"><span data-stu-id="39dc8-122">This scenario uses both File and Minimal Lower Layer Protocol (MLLP) adapter types.</span></span> <span data-ttu-id="39dc8-123">发布服务器不需要注意的订阅服务器，并[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接口引擎处理消息之后将相应的确认发送到发布服务器。</span><span class="sxs-lookup"><span data-stu-id="39dc8-123">The publisher does not need to be aware of the subscribers, and the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interface Engine sends an appropriate acknowledgement to the publisher after processing the message.</span></span>  
  
## <a name="interrogative-tutorial"></a><span data-ttu-id="39dc8-124">询问教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-124">Interrogative tutorial</span></span>  
 <span data-ttu-id="39dc8-125">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]询问教程提供了详细步骤用于实现在组织内的子系统之间的查询响应系统。</span><span class="sxs-lookup"><span data-stu-id="39dc8-125">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative tutorial provides you with detailed steps for implementing a query-response system between sub-systems within an organization.</span></span> <span data-ttu-id="39dc8-126">在此方案中，业务 (LOB) 应用程序在病人入院，释放，并将传输系统将查询发送到医院信息系统以获得患者实验室的结果。</span><span class="sxs-lookup"><span data-stu-id="39dc8-126">In this scenario, a line-of-business (LOB) application in the Admissions, Discharge, and Transfer system sends a query to the Hospital Information System to obtain patient lab results.</span></span> <span data-ttu-id="39dc8-127">医院信息系统收到查询后，它将请求的数据发送回发出查询的系统。</span><span class="sxs-lookup"><span data-stu-id="39dc8-127">After the Hospital Information System receives the query, it sends the requested data back to the system that issued the query.</span></span>  
  
 <span data-ttu-id="39dc8-128">此方案使用 MLLP 作为传输协议的所有消息，包括确认。</span><span class="sxs-lookup"><span data-stu-id="39dc8-128">This scenario uses MLLP as the transport protocol for all messages, including acknowledgments.</span></span>  
  
## <a name="message-enrichment-tutorial"></a><span data-ttu-id="39dc8-129">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-129">Message enrichment tutorial</span></span>  
 <span data-ttu-id="39dc8-130">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]充实教程提供了解决特定业务问题的详细步骤： 消息收集方案。</span><span class="sxs-lookup"><span data-stu-id="39dc8-130">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Enrichment tutorial provides you with detailed steps to solve a particular business problem: the message-enrichment scenario.</span></span> <span data-ttu-id="39dc8-131">消息扩充方案是需要添加或丰富的情况下，一条消息，不符合 HL7 和/或不完整。</span><span class="sxs-lookup"><span data-stu-id="39dc8-131">The message-enrichment scenario is a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="39dc8-132">这种情况下可能会出现应用程序，如患者注册应用程序，或将填充来自 XML 数据的消息时[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39dc8-132">This situation can occur with an application, such as a patient-registration application, or when you are populating a message with XML data from [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="39dc8-133">在消息扩充方案中，捕获的消息与[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]，并提供任何缺失的数据，例如，从患者记录数据库。</span><span class="sxs-lookup"><span data-stu-id="39dc8-133">In the message enrichment scenario, you capture the messages with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], and provide any missing data, for example, from a patient-records database.</span></span> <span data-ttu-id="39dc8-134">然后将消息转换，并将其发送到实验室、 保險、 或任何旧的业务线 (LOB) 应用程序使用 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="39dc8-134">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP adapter.</span></span>  
  
## <a name="batching-tutorial"></a><span data-ttu-id="39dc8-135">批处理教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-135">Batching tutorial</span></span>  
 <span data-ttu-id="39dc8-136">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]批处理教程提供了详细步骤，以接收和发送批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="39dc8-136">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Batching tutorial provides you with detailed steps to receive and send batched messages.</span></span> <span data-ttu-id="39dc8-137">批处理为单个复合消息包括接收和/或发送的一组各个消息 （或确认）。</span><span class="sxs-lookup"><span data-stu-id="39dc8-137">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="39dc8-138"> 支持以下三种消息批处理方案：</span><span class="sxs-lookup"><span data-stu-id="39dc8-138"> supports the following three message batching scenarios:</span></span>  
  
- <span data-ttu-id="39dc8-139">**零碎的入站的批处理**。</span><span class="sxs-lookup"><span data-stu-id="39dc8-139">**Fragmented inbound batch**.</span></span> <span data-ttu-id="39dc8-140">在此方案中，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收 HL7 消息批，，然后将各个消息路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="39dc8-140">In this scenario, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
- <span data-ttu-id="39dc8-141">**在批处理 / 出站批处理**。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]接收 HL7 消息批，验证在批处理中的单个消息，然后将消息批路由到目标系统。</span><span class="sxs-lookup"><span data-stu-id="39dc8-141">**Batch in/batch out**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
- <span data-ttu-id="39dc8-142">**创建批次 （或出站批处理）**。</span><span class="sxs-lookup"><span data-stu-id="39dc8-142">**Create batch (or outbound batching)**.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="39dc8-143"> 接收单个消息并将它们路由到目标系统之前对其进行批量。</span><span class="sxs-lookup"><span data-stu-id="39dc8-143"> receives individual messages and batches them before routing them to the destination system.</span></span>  
  
## <a name="tutorial-links"></a><span data-ttu-id="39dc8-144">教程的链接</span><span class="sxs-lookup"><span data-stu-id="39dc8-144">Tutorial links</span></span>  
  
-   [<span data-ttu-id="39dc8-145">端到端教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-145">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [<span data-ttu-id="39dc8-146">询问教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-146">Interrogative Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [<span data-ttu-id="39dc8-147">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-147">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [<span data-ttu-id="39dc8-148">批处理教程</span><span class="sxs-lookup"><span data-stu-id="39dc8-148">Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a><span data-ttu-id="39dc8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39dc8-149">See also</span></span>
  
[<span data-ttu-id="39dc8-150">为残障人士提供的辅助功能</span><span class="sxs-lookup"><span data-stu-id="39dc8-150">Accessibility for People with Disabilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)