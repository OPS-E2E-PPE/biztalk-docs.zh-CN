---
title: 步骤 3：配置并启动应用程序 |Microsoft Docs
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
ms.openlocfilehash: 6dd0d569355d0873b42bc708b44e12993e97f58e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367707"
---
# <a name="step-3-configure-and-start-the-application"></a><span data-ttu-id="86d72-102">步骤 3：配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="86d72-102">Step 3: Configure and Start the Application</span></span>
<span data-ttu-id="86d72-103">![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="86d72-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="86d72-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="86d72-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="86d72-105">**目标：** 在此步骤中，配置和启动 SampleApplication 应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d72-105">**Objective:** In this step, you configure and start the SampleApplication application.</span></span> <span data-ttu-id="86d72-106">在配置 SampleApplication 应用程序时，将关联中创建的逻辑项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]与其物理对应项。</span><span class="sxs-lookup"><span data-stu-id="86d72-106">When you configure the SampleApplication application, you associate the logical artifacts you created in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] with their physical counterparts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="86d72-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="86d72-107">Prerequisites</span></span>  
 <span data-ttu-id="86d72-108">你必须已完成[步骤 2:配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="86d72-108">You must have completed [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
### <a name="to-configure-and-start-the-application"></a><span data-ttu-id="86d72-109">若要配置和启动应用程序</span><span class="sxs-lookup"><span data-stu-id="86d72-109">To configure and start the application</span></span>  
  
1. <span data-ttu-id="86d72-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="86d72-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="86d72-111">在左侧控制台树中，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="86d72-111">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="86d72-112">展开**BizTalk 组**，展开**应用程序**，右键单击**SampleApplication**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="86d72-112">Expand **BizTalk Group**, expand **Applications**, right-click **SampleApplication**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="86d72-113">在中**配置应用程序**对话框中，在**EmployeeOrch**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86d72-113">In the **Configure Application** dialog box, on the **EmployeeOrch** tab, do the following:</span></span>  
  
   1.  <span data-ttu-id="86d72-114">有关**主机**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="86d72-114">For **Host** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
   2.  <span data-ttu-id="86d72-115">双击跨单元格**ReceiveNotification** ，然后选择**NotifyReceivePort**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="86d72-115">Double-click the cell across **ReceiveNotification** and select **NotifyReceivePort** from the drop-down list.</span></span>  
  
   3.  <span data-ttu-id="86d72-116">双击跨单元格**SQLOutboundPort** ，然后选择**SQLOutboundPort**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="86d72-116">Double-click the cell across **SQLOutboundPort** and select **SQLOutboundPort** from the drop-down list.</span></span>  
  
   4.  <span data-ttu-id="86d72-117">双击跨单元格**SaveResponsePort** ，然后选择**EmailResponse**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="86d72-117">Double-click the cell across **SaveResponsePort** and select **EmailResponse** from the drop-down list.</span></span>  
  
5. <span data-ttu-id="86d72-118">下图显示了配置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d72-118">The following figure shows a configured application.</span></span>  
  
    <span data-ttu-id="86d72-119">![配置应用程序](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span><span class="sxs-lookup"><span data-stu-id="86d72-119">![Configured application](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span></span>  
  
6. <span data-ttu-id="86d72-120">在中**配置应用程序**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="86d72-120">In the **Configure Application** dialog box, click **OK**.</span></span>  
  
7. <span data-ttu-id="86d72-121">在控制台树中，右键单击**SampleApplication**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="86d72-121">In the console tree, right-click **SampleApplication**, and then click **Start**.</span></span>  
  
8. <span data-ttu-id="86d72-122">在控制台树中，单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="86d72-122">In the console tree, click **Applications**.</span></span>  
  
9. <span data-ttu-id="86d72-123">在应用程序的详细信息窗格中，检查**状态**的**SampleApplication**是**已启动**。</span><span class="sxs-lookup"><span data-stu-id="86d72-123">In the Applications details pane, check that the **Status** of **SampleApplication** is **Started**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="86d72-124">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="86d72-124">What did I just do?</span></span>  
 <span data-ttu-id="86d72-125">已配置并启动 SampleApplication 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d72-125">You configured and started the SampleApplication application</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="86d72-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="86d72-126">Next Steps</span></span>  
 <span data-ttu-id="86d72-127">插入新入职员工的测试应用程序**员工**表，如中所述[步骤 4:测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)。</span><span class="sxs-lookup"><span data-stu-id="86d72-127">You test the application by inserting new employees in the **Employee** table, as described in [Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d72-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="86d72-128">See Also</span></span>  
 <span data-ttu-id="86d72-129">[步骤 2：配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="86d72-129">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 <span data-ttu-id="86d72-130">[步骤 4：测试应用程序](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="86d72-130">[Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span></span>  
 [<span data-ttu-id="86d72-131">第 5 课：部署解决方案</span><span class="sxs-lookup"><span data-stu-id="86d72-131">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)