---
title: 计划批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1522a050fc6cc1b690cdd59adb26ddde5d7449f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289900"
---
# <a name="scheduling-batching"></a><span data-ttu-id="51f65-102">计划批处理</span><span class="sxs-lookup"><span data-stu-id="51f65-102">Scheduling Batching</span></span>
<span data-ttu-id="51f65-103">您使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来激活、 请求，或终止出站批。</span><span class="sxs-lookup"><span data-stu-id="51f65-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="51f65-104">激活的出站批包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="51f65-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="51f65-105">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批处理计划**选项卡。</span><span class="sxs-lookup"><span data-stu-id="51f65-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 <span data-ttu-id="51f65-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span><span class="sxs-lookup"><span data-stu-id="51f65-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span></span>  
  
 <span data-ttu-id="51f65-107">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和计划批处理。</span><span class="sxs-lookup"><span data-stu-id="51f65-107">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="51f65-108">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="51f65-108">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="51f65-109">单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="51f65-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="51f65-110">若要计划消息批处理</span><span class="sxs-lookup"><span data-stu-id="51f65-110">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="51f65-111">打开 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="51f65-111">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="51f65-112">在 BTAHL7 配置资源管理器中**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，该参与的方，然后在**批处理计划**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="51f65-112">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="51f65-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="51f65-113">Use this</span></span>|<span data-ttu-id="51f65-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="51f65-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="51f65-115">**第一次批处理之前的小时数**</span><span class="sxs-lookup"><span data-stu-id="51f65-115">**Hours before first batch**</span></span>|<span data-ttu-id="51f65-116">键入第一批是启动前的小时数。</span><span class="sxs-lookup"><span data-stu-id="51f65-116">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="51f65-117">**重复执行批处理后**</span><span class="sxs-lookup"><span data-stu-id="51f65-117">**Repeat Batch After**</span></span>|<span data-ttu-id="51f65-118">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="51f65-118">Select one of the following:</span></span><br /><br /> <span data-ttu-id="51f65-119">-   **小时**。</span><span class="sxs-lookup"><span data-stu-id="51f65-119">-   **Hours**.</span></span> <span data-ttu-id="51f65-120">键入要重复批处理过程的小时数。</span><span class="sxs-lookup"><span data-stu-id="51f65-120">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="51f65-121">-   **消息**。</span><span class="sxs-lookup"><span data-stu-id="51f65-121">-   **Messages**.</span></span> <span data-ttu-id="51f65-122">开始键入你想要在下一步的批处理过程之前处理的消息数。</span><span class="sxs-lookup"><span data-stu-id="51f65-122">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="51f65-123">**批处理控件**</span><span class="sxs-lookup"><span data-stu-id="51f65-123">**Batch Control**</span></span>|<span data-ttu-id="51f65-124">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="51f65-124">Select one of the following:</span></span><br /><br /> <span data-ttu-id="51f65-125">-   **启动计划**:选择此项可启动批处理计划。</span><span class="sxs-lookup"><span data-stu-id="51f65-125">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="51f65-126">-   **立即发送**:选择此选项可以立即启动批处理过程。</span><span class="sxs-lookup"><span data-stu-id="51f65-126">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="51f65-127">-   **停止计划**:选择此项可停止当前批处理计划。</span><span class="sxs-lookup"><span data-stu-id="51f65-127">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51f65-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="51f65-128">See Also</span></span>  
 [<span data-ttu-id="51f65-129">配置批处理确认</span><span class="sxs-lookup"><span data-stu-id="51f65-129">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)