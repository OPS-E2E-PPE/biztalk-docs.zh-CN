---
title: 步骤 4：测试您的 SharePoint 应用程序 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40160ef6e2e3a27a10a74779aa7eb8d282b2a30b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372790"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="6e899-102">步骤 4：测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="6e899-102">Step 4: Test Your SharePoint Application</span></span>
<span data-ttu-id="6e899-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="6e899-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="6e899-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="6e899-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="6e899-105">**目标：** 在 SharePoint 站点中添加 Web 部件并创建了应用程序后，必须从 SAP 系统中检索一些数据来测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e899-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the SAP system.</span></span> <span data-ttu-id="6e899-106">本主题将说明了如何使用应用程序从 SAP 系统中检索数据。</span><span class="sxs-lookup"><span data-stu-id="6e899-106">This topic provides instructions on how to use the application to retrieve the data from the SAP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e899-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="6e899-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="6e899-108">您将会创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6e899-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="6e899-109">请参阅[步骤 3:创建 SharePoint 应用程序将数据从 SAP 检索](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="6e899-109">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="6e899-110">若要测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="6e899-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="6e899-111">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6e899-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="6e899-112">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="6e899-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="6e899-113">在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6e899-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="6e899-114">在左窗格中，单击**查看所有网站内容**。</span><span class="sxs-lookup"><span data-stu-id="6e899-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="6e899-115">在右窗格中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="6e899-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="6e899-116">在中**窗体类别**列表中，单击**Customer_SalesOrders**。</span><span class="sxs-lookup"><span data-stu-id="6e899-116">In the **Form Category** list, click **Customer_SalesOrders**.</span></span> <span data-ttu-id="6e899-117">创建 Web 部件页时指定此名称。</span><span class="sxs-lookup"><span data-stu-id="6e899-117">You specified this name when you created the Web Part page.</span></span> <span data-ttu-id="6e899-118">下图显示了你创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6e899-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="6e899-119">![已完成的 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span><span class="sxs-lookup"><span data-stu-id="6e899-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span></span>  
  
5.  <span data-ttu-id="6e899-120">搜索客户基于搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="6e899-120">Search for customers based on a search string.</span></span> <span data-ttu-id="6e899-121">例如，搜索客户名称以"John E"开头。</span><span class="sxs-lookup"><span data-stu-id="6e899-121">For example, search for customers with names starting with "John E".</span></span> <span data-ttu-id="6e899-122">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e899-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="6e899-123">在客户列表部分中，从第一个列表中，单击**CustomerName**。</span><span class="sxs-lookup"><span data-stu-id="6e899-123">In the Customer List section, from the first list, click **CustomerName**.</span></span>  
  
    2.  <span data-ttu-id="6e899-124">从第二个列表中，单击**开头**。</span><span class="sxs-lookup"><span data-stu-id="6e899-124">From the second list, click **starts with**.</span></span>  
  
    3.  <span data-ttu-id="6e899-125">在文本框中，键入**John E**。</span><span class="sxs-lookup"><span data-stu-id="6e899-125">In the text box, type **John E**.</span></span>  
  
    4.  <span data-ttu-id="6e899-126">单击**检索数据**链接，或按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="6e899-126">Click the **Retrieve Data** link or press ENTER.</span></span> <span data-ttu-id="6e899-127">下图显示了从 SAP 系统中检索满足搜索条件的记录。</span><span class="sxs-lookup"><span data-stu-id="6e899-127">The following figure shows the records retrieved from the SAP system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="6e899-128">![从 SAP 系统搜索的结果](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span><span class="sxs-lookup"><span data-stu-id="6e899-128">![Search results from the SAP system](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span></span>  
  
6.  <span data-ttu-id="6e899-129">现在可以看到列表中的任何客户的详细信息和销售订单与客户，如果有相关联。</span><span class="sxs-lookup"><span data-stu-id="6e899-129">You can now see the details of any customer in the list and the sales orders associated with the customers, if any.</span></span> <span data-ttu-id="6e899-130">若要执行此操作，请单击针对客户编号选项按钮。</span><span class="sxs-lookup"><span data-stu-id="6e899-130">To do so, click the option button against a customer number.</span></span> <span data-ttu-id="6e899-131">刷新该页面以显示详细信息和相应的 Web 部件中的特定客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="6e899-131">The page refreshes to present the details and the sales orders for a specific customer in the respective Web Parts.</span></span>  
  
     <span data-ttu-id="6e899-132">![显示在 SharePoint 上的 SAP 数据](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span><span class="sxs-lookup"><span data-stu-id="6e899-132">![SAP data presented on SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span></span>  
  
     <span data-ttu-id="6e899-133">如果未正确显示客户和关联的销售订单的详细信息，您已成功完成本教程。</span><span class="sxs-lookup"><span data-stu-id="6e899-133">If the details of the customers and the associated sales order are displayed correctly, you have successfully completed the tutorial.</span></span> <span data-ttu-id="6e899-134">如果没有或不正确的数据显示，请仔细检查您的工作以确保正确执行所有任务。</span><span class="sxs-lookup"><span data-stu-id="6e899-134">If no or incorrect data is displayed, carefully check your work to make sure you performed all the tasks correctly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6e899-135">总结</span><span class="sxs-lookup"><span data-stu-id="6e899-135">Summary</span></span>  
 <span data-ttu-id="6e899-136">在本教程中创建你想要从 SharePoint 门户网站访问 SAP 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6e899-136">In this tutorial you created a WCF service for the SAP artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="6e899-137">此外创建导入到 SharePoint 门户网站创建 Web 部件显示数据从 SAP 系统的 SAP 项目的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="6e899-137">You also created an application definition for the SAP artifacts that is imported into a SharePoint portal to create Web Parts to present data from an SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e899-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e899-138">See Also</span></span>  
 [<span data-ttu-id="6e899-139">教程 1:在 SharePoint 站点上提供来自 SAP 系统的数据</span><span class="sxs-lookup"><span data-stu-id="6e899-139">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)