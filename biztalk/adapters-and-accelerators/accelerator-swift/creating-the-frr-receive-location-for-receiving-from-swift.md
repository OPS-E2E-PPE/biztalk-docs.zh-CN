---
title: 创建 FRR 接收位置从 SWIFT 接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1912187c299e959c1a4f56c6650201efc5b37246
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378405"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="554b5-102">创建 FRR 接收位置从 SWIFT 接收</span><span class="sxs-lookup"><span data-stu-id="554b5-102">Creating the FRR Receive Location for Receiving from SWIFT</span></span>
<span data-ttu-id="554b5-103">若要执行 FIN 响应对帐，您需要创建到 A4SWIFT 从 SWIFT 网络接收消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="554b5-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the SWIFT Network into A4SWIFT.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="554b5-104">建议您设置两个接收位置接收来自 SAA 的消息： 一个用于接收平移/Nan，另一个用于接收其他消息。</span><span class="sxs-lookup"><span data-stu-id="554b5-104">It is advisable to set up two receive locations for receiving messages from SAA: one to receive PAN/NANs and one to receive all other messages.</span></span> <span data-ttu-id="554b5-105">若要设置两个接收位置，你必须从位于 SAA 的两个 MQSeries 队列接收消息： 一个用于平移/Nan，一个为所有其他消息类型。</span><span class="sxs-lookup"><span data-stu-id="554b5-105">To set up the two receive locations, you must receive messages from two MQSeries queues at SAA: one for PAN/NANs and one for all other message types.</span></span>  
  
 <span data-ttu-id="554b5-106">**摘要**</span><span class="sxs-lookup"><span data-stu-id="554b5-106">**Summary**</span></span>  
  
 <span data-ttu-id="554b5-107">创建接收位置具有以下属性和组件：</span><span class="sxs-lookup"><span data-stu-id="554b5-107">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="554b5-108">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="554b5-108">Property/Component</span></span>|<span data-ttu-id="554b5-109">设置</span><span class="sxs-lookup"><span data-stu-id="554b5-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="554b5-110">接收端口</span><span class="sxs-lookup"><span data-stu-id="554b5-110">Receive port</span></span>|<span data-ttu-id="554b5-111">单向端口</span><span class="sxs-lookup"><span data-stu-id="554b5-111">One-way port</span></span>|  
|<span data-ttu-id="554b5-112">传输类型</span><span class="sxs-lookup"><span data-stu-id="554b5-112">Transport type</span></span>|<span data-ttu-id="554b5-113">MQSeries</span><span class="sxs-lookup"><span data-stu-id="554b5-113">MQSeries</span></span>|  
|<span data-ttu-id="554b5-114">队列定义 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="554b5-114">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="554b5-115">MQSeries 服务器</span><span class="sxs-lookup"><span data-stu-id="554b5-115">MQSeries server</span></span><br /><span data-ttu-id="554b5-116">队列管理器</span><span class="sxs-lookup"><span data-stu-id="554b5-116">Queue manager</span></span><br /><span data-ttu-id="554b5-117">队列</span><span class="sxs-lookup"><span data-stu-id="554b5-117">Queue</span></span>|  
|<span data-ttu-id="554b5-118">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="554b5-118">Receive handler</span></span>|<span data-ttu-id="554b5-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="554b5-119">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="554b5-120">接收管道</span><span class="sxs-lookup"><span data-stu-id="554b5-120">Receive pipeline</span></span>|<span data-ttu-id="554b5-121">A4SWIFT 接收的 FRR 创建的管道</span><span class="sxs-lookup"><span data-stu-id="554b5-121">The A4SWIFT receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a><span data-ttu-id="554b5-122">若要添加 FRR 接收位置以便接收来自 SWIFT</span><span class="sxs-lookup"><span data-stu-id="554b5-122">To add an FRR receive location for receiving from SWIFT</span></span>  
  
1.  <span data-ttu-id="554b5-123">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。</span><span class="sxs-lookup"><span data-stu-id="554b5-123">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and  **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="554b5-124">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="554b5-124">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="554b5-125">在接收端口属性对话框中，在**名称**框中，键入接收端口，例如 FRRSWIFTReceivePort 的名称。</span><span class="sxs-lookup"><span data-stu-id="554b5-125">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRSWIFTReceivePort.</span></span>  
  
4.  <span data-ttu-id="554b5-126">单击**Apply**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="554b5-126">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="554b5-127">在管理控制台中，右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="554b5-127">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
6.  <span data-ttu-id="554b5-128">在选择接收端口对话框中，选择接收端口刚刚创建，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="554b5-128">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="554b5-129">在接收位置属性对话框中，在**名称**框中，键入接收位置，例如 FRRSWIFTReceiveLocation 的名称。</span><span class="sxs-lookup"><span data-stu-id="554b5-129">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location, such as FRRSWIFTReceiveLocation.</span></span>  
  
8.  <span data-ttu-id="554b5-130">在中**传输**部分中，对于**类型**文本框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="554b5-130">In the **Transport** section, for the **Type** text box, select **MQSeries**.</span></span>  
  
9. <span data-ttu-id="554b5-131">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="554b5-131">Click **Configure**.</span></span>  
  
10. <span data-ttu-id="554b5-132">在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="554b5-132">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis (**…**) button.</span></span>  
  
11. <span data-ttu-id="554b5-133">在中**队列定义**对话框中，输入的 MQSeries 服务器、 队列管理器和队列。</span><span class="sxs-lookup"><span data-stu-id="554b5-133">In the **Queue Definition** dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="554b5-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="554b5-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="554b5-135">在中**MQSeries 传输属性**对话框框中，验证属性是否根据需要。</span><span class="sxs-lookup"><span data-stu-id="554b5-135">In the **MQSeries Transport Properties** dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="554b5-136">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="554b5-136">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="554b5-137">MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。</span><span class="sxs-lookup"><span data-stu-id="554b5-137">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
13. <span data-ttu-id="554b5-138">在接收位置属性对话框中，对于**接收处理程序**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="554b5-138">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
14. <span data-ttu-id="554b5-139">有关**接收管道**部分中，选择此项 A4SWIFT 接收的 FRR 创建管道。</span><span class="sxs-lookup"><span data-stu-id="554b5-139">For **Receive Pipeline** section, select the A4SWIFT receive pipeline that you created for FRR.</span></span>  
  
15. <span data-ttu-id="554b5-140">单击**Apply**，然后单击**确定**</span><span class="sxs-lookup"><span data-stu-id="554b5-140">Click **Apply**, and then click **OK**</span></span>  
  
16. <span data-ttu-id="554b5-141">在 BizTalk 浏览器中，右键单击您刚接收位置创建，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="554b5-141">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>