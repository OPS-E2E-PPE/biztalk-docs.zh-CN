---
title: 步骤 3a:为 FileAct 实时方案添加文件接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e25342d623d9d9d32c055b450c9751af6b0cd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365755"
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a><span data-ttu-id="0ce06-102">步骤 3a:为 FileAct 实时方案添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="0ce06-102">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="0ce06-103">在开始此步骤之前，必须完成[步骤 2:为 FileAct 实时方案向 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce06-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="0ce06-104">若要添加 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="0ce06-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="0ce06-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0ce06-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ce06-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="0ce06-107">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="0ce06-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="0ce06-108">在中**接收端口属性**窗口中，名称的接收端口，Tutorial_FA_InputRequest_RealTime。</span><span class="sxs-lookup"><span data-stu-id="0ce06-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_RealTime.</span></span>  
  
5.  <span data-ttu-id="0ce06-109">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="0ce06-110">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="0ce06-111">在中**FILE 传输属性**对话框中**接收文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="0ce06-112">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ce06-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="0ce06-113">**使用此**</span><span class="sxs-lookup"><span data-stu-id="0ce06-113">**Use this**</span></span>|<span data-ttu-id="0ce06-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="0ce06-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="0ce06-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="0ce06-115">**Receive handler**</span></span>|<span data-ttu-id="0ce06-116">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="0ce06-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="0ce06-117">**Receive pipeline**</span></span>|<span data-ttu-id="0ce06-118">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="0ce06-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="0ce06-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0ce06-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce06-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce06-120">See Also</span></span>  
 <span data-ttu-id="0ce06-121">[步骤 3：创建发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0ce06-121">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0ce06-122">[步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0ce06-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="0ce06-123">[步骤 3c:添加 FILE 发送端口以捕获为 FileAct 实时方案： handlerequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="0ce06-123">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 <span data-ttu-id="0ce06-124">[步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0ce06-124">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="0ce06-125">步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="0ce06-125">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)