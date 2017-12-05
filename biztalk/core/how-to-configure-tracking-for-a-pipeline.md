---
title: "如何配置跟踪为管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [pipelines], tracking warning
- tracking, pipelines
- tracking, warnings
- configuring, pipelines
- pipelines, tracking
- managing [pipelines], configuring
- tracking, configuring
- pipelines, configuring
- configuring [HAT tracking], pipelines
- HAT, pipelines
- managing [pipelines], tracking
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f34abe4d9d8b97b1c61bfc6201c3d36b977d0697
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-tracking-for-a-pipeline"></a><span data-ttu-id="a7044-102">如何配置跟踪为管道</span><span class="sxs-lookup"><span data-stu-id="a7044-102">How to Configure Tracking for a Pipeline</span></span>
<span data-ttu-id="a7044-103">本主题将介绍如何使用 BizTalk Server 管理为管道配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="a7044-103">This topic describes how to use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="a7044-104">您可能会希望配置跟踪以进行故障排除和审核。</span><span class="sxs-lookup"><span data-stu-id="a7044-104">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="a7044-105">您可以查看消息属性、端口事件和消息事件。</span><span class="sxs-lookup"><span data-stu-id="a7044-105">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="a7044-106">您还可以跟踪消息事件和消息的端口事件。</span><span class="sxs-lookup"><span data-stu-id="a7044-106">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="a7044-107">对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供的任意默认管道或已部署到 BizTalk 应用程序中的自定义管道，您都可以配置跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="a7044-107">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="a7044-108">您配置的跟踪设置适用于相应管道的所有实例。</span><span class="sxs-lookup"><span data-stu-id="a7044-108">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7044-109">虽然可以为管道配置跟踪，但是，这将会生成大量的数据，因为这会对使用管道的所有端口全局性地收集数据。</span><span class="sxs-lookup"><span data-stu-id="a7044-109">Although you can configure tracking for a pipeline, this will generate a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="a7044-110">我们建议改为你配置跟踪你发送和接收端口中, 所述[如何配置跟踪发送端口](../core/how-to-configure-tracking-for-a-send-port.md)和[如何配置跟踪接收端口](../core/how-to-configure-tracking-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="a7044-110">We recommend instead that you configure tracking on your send and receive ports, as described in [How to Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="a7044-111">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="a7044-111">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7044-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="a7044-112">Prerequisites</span></span>  
 <span data-ttu-id="a7044-113">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a7044-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a7044-114">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a7044-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-pipeline"></a><span data-ttu-id="a7044-115">为管道配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a7044-115">To configure tracking for a pipeline</span></span>  
  
1.  <span data-ttu-id="a7044-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a7044-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a7044-117">在控制台树中，展开**BizTalk Server 管理**展开包含要为其配置跟踪管道的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="a7044-117">In the console tree, expand **BizTalk Server Administration** and expand the BizTalk group containing the pipeline for which to configure tracking.</span></span>  
  
3.  <span data-ttu-id="a7044-118">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="a7044-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="a7044-119">若要配置 BizTalk 管道跟踪的默认值之一，展开\<所有项目\>。</span><span class="sxs-lookup"><span data-stu-id="a7044-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts\>.</span></span>  
  
    -   <span data-ttu-id="a7044-120">若要为已部署到 BizTalk 应用程序中的自定义管道配置跟踪，请展开包含该管道的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7044-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
4.  <span data-ttu-id="a7044-121">单击**管道**文件夹，右键单击管道，，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a7044-121">Click the **Pipelines** folder, right-click the pipeline, and then click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7044-122">若要配置跟踪在一次，多个管道按住 Shift 键，单击要配置每个管道，右键单击其中一个管道，并依次**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a7044-122">To configure tracking for multiple pipelines at once, hold down the Shift key, click each pipeline to configure, right-click one of the pipelines, and then click **Tracking**.</span></span>  
  
5.  <span data-ttu-id="a7044-123">下表中所述配置所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a7044-123">Configure tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="a7044-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a7044-124">Use this</span></span>|<span data-ttu-id="a7044-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a7044-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a7044-126">**端口的开始和结束事件**</span><span class="sxs-lookup"><span data-stu-id="a7044-126">**Port start and end events**</span></span>|<span data-ttu-id="a7044-127">选中此复选框则仅在实例开始和结束时进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="a7044-127">Select this check box to track only when an instance starts and ends.</span></span> <span data-ttu-id="a7044-128">详细信息包括项名称、程序集和其他元数据。</span><span class="sxs-lookup"><span data-stu-id="a7044-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="a7044-129">**消息发送和接收事件**</span><span class="sxs-lookup"><span data-stu-id="a7044-129">**Message send and receive events**</span></span>|<span data-ttu-id="a7044-130">选中此复选框可跟踪消息发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="a7044-130">Select this check box to track message send and receive events.</span></span> <span data-ttu-id="a7044-131">此复选框才可用才**端口开始和结束事件**选择。</span><span class="sxs-lookup"><span data-stu-id="a7044-131">This check box is available only if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="a7044-132">**在管道处理之前的消息**</span><span class="sxs-lookup"><span data-stu-id="a7044-132">**Messages before pipeline processing**</span></span>|<span data-ttu-id="a7044-133">选中此复选框可保存并跟踪管道接收到的消息正文，其中包含诸如 URL 和已升级属性之类的元数据。</span><span class="sxs-lookup"><span data-stu-id="a7044-133">Select this check box to save and track the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="a7044-134">如果是接收管道，则消息正文部分是传输组件提交给该管道的原始消息。</span><span class="sxs-lookup"><span data-stu-id="a7044-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="a7044-135">根据相应的应用程序，可能对该消息进行加密、签名或编码。</span><span class="sxs-lookup"><span data-stu-id="a7044-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="a7044-136">在使用 BizTalk 映射时，如果这是接收管道，则在处理完入站映射后进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="a7044-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="a7044-137">此复选框才可用才**消息发送和接收事件**选择。</span><span class="sxs-lookup"><span data-stu-id="a7044-137">This check box is available only if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="a7044-138">**在管道处理后的消息**</span><span class="sxs-lookup"><span data-stu-id="a7044-138">**Messages after pipeline processing**</span></span>|<span data-ttu-id="a7044-139">选中此复选框可保存并跟踪管道发送的消息正文，其中包含诸如 URL 和已升级属性之类的元数据。</span><span class="sxs-lookup"><span data-stu-id="a7044-139">Select this check box to save and track the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="a7044-140">如果是接收管道，则消息正文部分是提交给 MessageBox 数据库的已处理消息（它可以是 XML，这取决于相应的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="a7044-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="a7044-141">在使用 BizTalk 映射时，如果这是发送管道，则在处理出站映射之前进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="a7044-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="a7044-142">此复选框才可用才**消息发送和接收事件**选择。</span><span class="sxs-lookup"><span data-stu-id="a7044-142">This check box is available only if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7044-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7044-143">See Also</span></span>  
 [<span data-ttu-id="a7044-144">管理管道</span><span class="sxs-lookup"><span data-stu-id="a7044-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)