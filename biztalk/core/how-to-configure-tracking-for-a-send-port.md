---
title: 启用发送端口上的跟踪 |Microsoft Docs
description: 打开消息正文跟踪，并在 BizTalk Server 中的发送端口上跟踪消息属性
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578d48c5eefe4866de974b11f1171cf271a24156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385990"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a><span data-ttu-id="28c48-103">在 BizTalk Server 中配置发送端口跟踪</span><span class="sxs-lookup"><span data-stu-id="28c48-103">Configure send port tracking in BizTalk Server</span></span>
<span data-ttu-id="28c48-104">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置跟踪的发送端口，如选项来查看消息正文和升级属性。</span><span class="sxs-lookup"><span data-stu-id="28c48-104">Use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="28c48-105">这可帮助你监视 BizTalk 实施的运行状况并确定任何瓶颈。</span><span class="sxs-lookup"><span data-stu-id="28c48-105">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="28c48-106">你配置的跟踪设置适用于所有发送端口的实例。</span><span class="sxs-lookup"><span data-stu-id="28c48-106">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="28c48-107">有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="28c48-107">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28c48-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="28c48-108">Prerequisites</span></span>  
<span data-ttu-id="28c48-109">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="28c48-109">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="28c48-110">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="28c48-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-tracking-on-a-send-port"></a><span data-ttu-id="28c48-111">启用发送端口上的跟踪</span><span class="sxs-lookup"><span data-stu-id="28c48-111">Enable tracking on a send port</span></span>  
  
1.  <span data-ttu-id="28c48-112">在中**BizTalk Server 管理**，展开 BizTalk 组，然后展开 BizTalk 应用程序可以发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-112">In **BizTalk Server Administration**, expand the BizTalk group, and then expand your BizTalk application that has the send port.</span></span>  
  
2.  <span data-ttu-id="28c48-113">选择**发送端口**，右键单击发送端口，选择**属性**，然后选择**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="28c48-113">Select **Send Ports**, right-click the send port, select **Properties**, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28c48-114">一个发送端口可以只有一个发送管道与相关联。</span><span class="sxs-lookup"><span data-stu-id="28c48-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="28c48-115">如果发送管道上禁用消息正文跟踪，则不会跟踪在发送端口上。</span><span class="sxs-lookup"><span data-stu-id="28c48-115">If message body tracking is disabled on the send pipeline, then nothing is tracked on the send port.</span></span> <span data-ttu-id="28c48-116">在此类方案中，您可以禁用"跟踪"选项上的发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
3.  <span data-ttu-id="28c48-117">使用以下详细信息来启用的跟踪选项，然后选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="28c48-117">Use the following details to enable the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="28c48-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="28c48-118">Use this</span></span>|<span data-ttu-id="28c48-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="28c48-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="28c48-120">**跟踪消息正文-端口处理前请求消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="28c48-121">保存并接收消息前跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="28c48-121">Saves and tracks message content before the message is received.</span></span> <br/><br/> <span data-ttu-id="28c48-122">**请注意**:请务必启用消息正文管道跟踪成功跟踪端口处理前的响应消息。</span><span class="sxs-lookup"><span data-stu-id="28c48-122">**Note**: Be sure to enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="28c48-123">**跟踪消息正文-端口处理后请求消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="28c48-124">保存并跟踪消息内容后接收消息。</span><span class="sxs-lookup"><span data-stu-id="28c48-124">Saves and tracks message content after the message is received.</span></span>|  
    |<span data-ttu-id="28c48-125">**跟踪消息正文-端口处理前响应消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-125">**Track Message Bodies – Response message before port processing**</span></span>|<span data-ttu-id="28c48-126">保存并发送消息前跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="28c48-126">Saves and tracks message content before the message is sent.</span></span> <span data-ttu-id="28c48-127">仅适用于要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-127">Only available for solicit-response send ports.</span></span>|    
    |<span data-ttu-id="28c48-128">**跟踪消息正文-端口处理后响应消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-128">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="28c48-129">保存并跟踪消息内容后将消息发送。</span><span class="sxs-lookup"><span data-stu-id="28c48-129">Saves and tracks message content after the message is sent.</span></span> <span data-ttu-id="28c48-130">仅适用于要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-130">Only available for solicit-response send ports.</span></span>|  
    |<span data-ttu-id="28c48-131">**跟踪消息正文-端口处理后响应消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-131">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="28c48-132">跟踪入站消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="28c48-132">Tracks the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="28c48-133">**跟踪消息属性-端口处理后请求消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-133">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="28c48-134">跟踪出站消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="28c48-134">Tracks the promoted properties of an outbound message.</span></span>|  
    |<span data-ttu-id="28c48-135">**跟踪消息属性-端口处理前响应消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-135">**Track Message Properties – Response message before port processing**</span></span>|<span data-ttu-id="28c48-136">保存并发送消息前跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="28c48-136">Saves and tracks message properties before the message is sent.</span></span> <span data-ttu-id="28c48-137">仅适用于要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-137">Only available for solicit-response send ports.</span></span>|   
    |<span data-ttu-id="28c48-138">**跟踪消息属性-端口处理后响应消息**</span><span class="sxs-lookup"><span data-stu-id="28c48-138">**Track Message Properties – Response message after port processing**</span></span>|<span data-ttu-id="28c48-139">保存并发送消息之后跟踪属性。</span><span class="sxs-lookup"><span data-stu-id="28c48-139">Saves and tracks properties after the message is sent.</span></span> <span data-ttu-id="28c48-140">仅适用于要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="28c48-140">Only available for solicit-response send ports.</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="28c48-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="28c48-141">See Also</span></span>  
 [<span data-ttu-id="28c48-142">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="28c48-142">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)
