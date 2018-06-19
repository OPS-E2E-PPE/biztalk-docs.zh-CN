---
title: 步骤 4： 测试 SharePoint 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218237"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="b9bdf-102">步骤 4： 测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="b9bdf-102">Step 4: Test your SharePoint application</span></span>
<span data-ttu-id="b9bdf-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="b9bdf-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="b9bdf-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="b9bdf-105">**目标：** 后您在 SharePoint 站点中添加 Web 部件，并且创建了应用程序，你必须通过从 Oracle E-business Suite 检索某些数据测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Oracle E-Business Suite.</span></span> <span data-ttu-id="b9bdf-106">本主题将说明了如何使用应用程序从 Oracle E-business Suite 检索数据。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-106">This topic provides instructions on how to use the application to retrieve the data from the Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9bdf-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b9bdf-107">Prerequisites</span></span>  
 <span data-ttu-id="b9bdf-108">您应已创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="b9bdf-109">请参阅[步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-109">See [Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a><span data-ttu-id="b9bdf-110">方案 1： 测试 SharePoint 应用程序创建使用业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="b9bdf-110">Scenario 1: To test the SharePoint application created using Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="b9bdf-111">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="b9bdf-112">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="b9bdf-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="b9bdf-113">在左侧的导航窗格中，单击在其下创建应用程序的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="b9bdf-114">在左窗格中，单击**查看所有站点内容**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="b9bdf-115">在右窗格中，单击**表单模板**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="b9bdf-116">在**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-116">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE**.</span></span> <span data-ttu-id="b9bdf-117">创建中的 Web 部件页时指定此名称[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-117">You specified this name when you created the Web Part page in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
5.  <span data-ttu-id="b9bdf-118">搜索员工基于搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-118">Search for employees based on a search string.</span></span> <span data-ttu-id="b9bdf-119">例如，若要搜索的所有员工，请键入 **%** 文本框中，然后单击**检索数据**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-119">For example, to search for all the employees, type **%** in the text box, and click **Retrieve Data**.</span></span> <span data-ttu-id="b9bdf-120">下图显示从 Oracle E-business Suite 中检索的记录：</span><span class="sxs-lookup"><span data-stu-id="b9bdf-120">The following figure shows the records retrieved from Oracle E-Business Suite:</span></span>  
  
     <span data-ttu-id="b9bdf-121">![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-121">![Search result](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span></span>  
  
6.  <span data-ttu-id="b9bdf-122">您还可以通过输入其名字或姓氏搜索特定雇员：</span><span class="sxs-lookup"><span data-stu-id="b9bdf-122">You can also search for a specific employee by entering their first name or last name:</span></span>  
  
    -   <span data-ttu-id="b9bdf-123">若要搜索使用第一个名称，请键入后跟雇员姓名首字母 **%** 符号返回的搜索条件匹配的所有雇员的记录。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-123">To search using the first name, type the initial letters of an employee name followed by the **%** symbol to return records of all the employees matching the search criteria.</span></span>  
  
    -   <span data-ttu-id="b9bdf-124">若要搜索使用最后一个名称，键入 **%** 跟员工的姓氏。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-124">To search using the last name, type **%** followed by employee’s last name.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b9bdf-125">区分大小写的搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-125">The search string is case sensitive.</span></span>  
  
     <span data-ttu-id="b9bdf-126">![员工的名字按搜索](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-126">![Searching by first name of an employee](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span></span>  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a><span data-ttu-id="b9bdf-127">方案 2： 测试 SharePoint 应用程序创建来执行全文搜索</span><span class="sxs-lookup"><span data-stu-id="b9bdf-127">Scenario 2: To test the SharePoint application created to perform a full-text search</span></span>  
  
1.  <span data-ttu-id="b9bdf-128">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-128">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="b9bdf-129">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="b9bdf-129">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="b9bdf-130">在左侧的导航窗格中，单击在其下创建应用程序的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-130">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="b9bdf-131">在左窗格中，单击**查看所有站点内容**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-131">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="b9bdf-132">在右窗格中，单击**表单模板**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-132">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="b9bdf-133">在**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE_Search**。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-133">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="b9bdf-134">创建中的 Web 部件页时指定此名称[方案 2： 使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)中[方案 2： 使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-134">You specified this name when you created the Web Part page in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
5.  <span data-ttu-id="b9bdf-135">MS_SAMPLE_EMPLOYEE_Search 页面显示搜索框中在你可以执行 MS_SAMPLE 员工表的全文搜索。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-135">The MS_SAMPLE_EMPLOYEE_Search page displays the search box where you can perform a full-text search on the MS_SAMPLE EMPLOYEE table.</span></span> <span data-ttu-id="b9bdf-136">例如，如果你想要搜索的位于纽约的所有员工，键入`New York`搜索框中，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-136">For example, if you want to search for all the employees who live in New York, type `New York` in the search box, and press ENTER.</span></span>  
  
     <span data-ttu-id="b9bdf-137">![指定的搜索参数](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-137">![Specify a search parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span></span>  
  
6.  <span data-ttu-id="b9bdf-138">使用的搜索结果将显示一个页面。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-138">A page appears with the search results.</span></span> <span data-ttu-id="b9bdf-139">每个匹配的记录显示为搜索结果页中的链接。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-139">Each matching records is displayed as a link in the search results page.</span></span>  
  
     <span data-ttu-id="b9bdf-140">![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-140">![Search results](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span></span>  
  
7.  <span data-ttu-id="b9bdf-141">单击以查看相应的员工记录的搜索结果中的链接。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-141">Click a link in the search result to view the respective employee record.</span></span>  
  
     <span data-ttu-id="b9bdf-142">![详细的员工记录](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span><span class="sxs-lookup"><span data-stu-id="b9bdf-142">![Detailed employee record](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="b9bdf-143">摘要</span><span class="sxs-lookup"><span data-stu-id="b9bdf-143">Summary</span></span>  
 <span data-ttu-id="b9bdf-144">在本教程中，你将创建你想要从 SharePoint 门户网站访问 Oracle E-business Suite 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-144">In this tutorial, you created a WCF service for the Oracle E-Business Suite artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="b9bdf-145">你还创建导入 SharePoint 门户网站创建 Web 部件，为在 Oracle E-business Suite 中搜索数据和呈现应用程序定义的 Oracle E-business Suite 项目。</span><span class="sxs-lookup"><span data-stu-id="b9bdf-145">You also created an application definition for the Oracle E-Business Suite artifacts that is imported into a SharePoint portal to create Web Parts to present and search data in Oracle E-Business Suite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9bdf-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9bdf-146">See Also</span></span>  
 [<span data-ttu-id="b9bdf-147">教程： 从 SharePoint 站点上的 Oracle E-business Suite 显示数据</span><span class="sxs-lookup"><span data-stu-id="b9bdf-147">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)