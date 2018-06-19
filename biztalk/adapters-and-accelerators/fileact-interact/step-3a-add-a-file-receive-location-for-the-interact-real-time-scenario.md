---
title: 步骤 3A： 添加一个文件接收位置交互实时方案 |Microsoft 文档
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
ms.openlocfilehash: 6c29b3eb291b1b36daab5d77aae74f6055a3c738
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224557"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="2eb12-102">步骤 3A： 添加一个文件接收位置交互实时方案</span><span class="sxs-lookup"><span data-stu-id="2eb12-102">Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="2eb12-103">设置使您能够轻松地删除用于验证测试文件的接收位置。</span><span class="sxs-lookup"><span data-stu-id="2eb12-103">Set up a receive location that enables you to easily drop test files for validation.</span></span> <span data-ttu-id="2eb12-104">此位置用于测试的方案。</span><span class="sxs-lookup"><span data-stu-id="2eb12-104">You use this location to test the scenario.</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="2eb12-105">添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="2eb12-105">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="2eb12-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2eb12-107">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2eb12-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="2eb12-108">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="2eb12-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="2eb12-109">在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_InputRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="2eb12-110">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="2eb12-111">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="2eb12-112">在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-112">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="2eb12-113">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2eb12-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2eb12-114">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="2eb12-114">**Use this**</span></span>|<span data-ttu-id="2eb12-115">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="2eb12-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2eb12-116">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="2eb12-116">**Receive handler**</span></span>|<span data-ttu-id="2eb12-117">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="2eb12-118">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="2eb12-118">**Receive pipeline**</span></span>|<span data-ttu-id="2eb12-119">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="2eb12-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2eb12-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb12-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eb12-121">See Also</span></span>  
 <span data-ttu-id="2eb12-122">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2eb12-122">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2eb12-123">[步骤 3B： 添加交互接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2eb12-123">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2eb12-124">[步骤 3c： 添加要捕获的 Sw:HandleRequest 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2eb12-124">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="2eb12-125">[步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="2eb12-125">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="2eb12-126">步骤 3E： 添加的交互发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="2eb12-126">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)