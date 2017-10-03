---
title: "步骤 1： 部署的业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8988fced-b2d5-4ee7-a851-20fc7c3dd087
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47565daf53f66fc5fc898e7c023ca09a34c78113
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-orchestration"></a><span data-ttu-id="d4c53-102">步骤 1： 部署的业务流程</span><span class="sxs-lookup"><span data-stu-id="d4c53-102">Step 1: Deploy the Orchestration</span></span>
<span data-ttu-id="d4c53-103">![步骤 1 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="d4c53-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="d4c53-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="d4c53-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="d4c53-105">**目标：**在此步骤中，将部署业务流程解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4c53-105">**Objective:** In this step, deploy the orchestration solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4c53-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="d4c53-106">Prerequisites</span></span>  
 <span data-ttu-id="d4c53-107">你必须已完成中的步骤[第 4 课： 执行采购订单表上的插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c53-107">You must have completed the steps in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
### <a name="to-deploy-the-solution"></a><span data-ttu-id="d4c53-108">若要部署解决方案</span><span class="sxs-lookup"><span data-stu-id="d4c53-108">To deploy the solution</span></span>  
  
1.  <span data-ttu-id="d4c53-109">在解决方案资源管理器，右键单击解决方案名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d4c53-109">In Solution Explorer, right-click the solution name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4c53-110">在属性页对话框中，在树控件中，展开**配置属性**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d4c53-110">In the properties pages dialog box, in the tree control, expand **Configuration Properties**, and then click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="d4c53-111">上**配置**页上，在**部署**列中，选择 BizTalk 项目中，对应的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d4c53-111">On the **Configuration** page, in the **Deploy** column, select the check box against the BizTalk project, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d4c53-112">在解决方案资源管理器，右键单击解决方案名称，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="d4c53-112">In Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
     <span data-ttu-id="d4c53-113">在屏幕底部的输出窗格中应显示为：**部署： 1 成功，0 失败，0 被跳过**。</span><span class="sxs-lookup"><span data-stu-id="d4c53-113">The Output pane at the bottom of the screen should read: **Deploy: 1 succeeded, 0 failed, 0 skipped**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d4c53-114">内容回顾</span><span class="sxs-lookup"><span data-stu-id="d4c53-114">What did I just do?</span></span>  
 <span data-ttu-id="d4c53-115">在此步骤中，部署到 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d4c53-115">In this step, you deployed the BizTalk orchestration to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d4c53-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d4c53-116">Next Steps</span></span>  
 <span data-ttu-id="d4c53-117">创建中的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中中, 所述[步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c53-117">You create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, as described in [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c53-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c53-118">See Also</span></span>  
 <span data-ttu-id="d4c53-119">[步骤 2： 配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="d4c53-119">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 [<span data-ttu-id="d4c53-120">第 5 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="d4c53-120">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)