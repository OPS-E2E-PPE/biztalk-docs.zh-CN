---
title: 步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互实时方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31e9c942-ba74-4ae2-b6e1-5266d0fbcb14
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ddc38913b8bf9ea5c9450334e58dfaeb5ff4ad3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224189"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a><span data-ttu-id="ebf7d-102">步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互实时方案</span><span class="sxs-lookup"><span data-stu-id="ebf7d-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct real-time scenario</span></span>
<span data-ttu-id="ebf7d-103">当你发送一条消息到你的合作伙伴时，SWIFT 转换消息标头，并将消息转发到你的合作伙伴作为 Sw:HandleRequest 消息。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-103">When you send a message to your partner, SWIFT transforms the message header and forwards the message to your partner as a Sw:HandleRequest message.</span></span> <span data-ttu-id="ebf7d-104">在开始此步骤之前，必须完成[步骤 3B： 对于交互的实时方案添加交互接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-104">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a><span data-ttu-id="ebf7d-105">若要添加一个文件，将发送端口捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="ebf7d-105">To add a FILE send port to capture Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="ebf7d-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ebf7d-107">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="ebf7d-108">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-108">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="ebf7d-109">在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendResponseToReceiver**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-109">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToReceiver**.</span></span>  
  
5.  <span data-ttu-id="ebf7d-110">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-110">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="ebf7d-111">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Interact\HandleRequest，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-111">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="ebf7d-112">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebf7d-112">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="ebf7d-113">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-113">**Use this**</span></span>|<span data-ttu-id="ebf7d-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="ebf7d-115">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-115">**Send handler**</span></span>|<span data-ttu-id="ebf7d-116">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="ebf7d-117">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-117">**Send pipeline**</span></span>|<span data-ttu-id="ebf7d-118">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-118">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="ebf7d-119">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebf7d-119">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="ebf7d-120">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-120">**Use this**</span></span>|<span data-ttu-id="ebf7d-121">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-121">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="ebf7d-122">**属性**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-122">**Property**</span></span>|<span data-ttu-id="ebf7d-123">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-123">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="ebf7d-124">**运算符**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-124">**Operator**</span></span>|<span data-ttu-id="ebf7d-125">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-125">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="ebf7d-126">**值**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-126">**Value**</span></span>|<span data-ttu-id="ebf7d-127">类型**Tutorial_IA_HandleRequestOneWay_RealTime。**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-127">Type **Tutorial_IA_HandleRequestOneWay_RealTime.**</span></span>|  
    |<span data-ttu-id="ebf7d-128">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="ebf7d-128">**Group by**</span></span>|<span data-ttu-id="ebf7d-129">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-129">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="ebf7d-130">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ebf7d-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf7d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf7d-131">See Also</span></span>  
 <span data-ttu-id="ebf7d-132">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ebf7d-132">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="ebf7d-133">[步骤 3A： 添加一个文件接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ebf7d-133">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="ebf7d-134">[步骤 3B： 添加交互接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ebf7d-134">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="ebf7d-135">[步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="ebf7d-135">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="ebf7d-136">步骤 3E： 添加的交互发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="ebf7d-136">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)