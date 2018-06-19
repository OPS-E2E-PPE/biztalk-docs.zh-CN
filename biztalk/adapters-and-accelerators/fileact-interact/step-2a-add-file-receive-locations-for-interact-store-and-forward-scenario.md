---
title: 步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置 |Microsoft 文档
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
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225269"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="1a9a7-102">步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置</span><span class="sxs-lookup"><span data-stu-id="1a9a7-102">Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="1a9a7-103">在开始此步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到交互应用商店应用和转发方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="1a9a7-104">若要添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="1a9a7-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="1a9a7-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1a9a7-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="1a9a7-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="1a9a7-108">在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="1a9a7-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="1a9a7-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="1a9a7-111">在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-111">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1a9a7-112">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a9a7-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1a9a7-113">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-113">**Use this**</span></span>|<span data-ttu-id="1a9a7-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1a9a7-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-115">**Receive handler**</span></span>|<span data-ttu-id="1a9a7-116">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="1a9a7-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-117">**Receive pipeline**</span></span>|<span data-ttu-id="1a9a7-118">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="1a9a7-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-119">Click **OK**.</span></span>  
  
10. <span data-ttu-id="1a9a7-120">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-120">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="1a9a7-121">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="1a9a7-122">在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_InputRequest_PullMode**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-122">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="1a9a7-123">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-123">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="1a9a7-124">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-124">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="1a9a7-125">在**文件传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-125">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="1a9a7-126">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a9a7-126">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1a9a7-127">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-127">**Use this**</span></span>|<span data-ttu-id="1a9a7-128">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-128">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1a9a7-129">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-129">**Receive handler**</span></span>|<span data-ttu-id="1a9a7-130">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-130">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="1a9a7-131">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="1a9a7-131">**Receive pipeline**</span></span>|<span data-ttu-id="1a9a7-132">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-132">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="1a9a7-133">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1a9a7-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9a7-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a9a7-134">See Also</span></span>  
 <span data-ttu-id="1a9a7-135">[步骤 2B： 添加要捕获 Sw:HandleRequest 消息交互，应用商店应用和进 （请求） 方案的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="1a9a7-135">[Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md) </span></span>  
 [<span data-ttu-id="1a9a7-136">步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="1a9a7-136">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)