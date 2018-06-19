---
title: 如何编辑的属性接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], properties
- managing [receive locations], editing
- receive locations, properties
- receive locations, editing
- editing, receive locations
- editing, properties
ms.assetid: 2b622050-a875-4896-bed6-65ca39a26dd3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578c5e2970e587180a7928563ebdd942c62dc396
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254461"
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="870b0-102">如何编辑接收位置的属性</span><span class="sxs-lookup"><span data-stu-id="870b0-102">How to Edit the Properties of a Receive Location</span></span>
<span data-ttu-id="870b0-103">本主题将介绍如何使用 BizTalk Server 管理控制台编辑现有接收位置的属性。</span><span class="sxs-lookup"><span data-stu-id="870b0-103">This topic describes how to use the BizTalk Server Administration console to edit properties of an existing receive location.</span></span> <span data-ttu-id="870b0-104">有关创建接收位置的说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="870b0-104">For instructions on creating a receive location, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="870b0-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="870b0-105">Prerequisites</span></span>  
 <span data-ttu-id="870b0-106">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="870b0-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="870b0-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="870b0-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="870b0-108">编辑接收位置的属性</span><span class="sxs-lookup"><span data-stu-id="870b0-108">To edit the properties of a receive location</span></span>  
  
1.  <span data-ttu-id="870b0-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="870b0-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="870b0-110">在控制台树中，展开 BizTalk 组和你想要编辑的接收位置的属性，然后单击 BizTalk 应用程序**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="870b0-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to edit the properties of a receive location and then click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="870b0-111">在右窗格中，右键单击接收位置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="870b0-111">In the right pane, right-click the receive location, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="870b0-112">在**接收位置属性**窗口中，编辑一个或多个以下属性，并依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="870b0-112">In the **Receive Location Properties** window, edit one or more of the following properties, and then click **OK**:</span></span>  
  
    |<span data-ttu-id="870b0-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="870b0-113">Use this</span></span>|<span data-ttu-id="870b0-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="870b0-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="870b0-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="870b0-115">**Name**</span></span>|<span data-ttu-id="870b0-116">键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="870b0-116">Type the name of the receive location.</span></span>|  
    |<span data-ttu-id="870b0-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="870b0-117">**Type**</span></span>|<span data-ttu-id="870b0-118">从下拉列表中，选择传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="870b0-118">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="870b0-119">如果更改传输类型，则必须按下文所述配置传输属性。</span><span class="sxs-lookup"><span data-stu-id="870b0-119">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
    |<span data-ttu-id="870b0-120">**配置**</span><span class="sxs-lookup"><span data-stu-id="870b0-120">**Configure**</span></span>|<span data-ttu-id="870b0-121">选择传输类型后，单击**配置**以显示**传输属性**对话框框中，并配置为接收位置的适配器属性。</span><span class="sxs-lookup"><span data-stu-id="870b0-121">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="870b0-122">有关说明，请单击**帮助**在对话框中。</span><span class="sxs-lookup"><span data-stu-id="870b0-122">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="870b0-123">有关配置的适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="870b0-123">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
    |<span data-ttu-id="870b0-124">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="870b0-124">**Receive handler**</span></span>|<span data-ttu-id="870b0-125">从下拉列表中，选择将运行接收位置的 BizTalk Server 主机实例。</span><span class="sxs-lookup"><span data-stu-id="870b0-125">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="870b0-126">接收处理程序必须在此主机上运行。</span><span class="sxs-lookup"><span data-stu-id="870b0-126">The receive handler must be running on this host.</span></span>|  
    |<span data-ttu-id="870b0-127">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="870b0-127">**Receive pipeline**</span></span>|<span data-ttu-id="870b0-128">从下拉列表中，选择用于在此接收位置接收消息的接收管道。</span><span class="sxs-lookup"><span data-stu-id="870b0-128">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
    |<span data-ttu-id="870b0-129">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="870b0-129">**Send pipeline**</span></span>|<span data-ttu-id="870b0-130">从下拉列表中，选择用于从此接收位置发送响应的发送管道。</span><span class="sxs-lookup"><span data-stu-id="870b0-130">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="870b0-131">此列表仅对与请求响应端口关联的接收位置可用。</span><span class="sxs-lookup"><span data-stu-id="870b0-131">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
    |<span data-ttu-id="870b0-132">**将此主位置**</span><span class="sxs-lookup"><span data-stu-id="870b0-132">**Make this the primary location**</span></span>|<span data-ttu-id="870b0-133">如果接收端口有多个接收位置，并且在需要将该接收端口传递到另一实体（例如需要向组织发送消息的业务合作伙伴）时要让此接收位置代表该接收端口，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="870b0-133">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="870b0-134">创建的第一个接收位置自动选择为主接收位置。</span><span class="sxs-lookup"><span data-stu-id="870b0-134">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="870b0-135">在将其他接收位置指定为主接收位置之前，此属性将一直处于选中状态和不可用状态。</span><span class="sxs-lookup"><span data-stu-id="870b0-135">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="870b0-136">在更改或修改接收位置、 重新启动独立主机辅助进程对应于已修改的情况下接收位置。</span><span class="sxs-lookup"><span data-stu-id="870b0-136">In case you change or modify Receive location, restart the Isolated Host Worker Processes corresponding to the modified receive location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870b0-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="870b0-137">See Also</span></span>  
 [<span data-ttu-id="870b0-138">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="870b0-138">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)