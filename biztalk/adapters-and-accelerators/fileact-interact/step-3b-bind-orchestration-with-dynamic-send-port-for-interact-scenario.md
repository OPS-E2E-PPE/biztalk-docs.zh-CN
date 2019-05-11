---
title: 步骤 3b:将替换为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55eec1f3-b920-48f8-946a-9ad7afa36fd6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4719f347004c473a9e9ab6159d33ab2afaaead21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365580"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="b158d-102">步骤 3b:将替换为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定</span><span class="sxs-lookup"><span data-stu-id="b158d-102">Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="b158d-103">在开始此步骤之前，必须完成[步骤 3A:创建为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="b158d-103">Before you begin this step, you must complete [Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="b158d-104">若要添加的文件接收位置</span><span class="sxs-lookup"><span data-stu-id="b158d-104">To add a FILE Receive location</span></span>  
  
1.  <span data-ttu-id="b158d-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b158d-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b158d-106">在 BizTalk Server 管理控制台，在左窗格中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="b158d-106">In the BizTalk Server Administration Console, in the left pane, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="b158d-107">验证的状态**BizTalkServerApplication**托管实例和交互主机实例是**运行**。</span><span class="sxs-lookup"><span data-stu-id="b158d-107">Verify that the status for the **BizTalkServerApplication** host instance and Interact host instance is **running**.</span></span> <span data-ttu-id="b158d-108">如果没有，请右键单击主机实例，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="b158d-108">If not, right-click the host instances, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="b158d-109">在左窗格中，展开应用程序，然后展开 BizTalk Application 1。</span><span class="sxs-lookup"><span data-stu-id="b158d-109">In the left pane, expand Applications, and then expand BizTalk Application 1.</span></span> <span data-ttu-id="b158d-110">单击业务流程。</span><span class="sxs-lookup"><span data-stu-id="b158d-110">Click Orchestrations.</span></span>  
  
4.  <span data-ttu-id="b158d-111">右键单击**DynamicSendOrchestration**然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b158d-111">Right-click **DynamicSendOrchestration** and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="b158d-112">在中**业务流程属性**对话框中，在左窗格中，单击**绑定**并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b158d-112">In the **Orchestration Properties** dialog box, in the left pane, click **Bindings** and do the following:</span></span>  
  
    |<span data-ttu-id="b158d-113">**使用此**</span><span class="sxs-lookup"><span data-stu-id="b158d-113">**Use this**</span></span>|<span data-ttu-id="b158d-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="b158d-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b158d-115">**主机**</span><span class="sxs-lookup"><span data-stu-id="b158d-115">**Host**</span></span>|<span data-ttu-id="b158d-116">从下拉列表中，选择**BizTalkServer 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b158d-116">From the drop-down list, select **BizTalkServer Application**.</span></span>|  
    |<span data-ttu-id="b158d-117">**动态请求**</span><span class="sxs-lookup"><span data-stu-id="b158d-117">**Dynamic Pull**</span></span>|<span data-ttu-id="b158d-118">从下拉列表中，选择**Tutorial_IA_DynamicSendPort**。</span><span class="sxs-lookup"><span data-stu-id="b158d-118">From the drop-down list, select **Tutorial_IA_DynamicSendPort**.</span></span>|  
    |<span data-ttu-id="b158d-119">**SendPullResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="b158d-119">**SendPullResponseToSender**</span></span>|<span data-ttu-id="b158d-120">从下拉列表中，选择**Tutorial_IA_SendPullResponsetoReceiver**。</span><span class="sxs-lookup"><span data-stu-id="b158d-120">From the drop-down list, select **Tutorial_IA_SendPullResponsetoReceiver**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b158d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b158d-121">See Also</span></span>  
 [<span data-ttu-id="b158d-122">步骤 3a:创建为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程</span><span class="sxs-lookup"><span data-stu-id="b158d-122">Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)