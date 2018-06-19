---
title: 步骤 9： 启动 Contoso 业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d58d7f2f9d725fca94eb6cf3d2412b3c376fe015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209445"
---
# <a name="step-9-starting-the-contoso-orchestration"></a><span data-ttu-id="1e52c-102">步骤 9： 启动 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="1e52c-102">Step 9: Starting the Contoso Orchestration</span></span>
<span data-ttu-id="1e52c-103">在此步骤中，你将通过定义物理源位置和目标位置来完成端口配置流程。</span><span class="sxs-lookup"><span data-stu-id="1e52c-103">In this step, you complete the port configuration process by defining the physical source and destination locations.</span></span> <span data-ttu-id="1e52c-104">将物理端口绑定到你在中创建的逻辑端口[步骤 7： 创建和配置端口](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="1e52c-104">You bind the physical ports to the logical ports you created in [Step 7: Creating and Configuring Ports](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md).</span></span> <span data-ttu-id="1e52c-105">然后登记服务关联的物理环境的业务流程将运行中的业务流程中设计的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e52c-105">You then enlist the service to associate the business process that you designed in the orchestration with the physical environment that the orchestration will run in.</span></span> <span data-ttu-id="1e52c-106">最后，你启动业务流程，以便它可以参与与 Fabrikam 的业务事务。</span><span class="sxs-lookup"><span data-stu-id="1e52c-106">Finally, you start the orchestration so that it can participate in business transactions with Fabrikam.</span></span>  
  
### <a name="to-bind-the-orchestration-ports"></a><span data-ttu-id="1e52c-107">绑定业务流程端口</span><span class="sxs-lookup"><span data-stu-id="1e52c-107">To bind the orchestration ports</span></span>  
  
1.  <span data-ttu-id="1e52c-108">打开**BizTalk 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-108">Open **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="1e52c-109">在 BizTalk 资源管理器中，展开**BizTalk 配置数据库**，展开**业务流程**，右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-109">In BizTalk Explorer, expand **BizTalk Configuration Database**, expand **Orchestrations**, right-click **ContosoPriceAndAvailability.PrivateResponderProcess**, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="1e52c-110">在端口绑定属性页中，选择**LOB_To_PrivateResponder**中**FromLOB**属性。</span><span class="sxs-lookup"><span data-stu-id="1e52c-110">On the Port Bindings Properties page, select **LOB_To_PrivateResponder** in the **FromLOB** property.</span></span>  
  
4.  <span data-ttu-id="1e52c-111">在**ContosoSQLReqResponsePort**框中，选择**3A2SQLReqResponseSendPort**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-111">In the **ContosoSQLReqResponsePort** box, select **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="1e52c-112">在**ToLOB**属性中，展开**发送端口**和选择**PrivateResponder_To_LOB**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-112">In the **ToLOB** property, expand **Send Ports** and select **PrivateResponder_To_LOB**.</span></span>  
  
6.  <span data-ttu-id="1e52c-113">在左窗格中的配置窗口中，选择**主机**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-113">In the Configuration window in the left pane, select **Host**.</span></span>  
  
7.  <span data-ttu-id="1e52c-114">在**主机**属性，请在**BizTalk 主机**类别中，选择**BizTalkServerApplication**从下拉列表，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="1e52c-114">In the **Host** property, in the **BizTalk Host** category, select **BizTalkServerApplication** from the drop-down list, and then click **OK**.</span></span>  
  
### <a name="to-start-the-biztalk-runtime-process"></a><span data-ttu-id="1e52c-115">启动 BizTalk 运行时流程</span><span class="sxs-lookup"><span data-stu-id="1e52c-115">To start the BizTalk runtime process</span></span>  
  
1.  <span data-ttu-id="1e52c-116">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-116">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1e52c-117">在 BizTalk 管理控制台中，在左窗格中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，，然后展开**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-117">In the BizTalk Administration Console, in the left pane, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="1e52c-118">验证的状态**BizTalkServerApplication**服务是**运行**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-118">Verify that the status of the **BizTalkServerApplication** service is **Running**.</span></span>  
  
### <a name="to-enlist-and-start-the-orchestration"></a><span data-ttu-id="1e52c-119">登记和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="1e52c-119">To enlist and start the orchestration</span></span>  
  
1.  <span data-ttu-id="1e52c-120">在 BizTalk 管理控制台的左窗格中，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-120">In the left pane of the BizTalk Administration Console, expand **Applications**, expand **BizTalk Application 1**, and then click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="1e52c-121">在右窗格中，右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**业务流程，，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="1e52c-121">In the right pane, right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Enlist**.</span></span>  
  
3.  <span data-ttu-id="1e52c-122">右键单击**ContosoPriceAndAvailability.PrivateResponderProcess**业务流程，，然后单击**启动**启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e52c-122">Right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Start** to start the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e52c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e52c-123">See Also</span></span>  
 [<span data-ttu-id="1e52c-124">创建 Fabrikam 解决方案</span><span class="sxs-lookup"><span data-stu-id="1e52c-124">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)