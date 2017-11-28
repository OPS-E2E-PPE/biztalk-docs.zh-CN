---
title: "单步 3F: FileAct 实时方案，以捕获软件 HandleFileEventRequest 消息的文件发送端口添加 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d70c338696f1c4455161a88c8d2988e0ea0ccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a><span data-ttu-id="77e28-102">单步 3F： 添加 FileAct 实时方案，以捕获软件 HandleFileEventRequest 消息文件发送端口</span><span class="sxs-lookup"><span data-stu-id="77e28-102">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>
<span data-ttu-id="77e28-103">在开始此步骤之前，必须完成[步骤 3E: FileAct 实时方案将文件发送端口添加到捕获 Sw:ExchangeFileResponse 消息](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span><span class="sxs-lookup"><span data-stu-id="77e28-103">Before you begin this step, you must complete [Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="77e28-104">若要添加捕获状态事件的文件发送端口：</span><span class="sxs-lookup"><span data-stu-id="77e28-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="77e28-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="77e28-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="77e28-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="77e28-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="77e28-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="77e28-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="77e28-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_ GetStatusReports。</span><span class="sxs-lookup"><span data-stu-id="77e28-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="77e28-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="77e28-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="77e28-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="77e28-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="77e28-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77e28-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="77e28-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="77e28-112">**Use this**</span></span>|<span data-ttu-id="77e28-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="77e28-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="77e28-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="77e28-114">**Send handler**</span></span>|<span data-ttu-id="77e28-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="77e28-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="77e28-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="77e28-116">**Send pipeline**</span></span>|<span data-ttu-id="77e28-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="77e28-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="77e28-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77e28-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="77e28-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="77e28-119">**Use this**</span></span>|<span data-ttu-id="77e28-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="77e28-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="77e28-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="77e28-121">**Property**</span></span>|<span data-ttu-id="77e28-122">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="77e28-122">Select BTS.</span></span> <span data-ttu-id="77e28-123">MessageType</span><span class="sxs-lookup"><span data-stu-id="77e28-123">MessageType</span></span>|  
    |<span data-ttu-id="77e28-124">**运算符**</span><span class="sxs-lookup"><span data-stu-id="77e28-124">**Operator**</span></span>|<span data-ttu-id="77e28-125">选择 = =</span><span class="sxs-lookup"><span data-stu-id="77e28-125">Select ==</span></span>|  
    |<span data-ttu-id="77e28-126">**值**</span><span class="sxs-lookup"><span data-stu-id="77e28-126">**Value**</span></span>|<span data-ttu-id="77e28-127">类型软件 HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="77e28-127">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="77e28-128">**分组**</span><span class="sxs-lookup"><span data-stu-id="77e28-128">**Group**</span></span>|<span data-ttu-id="77e28-129">或</span><span class="sxs-lookup"><span data-stu-id="77e28-129">Or</span></span>|  
    |<span data-ttu-id="77e28-130">**属性**</span><span class="sxs-lookup"><span data-stu-id="77e28-130">**Property**</span></span>|<span data-ttu-id="77e28-131">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="77e28-131">Select BTS.</span></span> <span data-ttu-id="77e28-132">MessageType</span><span class="sxs-lookup"><span data-stu-id="77e28-132">MessageType</span></span>|  
    |<span data-ttu-id="77e28-133">**运算符**</span><span class="sxs-lookup"><span data-stu-id="77e28-133">**Operator**</span></span>|<span data-ttu-id="77e28-134">选择 = =</span><span class="sxs-lookup"><span data-stu-id="77e28-134">Select ==</span></span>|  
    |<span data-ttu-id="77e28-135">**值**</span><span class="sxs-lookup"><span data-stu-id="77e28-135">**Value**</span></span>|<span data-ttu-id="77e28-136">类型软件 ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="77e28-136">Type Sw-ExchangeSnFResponse</span></span>|