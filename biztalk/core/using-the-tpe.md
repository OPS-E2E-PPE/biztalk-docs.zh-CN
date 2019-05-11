---
title: 使用 TPE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f46b8ce50662fca8c6b2b34eb6243ec094f6ad8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302840"
---
# <a name="using-the-tpe"></a><span data-ttu-id="c3f0e-102">使用 TPE</span><span class="sxs-lookup"><span data-stu-id="c3f0e-102">Using the TPE</span></span>
<span data-ttu-id="c3f0e-103">使用跟踪配置文件编辑器 (TPE) 将业务流程和属性映射到 BAM 活动定义。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-103">You use the Tracking Profile Editor (TPE) to map orchestrations and properties to BAM activity definitions.</span></span>  
  
 <span data-ttu-id="c3f0e-104">TPE 的用户创建的映射，即跟踪配置文件，如里程碑和上下文数据 （有时称为"可见性列表"） 的 BAM 活动中的项与这些项的 BizTalk 解决方案源之间。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-104">Users of the TPE create a map, or tracking profile, between items in a BAM activity such as milestones and contextual data (sometimes called the "visibility wish-list") and the BizTalk solution sources for those items.</span></span>  
  
 <span data-ttu-id="c3f0e-105">**创建跟踪配置文件**</span><span class="sxs-lookup"><span data-stu-id="c3f0e-105">**Creating a Tracking Profile**</span></span>  
  
 <span data-ttu-id="c3f0e-106">例如，考虑包含名为"接收的 PO。"里程碑的 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="c3f0e-106">For example, consider a BAM activity that includes a milestone called “PO Received.”</span></span> <span data-ttu-id="c3f0e-107">开发人员创建在其他 BizTalk Server 开发工具，了流程知道实际流程，包括通过哪些采购订单流动来启动处理的消息传送端口。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-107">The developer knows, from having created processes in other BizTalk Server development tools, that the actual process includes a messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="c3f0e-108">开发人员确定名为"收到的采购订单，"活动里程碑是与 BizTalk 消息传送的解决方案中的端口安全名为"PortEndTime"的属性最正确关联。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-108">The developer determines that the activity milestone, called “PO Received,” is most correctly associated with a BizTalk messaging property called “PortEndTime” for the port in the solution.</span></span> <span data-ttu-id="c3f0e-109">开发人员实现此映射和任何其他映射，以通过加载活动、 选择事件源，并将相应的项从事件源和放置在活动树定义中的相应节点上完成跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-109">The developer makes this and any other mappings to complete the tracking profile by loading the activity, selecting event sources, and dragging the appropriate items from the event source and dropping them on the corresponding nodes in the activity tree definition.</span></span>  
  
 <span data-ttu-id="c3f0e-110">**创建一个配置文件的先决条件**</span><span class="sxs-lookup"><span data-stu-id="c3f0e-110">**Prerequisites for Creating a Profile**</span></span>  
  
 <span data-ttu-id="c3f0e-111">有两个用于创建跟踪配置文件的先决条件：</span><span class="sxs-lookup"><span data-stu-id="c3f0e-111">There are two prerequisites for creating a tracking profile:</span></span>  
  
1. <span data-ttu-id="c3f0e-112">BAM 活动作为一个整体的观察模型的一部分定义由业务分析员并已由系统管理员部署。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-112">A BAM activity has been defined by the business analyst, as part of an overall observation model, and has been deployed by the system administrator.</span></span>  
  
2. <span data-ttu-id="c3f0e-113">BizTalk 解决方案 （包括业务流程、 架构、 映射和管道） 已成功部署在目标环境中。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-113">A BizTalk solution (including orchestrations, schemas, map, and pipelines) has been successfully deployed in the target environment.</span></span>  
  
   <span data-ttu-id="c3f0e-114">这些系统必备组件是必需的因为安装后 TPE 不填充与要从数据库中检索任何数据。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-114">These prerequisites are necessary since after installation the TPE is not populated with any data to retrieve from the databases.</span></span>  
  
   <span data-ttu-id="c3f0e-115">**为自定义的 BAM 解决方案创建一个配置文件**</span><span class="sxs-lookup"><span data-stu-id="c3f0e-115">**Creating a Profile for Customized BAM Solutions**</span></span>  
  
   <span data-ttu-id="c3f0e-116">跟踪配置文件都只与具有侦听器的运行时间相关。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-116">Tracking profiles are only relevant to run-times that have an interceptor.</span></span> <span data-ttu-id="c3f0e-117">对于由使用 BAM Api 的自定义代码的 BAM 解决方案，没有任何关联的 BAM 运行时侦听器，并将数据发送到 BAM 可以完成的唯一一种方法通过两种方式：</span><span class="sxs-lookup"><span data-stu-id="c3f0e-117">For BAM solutions that consist of custom code using the BAM APIs, there is no associated BAM run-time interceptor, and sending data to BAM can be done in only one of two ways:</span></span>  
  
- <span data-ttu-id="c3f0e-118">直接通过 BAM Api。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-118">Directly through the BAM APIs.</span></span> <span data-ttu-id="c3f0e-119">使用 Api，开发人员可以显式将事件数据发送到 BAM 基础结构中。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-119">Using the APIs developers can explicitly send event data to the BAM infrastructure.</span></span> <span data-ttu-id="c3f0e-120">有关使用 BAM Api 的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-120">For more information about using the BAM APIs, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
- <span data-ttu-id="c3f0e-121">通过间接，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-121">Indirectly, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] properties.</span></span> <span data-ttu-id="c3f0e-122">在具有关联的侦听技术，如自定义管道或表达式/操作形状中调用自定义程序集，一些运行时上下文内执行的自定义代码的位置的情况下可以使用 BAM Api，如上文所述，或使用传统数据升级技术。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-122">In the case where the custom code is executing inside some run-time context that does have an associated interception technology, such as a custom pipeline - or expression/action shapes in invoking a custom assembly, You can use the BAM APIs as noted above or use traditional data promotion techniques.</span></span> <span data-ttu-id="c3f0e-123">通过升级属性，使用户可进行到 TPE 和事件数据复制到 BAM 活动项的关联然后可在 TPE 中使用正确的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-123">By promoting the properties you make them accessible to the TPE and the association of that event data to a BAM activity item can then be made in the TPE using the correct context property.</span></span> <span data-ttu-id="c3f0e-124">有关升级属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-124">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3f0e-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="c3f0e-125">In This Section</span></span>  
  
-   [<span data-ttu-id="c3f0e-126">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c3f0e-126">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)  
  
-   [<span data-ttu-id="c3f0e-127">如何删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c3f0e-127">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [<span data-ttu-id="c3f0e-128">使用多个继续符</span><span class="sxs-lookup"><span data-stu-id="c3f0e-128">Using Multiple Continuations</span></span>](../core/using-multiple-continuations.md)