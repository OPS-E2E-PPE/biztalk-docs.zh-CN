---
title: "步骤 2B： 添加文件发送端口，以捕获 Sw:HandleFileRequest 和 Sw:HandleSnFRequest FileAct 存储和转发的消息 （请求） 方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c2eb55cd6aca9b26b8a8ac47ab6dbe192f174d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="750b4-102">步骤 2B： 添加文件发送端口，以捕获 Sw:HandleFileRequest 和 Sw:HandleSnFRequest FileAct 存储和转发的消息 （请求） 方案</span><span class="sxs-lookup"><span data-stu-id="750b4-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="750b4-103">在开始此步骤之前，必须完成[步骤 2A： 添加接收的文件位置的 FileAct 存储和转发 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)部分。</span><span class="sxs-lookup"><span data-stu-id="750b4-103">Before you begin this step, you must complete the [Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) section.</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a><span data-ttu-id="750b4-104">若要添加文件发送端口捕获软件： HandleFileRequest 消息</span><span class="sxs-lookup"><span data-stu-id="750b4-104">To add a FILE send port to capture the Sw: HandleFileRequest message</span></span>  
  
1.  <span data-ttu-id="750b4-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="750b4-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="750b4-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="750b4-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="750b4-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="750b4-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="750b4-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_FA_SendPullResponsetoReceiver**。</span><span class="sxs-lookup"><span data-stu-id="750b4-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>  
  
5.  <span data-ttu-id="750b4-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="750b4-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="750b4-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\FileAct\PullResponse**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="750b4-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\FileAct\PullResponse**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="750b4-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="750b4-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="750b4-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="750b4-112">**Use this**</span></span>|<span data-ttu-id="750b4-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="750b4-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="750b4-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="750b4-114">**Send handler**</span></span>|<span data-ttu-id="750b4-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="750b4-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="750b4-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="750b4-116">**Send pipeline**</span></span>|<span data-ttu-id="750b4-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="750b4-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="750b4-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="750b4-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="750b4-119">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="750b4-119">Repeat step 1 and 2.</span></span>  
  
10. <span data-ttu-id="750b4-120">右键单击**发送端口**，指向**新建**，然后单击**动态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="750b4-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  
  
11. <span data-ttu-id="750b4-121">在**发送端口属性**窗口中，名称发送端口**，Tutorial_IA_DynamicSendPort**。</span><span class="sxs-lookup"><span data-stu-id="750b4-121">In the **Send Port Properties** window, name the send port**, Tutorial_IA_DynamicSendPort**.</span></span>  
  
12. <span data-ttu-id="750b4-122">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="750b4-122">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="750b4-123">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="750b4-123">**Use this**</span></span>|<span data-ttu-id="750b4-124">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="750b4-124">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="750b4-125">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="750b4-125">**Send pipeline**</span></span>|<span data-ttu-id="750b4-126">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="750b4-126">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="750b4-127">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="750b4-127">**Receive pipeline**</span></span>|<span data-ttu-id="750b4-128">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="750b4-128">From the drop-down list, select **XMLReceive**.</span></span>|  
  
13. <span data-ttu-id="750b4-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="750b4-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750b4-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="750b4-130">See Also</span></span>  
 <span data-ttu-id="750b4-131">[步骤 2A： 添加文件接收 FileAct 应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="750b4-131">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="750b4-132">步骤 2c： 添加 FileAct 应用商店应用和进 （请求） 方案 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="750b4-132">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)