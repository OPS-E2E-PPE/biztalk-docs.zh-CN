---
title: "启用管道跟踪 |Microsoft 文档"
description: "跟踪消息正文和管道处理 BizTalk Server 中的消息时，事件"
ms.custom: 
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed836947ff47e21eeeb3bc306e94ea08f5464f0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a><span data-ttu-id="47407-103">配置 BizTalk Server 中跟踪的管道</span><span class="sxs-lookup"><span data-stu-id="47407-103">Configure pipeline tracking in BizTalk Server</span></span>
<span data-ttu-id="47407-104">使用 BizTalk Server 管理来配置跟踪的管道。</span><span class="sxs-lookup"><span data-stu-id="47407-104">Use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="47407-105">您可能会希望配置跟踪以进行故障排除和审核。</span><span class="sxs-lookup"><span data-stu-id="47407-105">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="47407-106">您可以查看消息属性、端口事件和消息事件。</span><span class="sxs-lookup"><span data-stu-id="47407-106">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="47407-107">您还可以跟踪消息事件和消息的端口事件。</span><span class="sxs-lookup"><span data-stu-id="47407-107">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="47407-108">对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供的任意默认管道或已部署到 BizTalk 应用程序中的自定义管道，您都可以配置跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="47407-108">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="47407-109">您配置的跟踪设置适用于相应管道的所有实例。</span><span class="sxs-lookup"><span data-stu-id="47407-109">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47407-110">虽然你可以配置为管道的跟踪，这会生成大量的数据，因为为使用管道的所有端口全局收集数据。</span><span class="sxs-lookup"><span data-stu-id="47407-110">Although you can configure tracking for a pipeline, this generates a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="47407-111">相反，我们建议你配置跟踪你发送和接收端口中, 所述[发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)和[配置为接收端口跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="47407-111">Instead, we recommend that you configure tracking on your send and receive ports, as described in [Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="47407-112">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="47407-112">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="47407-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="47407-113">Prerequisites</span></span>  
<span data-ttu-id="47407-114">使用 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="47407-114">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="47407-115">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="47407-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-pipeline-tracking"></a><span data-ttu-id="47407-116">启用管道跟踪</span><span class="sxs-lookup"><span data-stu-id="47407-116">Enable pipeline tracking</span></span>
  
1.  <span data-ttu-id="47407-117">在**BizTalk Server 管理**，展开包含管道的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="47407-117">In **BizTalk Server Administration**, expand the BizTalk group that contains the pipeline.</span></span> 
  
2.  <span data-ttu-id="47407-118">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="47407-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="47407-119">若要配置 BizTalk 管道跟踪的默认值之一，展开\<所有项目\>。</span><span class="sxs-lookup"><span data-stu-id="47407-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts\>.</span></span>  
  
    -   <span data-ttu-id="47407-120">若要为已部署到 BizTalk 应用程序中的自定义管道配置跟踪，请展开包含该管道的应用程序。</span><span class="sxs-lookup"><span data-stu-id="47407-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
3.  <span data-ttu-id="47407-121">选择**管道**文件夹中，右键单击管道，，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="47407-121">Select the **Pipelines** folder, right-click the pipeline, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47407-122">若要配置跟踪，同时，多个管道按住 Shift 键，选择要配置每个管道，右键单击其中一个管道，，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="47407-122">To configure tracking for multiple pipelines at once, hold down the Shift key, select each pipeline to configure, right-click one of the pipelines, and then select **Tracking**.</span></span>  
  
4.  <span data-ttu-id="47407-123">使用以下详细信息来配置跟踪所需的选项，然后选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="47407-123">Use the follwoing details to configure the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="47407-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="47407-124">Use this</span></span>|<span data-ttu-id="47407-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="47407-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="47407-126">**跟踪事件数-端口开始日期和结束事件**</span><span class="sxs-lookup"><span data-stu-id="47407-126">**Track Events - Port start and end events**</span></span>|<span data-ttu-id="47407-127">仅当实例开始和结束时跟踪。</span><span class="sxs-lookup"><span data-stu-id="47407-127">Tracks only when an instance starts and ends.</span></span> <span data-ttu-id="47407-128">详细信息包括项名称、程序集和其他元数据。</span><span class="sxs-lookup"><span data-stu-id="47407-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="47407-129">**跟踪事件的消息发送和接收事件**</span><span class="sxs-lookup"><span data-stu-id="47407-129">**Track Events - Message send and receive events**</span></span>|<span data-ttu-id="47407-130">跟踪消息发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="47407-130">Tracks message send and receive events.</span></span> <span data-ttu-id="47407-131">仅可用**端口开始和结束事件**选择。</span><span class="sxs-lookup"><span data-stu-id="47407-131">Only available if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="47407-132">**跟踪消息正文-在管道处理之前的消息**</span><span class="sxs-lookup"><span data-stu-id="47407-132">**Track Message Bodies - Messages before pipeline processing**</span></span>|<span data-ttu-id="47407-133">将保存并跟踪管道，其中包含元数据，例如 Url 并提升属性收到的消息正文。</span><span class="sxs-lookup"><span data-stu-id="47407-133">Saves and tracks the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="47407-134">如果是接收管道，则消息正文部分是传输组件提交给该管道的原始消息。</span><span class="sxs-lookup"><span data-stu-id="47407-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="47407-135">根据相应的应用程序，可能对该消息进行加密、签名或编码。</span><span class="sxs-lookup"><span data-stu-id="47407-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="47407-136">在使用 BizTalk 映射时，如果这是接收管道，则在处理完入站映射后进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="47407-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="47407-137">仅可用**消息发送和接收事件**选择。</span><span class="sxs-lookup"><span data-stu-id="47407-137">Only available if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="47407-138">**跟踪消息正文-在管道处理后的消息**</span><span class="sxs-lookup"><span data-stu-id="47407-138">**Track Message Bodies - Messages after pipeline processing**</span></span>|<span data-ttu-id="47407-139">将保存并跟踪发送管道，其中包含元数据，例如 Url 并提升属性的消息正文。</span><span class="sxs-lookup"><span data-stu-id="47407-139">Saves and tracks the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="47407-140">如果是接收管道，则消息正文部分是提交给 MessageBox 数据库的已处理消息（它可以是 XML，这取决于相应的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="47407-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="47407-141">在使用 BizTalk 映射时，如果这是发送管道，则在处理出站映射之前进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="47407-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="47407-142">仅可用**消息发送和接收事件**选择。</span><span class="sxs-lookup"><span data-stu-id="47407-142">Only available if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47407-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47407-143">See Also</span></span>  
 [<span data-ttu-id="47407-144">管理管道</span><span class="sxs-lookup"><span data-stu-id="47407-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)
