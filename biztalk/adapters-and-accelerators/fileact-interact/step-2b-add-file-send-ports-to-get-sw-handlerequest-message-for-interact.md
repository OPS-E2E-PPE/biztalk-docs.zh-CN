---
title: '步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36ca62623cc6dd78f9c980fa35c3f0e744bc2666
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366115"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="d894e-102">步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="d894e-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="d894e-103">在开始此步骤之前，必须完成[步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="d894e-103">Before you begin this step, you must complete [Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md).</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a><span data-ttu-id="d894e-104">若要添加一个 FILE 发送端口以捕获 sw: handlerequest 消息</span><span class="sxs-lookup"><span data-stu-id="d894e-104">To add a FILE send port to capture the Sw:HandleRequest message</span></span>  

1. <span data-ttu-id="d894e-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d894e-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="d894e-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d894e-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="d894e-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="d894e-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="d894e-108">在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_IA_SendPullResponsetoReceiver**。</span><span class="sxs-lookup"><span data-stu-id="d894e-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="d894e-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d894e-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="d894e-110">在中**FILE 传输属性**对话框中**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\PullResponse**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d894e-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="d894e-111">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d894e-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="d894e-112">**使用此**</span><span class="sxs-lookup"><span data-stu-id="d894e-112">**Use this**</span></span>    |                        <span data-ttu-id="d894e-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d894e-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="d894e-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d894e-114">**Send handler**</span></span>  | <span data-ttu-id="d894e-115">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d894e-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="d894e-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d894e-116">**Send pipeline**</span></span> |       <span data-ttu-id="d894e-117">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d894e-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="d894e-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d894e-118">Click **OK**.</span></span>  

9. <span data-ttu-id="d894e-119">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="d894e-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="d894e-120">右键单击**发送端口**，依次指向**新建**，然后单击**动态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d894e-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="d894e-121">在中**发送端口属性**窗口中，命名发送端口<strong>，Tutorial_IA_DynamicSendPort</strong>。</span><span class="sxs-lookup"><span data-stu-id="d894e-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="d894e-122">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d894e-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="d894e-123">**使用此**</span><span class="sxs-lookup"><span data-stu-id="d894e-123">**Use this**</span></span>     |                  <span data-ttu-id="d894e-124">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d894e-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="d894e-125">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d894e-125">**Send pipeline**</span></span>   | <span data-ttu-id="d894e-126">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d894e-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="d894e-127">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="d894e-127">**Receive pipeline**</span></span> | <span data-ttu-id="d894e-128">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="d894e-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="d894e-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d894e-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d894e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d894e-130">See Also</span></span>  
 <span data-ttu-id="d894e-131">[步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d894e-131">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="d894e-132">步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="d894e-132">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)