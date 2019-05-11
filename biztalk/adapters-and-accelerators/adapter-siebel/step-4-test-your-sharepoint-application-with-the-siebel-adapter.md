---
title: 步骤 4：使用 Siebel 适配器测试您的 SharePoint 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555339a90d51e5fa66f8be397be6af9eeb589f76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370667"
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a><span data-ttu-id="f44bb-102">步骤 4：使用 Siebel 适配器测试您的 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="f44bb-102">Step 4: Test Your SharePoint Application with the Siebel adapter</span></span>
<span data-ttu-id="f44bb-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="f44bb-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="f44bb-104">**若要完成的时间：** 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="f44bb-104">**Time to complete:** 5 minutes.</span></span>  
  
 <span data-ttu-id="f44bb-105">**目标：** 在 SharePoint 站点中添加 Web 部件并创建了应用程序后，必须从 Siebel 系统中检索一些数据来测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="f44bb-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Siebel system.</span></span> <span data-ttu-id="f44bb-106">本部分将说明了如何使用应用程序从 Siebel 系统中检索数据。</span><span class="sxs-lookup"><span data-stu-id="f44bb-106">This section provides instructions on how to use the application to retrieve the data from the Siebel system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f44bb-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="f44bb-107">Prerequisites</span></span>  
 <span data-ttu-id="f44bb-108">您将会创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="f44bb-108">You should have created the Web Part page containing the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="f44bb-109">请参阅[步骤 3:创建 SharePoint 应用程序以从 Siebel 检索数据](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="f44bb-109">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="f44bb-110">若要测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="f44bb-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="f44bb-111">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="f44bb-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="f44bb-112">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="f44bb-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="f44bb-113">在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="f44bb-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="f44bb-114">在左窗格中，单击**查看所有网站内容**。</span><span class="sxs-lookup"><span data-stu-id="f44bb-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="f44bb-115">在右窗格中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="f44bb-115">From the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="f44bb-116">在中**窗体类别**列表中，单击**Siebel 帐户**。</span><span class="sxs-lookup"><span data-stu-id="f44bb-116">In the **Form Category** list, click **Siebel Account**.</span></span> <span data-ttu-id="f44bb-117">创建 Web 部件页时指定此名称。</span><span class="sxs-lookup"><span data-stu-id="f44bb-117">You specified this name while creating the Web Part page.</span></span> <span data-ttu-id="f44bb-118">下图显示了你创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="f44bb-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="f44bb-119">![已完成的 Web 部件页](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span><span class="sxs-lookup"><span data-stu-id="f44bb-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span></span>  
  
5.  <span data-ttu-id="f44bb-120">查询帐户业务组件根据搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="f44bb-120">Query the Account business component based on a search string.</span></span> <span data-ttu-id="f44bb-121">例如，指定搜索表达式`[Name] LIKE ‘W*’`。</span><span class="sxs-lookup"><span data-stu-id="f44bb-121">For example, specify the search expression `[Name] LIKE ‘W*’`.</span></span> <span data-ttu-id="f44bb-122">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f44bb-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="f44bb-123">在中**Account List**部分中的，从第一个列表中，选择**SearchExpression**，然后选择**等于**。</span><span class="sxs-lookup"><span data-stu-id="f44bb-123">In the **Account List** section, from the first list, select **SearchExpression**, and then select **is equal to**.</span></span>  
  
    2.  <span data-ttu-id="f44bb-124">在文本字段中，键入`[Name] LIKE ‘W*’`。</span><span class="sxs-lookup"><span data-stu-id="f44bb-124">In the text field, type `[Name] LIKE ‘W*’`.</span></span>  
  
    3.  <span data-ttu-id="f44bb-125">单击**检索数据**链接，或按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f44bb-125">Click **Retrieve Data** link, or press ENTER.</span></span> <span data-ttu-id="f44bb-126">下图显示了从 Siebel 系统中检索满足搜索条件的记录。</span><span class="sxs-lookup"><span data-stu-id="f44bb-126">The following figure shows the records retrieved from the Siebel system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="f44bb-127">![搜索从 Siebel 系统的结果](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span><span class="sxs-lookup"><span data-stu-id="f44bb-127">![Search results from the Siebel system](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44bb-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f44bb-128">See Also</span></span>  
 [<span data-ttu-id="f44bb-129">教程 1:在 SharePoint 站点上提供来自 Siebel 系统的数据</span><span class="sxs-lookup"><span data-stu-id="f44bb-129">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)