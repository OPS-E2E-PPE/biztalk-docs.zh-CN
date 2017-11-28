---
title: "如何配置发送端口的跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a><span data-ttu-id="91fe7-102">如何为发送端口配置跟踪</span><span class="sxs-lookup"><span data-stu-id="91fe7-102">How to Configure Tracking for a Send Port</span></span>
<span data-ttu-id="91fe7-103">本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送端口的跟踪，例如用于查看消息正文和升级属性的选项。</span><span class="sxs-lookup"><span data-stu-id="91fe7-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="91fe7-104">这有助于您监视 BizTalk 实施的运行状况并确定存在的任何瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="91fe7-104">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="91fe7-105">所配置的跟踪设置将应用于发送端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="91fe7-105">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="91fe7-106">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="91fe7-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91fe7-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="91fe7-107">Prerequisites</span></span>  
 <span data-ttu-id="91fe7-108">若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="91fe7-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="91fe7-109">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="91fe7-109">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-send-port"></a><span data-ttu-id="91fe7-110">为发送端口配置跟踪</span><span class="sxs-lookup"><span data-stu-id="91fe7-110">To configure tracking for a send port</span></span>  
  
1.  <span data-ttu-id="91fe7-111">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="91fe7-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="91fe7-112">在控制台树中，展开要为其配置跟踪的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="91fe7-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a send port.</span></span>  
  
3.  <span data-ttu-id="91fe7-113">单击**发送端口**，右键单击发送端口，请单击**属性**，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="91fe7-113">Click **Send Ports**, right-click the send port, click **Properties**, and then click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91fe7-114">一个发送端口只能与一个发送管道相关联。</span><span class="sxs-lookup"><span data-stu-id="91fe7-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="91fe7-115">如果在发送管道上禁用消息正文跟踪，则在发送端口上也无法跟踪任何东西。</span><span class="sxs-lookup"><span data-stu-id="91fe7-115">If message body tracking is disabled on the send pipeline, nothing can be tracked on the send port as well.</span></span> <span data-ttu-id="91fe7-116">在这种情况中，您可以禁用该发送端口上的“跟踪”选项。</span><span class="sxs-lookup"><span data-stu-id="91fe7-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
4.  <span data-ttu-id="91fe7-117">下表中所述配置所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91fe7-117">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="91fe7-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="91fe7-118">Use this</span></span>|<span data-ttu-id="91fe7-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="91fe7-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="91fe7-120">**跟踪消息正文-端口处理前的请求消息**</span><span class="sxs-lookup"><span data-stu-id="91fe7-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="91fe7-121">选中此复选框，以便你能够保存和跟踪消息内容之前收到的消息。</span><span class="sxs-lookup"><span data-stu-id="91fe7-121">Select this check box to enable you to save and track message content before the message is received.</span></span> <span data-ttu-id="91fe7-122">**注意：**必须启用邮件正文管道跟踪成功跟踪端口处理前的响应消息。</span><span class="sxs-lookup"><span data-stu-id="91fe7-122">**Note:**  You must enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="91fe7-123">**跟踪消息正文-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="91fe7-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="91fe7-124">选中此复选框，以便你能够保存和跟踪消息内容后收到的消息。</span><span class="sxs-lookup"><span data-stu-id="91fe7-124">Select this check box to enable you to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="91fe7-125">**跟踪消息属性-端口处理前的请求消息**</span><span class="sxs-lookup"><span data-stu-id="91fe7-125">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="91fe7-126">选中此复选框可跟踪入站消息的升级属性。</span><span class="sxs-lookup"><span data-stu-id="91fe7-126">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="91fe7-127">**跟踪消息属性-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="91fe7-127">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="91fe7-128">如果需要，选中此复选框可跟踪出站消息已升级的属性。</span><span class="sxs-lookup"><span data-stu-id="91fe7-128">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="91fe7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91fe7-129">See Also</span></span>  
 [<span data-ttu-id="91fe7-130">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="91fe7-130">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)