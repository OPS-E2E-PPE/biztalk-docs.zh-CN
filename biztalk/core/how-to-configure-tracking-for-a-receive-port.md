---
title: 如何配置跟踪的接收端口 |Microsoft Docs
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
ms.openlocfilehash: a6f45158939210c3b084aa29234bee1b4a032b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385897"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="2a04f-102">如何配置跟踪的接收端口</span><span class="sxs-lookup"><span data-stu-id="2a04f-102">How to Configure Tracking for a Receive Port</span></span>
<span data-ttu-id="2a04f-103">本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台配置跟踪的接收端口，如选项来查看消息正文和升级属性...</span><span class="sxs-lookup"><span data-stu-id="2a04f-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a receive port, such as options to view message bodies and promoted properties..</span></span> <span data-ttu-id="2a04f-104">这可帮助你监视的运行状况在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现并识别任何瓶颈。</span><span class="sxs-lookup"><span data-stu-id="2a04f-104">This helps you monitor the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementation and identify any bottlenecks.</span></span> <span data-ttu-id="2a04f-105">你配置的跟踪设置适用于所有的接收端口的实例。</span><span class="sxs-lookup"><span data-stu-id="2a04f-105">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
 <span data-ttu-id="2a04f-106">有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[核对清单：消息和实例数据跟踪](../core/checklist-message-and-instance-data-tracking.md)</span><span class="sxs-lookup"><span data-stu-id="2a04f-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Message and Instance Data Tracking](../core/checklist-message-and-instance-data-tracking.md)</span></span>  
  
 <span data-ttu-id="2a04f-107">你配置的跟踪设置适用于所有的接收端口的实例。</span><span class="sxs-lookup"><span data-stu-id="2a04f-107">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a04f-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="2a04f-108">Prerequisites</span></span>  
 <span data-ttu-id="2a04f-109">若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="2a04f-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="2a04f-110">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2a04f-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="2a04f-111">若要配置跟踪的接收端口</span><span class="sxs-lookup"><span data-stu-id="2a04f-111">To configure tracking for a receive port</span></span>  
  
1. <span data-ttu-id="2a04f-112">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2a04f-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2a04f-113">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置跟踪的接收端口。</span><span class="sxs-lookup"><span data-stu-id="2a04f-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a receive port.</span></span>  
  
3. <span data-ttu-id="2a04f-114">单击**接收端口**，右键单击该接收端口，然后单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="2a04f-114">Click **Receive Ports**, right-click the receive port and click **Tracking**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2a04f-115">启用消息正文跟踪，接收端口之前, 请确保你想要在所有; 跟踪接收端口这可能是一项开销。</span><span class="sxs-lookup"><span data-stu-id="2a04f-115">Before enabling the message body tracking on a receive port, ensure if you want to track the receive port at all; it could be an overhead.</span></span> <span data-ttu-id="2a04f-116">例如，接收管道 RcvPipe 在不同的接收端口中的多个接收位置使用。</span><span class="sxs-lookup"><span data-stu-id="2a04f-116">For example, a receive pipeline RcvPipe is used at several receive locations in different receive ports.</span></span> <span data-ttu-id="2a04f-117">如果启用消息正文跟踪在 RcvPipe 上的选项，它会导致对所有接收位置，而您可能不想要执行跟踪消息正文。</span><span class="sxs-lookup"><span data-stu-id="2a04f-117">If you enable the message body tracking option on RcvPipe, it leads to message body tracking on all the receive locations, which you might not want to do.</span></span> <span data-ttu-id="2a04f-118">因此，设置消息正文跟踪在接收端口根据你的要求。</span><span class="sxs-lookup"><span data-stu-id="2a04f-118">Hence, set the message body tracking on receive ports as per your requirement.</span></span>  
  
4. <span data-ttu-id="2a04f-119">下表中所述配置所需的跟踪选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2a04f-119">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="2a04f-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2a04f-120">Use this</span></span>|<span data-ttu-id="2a04f-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2a04f-121">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="2a04f-122">**跟踪消息正文-端口处理前请求消息**</span><span class="sxs-lookup"><span data-stu-id="2a04f-122">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="2a04f-123">选中此复选框可保存并跟踪消息内容之前接收消息。</span><span class="sxs-lookup"><span data-stu-id="2a04f-123">Select this check box to save and track message content before the message is received.</span></span>|  
   |<span data-ttu-id="2a04f-124">**跟踪消息正文-端口处理后请求消息**</span><span class="sxs-lookup"><span data-stu-id="2a04f-124">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="2a04f-125">选中此复选框可保存并跟踪消息内容后接收消息。</span><span class="sxs-lookup"><span data-stu-id="2a04f-125">Select this check box to save and track message content after the message is received.</span></span>|  
   |||  
   |||  
   |<span data-ttu-id="2a04f-126">**跟踪消息属性-端口处理前请求消息**</span><span class="sxs-lookup"><span data-stu-id="2a04f-126">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="2a04f-127">选择此复选框可跟踪入站消息的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="2a04f-127">Select this check box to track the promoted properties of an inbound message.</span></span>|  
   |<span data-ttu-id="2a04f-128">**跟踪消息属性-端口处理后请求消息**</span><span class="sxs-lookup"><span data-stu-id="2a04f-128">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="2a04f-129">如果你想要跟踪出站消息的升级的属性，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="2a04f-129">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
   |||  
   |||  
  
## <a name="see-also"></a><span data-ttu-id="2a04f-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a04f-130">See Also</span></span>  
 [<span data-ttu-id="2a04f-131">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="2a04f-131">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)