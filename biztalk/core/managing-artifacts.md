---
title: 管理项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262253"
---
# <a name="managing-artifacts"></a><span data-ttu-id="843ef-102">管理项目</span><span class="sxs-lookup"><span data-stu-id="843ef-102">Managing Artifacts</span></span>
<span data-ttu-id="843ef-103">本部分介绍如何管理项目，包括如何在 BizTalk 应用程序中添加和删除项目，以及如何配置项目的属性。</span><span class="sxs-lookup"><span data-stu-id="843ef-103">This section describes how to manage artifacts, including how to add and remove them from a BizTalk application and how to configure their properties.</span></span>  
  
 <span data-ttu-id="843ef-104">项目是 BizTalk 应用程序中包含的项，BizTalk 应用程序运行时需要它们。</span><span class="sxs-lookup"><span data-stu-id="843ef-104">Artifacts are the items contained in a BizTalk application that are required for it to run.</span></span> <span data-ttu-id="843ef-105">有关如何在 BizTalk 应用程序中使用的项目的背景信息，请参阅[BizTalk 应用程序是什么？](../core/what-is-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="843ef-105">For background information about how artifacts are used in a BizTalk application, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md)</span></span> <span data-ttu-id="843ef-106">有关项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="843ef-106">For background information about artifacts, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="843ef-107">有关如何创建和修改 BizTalk 应用程序时操作项目的信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="843ef-107">For information about how you manipulate artifacts when you create and modify a BizTalk application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span>  

## <a name="tracking-artifacts"></a><span data-ttu-id="843ef-108">跟踪的项目</span><span class="sxs-lookup"><span data-stu-id="843ef-108">Tracking artifacts</span></span>
<span data-ttu-id="843ef-109">管理你创建的项目的重要部分跟踪。</span><span class="sxs-lookup"><span data-stu-id="843ef-109">A big part of managing the artifacts you create is tracking.</span></span> <span data-ttu-id="843ef-110">您可以使用 BizTalk Server 管理控制台为业务流程、发送端口、接收端口和管道配置不同的运行时跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="843ef-110">You can configure various tracking options during run time for orchestrations, send ports, receive ports, and pipelines using the BizTalk Server Administration console.</span></span> <span data-ttu-id="843ef-111">您随时可以在不中断业务流程的情况下更改某项的跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="843ef-111">You can change the tracking options for an item at any time, without interrupting the business process.</span></span>

<span data-ttu-id="843ef-112">使用跟踪配置设置，可以跟踪以下类型的数据：</span><span class="sxs-lookup"><span data-stu-id="843ef-112">The tracking configuration settings allow you to track the following types of data:</span></span>

- <span data-ttu-id="843ef-113">入站和/或出站事件数据。</span><span class="sxs-lookup"><span data-stu-id="843ef-113">Inbound and/or outbound event data.</span></span> <span data-ttu-id="843ef-114">例如，消息 ID、项目的开始和结束时间。</span><span class="sxs-lookup"><span data-stu-id="843ef-114">For example, message ID, start and stop times for the artifact.</span></span>

- <span data-ttu-id="843ef-115">入站和/或出站消息属性。</span><span class="sxs-lookup"><span data-stu-id="843ef-115">Inbound and/or outbound message properties.</span></span> <span data-ttu-id="843ef-116">例如，项目所处理的各消息的一般和升级的属性。</span><span class="sxs-lookup"><span data-stu-id="843ef-116">For example, general and promoted properties for each message that the artifact processes.</span></span>

- <span data-ttu-id="843ef-117">入站和/或出站消息正文和部分。</span><span class="sxs-lookup"><span data-stu-id="843ef-117">Inbound and/or outbound message bodies and parts.</span></span> <span data-ttu-id="843ef-118">例如，项目所处理的各消息的正文和部分。</span><span class="sxs-lookup"><span data-stu-id="843ef-118">For example, body and parts for each message that the artifact processes.</span></span>

- <span data-ttu-id="843ef-119">业务流程。</span><span class="sxs-lookup"><span data-stu-id="843ef-119">Orchestrations.</span></span> <span data-ttu-id="843ef-120">业务流程形状的执行数据。</span><span class="sxs-lookup"><span data-stu-id="843ef-120">Execution data for orchestration shapes.</span></span>

<span data-ttu-id="843ef-121">[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)提供了一些良好的信息。</span><span class="sxs-lookup"><span data-stu-id="843ef-121">[Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md) provides some good info.</span></span> 


> [!TIP]
> <span data-ttu-id="843ef-122">如果你设置跟踪选项卡上的管道，然后跟踪选项设置全局使用管道的每个端口。</span><span class="sxs-lookup"><span data-stu-id="843ef-122">If you set tracking options on a pipeline, then the tracking options are set globally for every port that uses the pipeline.</span></span> <span data-ttu-id="843ef-123">这会导致不是你可能想，并可能会影响系统性能被跟踪的更多数据。</span><span class="sxs-lookup"><span data-stu-id="843ef-123">This results in far more data being tracked than you may intend, and may impact system performance.</span></span> <span data-ttu-id="843ef-124">在开发期间，这可能是正常的内容。</span><span class="sxs-lookup"><span data-stu-id="843ef-124">During development, this may be normal.</span></span> <span data-ttu-id="843ef-125">在生产方案中，我们建议你启用发送端口上的任何跟踪选项并接收端口，而不是管道。</span><span class="sxs-lookup"><span data-stu-id="843ef-125">In production scenarios, we recommend you enable any tracking options on the send ports and receive ports, instead of the pipelines.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="843ef-126">在本节中</span><span class="sxs-lookup"><span data-stu-id="843ef-126">In this section</span></span>  
  
-   [<span data-ttu-id="843ef-127">管理业务流程</span><span class="sxs-lookup"><span data-stu-id="843ef-127">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)  
  
-   [<span data-ttu-id="843ef-128">管理角色链接</span><span class="sxs-lookup"><span data-stu-id="843ef-128">Managing Role Links</span></span>](../core/managing-role-links.md)  
  
-   [<span data-ttu-id="843ef-129">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="843ef-129">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [<span data-ttu-id="843ef-130">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="843ef-130">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)  
  
-   [<span data-ttu-id="843ef-131">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="843ef-131">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)  
  
-   [<span data-ttu-id="843ef-132">管理策略</span><span class="sxs-lookup"><span data-stu-id="843ef-132">Managing Policies</span></span>](../core/managing-policies.md)  
  
-   [<span data-ttu-id="843ef-133">管理架构</span><span class="sxs-lookup"><span data-stu-id="843ef-133">Managing Schemas</span></span>](../core/managing-schemas.md)  
  
-   [<span data-ttu-id="843ef-134">管理映射</span><span class="sxs-lookup"><span data-stu-id="843ef-134">Managing Maps</span></span>](../core/managing-maps.md)  
  
-   [<span data-ttu-id="843ef-135">管理管道</span><span class="sxs-lookup"><span data-stu-id="843ef-135">Managing Pipelines</span></span>](../core/managing-pipelines.md)  
  
-   [<span data-ttu-id="843ef-136">管理资源</span><span class="sxs-lookup"><span data-stu-id="843ef-136">Managing Resources</span></span>](../core/managing-resources.md)