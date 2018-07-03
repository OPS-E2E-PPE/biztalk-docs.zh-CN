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
ms.openlocfilehash: 03cde68788e6be74a6d49fe0dd894b3f912819bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968158"
---
# <a name="using-the-tpe"></a><span data-ttu-id="43048-102">使用 TPE</span><span class="sxs-lookup"><span data-stu-id="43048-102">Using the TPE</span></span>
<span data-ttu-id="43048-103">使用跟踪配置文件编辑器 (TPE)，可以将业务流程和属性映射到 BAM 活动定义。</span><span class="sxs-lookup"><span data-stu-id="43048-103">You use the Tracking Profile Editor (TPE) to map orchestrations and properties to BAM activity definitions.</span></span>  
  
 <span data-ttu-id="43048-104">TPE 用户可以创建 BAM 活动中的项（如里程碑和上下文数据，有时称为“所需可见性列表”）与其 BizTalk 解决方案源之间的映射，即跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="43048-104">Users of the TPE create a map, or tracking profile, between items in a BAM activity such as milestones and contextual data (sometimes called the "visibility wish-list") and the BizTalk solution sources for those items.</span></span>  
  
 <span data-ttu-id="43048-105">**创建跟踪配置文件**</span><span class="sxs-lookup"><span data-stu-id="43048-105">**Creating a Tracking Profile**</span></span>  
  
 <span data-ttu-id="43048-106">例如，请考虑包含名为“接收的 PO”里程碑的一个 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="43048-106">For example, consider a BAM activity that includes a milestone called “PO Received.”</span></span> <span data-ttu-id="43048-107">开发人员由于已在其他 BizTalk Server 开发工具中创建了流程，因此他们知道实际流程包含一个消息传送端口，采购订单通过该消息端口流动来启动处理过程。</span><span class="sxs-lookup"><span data-stu-id="43048-107">The developer knows, from having created processes in other BizTalk Server development tools, that the actual process includes a messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="43048-108">开发人员由此可以确定，名为“接收的 PO”的活动里程碑最可能与解决方案中用于端口的名为“PortEndTime”的 BizTalk 消息传送属性相关联。</span><span class="sxs-lookup"><span data-stu-id="43048-108">The developer determines that the activity milestone, called “PO Received,” is most correctly associated with a BizTalk messaging property called “PortEndTime” for the port in the solution.</span></span> <span data-ttu-id="43048-109">开发人员通过加载活动、选择事件源，然后将适当的项从事件源拖放到活动树定义中的相应节点，来作出此映射以及任何其他映射，以完成跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="43048-109">The developer makes this and any other mappings to complete the tracking profile by loading the activity, selecting event sources, and dragging the appropriate items from the event source and dropping them on the corresponding nodes in the activity tree definition.</span></span>  
  
 <span data-ttu-id="43048-110">**创建一个配置文件的先决条件**</span><span class="sxs-lookup"><span data-stu-id="43048-110">**Prerequisites for Creating a Profile**</span></span>  
  
 <span data-ttu-id="43048-111">创建跟踪配置文件有两个前提条件：</span><span class="sxs-lookup"><span data-stu-id="43048-111">There are two prerequisites for creating a tracking profile:</span></span>  
  
1. <span data-ttu-id="43048-112">BAM 活动已由业务分析员定义为整个观察模型的一部分，并已由系统管理员部署。</span><span class="sxs-lookup"><span data-stu-id="43048-112">A BAM activity has been defined by the business analyst, as part of an overall observation model, and has been deployed by the system administrator.</span></span>  
  
2. <span data-ttu-id="43048-113">BizTalk 解决方案（包括业务流程、架构、映射和管道）已在目标环境中成功部署。</span><span class="sxs-lookup"><span data-stu-id="43048-113">A BizTalk solution (including orchestrations, schemas, map, and pipelines) has been successfully deployed in the target environment.</span></span>  
  
   <span data-ttu-id="43048-114">这些前提条件是必需的，因为在安装后，没有使用从数据库中检索的任何数据填充 TPE。</span><span class="sxs-lookup"><span data-stu-id="43048-114">These prerequisites are necessary since after installation the TPE is not populated with any data to retrieve from the databases.</span></span>  
  
   <span data-ttu-id="43048-115">**为自定义的 BAM 解决方案创建一个配置文件**</span><span class="sxs-lookup"><span data-stu-id="43048-115">**Creating a Profile for Customized BAM Solutions**</span></span>  
  
   <span data-ttu-id="43048-116">跟踪配置文件只与具有侦听器的运行时相关。</span><span class="sxs-lookup"><span data-stu-id="43048-116">Tracking profiles are only relevant to run-times that have an interceptor.</span></span> <span data-ttu-id="43048-117">对于由使用 BAM API 的自定义代码构成的 BAM 解决方案，没有任何关联的 BAM 运行时侦听器，并且可以采用以下两种方式之一将数据发送至 BAM：</span><span class="sxs-lookup"><span data-stu-id="43048-117">For BAM solutions that consist of custom code using the BAM APIs, there is no associated BAM run-time interceptor, and sending data to BAM can be done in only one of two ways:</span></span>  
  
- <span data-ttu-id="43048-118">直接通过 BAM API。</span><span class="sxs-lookup"><span data-stu-id="43048-118">Directly through the BAM APIs.</span></span> <span data-ttu-id="43048-119">使用 API，开发人员可以将事件数据显式发送至 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="43048-119">Using the APIs developers can explicitly send event data to the BAM infrastructure.</span></span> <span data-ttu-id="43048-120">有关使用 BAM Api 的详细信息，请参阅[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="43048-120">For more information about using the BAM APIs, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
- <span data-ttu-id="43048-121">通过间接，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="43048-121">Indirectly, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] properties.</span></span> <span data-ttu-id="43048-122">在此情况下，当调用自定义程序集时，将在某些具有关联的侦听技术（例如，自定义管道或表达式/操作形状）的运行时上下文中执行自定义代码。您可以按上述说明使用 BAM API，也可以使用传统的数据升级技术。</span><span class="sxs-lookup"><span data-stu-id="43048-122">In the case where the custom code is executing inside some run-time context that does have an associated interception technology, such as a custom pipeline - or expression/action shapes in invoking a custom assembly, You can use the BAM APIs as noted above or use traditional data promotion techniques.</span></span> <span data-ttu-id="43048-123">通过升级属性，可使 TPE 能够访问它们，并使用正确的上下文属性在 TPE 中关联事件数据和 BAM 活动项。</span><span class="sxs-lookup"><span data-stu-id="43048-123">By promoting the properties you make them accessible to the TPE and the association of that event data to a BAM activity item can then be made in the TPE using the correct context property.</span></span> <span data-ttu-id="43048-124">有关升级属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="43048-124">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43048-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="43048-125">In This Section</span></span>  
  
-   [<span data-ttu-id="43048-126">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="43048-126">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)  
  
-   [<span data-ttu-id="43048-127">如何删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="43048-127">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [<span data-ttu-id="43048-128">使用多个继续符</span><span class="sxs-lookup"><span data-stu-id="43048-128">Using Multiple Continuations</span></span>](../core/using-multiple-continuations.md)