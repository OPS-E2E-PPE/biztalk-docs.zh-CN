---
title: 步骤 4：生成项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6216d96e0d9ce0f8e564fa45bc28c075ce124c8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367700"
---
# <a name="step-4-build-the-project"></a><span data-ttu-id="b5b45-102">步骤 4：生成项目</span><span class="sxs-lookup"><span data-stu-id="b5b45-102">Step 4: Build the Project</span></span>
<span data-ttu-id="b5b45-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="b5b45-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="b5b45-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="b5b45-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b5b45-105">**目标：** 在此步骤中，您将编译 BizTalk 业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="b5b45-105">**Objective:** In this step, you compile the BizTalk orchestration project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5b45-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="b5b45-106">Prerequisites</span></span>  
 <span data-ttu-id="b5b45-107">你必须已完成[步骤 3:发送要插入记录，并接收响应的请求消息](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b45-107">You must have completed [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  
  
### <a name="to-build-the-biztalk-orchestration-project"></a><span data-ttu-id="b5b45-108">若要生成 BizTalk 业务流程项目</span><span class="sxs-lookup"><span data-stu-id="b5b45-108">To build the BizTalk orchestration project</span></span>  
  
1. <span data-ttu-id="b5b45-109">在解决方案资源管理器，右键单击 BizTalk 项目名称，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5b45-109">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="b5b45-110">在属性页对话框中，在树窗格中，展开**常见属性**，单击**程序集**，然后在属性列表中，单击**程序集密钥文件**省略号 **[...]**.</span><span class="sxs-lookup"><span data-stu-id="b5b45-110">In the property pages dialog box, in the tree pane, expand **Common Properties**, click **Assembly**, and then in the properties list, click the **Assembly Key File** ellipsis **[…]**.</span></span>  
  
3. <span data-ttu-id="b5b45-111">指定创建中所述的程序集密钥文件的路径[创建 SQL 应用程序使用 SQL 适配器的先决条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b5b45-111">Specify a path to the assembly key file you created as described in [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md), and then click **Open**.</span></span>  
  
4. <span data-ttu-id="b5b45-112">在属性页对话框中，在树窗格中，展开**配置属性**，单击**部署**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5b45-112">In the property pages dialog box, in the tree pane, expand **Configuration Properties**, click **Deployment**, and then do the following:</span></span>  
  
   1. <span data-ttu-id="b5b45-113">有关**应用程序名称**属性中，键入`SampleApplication`。</span><span class="sxs-lookup"><span data-stu-id="b5b45-113">For the **Application Name** property, type `SampleApplication`.</span></span>  
  
   2. <span data-ttu-id="b5b45-114">有关**重新部署**属性中，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="b5b45-114">For the **Redeploy** property, select **True**.</span></span>  
  
      <span data-ttu-id="b5b45-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b5b45-115">Click **OK**.</span></span>  
  
5. <span data-ttu-id="b5b45-116">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="b5b45-116">On the **File** menu, click **Save All**.</span></span>  
  
6. <span data-ttu-id="b5b45-117">在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="b5b45-117">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
    <span data-ttu-id="b5b45-118">在屏幕底部的输出窗格如下所示：**生成中：3 个成功或最新，0 失败，0 已跳过。**</span><span class="sxs-lookup"><span data-stu-id="b5b45-118">The Output pane at the bottom of the screen should read: **Build: 3 succeeded or up-to-date, 0 failed, 0 skipped.**</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b5b45-119">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="b5b45-119">What did I just do?</span></span>  
 <span data-ttu-id="b5b45-120">在此步骤中，您编译包含 BizTalk 项目和两个类库项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b5b45-120">In this step, you compiled the solution containing the BizTalk project and two class library projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b5b45-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b5b45-121">Next Steps</span></span>  
 <span data-ttu-id="b5b45-122">在部署解决方案，如中所述[第 5 课：部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="b5b45-122">You deploy the solution, as described in [Lesson 5: Deploy the Solution](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b45-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b45-123">See Also</span></span>  
 <span data-ttu-id="b5b45-124">[步骤 3：发送要插入记录，并接收响应的请求消息](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span><span class="sxs-lookup"><span data-stu-id="b5b45-124">[Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span></span>  
 [<span data-ttu-id="b5b45-125">第 4 课：在采购订单表中执行插入操作</span><span class="sxs-lookup"><span data-stu-id="b5b45-125">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)