---
title: "启用发送端口上的跟踪 |Microsoft 文档"
description: "打开跟踪的消息正文，并在 BizTalk Server 发送端口上跟踪消息属性"
ms.custom: 
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 223c417769086cc71f501b044410bf2d3e4cbc74
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a><span data-ttu-id="ebdc0-103">在 BizTalk Server 中配置发送端口跟踪</span><span class="sxs-lookup"><span data-stu-id="ebdc0-103">Configure send port tracking in BizTalk Server</span></span>
<span data-ttu-id="ebdc0-104">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置跟踪发送端口，如选项，以查看消息正文和升级的属性。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-104">Use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="ebdc0-105">这有助于您监视 BizTalk 实施的运行状况并确定存在的任何瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-105">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="ebdc0-106">所配置的跟踪设置将应用于发送端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-106">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="ebdc0-107">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="ebdc0-107">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ebdc0-108">必备条件</span><span class="sxs-lookup"><span data-stu-id="ebdc0-108">Prerequisites</span></span>  
<span data-ttu-id="ebdc0-109">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-109">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="ebdc0-110">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-tracking-on-a-send-port"></a><span data-ttu-id="ebdc0-111">启用发送端口上的跟踪</span><span class="sxs-lookup"><span data-stu-id="ebdc0-111">Enable tracking on a send port</span></span>  
  
1.  <span data-ttu-id="ebdc0-112">在**BizTalk Server 管理**，展开 BizTalk 组，然后展开你的 BizTalk 应用程序具有发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-112">In **BizTalk Server Administration**, expand the BizTalk group, and then expand your BizTalk application that has the send port.</span></span>  
  
2.  <span data-ttu-id="ebdc0-113">选择**发送端口**，右键单击发送端口，选择**属性**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-113">Select **Send Ports**, right-click the send port, select **Properties**, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebdc0-114">一个发送端口只能与一个发送管道相关联。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="ebdc0-115">如果发送管道上禁用跟踪的消息正文，然后执行任何操作会跟踪上发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-115">If message body tracking is disabled on the send pipeline, then nothing is tracked on the send port.</span></span> <span data-ttu-id="ebdc0-116">在这种情况中，您可以禁用该发送端口上的“跟踪”选项。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
3.  <span data-ttu-id="ebdc0-117">使用以下详细信息来启用跟踪所需的选项，然后选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-117">Use the following details to enable the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="ebdc0-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ebdc0-118">Use this</span></span>|<span data-ttu-id="ebdc0-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ebdc0-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ebdc0-120">**跟踪消息正文-端口处理前的请求消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="ebdc0-121">将保存并在收到消息前跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-121">Saves and tracks message content before the message is received.</span></span> <br/><br/> <span data-ttu-id="ebdc0-122">**请注意**： 请务必启用消息正文管道跟踪来成功跟踪端口处理前的响应消息。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-122">**Note**: Be sure to enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="ebdc0-123">**跟踪消息正文-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="ebdc0-124">保存并消息后，收到的消息跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-124">Saves and tracks message content after the message is received.</span></span>|  
    |<span data-ttu-id="ebdc0-125">**跟踪消息正文-端口处理前的响应消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-125">**Track Message Bodies – Response message before port processing**</span></span>|<span data-ttu-id="ebdc0-126">将保存并发送消息前跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-126">Saves and tracks message content before the message is sent.</span></span> <span data-ttu-id="ebdc0-127">仅适用于请求作出响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-127">Only available for solicit-response send ports.</span></span>|    
    |<span data-ttu-id="ebdc0-128">**跟踪消息正文-端口处理后的响应消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-128">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="ebdc0-129">保存并消息后，将消息发送跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-129">Saves and tracks message content after the message is sent.</span></span> <span data-ttu-id="ebdc0-130">仅适用于请求作出响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-130">Only available for solicit-response send ports.</span></span>|  
    |<span data-ttu-id="ebdc0-131">**跟踪消息正文-端口处理后的响应消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-131">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="ebdc0-132">跟踪的入站消息提升的属性。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-132">Tracks the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="ebdc0-133">**跟踪消息属性-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-133">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="ebdc0-134">跟踪的出站消息提升的属性。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-134">Tracks the promoted properties of an outbound message.</span></span>|  
    |<span data-ttu-id="ebdc0-135">**跟踪消息属性 – 端口处理前的响应消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-135">**Track Message Properties – Response message before port processing**</span></span>|<span data-ttu-id="ebdc0-136">将保存并发送消息前跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-136">Saves and tracks message properties before the message is sent.</span></span> <span data-ttu-id="ebdc0-137">仅适用于请求作出响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-137">Only available for solicit-response send ports.</span></span>|   
    |<span data-ttu-id="ebdc0-138">**跟踪消息属性 – 端口处理后的响应消息**</span><span class="sxs-lookup"><span data-stu-id="ebdc0-138">**Track Message Properties – Response message after port processing**</span></span>|<span data-ttu-id="ebdc0-139">保存并消息后，将消息发送跟踪属性。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-139">Saves and tracks properties after the message is sent.</span></span> <span data-ttu-id="ebdc0-140">仅适用于请求作出响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="ebdc0-140">Only available for solicit-response send ports.</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="ebdc0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebdc0-141">See Also</span></span>  
 [<span data-ttu-id="ebdc0-142">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="ebdc0-142">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)
