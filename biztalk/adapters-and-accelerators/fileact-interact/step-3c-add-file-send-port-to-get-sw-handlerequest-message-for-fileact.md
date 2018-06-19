---
title: 步骤 3c： 将文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息添加 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc0a9173-20df-4c73-80ee-755987d639d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f0b649e7f8d1c85898677ddc0301851dd302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224869"
---
# <a name="step-3c-add-a-file-send-port-to-capture-swhandlerequest-message-for-the-fileact-real-time-scenario"></a><span data-ttu-id="52add-102">步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="52add-102">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="52add-103">在开始此步骤之前，必须完成[步骤 3B: FileAct 实时方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="52add-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlefilerequest-message"></a><span data-ttu-id="52add-104">若要添加一个文件，将发送端口捕获 Sw:HandleFileRequest 消息</span><span class="sxs-lookup"><span data-stu-id="52add-104">To add a FILE send port to capture Sw:HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="52add-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="52add-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="52add-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="52add-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="52add-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="52add-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="52add-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendResponseToReceiver。</span><span class="sxs-lookup"><span data-stu-id="52add-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="52add-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="52add-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="52add-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseServer，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="52add-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="52add-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52add-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="52add-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="52add-112">**Use this**</span></span>|<span data-ttu-id="52add-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="52add-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="52add-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="52add-114">**Send handler**</span></span>|<span data-ttu-id="52add-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="52add-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="52add-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="52add-116">**Send pipeline**</span></span>|<span data-ttu-id="52add-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="52add-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="52add-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52add-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="52add-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="52add-119">**Use this**</span></span>|<span data-ttu-id="52add-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="52add-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="52add-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="52add-121">**Property**</span></span>|<span data-ttu-id="52add-122">从下拉列表中选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="52add-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="52add-123">**运算符**</span><span class="sxs-lookup"><span data-stu-id="52add-123">**Operator**</span></span>|<span data-ttu-id="52add-124">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="52add-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="52add-125">**值**</span><span class="sxs-lookup"><span data-stu-id="52add-125">**Value**</span></span>|<span data-ttu-id="52add-126">类型**软件 HandleFileRequest**。</span><span class="sxs-lookup"><span data-stu-id="52add-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="52add-127">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="52add-127">**Group by**</span></span>|<span data-ttu-id="52add-128">保留默认值</span><span class="sxs-lookup"><span data-stu-id="52add-128">Leave the default value</span></span>|  
  
9. <span data-ttu-id="52add-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="52add-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52add-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52add-130">See Also</span></span>  
 <span data-ttu-id="52add-131">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="52add-131">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="52add-132">[步骤 3A： 添加一个文件接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="52add-132">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="52add-133">[步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="52add-133">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="52add-134">[步骤 3D: FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="52add-134">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="52add-135">步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="52add-135">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)