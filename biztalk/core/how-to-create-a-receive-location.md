---
title: 如何创建接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceivelocation
helpviewer_keywords:
- receive locations, creating
- managing [receive locations], creating
- creating, receive locations
ms.assetid: ec0202cf-0e69-4ae2-aba6-8cd2c3c77e82
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08c58f61013d6ef0596ed234d10baa0c055c19e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339885"
---
# <a name="how-to-create-a-receive-location"></a><span data-ttu-id="7e5d1-102">如何创建接收位置</span><span class="sxs-lookup"><span data-stu-id="7e5d1-102">How to Create a Receive Location</span></span>
<span data-ttu-id="7e5d1-103">本主题介绍如何使用 BizTalk Server 管理控制台来创建新的接收位置，并指定其所属于的接收端口。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-103">This topic describes how to use the BizTalk Server Administration console to create a new receive location and specify the receive port to which it belongs.</span></span> <span data-ttu-id="7e5d1-104">接收位置是在入站的消息的到达以及处理在该地址接收的消息的消息传送管道的地址。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-104">A receive location is an address where inbound messages arrive as well as the messaging pipeline that processes messages received at that address.</span></span>  
  
 <span data-ttu-id="7e5d1-105">创建接收位置之前，接收端口必须存在此应用程序要创建的接收位置与相同的类型。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-105">Before you can create a receive location, a receive port must already exist in this application that of the same type as the receive location you want to create.</span></span> <span data-ttu-id="7e5d1-106">有关创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-106">For instructions on creating a receive port, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="7e5d1-107">您可以创建以下类型的接收位置：</span><span class="sxs-lookup"><span data-stu-id="7e5d1-107">You can create the following types of receive locations:</span></span>  
  
-   <span data-ttu-id="7e5d1-108">单向端口 — 用于丢弃消息并不等待同步回复的应用程序</span><span class="sxs-lookup"><span data-stu-id="7e5d1-108">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  
  
-   <span data-ttu-id="7e5d1-109">请求-响应 — 用于要求对消息的响应的应用程序</span><span class="sxs-lookup"><span data-stu-id="7e5d1-109">Request-response — used with applications that require a response to a message</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e5d1-110">应用程序开发人员可以通过使用本主题中的过程在开发过程中创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-110">The application developer can create a receive location during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7e5d1-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="7e5d1-111">Prerequisites</span></span>  
 <span data-ttu-id="7e5d1-112">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="7e5d1-113">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span> <span data-ttu-id="7e5d1-114">此外，您需要对 SSO 数据库中具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-114">In addition, you need to have appropriate permissions on the SSO database.</span></span>  
  
### <a name="to-create-a-receive-location"></a><span data-ttu-id="7e5d1-115">若要创建的接收位置</span><span class="sxs-lookup"><span data-stu-id="7e5d1-115">To create a receive location</span></span>  
  
1. <span data-ttu-id="7e5d1-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="7e5d1-117">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive location.</span></span>  
  
3. <span data-ttu-id="7e5d1-118">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**或**请求响应接收位置**根据接收的类型的创建位置。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-118">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location** or **Request Response Receive Location**, according to the type of receive location to create.</span></span>  
  
4. <span data-ttu-id="7e5d1-119">在选择接收端口窗口，单击接收端口，将包含此接收位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-119">In the Select a Receive Port window, click the receive port that will contain this receive location, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="7e5d1-120">在中**接收位置属性**窗口中，执行以下操作，然后依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="7e5d1-120">In the **Receive Location Properties** window, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="7e5d1-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7e5d1-121">Use this</span></span>|<span data-ttu-id="7e5d1-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7e5d1-122">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="7e5d1-123">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-123">**Name**</span></span>|<span data-ttu-id="7e5d1-124">键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-124">Type the name of the receive location.</span></span>|  
   |<span data-ttu-id="7e5d1-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-125">**Type**</span></span>|<span data-ttu-id="7e5d1-126">从下拉列表中，选择传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-126">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="7e5d1-127">如果更改传输类型，则必须按下文所述配置传输属性。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-127">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
   |<span data-ttu-id="7e5d1-128">**配置**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-128">**Configure**</span></span>|<span data-ttu-id="7e5d1-129">选择传输类型后，单击**配置**以显示**传输属性**对话框框，并配置接收位置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-129">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="7e5d1-130">有关说明，请单击**帮助**对话框框中。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-130">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="7e5d1-131">有关配置适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-131">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
   |<span data-ttu-id="7e5d1-132">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-132">**Receive handler**</span></span>|<span data-ttu-id="7e5d1-133">从下拉列表中，选择接收位置将在其中运行的 BizTalk Server 主机的实例。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-133">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="7e5d1-134">必须在此主机上运行的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-134">The receive handler must be running on this host.</span></span>|  
   |<span data-ttu-id="7e5d1-135">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-135">**Receive pipeline**</span></span>|<span data-ttu-id="7e5d1-136">从下拉列表中，选择要用于此接收位置接收消息的接收管道。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-136">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
   |<span data-ttu-id="7e5d1-137">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-137">**Send pipeline**</span></span>|<span data-ttu-id="7e5d1-138">从下拉列表中，选择要用于发送响应从该接收位置的发送管道。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-138">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="7e5d1-139">此列表是仅适用于与请求-响应接收端口相关联的接收位置。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-139">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
   |<span data-ttu-id="7e5d1-140">**将此主位置**</span><span class="sxs-lookup"><span data-stu-id="7e5d1-140">**Make this the primary location**</span></span>|<span data-ttu-id="7e5d1-141">选中此复选框，如果有多个接收端口的接收位置，并且你想以代表该接收端口，端口需要传递到另一个实体，如业务伙伴，需要将消息发送到你 organizat 时此接收位置离子电池。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-141">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="7e5d1-142">第一个接收位置创建会自动选择为主接收位置。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-142">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="7e5d1-143">处于选定状态的此属性和不可用，直到您指定不同的接收位置的主数据库。</span><span class="sxs-lookup"><span data-stu-id="7e5d1-143">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e5d1-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e5d1-144">See Also</span></span>  
 [<span data-ttu-id="7e5d1-145">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="7e5d1-145">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)