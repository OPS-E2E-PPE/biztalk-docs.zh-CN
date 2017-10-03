---
title: "步骤 3E： 将文件发送端口 FileAct 应用商店应用和转发方案，以捕获软件 ExchangeSnFResponse 消息添加 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cf320f22f5acc2511d6327c36c54cda8f0dd1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a><span data-ttu-id="fe7ff-102">步骤 3E： 添加 FileAct 应用商店应用和转发方案，以捕获软件 ExchangeSnFResponse 消息文件发送端口</span><span class="sxs-lookup"><span data-stu-id="fe7ff-102">Step 3E: Add a FILE Send Port for the FileAct Store and Forward Scenario to capture Sw-ExchangeSnFResponse messages</span></span>
<span data-ttu-id="fe7ff-103">在开始此步骤之前，必须完成[步骤 3D： 添加 FILEACT 发送端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="fe7ff-104">若要添加捕获状态事件的文件发送端口：</span><span class="sxs-lookup"><span data-stu-id="fe7ff-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="fe7ff-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fe7ff-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="fe7ff-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="fe7ff-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_ GetStatusReports。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="fe7ff-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="fe7ff-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="fe7ff-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fe7ff-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="fe7ff-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-112">**Use this**</span></span>|<span data-ttu-id="fe7ff-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fe7ff-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-114">**Send handler**</span></span>|<span data-ttu-id="fe7ff-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="fe7ff-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-116">**Send pipeline**</span></span>|<span data-ttu-id="fe7ff-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="fe7ff-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fe7ff-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="fe7ff-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-119">**Use this**</span></span>|<span data-ttu-id="fe7ff-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fe7ff-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-121">**Property**</span></span>|<span data-ttu-id="fe7ff-122">选择 BTS。MessageType</span><span class="sxs-lookup"><span data-stu-id="fe7ff-122">Select BTS.MessageType</span></span>|  
    |<span data-ttu-id="fe7ff-123">**运算符**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-123">**Operator**</span></span>|<span data-ttu-id="fe7ff-124">选择 = =</span><span class="sxs-lookup"><span data-stu-id="fe7ff-124">Select ==</span></span>|  
    |<span data-ttu-id="fe7ff-125">**值**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-125">**Value**</span></span>|<span data-ttu-id="fe7ff-126">类型软件 HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="fe7ff-126">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="fe7ff-127">**分组**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-127">**Group**</span></span>|<span data-ttu-id="fe7ff-128">或</span><span class="sxs-lookup"><span data-stu-id="fe7ff-128">Or</span></span>|  
    |<span data-ttu-id="fe7ff-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-129">**Property**</span></span>|<span data-ttu-id="fe7ff-130">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="fe7ff-130">Select BTS.</span></span> <span data-ttu-id="fe7ff-131">MessageType</span><span class="sxs-lookup"><span data-stu-id="fe7ff-131">MessageType</span></span>|  
    |<span data-ttu-id="fe7ff-132">**运算符**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-132">**Operator**</span></span>|<span data-ttu-id="fe7ff-133">选择 = =</span><span class="sxs-lookup"><span data-stu-id="fe7ff-133">Select ==</span></span>|  
    |<span data-ttu-id="fe7ff-134">**值**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-134">**Value**</span></span>|<span data-ttu-id="fe7ff-135">类型软件 ExchangeSnFResponse</span><span class="sxs-lookup"><span data-stu-id="fe7ff-135">Type Sw-ExchangeSnFResponse</span></span>|