---
title: 步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39fe96e60ea183c4ab9ccde767f9848395191233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366221"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="273dd-102">步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="273dd-102">Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="273dd-103">在开始此步骤之前，必须完成[步骤 2:为 InterAct 存储和转发方案向 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="273dd-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="273dd-104">若要添加的文件接收位置</span><span class="sxs-lookup"><span data-stu-id="273dd-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="273dd-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="273dd-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="273dd-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="273dd-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="273dd-107">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="273dd-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="273dd-108">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="273dd-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="273dd-109">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="273dd-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="273dd-110">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="273dd-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="273dd-111">在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="273dd-111">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="273dd-112">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="273dd-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="273dd-113">**使用此**</span><span class="sxs-lookup"><span data-stu-id="273dd-113">**Use this**</span></span>|<span data-ttu-id="273dd-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="273dd-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="273dd-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="273dd-115">**Receive handler**</span></span>|<span data-ttu-id="273dd-116">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="273dd-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="273dd-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="273dd-117">**Receive pipeline**</span></span>|<span data-ttu-id="273dd-118">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="273dd-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="273dd-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="273dd-119">Click **OK**.</span></span>  
  
10. <span data-ttu-id="273dd-120">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="273dd-120">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="273dd-121">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="273dd-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="273dd-122">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_IA_InputRequest_PullMode**。</span><span class="sxs-lookup"><span data-stu-id="273dd-122">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="273dd-123">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="273dd-123">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="273dd-124">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="273dd-124">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="273dd-125">在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="273dd-125">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="273dd-126">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="273dd-126">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="273dd-127">**使用此**</span><span class="sxs-lookup"><span data-stu-id="273dd-127">**Use this**</span></span>|<span data-ttu-id="273dd-128">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="273dd-128">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="273dd-129">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="273dd-129">**Receive handler**</span></span>|<span data-ttu-id="273dd-130">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="273dd-130">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="273dd-131">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="273dd-131">**Receive pipeline**</span></span>|<span data-ttu-id="273dd-132">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="273dd-132">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="273dd-133">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="273dd-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273dd-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="273dd-134">See Also</span></span>  
 <span data-ttu-id="273dd-135">[步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="273dd-135">[Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span></span>  
 [<span data-ttu-id="273dd-136">步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="273dd-136">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)