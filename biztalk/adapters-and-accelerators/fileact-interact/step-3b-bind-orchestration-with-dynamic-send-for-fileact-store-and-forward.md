---
title: "步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb973066-8797-4f51-a89e-3845f2811605
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10111de1080aacd532be96f501be1d20acda1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="6cc23-102">步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程</span><span class="sxs-lookup"><span data-stu-id="6cc23-102">Step 3B: Bind the orchestration with dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="6cc23-103">在开始此步骤之前，必须完成[步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="6cc23-103">Before you begin this step, you must complete [Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="6cc23-104">若要添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="6cc23-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="6cc23-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6cc23-106">在 BizTalk Server 管理控制台中，在左窗格中，展开 BizTalk Server 管理，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**.</span><span class="sxs-lookup"><span data-stu-id="6cc23-106">In the BizTalk Server Administration Console, in the left pane, expand BizTalk Server Administration, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="6cc23-107">验证的状态**BizTalkServerApplication**托管实例和 FileActhost 实例是**运行**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-107">Verify that the status for the **BizTalkServerApplication** host instance and FileActhost instance is **running**.</span></span> <span data-ttu-id="6cc23-108">如果没有，右键单击主机实例，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-108">If not, right-click the host instances, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="6cc23-109">在左窗格中，展开应用程序，然后展开 BizTalk 应用程序 1。</span><span class="sxs-lookup"><span data-stu-id="6cc23-109">In the left pane, expand Applications, and then expand BizTalk Application 1.</span></span> <span data-ttu-id="6cc23-110">单击业务流程。</span><span class="sxs-lookup"><span data-stu-id="6cc23-110">Click Orchestrations.</span></span>  
  
4.  <span data-ttu-id="6cc23-111">右键单击**DynamicSendOrchestration**单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-111">Right-click **DynamicSendOrchestration** and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="6cc23-112">在**业务流程属性**对话框中，在左窗格中，单击**绑定**和执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6cc23-112">In the **Orchestration Properties** dialog box, in the left pane, click **Bindings** and do the following:</span></span>  
  
    |<span data-ttu-id="6cc23-113">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="6cc23-113">**Use this**</span></span>|<span data-ttu-id="6cc23-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="6cc23-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6cc23-115">**主机**</span><span class="sxs-lookup"><span data-stu-id="6cc23-115">**Host**</span></span>|<span data-ttu-id="6cc23-116">从下拉列表中选择**BizTalkServer 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-116">From the drop-down list, select **BizTalkServer Application**.</span></span>|  
    |<span data-ttu-id="6cc23-117">**动态请求**</span><span class="sxs-lookup"><span data-stu-id="6cc23-117">**Dynamic Pull**</span></span>|<span data-ttu-id="6cc23-118">从下拉列表中选择**Tutorial_FA_DynamicSendPort**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-118">From the drop-down list, select **Tutorial_FA_DynamicSendPort**.</span></span>|  
    |<span data-ttu-id="6cc23-119">**SendPullResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="6cc23-119">**SendPullResponseToSender**</span></span>|<span data-ttu-id="6cc23-120">从下拉列表中选择**Tutorial_FA_SendPullResponsetoReceiver**。</span><span class="sxs-lookup"><span data-stu-id="6cc23-120">From the drop-down list, select **Tutorial_FA_SendPullResponsetoReceiver**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cc23-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cc23-121">See Also</span></span>  
 [<span data-ttu-id="6cc23-122">步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程</span><span class="sxs-lookup"><span data-stu-id="6cc23-122">Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)