---
title: "步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互存储和转发 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c57f2f3a6e2fcfc199e56d34c44aa7667451d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a><span data-ttu-id="6a740-102">步骤 3c： 添加文件发送端口，以获取 Sw:HandleRequest-交互存储和转发</span><span class="sxs-lookup"><span data-stu-id="6a740-102">Step 3C: Add FILE send port to get Sw:HandleRequest-InterAct Store and Forward</span></span>
<span data-ttu-id="6a740-103">在开始此步骤之前，必须完成[步骤 3B： 添加交互接收位置的交互，存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="6a740-103">Before you begin this step, you must complete [Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="6a740-104">若要添加一个文件，将发送端口捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="6a740-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  
  
1.  <span data-ttu-id="6a740-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6a740-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6a740-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a740-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="6a740-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="6a740-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="6a740-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_IA_SendResponseToReceiver。</span><span class="sxs-lookup"><span data-stu-id="6a740-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="6a740-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="6a740-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="6a740-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Interact\HandleRequest，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a740-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Interact\HandleRequest, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6a740-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a740-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="6a740-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="6a740-112">**Use this**</span></span>|<span data-ttu-id="6a740-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="6a740-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6a740-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="6a740-114">**Send handler**</span></span>|<span data-ttu-id="6a740-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="6a740-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="6a740-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="6a740-116">**Send pipeline**</span></span>|<span data-ttu-id="6a740-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="6a740-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="6a740-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a740-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="6a740-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="6a740-119">**Use this**</span></span>|<span data-ttu-id="6a740-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="6a740-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6a740-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="6a740-121">**Property**</span></span>|<span data-ttu-id="6a740-122">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="6a740-122">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="6a740-123">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6a740-123">**Operator**</span></span>|<span data-ttu-id="6a740-124">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="6a740-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="6a740-125">**值**</span><span class="sxs-lookup"><span data-stu-id="6a740-125">**Value**</span></span>|<span data-ttu-id="6a740-126">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="6a740-126">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="6a740-127">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="6a740-127">**Group by**</span></span>|<span data-ttu-id="6a740-128">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="6a740-128">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="6a740-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6a740-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a740-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a740-130">See Also</span></span>  
 <span data-ttu-id="6a740-131">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6a740-131">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="6a740-132">[步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6a740-132">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="6a740-133">[步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6a740-133">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="6a740-134">步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="6a740-134">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)