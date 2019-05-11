---
title: 批处理计划选项卡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf479425a6a0e80b75791d9b43ee0880e6ada63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251805"
---
# <a name="batch-schedule-tab"></a><span data-ttu-id="72f90-102">批处理计划选项卡</span><span class="sxs-lookup"><span data-stu-id="72f90-102">Batch Schedule Tab</span></span>
<span data-ttu-id="72f90-103">您使用**批处理计划**选项卡以激活、 请求或终止出站批。</span><span class="sxs-lookup"><span data-stu-id="72f90-103">You use the **Batch Schedule** tab to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="72f90-104">激活的出站批包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="72f90-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="72f90-105">你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]创建基于时间的使用出站批或消息计数条件或这两者的组合。</span><span class="sxs-lookup"><span data-stu-id="72f90-105">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to create an outbound batch using time-based or message count criteria or a combination of both.</span></span> <span data-ttu-id="72f90-106">设置批处理激活条件是可选的。</span><span class="sxs-lookup"><span data-stu-id="72f90-106">Setting batch activation criteria is optional.</span></span> <span data-ttu-id="72f90-107">如果未指定，则可以手动激活批处理。</span><span class="sxs-lookup"><span data-stu-id="72f90-107">If not specified, you can activate a batch manually.</span></span> <span data-ttu-id="72f90-108">如果你想要激活使用基于时间的批处理或消息计数条件，则必须在激活批处理之前指定这些条件。</span><span class="sxs-lookup"><span data-stu-id="72f90-108">If you want to activate a batch using time-based or message count criteria, you must specify these criteria before activating the batch.</span></span>  
  
 <span data-ttu-id="72f90-109">在中**BTAHL7 配置资源管理器**对话框中，在**批处理计划**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72f90-109">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Schedule** tab, do the following:</span></span>  
  
|<span data-ttu-id="72f90-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="72f90-110">Use this</span></span>|<span data-ttu-id="72f90-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="72f90-111">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="72f90-112">**第一次批处理之前的小时数**</span><span class="sxs-lookup"><span data-stu-id="72f90-112">**Hours before first batch**</span></span>|<span data-ttu-id="72f90-113">键入前启动第一批的小时数。</span><span class="sxs-lookup"><span data-stu-id="72f90-113">Type the number of hours before starting the first batch.</span></span><br /><br /> <span data-ttu-id="72f90-114">选择消息计数作为批处理控件时，此选项不可用。</span><span class="sxs-lookup"><span data-stu-id="72f90-114">This option is not available when you select message count as the batch control.</span></span>|  
|<span data-ttu-id="72f90-115">**重复执行批处理后**</span><span class="sxs-lookup"><span data-stu-id="72f90-115">**Repeat Batch After**</span></span>|<span data-ttu-id="72f90-116">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="72f90-116">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="72f90-117">-                   **小时**。</span><span class="sxs-lookup"><span data-stu-id="72f90-117">-                   **Hours**.</span></span> <span data-ttu-id="72f90-118">键入要重复批处理过程之前等待小时的数。</span><span class="sxs-lookup"><span data-stu-id="72f90-118">Type the number of hours to wait before repeating the batch process.</span></span><br /><br /> <span data-ttu-id="72f90-119">-                   **消息**。</span><span class="sxs-lookup"><span data-stu-id="72f90-119">-                   **Messages**.</span></span> <span data-ttu-id="72f90-120">键入你想要启动下一批之前处理的消息数。</span><span class="sxs-lookup"><span data-stu-id="72f90-120">Type the number of messages that you want to process before initiating the next batch.</span></span>|  
|<span data-ttu-id="72f90-121">**批处理控件**</span><span class="sxs-lookup"><span data-stu-id="72f90-121">**Batch Control**</span></span>|<span data-ttu-id="72f90-122">使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="72f90-122">Use the following options:</span></span><br /><br /> <span data-ttu-id="72f90-123">-                   **启动计划**:选择此选项以启动批处理计划。</span><span class="sxs-lookup"><span data-stu-id="72f90-123">-                   **Start Schedule**: Select this option to start your batch schedule.</span></span><br /><br /> <span data-ttu-id="72f90-124">-                   **立即发送**:选择此选项以立即启动批处理过程。</span><span class="sxs-lookup"><span data-stu-id="72f90-124">-                   **Send Now**: Select this option to start the batch process immediately.</span></span> <span data-ttu-id="72f90-125">此设置将替代**小时之后第一批,** 并**重复执行批处理后**设置。</span><span class="sxs-lookup"><span data-stu-id="72f90-125">This overrides the **Hours before first batch** and **Repeat Batch After** settings.</span></span><br /><br /> <span data-ttu-id="72f90-126">-                   **停止计划**:选择此选项可停止当前批处理计划。</span><span class="sxs-lookup"><span data-stu-id="72f90-126">-                   **Stop Schedule**: Select this option to stop the current batch schedule.</span></span> <span data-ttu-id="72f90-127">这完成当前批次，然后停止批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="72f90-127">This completes the current batch and then stops the batch orchestration.</span></span>|