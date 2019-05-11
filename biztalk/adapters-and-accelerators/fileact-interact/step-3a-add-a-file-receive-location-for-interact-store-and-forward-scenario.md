---
title: 步骤 3a:为 InterAct 存储和转发方案添加文件接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb4594877cb4679bbb355d8ea9ee66041c12dfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365923"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="113ca-102">步骤 3a:为 InterAct 存储和转发方案添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="113ca-102">Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="113ca-103">完整[步骤 2:向为 InterAct 存储和转发方案 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="113ca-103">Complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="113ca-104">添加 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="113ca-104">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="113ca-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="113ca-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="113ca-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="113ca-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="113ca-107">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="113ca-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="113ca-108">在中**接收端口属性**窗口中，名称的接收端口，Tutorial_IA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="113ca-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="113ca-109">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="113ca-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="113ca-110">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="113ca-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="113ca-111">在中**FILE 传输属性**对话框中，键入 C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="113ca-111">In the **FILE Transport Properties** dialog box, type C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="113ca-112">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="113ca-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="113ca-113">**使用此**</span><span class="sxs-lookup"><span data-stu-id="113ca-113">**Use this**</span></span>|<span data-ttu-id="113ca-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="113ca-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="113ca-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="113ca-115">**Receive handler**</span></span>|<span data-ttu-id="113ca-116">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="113ca-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="113ca-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="113ca-117">**Receive pipeline**</span></span>|<span data-ttu-id="113ca-118">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="113ca-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="113ca-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="113ca-119">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="113ca-120">完成的步骤</span><span class="sxs-lookup"><span data-stu-id="113ca-120">Complete steps</span></span>
 <span data-ttu-id="113ca-121">[步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="113ca-121">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="113ca-122">[步骤 3b:为 InterAct 存储和转发方案添加 INTERACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="113ca-122">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="113ca-123">步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="113ca-123">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="113ca-124">步骤 3D:为 InterAct 存储和转发方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="113ca-124">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)