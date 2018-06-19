---
title: 步骤 3： 配置并启动应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f26035094ee6e39b672b480525747f8aaf4ede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223501"
---
# <a name="step-3-configure-and-start-the-application"></a><span data-ttu-id="01cfb-102">步骤 3： 配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="01cfb-102">Step 3: Configure and Start the Application</span></span>
<span data-ttu-id="01cfb-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="01cfb-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="01cfb-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="01cfb-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="01cfb-105">**目标：** 在此步骤中，可以配置和启动 SampleApplication 应用程序。</span><span class="sxs-lookup"><span data-stu-id="01cfb-105">**Objective:** In this step, you configure and start the SampleApplication application.</span></span> <span data-ttu-id="01cfb-106">当配置 SampleApplication 应用程序时，你将关联中创建的逻辑项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]与其物理对应项。</span><span class="sxs-lookup"><span data-stu-id="01cfb-106">When you configure the SampleApplication application, you associate the logical artifacts you created in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] with their physical counterparts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01cfb-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="01cfb-107">Prerequisites</span></span>  
 <span data-ttu-id="01cfb-108">你必须已完成[步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="01cfb-108">You must have completed [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
### <a name="to-configure-and-start-the-application"></a><span data-ttu-id="01cfb-109">若要配置和启动应用程序</span><span class="sxs-lookup"><span data-stu-id="01cfb-109">To configure and start the application</span></span>  
  
1.  <span data-ttu-id="01cfb-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="01cfb-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="01cfb-111">在控制台树中的左侧上，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-111">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="01cfb-112">展开**BizTalk 组**，展开**应用程序**，右键单击**SampleApplication**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-112">Expand **BizTalk Group**, expand **Applications**, right-click **SampleApplication**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="01cfb-113">在**配置应用程序**对话框中，在**EmployeeOrch**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01cfb-113">In the **Configure Application** dialog box, on the **EmployeeOrch** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="01cfb-114">有关**主机**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-114">For **Host** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
    2.  <span data-ttu-id="01cfb-115">双击跨单元格**ReceiveNotification**和选择**NotifyReceivePort**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01cfb-115">Double-click the cell across **ReceiveNotification** and select **NotifyReceivePort** from the drop-down list.</span></span>  
  
    3.  <span data-ttu-id="01cfb-116">双击跨单元格**SQLOutboundPort**和选择**SQLOutboundPort**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01cfb-116">Double-click the cell across **SQLOutboundPort** and select **SQLOutboundPort** from the drop-down list.</span></span>  
  
    4.  <span data-ttu-id="01cfb-117">双击跨单元格**SaveResponsePort**和选择**EmailResponse**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01cfb-117">Double-click the cell across **SaveResponsePort** and select **EmailResponse** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="01cfb-118">下图显示了配置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="01cfb-118">The following figure shows a configured application.</span></span>  
  
     <span data-ttu-id="01cfb-119">![配置应用程序](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span><span class="sxs-lookup"><span data-stu-id="01cfb-119">![Configured application](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span></span>  
  
6.  <span data-ttu-id="01cfb-120">在**配置应用程序**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-120">In the **Configure Application** dialog box, click **OK**.</span></span>  
  
7.  <span data-ttu-id="01cfb-121">在控制台树中，右键单击**SampleApplication**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-121">In the console tree, right-click **SampleApplication**, and then click **Start**.</span></span>  
  
8.  <span data-ttu-id="01cfb-122">在控制台树中，单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-122">In the console tree, click **Applications**.</span></span>  
  
9. <span data-ttu-id="01cfb-123">在应用程序详细信息窗格中，检查**状态**的**SampleApplication**是**已启动**。</span><span class="sxs-lookup"><span data-stu-id="01cfb-123">In the Applications details pane, check that the **Status** of **SampleApplication** is **Started**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="01cfb-124">内容回顾</span><span class="sxs-lookup"><span data-stu-id="01cfb-124">What did I just do?</span></span>  
 <span data-ttu-id="01cfb-125">配置和启动 SampleApplication 应用程序</span><span class="sxs-lookup"><span data-stu-id="01cfb-125">You configured and started the SampleApplication application</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="01cfb-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="01cfb-126">Next Steps</span></span>  
 <span data-ttu-id="01cfb-127">测试应用程序插入中的新员工**员工**表中所述[步骤 4： 测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)。</span><span class="sxs-lookup"><span data-stu-id="01cfb-127">You test the application by inserting new employees in the **Employee** table, as described in [Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cfb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01cfb-128">See Also</span></span>  
 <span data-ttu-id="01cfb-129">[步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="01cfb-129">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 <span data-ttu-id="01cfb-130">[步骤 4： 测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="01cfb-130">[Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span></span>  
 [<span data-ttu-id="01cfb-131">第 5 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="01cfb-131">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)