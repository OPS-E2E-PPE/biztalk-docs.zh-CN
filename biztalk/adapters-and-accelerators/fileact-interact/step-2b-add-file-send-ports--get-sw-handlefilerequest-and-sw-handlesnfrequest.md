---
title: '步骤 2B： 添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47515324fae89937754e0643563f16df9777868a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991486"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="64f3f-102">步骤 2B： 添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="64f3f-102">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="64f3f-103">在开始此步骤之前，必须完成[步骤 2A： 添加文件接收位置为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)部分。</span><span class="sxs-lookup"><span data-stu-id="64f3f-103">Before you begin this step, you must complete the [Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) section.</span></span>  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a><span data-ttu-id="64f3f-104">若要添加一个 FILE 发送端口以捕获 Sw: HandleFileRequest 消息</span><span class="sxs-lookup"><span data-stu-id="64f3f-104">To add a FILE send port to capture the Sw: HandleFileRequest message</span></span>  

1. <span data-ttu-id="64f3f-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-105">Start **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="64f3f-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="64f3f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  

3. <span data-ttu-id="64f3f-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="64f3f-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  

4. <span data-ttu-id="64f3f-108">在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_FA_SendPullResponsetoReceiver**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>  

5. <span data-ttu-id="64f3f-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="64f3f-110">在中**FILE 传输属性**对话框中**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\FileAct\PullResponse**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\FileAct\PullResponse**, and then click **OK**.</span></span>  

7. <span data-ttu-id="64f3f-111">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64f3f-111">In the **Send Port Properties** window, do the following:</span></span>  


   |   <span data-ttu-id="64f3f-112">**使用此**</span><span class="sxs-lookup"><span data-stu-id="64f3f-112">**Use this**</span></span>    |                        <span data-ttu-id="64f3f-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="64f3f-113">**To do this**</span></span>                         |
   |-------------------|---------------------------------------------------------------|
   | <span data-ttu-id="64f3f-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="64f3f-114">**Send handler**</span></span>  | <span data-ttu-id="64f3f-115">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-115">From the drop-down list, select **BizTalkServerApplication**.</span></span> |
   | <span data-ttu-id="64f3f-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="64f3f-116">**Send pipeline**</span></span> |       <span data-ttu-id="64f3f-117">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-117">From the drop-down list, select **XMLTransmit**.</span></span>        |


8. <span data-ttu-id="64f3f-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="64f3f-118">Click **OK**.</span></span>  

9. <span data-ttu-id="64f3f-119">重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="64f3f-119">Repeat step 1 and 2.</span></span>  

10. <span data-ttu-id="64f3f-120">右键单击**发送端口**，依次指向**新建**，然后单击**动态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-120">Right-click **Send Ports**, point to **New**, and then click **Dynamic Solicit-Response Send Port**.</span></span>  

11. <span data-ttu-id="64f3f-121">在中**发送端口属性**窗口中，命名发送端口<strong>，Tutorial_IA_DynamicSendPort</strong>。</span><span class="sxs-lookup"><span data-stu-id="64f3f-121">In the **Send Port Properties** window, name the send port<strong>, Tutorial_IA_DynamicSendPort</strong>.</span></span>  

12. <span data-ttu-id="64f3f-122">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64f3f-122">In the **Send Port Properties** window, do the following:</span></span>  


    |     <span data-ttu-id="64f3f-123">**使用此**</span><span class="sxs-lookup"><span data-stu-id="64f3f-123">**Use this**</span></span>     |                  <span data-ttu-id="64f3f-124">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="64f3f-124">**To do this**</span></span>                  |
    |----------------------|--------------------------------------------------|
    |  <span data-ttu-id="64f3f-125">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="64f3f-125">**Send pipeline**</span></span>   | <span data-ttu-id="64f3f-126">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-126">From the drop-down list, select **XMLTransmit**.</span></span> |
    | <span data-ttu-id="64f3f-127">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="64f3f-127">**Receive pipeline**</span></span> | <span data-ttu-id="64f3f-128">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="64f3f-128">From the drop-down list, select **XMLReceive**.</span></span>  |


13. <span data-ttu-id="64f3f-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="64f3f-129">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="64f3f-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="64f3f-130">See Also</span></span>  
 <span data-ttu-id="64f3f-131">[步骤 2A： 为 FileAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="64f3f-131">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="64f3f-132">步骤 2C：为 FileAct 存储和转发（拉取）方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="64f3f-132">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)