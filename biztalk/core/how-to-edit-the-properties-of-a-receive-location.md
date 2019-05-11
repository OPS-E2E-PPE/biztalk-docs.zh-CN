---
title: 如何编辑属性的接收位置 |Microsoft Docs
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
ms.openlocfilehash: d28c1c8d44c76cfff61f3eaef6b00a61cd36f7d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385153"
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="8c79b-102">如何编辑属性的接收位置</span><span class="sxs-lookup"><span data-stu-id="8c79b-102">How to Edit the Properties of a Receive Location</span></span>
<span data-ttu-id="8c79b-103">本主题介绍如何使用 BizTalk Server 管理控制台编辑属性对现有的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8c79b-103">This topic describes how to use the BizTalk Server Administration console to edit properties of an existing receive location.</span></span> <span data-ttu-id="8c79b-104">有关创建接收位置的说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="8c79b-104">For instructions on creating a receive location, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c79b-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="8c79b-105">Prerequisites</span></span>  
 <span data-ttu-id="8c79b-106">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8c79b-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="8c79b-107">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="8c79b-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="8c79b-108">若要编辑的接收位置属性</span><span class="sxs-lookup"><span data-stu-id="8c79b-108">To edit the properties of a receive location</span></span>  
  
1. <span data-ttu-id="8c79b-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="8c79b-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8c79b-110">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要编辑的接收位置属性，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="8c79b-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to edit the properties of a receive location and then click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="8c79b-111">在右窗格中，右键单击该接收位置，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="8c79b-111">In the right pane, right-click the receive location, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="8c79b-112">在中**接收位置属性**窗口中，编辑一个或多个以下属性，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="8c79b-112">In the **Receive Location Properties** window, edit one or more of the following properties, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="8c79b-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8c79b-113">Use this</span></span>|<span data-ttu-id="8c79b-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8c79b-114">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="8c79b-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c79b-115">**Name**</span></span>|<span data-ttu-id="8c79b-116">键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="8c79b-116">Type the name of the receive location.</span></span>|  
   |<span data-ttu-id="8c79b-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="8c79b-117">**Type**</span></span>|<span data-ttu-id="8c79b-118">从下拉列表中，选择传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="8c79b-118">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="8c79b-119">如果更改传输类型，则必须按下文所述配置传输属性。</span><span class="sxs-lookup"><span data-stu-id="8c79b-119">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
   |<span data-ttu-id="8c79b-120">**配置**</span><span class="sxs-lookup"><span data-stu-id="8c79b-120">**Configure**</span></span>|<span data-ttu-id="8c79b-121">选择传输类型后，单击**配置**以显示**传输属性**对话框框，并配置接收位置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="8c79b-121">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="8c79b-122">有关说明，请单击**帮助**对话框框中。</span><span class="sxs-lookup"><span data-stu-id="8c79b-122">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="8c79b-123">有关配置适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="8c79b-123">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
   |<span data-ttu-id="8c79b-124">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="8c79b-124">**Receive handler**</span></span>|<span data-ttu-id="8c79b-125">从下拉列表中，选择接收位置将在其中运行的 BizTalk Server 主机的实例。</span><span class="sxs-lookup"><span data-stu-id="8c79b-125">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="8c79b-126">必须在此主机上运行的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="8c79b-126">The receive handler must be running on this host.</span></span>|  
   |<span data-ttu-id="8c79b-127">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="8c79b-127">**Receive pipeline**</span></span>|<span data-ttu-id="8c79b-128">从下拉列表中，选择要用于此接收位置接收消息的接收管道。</span><span class="sxs-lookup"><span data-stu-id="8c79b-128">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
   |<span data-ttu-id="8c79b-129">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="8c79b-129">**Send pipeline**</span></span>|<span data-ttu-id="8c79b-130">从下拉列表中，选择要用于发送响应从该接收位置的发送管道。</span><span class="sxs-lookup"><span data-stu-id="8c79b-130">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="8c79b-131">此列表是仅适用于与请求-响应接收端口相关联的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8c79b-131">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
   |<span data-ttu-id="8c79b-132">**将此主位置**</span><span class="sxs-lookup"><span data-stu-id="8c79b-132">**Make this the primary location**</span></span>|<span data-ttu-id="8c79b-133">选中此复选框，如果有多个接收端口的接收位置，并且你想以代表该接收端口，端口需要传递到另一个实体，如业务伙伴，需要将消息发送到你 organizat 时此接收位置离子电池。</span><span class="sxs-lookup"><span data-stu-id="8c79b-133">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="8c79b-134">第一个接收位置创建会自动选择为主接收位置。</span><span class="sxs-lookup"><span data-stu-id="8c79b-134">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="8c79b-135">处于选定状态的此属性和不可用，直到您指定不同的接收位置的主数据库。</span><span class="sxs-lookup"><span data-stu-id="8c79b-135">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8c79b-136">在更改或修改接收位置，重新启动独立主机工作进程相对应的已修改的情况下接收位置。</span><span class="sxs-lookup"><span data-stu-id="8c79b-136">In case you change or modify Receive location, restart the Isolated Host Worker Processes corresponding to the modified receive location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c79b-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c79b-137">See Also</span></span>  
 [<span data-ttu-id="8c79b-138">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="8c79b-138">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)