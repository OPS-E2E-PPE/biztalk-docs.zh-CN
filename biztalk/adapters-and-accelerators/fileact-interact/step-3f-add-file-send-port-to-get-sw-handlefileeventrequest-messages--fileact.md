---
title: 步骤 3F:添加 FILE 发送端口为 FileAct 实时方案，以捕获 Sw-handlefileeventrequest 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ad02b111d6fabde4260994f29a0b756cb1dd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365350"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a><span data-ttu-id="fccac-102">步骤 3F:添加 FILE 发送端口为 FileAct 实时方案，以捕获 Sw-handlefileeventrequest 消息</span><span class="sxs-lookup"><span data-stu-id="fccac-102">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>
<span data-ttu-id="fccac-103">在开始此步骤之前，必须完成[步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span><span class="sxs-lookup"><span data-stu-id="fccac-103">Before you begin this step, you must complete [Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="fccac-104">若要添加 FILE 发送端口以捕获状态事件：</span><span class="sxs-lookup"><span data-stu-id="fccac-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="fccac-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="fccac-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fccac-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fccac-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="fccac-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fccac-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="fccac-108">在中**发送端口属性**窗口中，命名该发送端口，Tutorial_ GetStatusReports。</span><span class="sxs-lookup"><span data-stu-id="fccac-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="fccac-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fccac-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="fccac-110">在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fccac-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="fccac-111">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fccac-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="fccac-112">**使用此**</span><span class="sxs-lookup"><span data-stu-id="fccac-112">**Use this**</span></span>|<span data-ttu-id="fccac-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fccac-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fccac-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="fccac-114">**Send handler**</span></span>|<span data-ttu-id="fccac-115">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="fccac-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="fccac-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="fccac-116">**Send pipeline**</span></span>|<span data-ttu-id="fccac-117">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="fccac-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="fccac-118">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fccac-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="fccac-119">**使用此**</span><span class="sxs-lookup"><span data-stu-id="fccac-119">**Use this**</span></span>|<span data-ttu-id="fccac-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fccac-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fccac-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="fccac-121">**Property**</span></span>|<span data-ttu-id="fccac-122">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="fccac-122">Select BTS.</span></span> <span data-ttu-id="fccac-123">MessageType</span><span class="sxs-lookup"><span data-stu-id="fccac-123">MessageType</span></span>|  
    |<span data-ttu-id="fccac-124">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="fccac-124">**Operator**</span></span>|<span data-ttu-id="fccac-125">选择 = =</span><span class="sxs-lookup"><span data-stu-id="fccac-125">Select ==</span></span>|  
    |<span data-ttu-id="fccac-126">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="fccac-126">**Value**</span></span>|<span data-ttu-id="fccac-127">Type Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="fccac-127">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="fccac-128">**分组**</span><span class="sxs-lookup"><span data-stu-id="fccac-128">**Group**</span></span>|<span data-ttu-id="fccac-129">或</span><span class="sxs-lookup"><span data-stu-id="fccac-129">Or</span></span>|  
    |<span data-ttu-id="fccac-130">**属性**</span><span class="sxs-lookup"><span data-stu-id="fccac-130">**Property**</span></span>|<span data-ttu-id="fccac-131">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="fccac-131">Select BTS.</span></span> <span data-ttu-id="fccac-132">MessageType</span><span class="sxs-lookup"><span data-stu-id="fccac-132">MessageType</span></span>|  
    |<span data-ttu-id="fccac-133">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="fccac-133">**Operator**</span></span>|<span data-ttu-id="fccac-134">选择 = =</span><span class="sxs-lookup"><span data-stu-id="fccac-134">Select ==</span></span>|  
    |<span data-ttu-id="fccac-135">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="fccac-135">**Value**</span></span>|<span data-ttu-id="fccac-136">类型 Sw-exchangesnfresponse</span><span class="sxs-lookup"><span data-stu-id="fccac-136">Type Sw-ExchangeSnFResponse</span></span>|