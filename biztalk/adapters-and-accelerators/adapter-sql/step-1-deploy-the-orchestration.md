---
title: 第 1 步：部署业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8988fced-b2d5-4ee7-a851-20fc7c3dd087
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 570b5e0996864fa047c2b196338c1294804a5b11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367886"
---
# <a name="step-1-deploy-the-orchestration"></a><span data-ttu-id="a8d3c-102">第 1 步：部署业务流程</span><span class="sxs-lookup"><span data-stu-id="a8d3c-102">Step 1: Deploy the Orchestration</span></span>
<span data-ttu-id="a8d3c-103">![步骤 1，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="a8d3c-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="a8d3c-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="a8d3c-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="a8d3c-105">**目标：** 在此步骤中，将部署业务流程解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-105">**Objective:** In this step, deploy the orchestration solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8d3c-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a8d3c-106">Prerequisites</span></span>  
 <span data-ttu-id="a8d3c-107">你必须完成中的步骤[第 4 课：执行插入操作上采购订单表](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-107">You must have completed the steps in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
### <a name="to-deploy-the-solution"></a><span data-ttu-id="a8d3c-108">若要部署解决方案</span><span class="sxs-lookup"><span data-stu-id="a8d3c-108">To deploy the solution</span></span>  
  
1.  <span data-ttu-id="a8d3c-109">在解决方案资源管理器，右键单击解决方案名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-109">In Solution Explorer, right-click the solution name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a8d3c-110">在属性页对话框中，在树控件中，展开**配置属性**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-110">In the properties pages dialog box, in the tree control, expand **Configuration Properties**, and then click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="a8d3c-111">上**配置**页上，在**部署**列中，选择 BizTalk 项目中，对应的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-111">On the **Configuration** page, in the **Deploy** column, select the check box against the BizTalk project, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a8d3c-112">在解决方案资源管理器，右键单击解决方案名称，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-112">In Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
     <span data-ttu-id="a8d3c-113">在屏幕底部的输出窗格如下所示：**部署：1 个成功，0 失败，0 已跳过**。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-113">The Output pane at the bottom of the screen should read: **Deploy: 1 succeeded, 0 failed, 0 skipped**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a8d3c-114">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="a8d3c-114">What did I just do?</span></span>  
 <span data-ttu-id="a8d3c-115">在此步骤中，你已部署到 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-115">In this step, you deployed the BizTalk orchestration to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8d3c-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a8d3c-116">Next Steps</span></span>  
 <span data-ttu-id="a8d3c-117">创建中的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，如中所述[步骤 2:配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="a8d3c-117">You create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, as described in [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d3c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8d3c-118">See Also</span></span>  
 <span data-ttu-id="a8d3c-119">[步骤 2：配置的端口](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a8d3c-119">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 [<span data-ttu-id="a8d3c-120">第 5 课：部署解决方案</span><span class="sxs-lookup"><span data-stu-id="a8d3c-120">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)