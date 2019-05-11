---
title: 步骤 3c:添加 FILE 发送端口以获取： handlerequest-InterAct 实时方案 |Microsoft Docs
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
ms.openlocfilehash: 2a1deeb12f4af2cf5540217463c211f31a385ba3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365663"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a><span data-ttu-id="b9b65-102">步骤 3c:添加 FILE 发送端口以获取： handlerequest-InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="b9b65-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct real-time scenario</span></span>
<span data-ttu-id="b9b65-103">当向合作伙伴发送一条消息时，SWIFT 转换消息标头并将消息转发给您作为： handlerequest 消息的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="b9b65-103">When you send a message to your partner, SWIFT transforms the message header and forwards the message to your partner as a Sw:HandleRequest message.</span></span> <span data-ttu-id="b9b65-104">在开始此步骤之前，必须完成[步骤 3B:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b65-104">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a><span data-ttu-id="b9b65-105">若要添加一个 FILE 发送端口以捕获： handlerequest 消息</span><span class="sxs-lookup"><span data-stu-id="b9b65-105">To add a FILE send port to capture Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="b9b65-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b9b65-107">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9b65-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="b9b65-108">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="b9b65-108">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="b9b65-109">在中**发送端口属性**窗口中，命名发送端口**Tutorial_IA_SendResponseToReceiver**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-109">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToReceiver**.</span></span>  
  
5.  <span data-ttu-id="b9b65-110">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-110">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="b9b65-111">在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Interact\HandleRequest，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-111">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b9b65-112">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9b65-112">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="b9b65-113">**使用此**</span><span class="sxs-lookup"><span data-stu-id="b9b65-113">**Use this**</span></span>|<span data-ttu-id="b9b65-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="b9b65-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b9b65-115">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="b9b65-115">**Send handler**</span></span>|<span data-ttu-id="b9b65-116">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="b9b65-117">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="b9b65-117">**Send pipeline**</span></span>|<span data-ttu-id="b9b65-118">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-118">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="b9b65-119">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9b65-119">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b9b65-120">**使用此**</span><span class="sxs-lookup"><span data-stu-id="b9b65-120">**Use this**</span></span>|<span data-ttu-id="b9b65-121">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="b9b65-121">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b9b65-122">**属性**</span><span class="sxs-lookup"><span data-stu-id="b9b65-122">**Property**</span></span>|<span data-ttu-id="b9b65-123">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-123">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="b9b65-124">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="b9b65-124">**Operator**</span></span>|<span data-ttu-id="b9b65-125">从下拉列表中，选择**==**。</span><span class="sxs-lookup"><span data-stu-id="b9b65-125">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="b9b65-126">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="b9b65-126">**Value**</span></span>|<span data-ttu-id="b9b65-127">类型**Tutorial_IA_HandleRequestOneWay_RealTime。**</span><span class="sxs-lookup"><span data-stu-id="b9b65-127">Type **Tutorial_IA_HandleRequestOneWay_RealTime.**</span></span>|  
    |<span data-ttu-id="b9b65-128">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="b9b65-128">**Group by**</span></span>|<span data-ttu-id="b9b65-129">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="b9b65-129">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="b9b65-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b9b65-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b65-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b65-131">See Also</span></span>  
 <span data-ttu-id="b9b65-132">[步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b9b65-132">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b9b65-133">[步骤 3a:添加 FILE 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b9b65-133">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b9b65-134">[步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b9b65-134">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b9b65-135">[步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="b9b65-135">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="b9b65-136">步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="b9b65-136">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)