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
ms.openlocfilehash: e13968abd25f0f7bf85743122688e44a8f2bb25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003718"
---
# <a name="how-to-create-a-receive-location"></a><span data-ttu-id="f9133-102">如何创建接收位置</span><span class="sxs-lookup"><span data-stu-id="f9133-102">How to Create a Receive Location</span></span>
<span data-ttu-id="f9133-103">本主题将介绍如何使用 BizTalk Server 管理控制台创建新的接收位置，并指定其所属的接收端口。</span><span class="sxs-lookup"><span data-stu-id="f9133-103">This topic describes how to use the BizTalk Server Administration console to create a new receive location and specify the receive port to which it belongs.</span></span> <span data-ttu-id="f9133-104">接收位置为入站消息到达的地址，以及处理在该地址接收到的消息的消息传送管道。</span><span class="sxs-lookup"><span data-stu-id="f9133-104">A receive location is an address where inbound messages arrive as well as the messaging pipeline that processes messages received at that address.</span></span>  
  
 <span data-ttu-id="f9133-105">在可以创建接收位置之前，此应用程序中必须已存在与希望创建的接收位置类型相同的接收端口，。</span><span class="sxs-lookup"><span data-stu-id="f9133-105">Before you can create a receive location, a receive port must already exist in this application that of the same type as the receive location you want to create.</span></span> <span data-ttu-id="f9133-106">有关创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f9133-106">For instructions on creating a receive port, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="f9133-107">您可以创建以下类型的接收位置：</span><span class="sxs-lookup"><span data-stu-id="f9133-107">You can create the following types of receive locations:</span></span>  
  
-   <span data-ttu-id="f9133-108">单向端口 — 用于丢弃消息并且不等待同步回复的应用程序</span><span class="sxs-lookup"><span data-stu-id="f9133-108">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  
  
-   <span data-ttu-id="f9133-109">请求-响应 — 用于请求消息响应的应用程序</span><span class="sxs-lookup"><span data-stu-id="f9133-109">Request-response — used with applications that require a response to a message</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9133-110">应用程序开发人员可以通过在开发过程中使用本主题中的过程来创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="f9133-110">The application developer can create a receive location during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f9133-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="f9133-111">Prerequisites</span></span>  
 <span data-ttu-id="f9133-112">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f9133-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f9133-113">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f9133-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span> <span data-ttu-id="f9133-114">此外，还需有 SSO 数据库的相应权限。</span><span class="sxs-lookup"><span data-stu-id="f9133-114">In addition, you need to have appropriate permissions on the SSO database.</span></span>  
  
### <a name="to-create-a-receive-location"></a><span data-ttu-id="f9133-115">若要创建的接收位置</span><span class="sxs-lookup"><span data-stu-id="f9133-115">To create a receive location</span></span>  
  
1. <span data-ttu-id="f9133-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f9133-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f9133-117">在控制台树中，展开要为其创建接收位置的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9133-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive location.</span></span>  
  
3. <span data-ttu-id="f9133-118">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**或**请求响应接收位置**根据接收的类型的创建位置。</span><span class="sxs-lookup"><span data-stu-id="f9133-118">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location** or **Request Response Receive Location**, according to the type of receive location to create.</span></span>  
  
4. <span data-ttu-id="f9133-119">在选择接收端口窗口，单击接收端口，将包含此接收位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f9133-119">In the Select a Receive Port window, click the receive port that will contain this receive location, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="f9133-120">在中**接收位置属性**窗口中，执行以下操作，然后依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="f9133-120">In the **Receive Location Properties** window, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="f9133-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f9133-121">Use this</span></span>|<span data-ttu-id="f9133-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f9133-122">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="f9133-123">**名称**</span><span class="sxs-lookup"><span data-stu-id="f9133-123">**Name**</span></span>|<span data-ttu-id="f9133-124">键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="f9133-124">Type the name of the receive location.</span></span>|  
   |<span data-ttu-id="f9133-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9133-125">**Type**</span></span>|<span data-ttu-id="f9133-126">从下拉列表中，选择传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="f9133-126">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="f9133-127">如果更改传输类型，则必须按下文所述配置传输属性。</span><span class="sxs-lookup"><span data-stu-id="f9133-127">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
   |<span data-ttu-id="f9133-128">**配置**</span><span class="sxs-lookup"><span data-stu-id="f9133-128">**Configure**</span></span>|<span data-ttu-id="f9133-129">选择传输类型后，单击**配置**以显示**传输属性**对话框框，并配置接收位置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="f9133-129">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="f9133-130">有关说明，请单击**帮助**对话框框中。</span><span class="sxs-lookup"><span data-stu-id="f9133-130">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="f9133-131">有关配置适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="f9133-131">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
   |<span data-ttu-id="f9133-132">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="f9133-132">**Receive handler**</span></span>|<span data-ttu-id="f9133-133">从下拉列表中，选择将运行接收位置的 BizTalk Server 主机实例。</span><span class="sxs-lookup"><span data-stu-id="f9133-133">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="f9133-134">接收处理程序必须在此主机上运行。</span><span class="sxs-lookup"><span data-stu-id="f9133-134">The receive handler must be running on this host.</span></span>|  
   |<span data-ttu-id="f9133-135">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="f9133-135">**Receive pipeline**</span></span>|<span data-ttu-id="f9133-136">从下拉列表中，选择用于在此接收位置接收消息的接收管道。</span><span class="sxs-lookup"><span data-stu-id="f9133-136">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
   |<span data-ttu-id="f9133-137">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="f9133-137">**Send pipeline**</span></span>|<span data-ttu-id="f9133-138">从下拉列表中，选择用于从此接收位置发送响应的发送管道。</span><span class="sxs-lookup"><span data-stu-id="f9133-138">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="f9133-139">此列表仅对与请求响应端口关联的接收位置可用。</span><span class="sxs-lookup"><span data-stu-id="f9133-139">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
   |<span data-ttu-id="f9133-140">**将此主位置**</span><span class="sxs-lookup"><span data-stu-id="f9133-140">**Make this the primary location**</span></span>|<span data-ttu-id="f9133-141">如果接收端口有多个接收位置，并且在需要将该接收端口传递到另一实体（例如需要向组织发送消息的业务合作伙伴）时要让此接收位置代表该接收端口，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="f9133-141">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="f9133-142">创建的第一个接收位置自动选择为主接收位置。</span><span class="sxs-lookup"><span data-stu-id="f9133-142">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="f9133-143">在将其他接收位置指定为主接收位置之前，此属性将一直处于选中状态和不可用状态。</span><span class="sxs-lookup"><span data-stu-id="f9133-143">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9133-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9133-144">See Also</span></span>  
 [<span data-ttu-id="f9133-145">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="f9133-145">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)