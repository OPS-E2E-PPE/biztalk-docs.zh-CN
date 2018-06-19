---
title: 步骤 3A： 添加一个文件接收位置交互应用商店应用和向前方案 |Microsoft 文档
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
ms.openlocfilehash: 7d2027878771249ceb2dcb45683a71b4475a75cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224173"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="ab7d5-102">步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置</span><span class="sxs-lookup"><span data-stu-id="ab7d5-102">Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="ab7d5-103">完成[步骤 2： 将 SWIFTNet 配置添加到交互应用商店应用和转发方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-103">Complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="ab7d5-104">添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="ab7d5-104">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="ab7d5-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ab7d5-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="ab7d5-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="ab7d5-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="ab7d5-108">在**接收端口属性**窗口中，名称接收端口，Tutorial_IA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="ab7d5-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="ab7d5-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ab7d5-111">在**文件传输属性**对话框中，键入 C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-111">In the **FILE Transport Properties** dialog box, type C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="ab7d5-112">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab7d5-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="ab7d5-113">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="ab7d5-113">**Use this**</span></span>|<span data-ttu-id="ab7d5-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="ab7d5-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="ab7d5-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="ab7d5-115">**Receive handler**</span></span>|<span data-ttu-id="ab7d5-116">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="ab7d5-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="ab7d5-117">**Receive pipeline**</span></span>|<span data-ttu-id="ab7d5-118">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="ab7d5-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ab7d5-119">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="ab7d5-120">完成步骤</span><span class="sxs-lookup"><span data-stu-id="ab7d5-120">Complete steps</span></span>
 <span data-ttu-id="ab7d5-121">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ab7d5-121">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="ab7d5-122">[步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ab7d5-122">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="ab7d5-123">步骤 3c： 添加文件发送端口交互应用商店应用和向前情况下捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="ab7d5-123">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="ab7d5-124">步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="ab7d5-124">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)