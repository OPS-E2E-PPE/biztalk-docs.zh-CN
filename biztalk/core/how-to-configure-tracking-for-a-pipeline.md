---
title: 启用管道跟踪 |Microsoft Docs
description: 跟踪消息正文和管道处理 BizTalk Server 中的消息时的事件
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689d5395d75a558e3f437c4a3efea13c70f593e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385871"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a><span data-ttu-id="035c8-103">跟踪 BizTalk Server 中的管道配置</span><span class="sxs-lookup"><span data-stu-id="035c8-103">Configure pipeline tracking in BizTalk Server</span></span>
<span data-ttu-id="035c8-104">使用 BizTalk Server 管理为管道配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="035c8-104">Use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="035c8-105">您可能想要配置用于故障排除和审核目的的跟踪。</span><span class="sxs-lookup"><span data-stu-id="035c8-105">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="035c8-106">您可以查看消息属性、 端口事件和消息事件。</span><span class="sxs-lookup"><span data-stu-id="035c8-106">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="035c8-107">您还可以跟踪消息事件和消息的端口事件。</span><span class="sxs-lookup"><span data-stu-id="035c8-107">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="035c8-108">您可以配置跟踪功能的任意默认管道中包含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或已部署到 BizTalk 应用程序中的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="035c8-108">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="035c8-109">你配置的跟踪设置适用于所有管道的实例。</span><span class="sxs-lookup"><span data-stu-id="035c8-109">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="035c8-110">尽管可以配置跟踪的管道，但因为使用管道的所有端口全局性地都收集数据这会生成大量的数据。</span><span class="sxs-lookup"><span data-stu-id="035c8-110">Although you can configure tracking for a pipeline, this generates a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="035c8-111">相反，我们建议你配置跟踪上发送和接收端口，如中所述[为发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)并[配置为接收端口跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="035c8-111">Instead, we recommend that you configure tracking on your send and receive ports, as described in [Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="035c8-112">有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="035c8-112">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="035c8-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="035c8-113">Prerequisites</span></span>  
<span data-ttu-id="035c8-114">使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="035c8-114">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="035c8-115">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="035c8-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-pipeline-tracking"></a><span data-ttu-id="035c8-116">启用管道跟踪</span><span class="sxs-lookup"><span data-stu-id="035c8-116">Enable pipeline tracking</span></span>
  
1.  <span data-ttu-id="035c8-117">在中**BizTalk Server 管理**，包含管道的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="035c8-117">In **BizTalk Server Administration**, expand the BizTalk group that contains the pipeline.</span></span> 
  
2.  <span data-ttu-id="035c8-118">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="035c8-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="035c8-119">若要配置跟踪的默认 BizTalk 管道，请展开\<的所有项目\>。</span><span class="sxs-lookup"><span data-stu-id="035c8-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts\>.</span></span>  
  
    -   <span data-ttu-id="035c8-120">若要配置已部署到 BizTalk 应用程序的自定义管道的跟踪，请展开包含管道的应用程序。</span><span class="sxs-lookup"><span data-stu-id="035c8-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
3.  <span data-ttu-id="035c8-121">选择**管道**文件夹中，右键单击该管道，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="035c8-121">Select the **Pipelines** folder, right-click the pipeline, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="035c8-122">要在一次，多个管道按住 Shift 键，选择要配置每个管道配置跟踪，请右键单击一个管道，并选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="035c8-122">To configure tracking for multiple pipelines at once, hold down the Shift key, select each pipeline to configure, right-click one of the pipelines, and then select **Tracking**.</span></span>  
  
4.  <span data-ttu-id="035c8-123">使用以下详细信息来配置的跟踪选项，然后选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="035c8-123">Use the follwoing details to configure the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="035c8-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="035c8-124">Use this</span></span>|<span data-ttu-id="035c8-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="035c8-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="035c8-126">**跟踪事件-端口开始和结束事件**</span><span class="sxs-lookup"><span data-stu-id="035c8-126">**Track Events - Port start and end events**</span></span>|<span data-ttu-id="035c8-127">仅当实例开始和结束跟踪。</span><span class="sxs-lookup"><span data-stu-id="035c8-127">Tracks only when an instance starts and ends.</span></span> <span data-ttu-id="035c8-128">详细信息包括项名称、 程序集和其他元数据。</span><span class="sxs-lookup"><span data-stu-id="035c8-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="035c8-129">**跟踪事件-消息发送和接收事件**</span><span class="sxs-lookup"><span data-stu-id="035c8-129">**Track Events - Message send and receive events**</span></span>|<span data-ttu-id="035c8-130">跟踪消息发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="035c8-130">Tracks message send and receive events.</span></span> <span data-ttu-id="035c8-131">只有**端口开始和结束事件**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="035c8-131">Only available if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="035c8-132">**跟踪消息正文-管道处理前的消息**</span><span class="sxs-lookup"><span data-stu-id="035c8-132">**Track Message Bodies - Messages before pipeline processing**</span></span>|<span data-ttu-id="035c8-133">保存并跟踪管道，其中包含元数据，例如 Url 和升级属性收到的消息正文。</span><span class="sxs-lookup"><span data-stu-id="035c8-133">Saves and tracks the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="035c8-134">如果这是接收管道，消息正文是原始消息由传输组件提交到管道。</span><span class="sxs-lookup"><span data-stu-id="035c8-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="035c8-135">根据应用程序，该消息可能加密、 签名，或编码。</span><span class="sxs-lookup"><span data-stu-id="035c8-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="035c8-136">在使用 BizTalk 映射时，如果这是接收管道，跟踪都将处理入站的映射后进行。</span><span class="sxs-lookup"><span data-stu-id="035c8-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="035c8-137">只有**消息发送和接收事件**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="035c8-137">Only available if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="035c8-138">**跟踪消息正文-管道处理后的消息**</span><span class="sxs-lookup"><span data-stu-id="035c8-138">**Track Message Bodies - Messages after pipeline processing**</span></span>|<span data-ttu-id="035c8-139">保存并跟踪管道，其中包含元数据，例如 Url 和升级的属性发送的消息正文。</span><span class="sxs-lookup"><span data-stu-id="035c8-139">Saves and tracks the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="035c8-140">如果这是接收管道，消息正文是已处理的消息提交到 MessageBox 数据库，这可以是 XML，具体取决于你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="035c8-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="035c8-141">在使用 BizTalk 映射时，如果这是发送管道，跟踪都将处理出站映射之前进行。</span><span class="sxs-lookup"><span data-stu-id="035c8-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="035c8-142">只有**消息发送和接收事件**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="035c8-142">Only available if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="035c8-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="035c8-143">See Also</span></span>  
 [<span data-ttu-id="035c8-144">管理管道</span><span class="sxs-lookup"><span data-stu-id="035c8-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)
