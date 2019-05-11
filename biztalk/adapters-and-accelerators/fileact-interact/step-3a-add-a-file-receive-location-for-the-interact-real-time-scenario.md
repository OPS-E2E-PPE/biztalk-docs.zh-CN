---
title: 步骤 3a:添加 FILE 接收位置 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 776a5b8c708e9b86c6bd844fc2dcb46aed9efe40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365673"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="74f03-102">步骤 3a:添加 FILE 接收位置 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="74f03-102">Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="74f03-103">设置接收位置，可用于轻松地删除测试文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="74f03-103">Set up a receive location that enables you to easily drop test files for validation.</span></span> <span data-ttu-id="74f03-104">此位置用于测试的方案。</span><span class="sxs-lookup"><span data-stu-id="74f03-104">You use this location to test the scenario.</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="74f03-105">添加 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="74f03-105">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="74f03-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="74f03-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="74f03-107">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="74f03-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="74f03-108">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="74f03-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="74f03-109">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_IA_InputRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="74f03-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="74f03-110">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="74f03-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="74f03-111">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="74f03-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="74f03-112">在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="74f03-112">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="74f03-113">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74f03-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="74f03-114">**使用此**</span><span class="sxs-lookup"><span data-stu-id="74f03-114">**Use this**</span></span>|<span data-ttu-id="74f03-115">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="74f03-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="74f03-116">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="74f03-116">**Receive handler**</span></span>|<span data-ttu-id="74f03-117">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="74f03-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="74f03-118">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="74f03-118">**Receive pipeline**</span></span>|<span data-ttu-id="74f03-119">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="74f03-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="74f03-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="74f03-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f03-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="74f03-121">See Also</span></span>  
 <span data-ttu-id="74f03-122">[步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="74f03-122">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="74f03-123">[步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="74f03-123">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="74f03-124">[步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="74f03-124">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="74f03-125">[步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="74f03-125">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="74f03-126">步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="74f03-126">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)