---
title: 如何配置跟踪接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249101"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="caba9-102">如何配置跟踪接收端口</span><span class="sxs-lookup"><span data-stu-id="caba9-102">How to Configure Tracking for a Receive Port</span></span>
<span data-ttu-id="caba9-103">本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为接收端口配置跟踪，如查看消息正文和升级属性的选项。</span><span class="sxs-lookup"><span data-stu-id="caba9-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a receive port, such as options to view message bodies and promoted properties..</span></span> <span data-ttu-id="caba9-104">这可帮助你监视的运行状况你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现，并确定任何瓶颈。</span><span class="sxs-lookup"><span data-stu-id="caba9-104">This helps you monitor the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementation and identify any bottlenecks.</span></span> <span data-ttu-id="caba9-105">所配置的跟踪设置将应用于接收端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="caba9-105">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
 <span data-ttu-id="caba9-106">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[清单： 消息和实例数据跟踪](../core/checklist-message-and-instance-data-tracking.md)</span><span class="sxs-lookup"><span data-stu-id="caba9-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Message and Instance Data Tracking](../core/checklist-message-and-instance-data-tracking.md)</span></span>  
  
 <span data-ttu-id="caba9-107">所配置的跟踪设置将应用于接收端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="caba9-107">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="caba9-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="caba9-108">Prerequisites</span></span>  
 <span data-ttu-id="caba9-109">若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="caba9-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="caba9-110">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="caba9-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="caba9-111">为接收端口配置跟踪</span><span class="sxs-lookup"><span data-stu-id="caba9-111">To configure tracking for a receive port</span></span>  
  
1.  <span data-ttu-id="caba9-112">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="caba9-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="caba9-113">在控制台树中，展开要为其配置跟踪的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="caba9-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a receive port.</span></span>  
  
3.  <span data-ttu-id="caba9-114">单击**接收端口**，右键单击接收端口，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="caba9-114">Click **Receive Ports**, right-click the receive port and click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="caba9-115">启用之前接收端口上跟踪消息正文，请确保你想要在所有; 跟踪接收端口这可能是开销。</span><span class="sxs-lookup"><span data-stu-id="caba9-115">Before enabling the message body tracking on a receive port, ensure if you want to track the receive port at all; it could be an overhead.</span></span> <span data-ttu-id="caba9-116">例如，接收管道 RcvPipe 在不同接收端口中的多个接收位置上使用。</span><span class="sxs-lookup"><span data-stu-id="caba9-116">For example, a receive pipeline RcvPipe is used at several receive locations in different receive ports.</span></span> <span data-ttu-id="caba9-117">如果启用跟踪 RcvPipe 上的选项的消息正文时，它会导致对上所有接收位置，而你可能希望执行跟踪的消息正文。</span><span class="sxs-lookup"><span data-stu-id="caba9-117">If you enable the message body tracking option on RcvPipe, it leads to message body tracking on all the receive locations, which you might not want to do.</span></span> <span data-ttu-id="caba9-118">因此，设置该消息正文上跟踪接收端口根据你的要求。</span><span class="sxs-lookup"><span data-stu-id="caba9-118">Hence, set the message body tracking on receive ports as per your requirement.</span></span>  
  
4.  <span data-ttu-id="caba9-119">下表中所述配置所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="caba9-119">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="caba9-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="caba9-120">Use this</span></span>|<span data-ttu-id="caba9-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="caba9-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="caba9-122">**跟踪消息正文-端口处理前的请求消息**</span><span class="sxs-lookup"><span data-stu-id="caba9-122">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="caba9-123">选中此复选框可在接收消息之前保存并跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="caba9-123">Select this check box to save and track message content before the message is received.</span></span>|  
    |<span data-ttu-id="caba9-124">**跟踪消息正文-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="caba9-124">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="caba9-125">选中此复选框可在接收消息之后保存并跟踪消息内容。</span><span class="sxs-lookup"><span data-stu-id="caba9-125">Select this check box to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="caba9-126">**跟踪消息属性-端口处理前的请求消息**</span><span class="sxs-lookup"><span data-stu-id="caba9-126">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="caba9-127">选中此复选框可跟踪入站消息的升级属性。</span><span class="sxs-lookup"><span data-stu-id="caba9-127">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="caba9-128">**跟踪消息属性-端口处理后的请求消息**</span><span class="sxs-lookup"><span data-stu-id="caba9-128">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="caba9-129">如果需要，选中此复选框可跟踪出站消息已升级的属性。</span><span class="sxs-lookup"><span data-stu-id="caba9-129">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="caba9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="caba9-130">See Also</span></span>  
 [<span data-ttu-id="caba9-131">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="caba9-131">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)