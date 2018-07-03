---
title: 动态发送端口处理程序是可配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea7fb4a2f877baf70c0684c57b83e5f32edaa4d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971774"
---
# <a name="dynamic-send-port-handler-is-configurable"></a><span data-ttu-id="771c7-102">动态发送端口处理程序可配置</span><span class="sxs-lookup"><span data-stu-id="771c7-102">Dynamic Send Port Handler is Configurable</span></span>
<span data-ttu-id="771c7-103">创建动态发送端口时，可为*每个*安装的适配器配置适配器发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="771c7-103">When creating a Dynamic Send Port, an adapter Send Handler is configurable for *every* installed adapter.</span></span> <span data-ttu-id="771c7-104">请考虑下列方案：</span><span class="sxs-lookup"><span data-stu-id="771c7-104">Consider the following scenario:</span></span>  
  
 <span data-ttu-id="771c7-105">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="771c7-105">**Scenario**</span></span>  
  
 <span data-ttu-id="771c7-106">应用程序中有两个 ESB 行程。</span><span class="sxs-lookup"><span data-stu-id="771c7-106">There are two ESB itineraries in an application.</span></span> <span data-ttu-id="771c7-107">Itinerary1 使用动态发送端口向文件共享发送数据。</span><span class="sxs-lookup"><span data-stu-id="771c7-107">Itinerary1 uses a Dynamic Send Port to send data to a File share.</span></span> <span data-ttu-id="771c7-108">Itinerary2 使用动态发送端口发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="771c7-108">Itinerary2 uses a Dynamic Send Port to send e-mail.</span></span> <span data-ttu-id="771c7-109">以前，动态发送端口在适配器的默认主机中执行。</span><span class="sxs-lookup"><span data-stu-id="771c7-109">In the past, Dynamic send ports execute in the adapter's default host.</span></span> <span data-ttu-id="771c7-110">Itinerary1 针对“低容量 - 大消息大小”方案。</span><span class="sxs-lookup"><span data-stu-id="771c7-110">Itinerary1 is designed to target a low volume - big message size scenario.</span></span> <span data-ttu-id="771c7-111">Itinerary2 针对“高容量 - 小消息大小”方案。</span><span class="sxs-lookup"><span data-stu-id="771c7-111">Itinerary2 targets a high volume - small message size scenario.</span></span> <span data-ttu-id="771c7-112">由于适配器仅有一个默认主机，因此，所有消息均使用同一主机进行路由，导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="771c7-112">Since there is only one default host for an adapter, all messages are routed using the same host, decreasing the performance.</span></span>  
  
 <span data-ttu-id="771c7-113">**更改**</span><span class="sxs-lookup"><span data-stu-id="771c7-113">**The Change**</span></span>  
  
 <span data-ttu-id="771c7-114">为了提高动态发送端口的性能，可以将适配器发送处理程序配置为使用任何主机。</span><span class="sxs-lookup"><span data-stu-id="771c7-114">To improve the performance of Dynamic Send Ports, an adapter Send Handler is configurable to use any host.</span></span> <span data-ttu-id="771c7-115">在该 ESB 方案中，Itinerary1 使用 HostA 向文件共享发送数据。</span><span class="sxs-lookup"><span data-stu-id="771c7-115">In the ESB scenario, Itinerary1 uses HostA to send data to a File share.</span></span> <span data-ttu-id="771c7-116">Itinerary2 使用 HostB 端口发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="771c7-116">Itinerary2 uses HostB Port to send e-mail.</span></span>  
  
## <a name="select-a-send-handler"></a><span data-ttu-id="771c7-117">选择发送处理程序</span><span class="sxs-lookup"><span data-stu-id="771c7-117">Select a Send Handler</span></span>  
 <span data-ttu-id="771c7-118">当创建动态单向发送端口或动态要求响应发送端口时，可以为每个安装的适配器配置发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="771c7-118">When creating a Dynamic One-Way Send Port or Dynamic Solicit-Response Send Port, the Send Handler is configurable for every installed adapter.</span></span> <span data-ttu-id="771c7-119">步骤：</span><span class="sxs-lookup"><span data-stu-id="771c7-119">Steps:</span></span>  
  
1. <span data-ttu-id="771c7-120">在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="771c7-120">In the **BizTalk Server Administration** console, expand **BizTalk Group [*GroupName*]**, expand **Applications**, and then expand the application to contain the send port.</span></span>  
  
2. <span data-ttu-id="771c7-121">右键单击**发送端口**，单击**新建**，然后单击**动态单向发送端口**或者**动态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="771c7-121">Right-click **Send Ports**, click **New**, and then click **Dynamic One-way Send Port** or **Dynamic Solicit-Response Send Port**.</span></span>  
  
3. <span data-ttu-id="771c7-122">在中**属性**，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="771c7-122">In  **Properties**, click **Configure**.</span></span>  
  
    <span data-ttu-id="771c7-123">此时会列出适配器及默认发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="771c7-123">The adapters are listed with the default Send Handler.</span></span> <span data-ttu-id="771c7-124">单击向下箭头可选择其他主机。</span><span class="sxs-lookup"><span data-stu-id="771c7-124">Click the down arrow to select a different host.</span></span>  
  
4. <span data-ttu-id="771c7-125">单击**确定**保存设置。</span><span class="sxs-lookup"><span data-stu-id="771c7-125">Click **OK** save the settings.</span></span>  
  
5. <span data-ttu-id="771c7-126">取消登记并重新登记新的动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="771c7-126">Unenlist and reenlist the new dynamic send port.</span></span>  
  
6. <span data-ttu-id="771c7-127">重新启动原始主机实例。</span><span class="sxs-lookup"><span data-stu-id="771c7-127">Restart the original host instance.</span></span>  
  
7. <span data-ttu-id="771c7-128">重新启动新的主机实例。</span><span class="sxs-lookup"><span data-stu-id="771c7-128">Restart the new host instance.</span></span>  
  
   <span data-ttu-id="771c7-129">其他发送端口配置选项包括：</span><span class="sxs-lookup"><span data-stu-id="771c7-129">Additional Send Port configuration options include:</span></span>  
  
- [<span data-ttu-id="771c7-130">如何为发送端口配置传输高级选项</span><span class="sxs-lookup"><span data-stu-id="771c7-130">How to Configure Transport Advanced Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
- [<span data-ttu-id="771c7-131">如何为发送端口配置备份传输选项</span><span class="sxs-lookup"><span data-stu-id="771c7-131">How to Configure Backup Transport Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
- [<span data-ttu-id="771c7-132">如何配置发送端口的出站映射</span><span class="sxs-lookup"><span data-stu-id="771c7-132">How to Configure Outbound Maps for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
- [<span data-ttu-id="771c7-133">如何为发送端口配置筛选器</span><span class="sxs-lookup"><span data-stu-id="771c7-133">How to Configure Filters for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
- [<span data-ttu-id="771c7-134">如何为发送端口分配证书</span><span class="sxs-lookup"><span data-stu-id="771c7-134">How to Assign a Certificate to a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
- [<span data-ttu-id="771c7-135">如何为发送端口配置跟踪</span><span class="sxs-lookup"><span data-stu-id="771c7-135">How to Configure Tracking for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
  <span data-ttu-id="771c7-136">可以对其他主机进行微调。</span><span class="sxs-lookup"><span data-stu-id="771c7-136">The different hosts can be fine-tuned.</span></span> <span data-ttu-id="771c7-137">以下链接讨论了性能优化：</span><span class="sxs-lookup"><span data-stu-id="771c7-137">The following links discuss performance optimization:</span></span>  
  
  [<span data-ttu-id="771c7-138">一般 BizTalk Server 优化</span><span class="sxs-lookup"><span data-stu-id="771c7-138">General BizTalk Server Optimizations</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
  [<span data-ttu-id="771c7-139">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="771c7-139">Managing BizTalk Server Performance Settings</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267704)