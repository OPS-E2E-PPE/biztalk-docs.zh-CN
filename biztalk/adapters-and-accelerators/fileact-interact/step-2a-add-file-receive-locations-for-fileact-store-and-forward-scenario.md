---
title: 步骤 2A-添加 FILE 接收位置 |Microsoft Docs
description: 步骤 2A-添加 FILE 接收位置为 FileAct 存储和转发 （拉取） 方案，BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30311c846b26142e0beeea5ab503dd9599b41e18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366192"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="9d7ca-103">步骤 2A:为 FileAct 存储和转发 （拉取） 方案添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="9d7ca-103">Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="9d7ca-104">在开始此步骤之前，必须完成[步骤 1:配置 SWIFT 适配器为 FileAct 存储和转发 （拉取） 方案](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward (Pull) Scenario](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="9d7ca-105">添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="9d7ca-105">Add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="9d7ca-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9d7ca-107">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="9d7ca-108">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="9d7ca-109">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_FA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_FA_InputRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="9d7ca-110">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="9d7ca-111">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="9d7ca-112">在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-112">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="9d7ca-113">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9d7ca-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9d7ca-114">**使用此**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-114">**Use this**</span></span>|<span data-ttu-id="9d7ca-115">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9d7ca-116">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-116">**Receive handler**</span></span>|<span data-ttu-id="9d7ca-117">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="9d7ca-118">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-118">**Receive pipeline**</span></span>|<span data-ttu-id="9d7ca-119">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="9d7ca-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-120">Click **OK**.</span></span>  
  
10. <span data-ttu-id="9d7ca-121">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-121">Repeat steps 1 and 2.</span></span>  
  
11. <span data-ttu-id="9d7ca-122">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-122">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
12. <span data-ttu-id="9d7ca-123">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_ FA_InputRequest_PullMode**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-123">In the **Receive Port Properties** window, name the receive port, **Tutorial_ FA_InputRequest_PullMode**.</span></span>  
  
13. <span data-ttu-id="9d7ca-124">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-124">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
14. <span data-ttu-id="9d7ca-125">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-125">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
15. <span data-ttu-id="9d7ca-126">在中**FILE 传输属性**对话框中，键入**C:\SWIFTAdapterTutorial\Interact\PullRequest**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-126">In the **FILE Transport Properties** dialog box, type **C:\SWIFTAdapterTutorial\Interact\PullRequest**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="9d7ca-127">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9d7ca-127">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9d7ca-128">**使用此**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-128">**Use this**</span></span>|<span data-ttu-id="9d7ca-129">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-129">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9d7ca-130">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-130">**Receive handler**</span></span>|<span data-ttu-id="9d7ca-131">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-131">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="9d7ca-132">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="9d7ca-132">**Receive pipeline**</span></span>|<span data-ttu-id="9d7ca-133">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-133">From the drop-down list, select **XMLReceive**.</span></span>|  
  
17. <span data-ttu-id="9d7ca-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d7ca-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9d7ca-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9d7ca-135">Next steps</span></span>
-  [<span data-ttu-id="9d7ca-136">步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="9d7ca-136">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [<span data-ttu-id="9d7ca-137">步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="9d7ca-137">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)