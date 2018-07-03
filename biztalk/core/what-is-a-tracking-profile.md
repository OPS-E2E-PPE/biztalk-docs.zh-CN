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
ms.openlocfilehash: d9dbcdd4ff93749de5059b80fecfa140e41df422
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977873"
---
# <a name="what-is-a-tracking-profile"></a><span data-ttu-id="ebd9f-103">什么是跟踪配置文件？</span><span class="sxs-lookup"><span data-stu-id="ebd9f-103">What Is a Tracking Profile?</span></span>
<span data-ttu-id="ebd9f-104">配置文件是定义业务流程的特性组。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-104">A profile is a set of characteristics that define a business process.</span></span> <span data-ttu-id="ebd9f-105">跟踪配置文件包含这些特性从活动到业务流程和端口的映射。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-105">A tracking profile contains the mapping of these characteristics from an activity to orchestrations and ports.</span></span> <span data-ttu-id="ebd9f-106">跟踪配置文件是文件扩展名为 .btt 的文件。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-106">A tracking profile is a file with a .btt file name extension.</span></span>  
  
## <a name="using-tracking-profiles-in-the-tpe"></a><span data-ttu-id="ebd9f-107">在 TPE 中使用跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ebd9f-107">Using tracking profiles in the TPE</span></span>  
 <span data-ttu-id="ebd9f-108">TPE 的用户可以创建 BAM 活动中的项和这些项的 BizTalk Server 解决方案源之间的映射或跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-108">Users of the TPE create a map, or tracking profile, between items in a BAM activity and the BizTalk Server solution sources for those items.</span></span> <span data-ttu-id="ebd9f-109">BAM 活动由构成“想看的列表”的里程碑和上下文数据组成，并在业务中定义了跟踪配置文件跟随的工作单位。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-109">BAM activities consist of the milestones and contextual data that make up the "visibility wish-list" and define a unit of work in the business that the tracking profile follows.</span></span> <span data-ttu-id="ebd9f-110">有关活动的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-110">For more information about activities, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
 <span data-ttu-id="ebd9f-111">在使用 TPE 创建跟踪配置文件时，您要使用以下对象：</span><span class="sxs-lookup"><span data-stu-id="ebd9f-111">When you create a tracking profile using the TPE, you are working with the following objects:</span></span>  
  
- <span data-ttu-id="ebd9f-112">BAM 活动</span><span class="sxs-lookup"><span data-stu-id="ebd9f-112">BAM activities</span></span>  
  
- <span data-ttu-id="ebd9f-113">已部署的程序集中的 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="ebd9f-113">BizTalk orchestrations in deployed assemblies</span></span>  
  
- <span data-ttu-id="ebd9f-114">接收端口和发送端口</span><span class="sxs-lookup"><span data-stu-id="ebd9f-114">Receive and send ports</span></span>  
  
- <span data-ttu-id="ebd9f-115">已部署的程序集中的消息架构</span><span class="sxs-lookup"><span data-stu-id="ebd9f-115">Message schemas in deployed assemblies</span></span>  
  
- <span data-ttu-id="ebd9f-116">上下文属性</span><span class="sxs-lookup"><span data-stu-id="ebd9f-116">Context properties</span></span>  
  
- <span data-ttu-id="ebd9f-117">BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="ebd9f-117">BAM Primary Import database</span></span>  
  
- <span data-ttu-id="ebd9f-118">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="ebd9f-118">BizTalk Management database</span></span>  
  
- <span data-ttu-id="ebd9f-119">BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="ebd9f-119">BizTalk Tracking database</span></span>  
  
  <span data-ttu-id="ebd9f-120">将项从消息架构、业务流程形状和上下文属性中拖到业务里程碑（事件）和数据项文件夹中，可以定义从业务流程的数据提取。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-120">You define the data extraction from an orchestration by dropping items from message schemas, orchestration shapes, and context properties into business milestone (event) and data item folders.</span></span>  
  
  <span data-ttu-id="ebd9f-121">例如，假设 BAM 活动包含名为“PO Received”的里程碑，并且具有一个消息传送端口，采购订单流通过该端口启动处理过程。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-121">For example, consider a BAM activity that includes a milestone called PO Received and has a Messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="ebd9f-122">开发人员可以在其解决方案中将 `PO Received` 里程碑与该端口的一个名为 `PortEndTime` 的 BizTalk 消息传送属性关联在一起。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-122">Developers can associate the `PO Received` milestone with a BizTalk Messaging property called `PortEndTime` for the port in their solution.</span></span> <span data-ttu-id="ebd9f-123">也就是说，这表明只要接收端口结束其操作并填充 `PortEndTime` 属性，PO 就成功被接收。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-123">Semantically, this indicates that the PO is successfully received once the receive port concludes its action and populates the `PortEndTime` property.</span></span> <span data-ttu-id="ebd9f-124">开发人员实现此映射和所有其他映射来完成跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-124">The developer makes this and any other mappings to complete the tracking profile.</span></span> <span data-ttu-id="ebd9f-125">如果活动中的所有项都具有 BizTalk Server 源，则这些项会被映射，否则如果数据源或事件源来自于 BizTalk Server 运行时环境之外的进程，则这些项将保留为未映射，以便被 API 调用直接填充。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-125">All items in the activity are mapped if they have a BizTalk Server source, or are left unmapped to be populated by API calls directly if the source of the data or event is from a process outside of BizTalk Server’s run-time environment.</span></span>  
  
  <span data-ttu-id="ebd9f-126">尽管 TPE 中的每个窗格或视图都具有唯一的功能，但所有视图和文件夹都具有相似的导航功能以帮助您查找和操作信息。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-126">Although each pane or view in the TPE has a unique function, all the views and folders have similar navigational features to help you find and manipulate information.</span></span>  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a><span data-ttu-id="ebd9f-127">谁使用跟踪配置文件和 TPE？</span><span class="sxs-lookup"><span data-stu-id="ebd9f-127">Who uses tracking profiles and the TPE?</span></span>  
 <span data-ttu-id="ebd9f-128">涉及企业集成开发的用户使用跟踪配置文件和 TPE 将 BizTalk Server 事件源映射到 BAM 目标活动。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-128">Users involved with enterprise integration development use tracking profiles and the TPE to map BizTalk Server event sources to BAM target activities.</span></span> <span data-ttu-id="ebd9f-129">生成的 .btt 文件被移交至 IT 实施部门以便进行部署。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-129">The resulting .btt file is handed off to IT Implementation for deployment.</span></span>  
  
 <span data-ttu-id="ebd9f-130">通常，IT 实施部门的用户将使用命令行工具 (BTTDeploy) 应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-130">IT Implementation users will typically apply tracking profiles using command-line tools (BTTDeploy).</span></span> <span data-ttu-id="ebd9f-131">IT 用户还可以直接使用 TPE 应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-131">The IT user can also use the TPE directly to apply the tracking profile.</span></span>  
  
 <span data-ttu-id="ebd9f-132">IT 运作部门的用户可能负责根据计划定期对跟踪配置文件进行更新（其中包括必需的任何数据库操作，如备份和还原），尤其当业务要求发生更改时。</span><span class="sxs-lookup"><span data-stu-id="ebd9f-132">Users in IT Operations may be responsible for periodic updates to tracking profiles on a scheduled basis (including any database operations required, such as backup and restore), especially as a result of changes in business requirements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd9f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebd9f-133">See Also</span></span>  
 [<span data-ttu-id="ebd9f-134">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="ebd9f-134">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)