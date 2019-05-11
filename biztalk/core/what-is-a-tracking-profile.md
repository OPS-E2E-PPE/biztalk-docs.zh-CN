---
title: 什么是跟踪配置文件？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42c4331dacd451e2a4d9f495d495dbf10fbf911a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379718"
---
# <a name="what-is-a-tracking-profile"></a><span data-ttu-id="58a7a-103">什么是跟踪配置文件？</span><span class="sxs-lookup"><span data-stu-id="58a7a-103">What Is a Tracking Profile?</span></span>
<span data-ttu-id="58a7a-104">配置文件是一组定义业务流程的特征。</span><span class="sxs-lookup"><span data-stu-id="58a7a-104">A profile is a set of characteristics that define a business process.</span></span> <span data-ttu-id="58a7a-105">跟踪配置文件包含这些特性从活动到业务流程和端口的映射。</span><span class="sxs-lookup"><span data-stu-id="58a7a-105">A tracking profile contains the mapping of these characteristics from an activity to orchestrations and ports.</span></span> <span data-ttu-id="58a7a-106">跟踪配置文件是扩展名为.btt 的文件。</span><span class="sxs-lookup"><span data-stu-id="58a7a-106">A tracking profile is a file with a .btt file name extension.</span></span>  
  
## <a name="using-tracking-profiles-in-the-tpe"></a><span data-ttu-id="58a7a-107">在 TPE 中使用跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="58a7a-107">Using tracking profiles in the TPE</span></span>  
 <span data-ttu-id="58a7a-108">TPE 的用户创建的映射，即跟踪配置文件，BAM 活动中的项与这些项的 BizTalk Server 解决方案源之间。</span><span class="sxs-lookup"><span data-stu-id="58a7a-108">Users of the TPE create a map, or tracking profile, between items in a BAM activity and the BizTalk Server solution sources for those items.</span></span> <span data-ttu-id="58a7a-109">BAM 活动里程碑和构成"想看的列表"的上下文数据组成，并跟踪配置文件跟随在业务中定义的工作单元。</span><span class="sxs-lookup"><span data-stu-id="58a7a-109">BAM activities consist of the milestones and contextual data that make up the "visibility wish-list" and define a unit of work in the business that the tracking profile follows.</span></span> <span data-ttu-id="58a7a-110">有关活动的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="58a7a-110">For more information about activities, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
 <span data-ttu-id="58a7a-111">当创建跟踪配置文件使用 TPE 时，您正在使用以下对象：</span><span class="sxs-lookup"><span data-stu-id="58a7a-111">When you create a tracking profile using the TPE, you are working with the following objects:</span></span>  
  
- <span data-ttu-id="58a7a-112">BAM 活动</span><span class="sxs-lookup"><span data-stu-id="58a7a-112">BAM activities</span></span>  
  
- <span data-ttu-id="58a7a-113">在已部署的程序集中 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="58a7a-113">BizTalk orchestrations in deployed assemblies</span></span>  
  
- <span data-ttu-id="58a7a-114">接收和发送端口</span><span class="sxs-lookup"><span data-stu-id="58a7a-114">Receive and send ports</span></span>  
  
- <span data-ttu-id="58a7a-115">在已部署程序集的消息架构</span><span class="sxs-lookup"><span data-stu-id="58a7a-115">Message schemas in deployed assemblies</span></span>  
  
- <span data-ttu-id="58a7a-116">上下文属性</span><span class="sxs-lookup"><span data-stu-id="58a7a-116">Context properties</span></span>  
  
- <span data-ttu-id="58a7a-117">BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="58a7a-117">BAM Primary Import database</span></span>  
  
- <span data-ttu-id="58a7a-118">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="58a7a-118">BizTalk Management database</span></span>  
  
- <span data-ttu-id="58a7a-119">BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="58a7a-119">BizTalk Tracking database</span></span>  
  
  <span data-ttu-id="58a7a-120">通过将项从消息架构、 业务流程形状和上下文属性放入业务里程碑 （事件） 和数据项文件夹定义从业务流程的数据提取。</span><span class="sxs-lookup"><span data-stu-id="58a7a-120">You define the data extraction from an orchestration by dropping items from message schemas, orchestration shapes, and context properties into business milestone (event) and data item folders.</span></span>  
  
  <span data-ttu-id="58a7a-121">例如，考虑包含名为 PO Received 里程碑且具有通过哪些采购订单流动来启动处理的消息传送端口的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="58a7a-121">For example, consider a BAM activity that includes a milestone called PO Received and has a Messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="58a7a-122">开发人员可以将相关联`PO Received`里程碑与 BizTalk 消息传送属性调用`PortEndTime`在其解决方案中的端口。</span><span class="sxs-lookup"><span data-stu-id="58a7a-122">Developers can associate the `PO Received` milestone with a BizTalk Messaging property called `PortEndTime` for the port in their solution.</span></span> <span data-ttu-id="58a7a-123">也就是说，这表明只要接收端口结束其操作并填充成功接收采购订单`PortEndTime`属性。</span><span class="sxs-lookup"><span data-stu-id="58a7a-123">Semantically, this indicates that the PO is successfully received once the receive port concludes its action and populates the `PortEndTime` property.</span></span> <span data-ttu-id="58a7a-124">开发人员实现此映射和所有其他映射来完成跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="58a7a-124">The developer makes this and any other mappings to complete the tracking profile.</span></span> <span data-ttu-id="58a7a-125">如果它们具有 BizTalk Server 源，或处于活动中的所有项将都映射未映射，以便通过 API 调用直接如果填充的数据或事件的源是从 BizTalk Server 运行时环境之外的进程。</span><span class="sxs-lookup"><span data-stu-id="58a7a-125">All items in the activity are mapped if they have a BizTalk Server source, or are left unmapped to be populated by API calls directly if the source of the data or event is from a process outside of BizTalk Server’s run-time environment.</span></span>  
  
  <span data-ttu-id="58a7a-126">尽管每个窗格或在 TPE 中的视图有一个独特的功能，但所有视图和文件夹将都具有相似的导航功能以帮助您查找和操作信息。</span><span class="sxs-lookup"><span data-stu-id="58a7a-126">Although each pane or view in the TPE has a unique function, all the views and folders have similar navigational features to help you find and manipulate information.</span></span>  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a><span data-ttu-id="58a7a-127">谁可使用跟踪配置文件和 TPE？</span><span class="sxs-lookup"><span data-stu-id="58a7a-127">Who uses tracking profiles and the TPE?</span></span>  
 <span data-ttu-id="58a7a-128">涉及企业集成开发的用户使用跟踪配置文件和 TPE 将 BizTalk Server 事件源映射到 BAM 目标活动。</span><span class="sxs-lookup"><span data-stu-id="58a7a-128">Users involved with enterprise integration development use tracking profiles and the TPE to map BizTalk Server event sources to BAM target activities.</span></span> <span data-ttu-id="58a7a-129">生成的.btt 文件被移交至 IT 实施的部署。</span><span class="sxs-lookup"><span data-stu-id="58a7a-129">The resulting .btt file is handed off to IT Implementation for deployment.</span></span>  
  
 <span data-ttu-id="58a7a-130">IT 实现用户通常将应用跟踪配置文件使用命令行工具 (BTTDeploy)。</span><span class="sxs-lookup"><span data-stu-id="58a7a-130">IT Implementation users will typically apply tracking profiles using command-line tools (BTTDeploy).</span></span> <span data-ttu-id="58a7a-131">IT 用户还可以使用 TPE 直接以应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="58a7a-131">The IT user can also use the TPE directly to apply the tracking profile.</span></span>  
  
 <span data-ttu-id="58a7a-132">IT 操作中的用户可能负责对跟踪配置文件按计划定期 （包括必需的例如备份和还原任何数据库操作），尤其是由于业务要求的更改而进行定期更新。</span><span class="sxs-lookup"><span data-stu-id="58a7a-132">Users in IT Operations may be responsible for periodic updates to tracking profiles on a scheduled basis (including any database operations required, such as backup and restore), especially as a result of changes in business requirements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a7a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="58a7a-133">See Also</span></span>  
 [<span data-ttu-id="58a7a-134">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="58a7a-134">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)