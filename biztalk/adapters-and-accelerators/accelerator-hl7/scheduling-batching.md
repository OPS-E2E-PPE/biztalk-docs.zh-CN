---
title: "计划批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08337171897a4a78e605054e9126e8c8238d5fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scheduling-batching"></a><span data-ttu-id="aa696-102">计划批处理</span><span class="sxs-lookup"><span data-stu-id="aa696-102">Scheduling Batching</span></span>
<span data-ttu-id="aa696-103">你使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器，若要激活、 请求，或终止出站批处理。</span><span class="sxs-lookup"><span data-stu-id="aa696-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="aa696-104">激活的出站批处理包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="aa696-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="aa696-105">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批处理计划**选项卡。</span><span class="sxs-lookup"><span data-stu-id="aa696-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 <span data-ttu-id="aa696-106">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和计划批处理。</span><span class="sxs-lookup"><span data-stu-id="aa696-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="aa696-107">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="aa696-107">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="aa696-108">单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="aa696-108">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="aa696-109">若要计划消息批处理</span><span class="sxs-lookup"><span data-stu-id="aa696-109">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="aa696-110">打开 BTAHL7 配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="aa696-110">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="aa696-111">在 BTAHL7 配置资源管理器，在**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，的方，然后在**批处理计划**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa696-111">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="aa696-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="aa696-112">Use this</span></span>|<span data-ttu-id="aa696-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="aa696-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="aa696-114">**第一次批处理前的小时数**</span><span class="sxs-lookup"><span data-stu-id="aa696-114">**Hours before first batch**</span></span>|<span data-ttu-id="aa696-115">键入第一个批处理是从开始前的小时数。</span><span class="sxs-lookup"><span data-stu-id="aa696-115">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="aa696-116">**重复后的批处理**</span><span class="sxs-lookup"><span data-stu-id="aa696-116">**Repeat Batch After**</span></span>|<span data-ttu-id="aa696-117">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="aa696-117">Select one of the following:</span></span><br /><br /> <span data-ttu-id="aa696-118">-   **小时**。</span><span class="sxs-lookup"><span data-stu-id="aa696-118">-   **Hours**.</span></span> <span data-ttu-id="aa696-119">键入要重复的批处理的小时数。</span><span class="sxs-lookup"><span data-stu-id="aa696-119">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="aa696-120">-   **消息**。</span><span class="sxs-lookup"><span data-stu-id="aa696-120">-   **Messages**.</span></span> <span data-ttu-id="aa696-121">开始键入你想要在下一步批处理之前处理的消息数。</span><span class="sxs-lookup"><span data-stu-id="aa696-121">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="aa696-122">**批处理控件**</span><span class="sxs-lookup"><span data-stu-id="aa696-122">**Batch Control**</span></span>|<span data-ttu-id="aa696-123">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="aa696-123">Select one of the following:</span></span><br /><br /> <span data-ttu-id="aa696-124">-   **启动计划**： 选择用于启动批处理计划。</span><span class="sxs-lookup"><span data-stu-id="aa696-124">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="aa696-125">-   **立即发送**： 选择要启动批处理立即处理。</span><span class="sxs-lookup"><span data-stu-id="aa696-125">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="aa696-126">-   **停止计划**： 选择此项可停止当前的批处理计划。</span><span class="sxs-lookup"><span data-stu-id="aa696-126">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa696-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa696-127">See Also</span></span>  
 [<span data-ttu-id="aa696-128">配置批处理确认</span><span class="sxs-lookup"><span data-stu-id="aa696-128">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)