---
title: 步骤 4：测试 SharePoint 应用程序 |Microsoft Docs
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
ms.openlocfilehash: 1ac732b009f25628651fae133e83acd7fcd5deb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374544"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="ca607-102">步骤 4：测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="ca607-102">Step 4: Test your SharePoint application</span></span>
<span data-ttu-id="ca607-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="ca607-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="ca607-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="ca607-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="ca607-105">**目标：** 在 SharePoint 站点中添加 Web 部件并创建了应用程序后，必须通过从 Oracle E-business Suite 中检索一些数据来测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca607-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Oracle E-Business Suite.</span></span> <span data-ttu-id="ca607-106">本主题将说明了如何使用应用程序来从 Oracle E-business Suite 中检索数据。</span><span class="sxs-lookup"><span data-stu-id="ca607-106">This topic provides instructions on how to use the application to retrieve the data from the Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca607-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="ca607-107">Prerequisites</span></span>  
 <span data-ttu-id="ca607-108">您将会创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="ca607-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="ca607-109">请参阅[步骤 3:创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="ca607-109">See [Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a><span data-ttu-id="ca607-110">应用场景 1：若要测试创建使用业务数据列表 Web 部件的 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="ca607-110">Scenario 1: To test the SharePoint application created using Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="ca607-111">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="ca607-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ca607-112">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="ca607-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ca607-113">在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ca607-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="ca607-114">在左窗格中，单击**查看所有网站内容**。</span><span class="sxs-lookup"><span data-stu-id="ca607-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="ca607-115">在右窗格中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="ca607-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="ca607-116">在中**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE**。</span><span class="sxs-lookup"><span data-stu-id="ca607-116">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE**.</span></span> <span data-ttu-id="ca607-117">在创建中的 Web 部件页时指定此名称[方案 1:使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="ca607-117">You specified this name when you created the Web Part page in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
5.  <span data-ttu-id="ca607-118">搜索基于搜索字符串的员工。</span><span class="sxs-lookup"><span data-stu-id="ca607-118">Search for employees based on a search string.</span></span> <span data-ttu-id="ca607-119">例如，若要搜索的所有员工，请键入**%** 在文本框中，单击**检索数据**。</span><span class="sxs-lookup"><span data-stu-id="ca607-119">For example, to search for all the employees, type **%** in the text box, and click **Retrieve Data**.</span></span> <span data-ttu-id="ca607-120">下图显示了从 Oracle E-business Suite 中检索到的记录：</span><span class="sxs-lookup"><span data-stu-id="ca607-120">The following figure shows the records retrieved from Oracle E-Business Suite:</span></span>  
  
     <span data-ttu-id="ca607-121">![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span><span class="sxs-lookup"><span data-stu-id="ca607-121">![Search result](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span></span>  
  
6.  <span data-ttu-id="ca607-122">您还可以通过输入其名字或姓氏搜索特定雇员：</span><span class="sxs-lookup"><span data-stu-id="ca607-122">You can also search for a specific employee by entering their first name or last name:</span></span>  
  
    -   <span data-ttu-id="ca607-123">若要使用第一个名称进行搜索，请键入后跟一个雇员的姓名首字母**%** 符号以返回与搜索条件匹配的所有员工记录。</span><span class="sxs-lookup"><span data-stu-id="ca607-123">To search using the first name, type the initial letters of an employee name followed by the **%** symbol to return records of all the employees matching the search criteria.</span></span>  
  
    -   <span data-ttu-id="ca607-124">若要使用的最后一个名称进行搜索，请键入**%** 跟员工的姓氏。</span><span class="sxs-lookup"><span data-stu-id="ca607-124">To search using the last name, type **%** followed by employee’s last name.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca607-125">区分大小写的搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="ca607-125">The search string is case sensitive.</span></span>  
  
     <span data-ttu-id="ca607-126">![搜索按员工的名字](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span><span class="sxs-lookup"><span data-stu-id="ca607-126">![Searching by first name of an employee](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span></span>  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a><span data-ttu-id="ca607-127">应用场景 2：若要测试创建执行全文搜索的 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="ca607-127">Scenario 2: To test the SharePoint application created to perform a full-text search</span></span>  
  
1.  <span data-ttu-id="ca607-128">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="ca607-128">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ca607-129">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="ca607-129">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ca607-130">在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ca607-130">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="ca607-131">在左窗格中，单击**查看所有网站内容**。</span><span class="sxs-lookup"><span data-stu-id="ca607-131">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="ca607-132">在右窗格中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="ca607-132">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="ca607-133">在中**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE_Search**。</span><span class="sxs-lookup"><span data-stu-id="ca607-133">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="ca607-134">在创建中的 Web 部件页时指定此名称[方案 2:执行搜索使用搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)在[方案 2:使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="ca607-134">You specified this name when you created the Web Part page in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
5.  <span data-ttu-id="ca607-135">MS_SAMPLE_EMPLOYEE_Search 页将显示可在其中执行全文搜索 MS_SAMPLE EMPLOYEE 表的搜索框。</span><span class="sxs-lookup"><span data-stu-id="ca607-135">The MS_SAMPLE_EMPLOYEE_Search page displays the search box where you can perform a full-text search on the MS_SAMPLE EMPLOYEE table.</span></span> <span data-ttu-id="ca607-136">例如，如果你想要搜索的所有员工居住在纽约，键入`New York`在搜索框中，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ca607-136">For example, if you want to search for all the employees who live in New York, type `New York` in the search box, and press ENTER.</span></span>  
  
     <span data-ttu-id="ca607-137">![指定搜索参数](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span><span class="sxs-lookup"><span data-stu-id="ca607-137">![Specify a search parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span></span>  
  
6.  <span data-ttu-id="ca607-138">使用搜索结果将显示一个页面。</span><span class="sxs-lookup"><span data-stu-id="ca607-138">A page appears with the search results.</span></span> <span data-ttu-id="ca607-139">每个匹配的记录显示为搜索结果页中的链接。</span><span class="sxs-lookup"><span data-stu-id="ca607-139">Each matching records is displayed as a link in the search results page.</span></span>  
  
     <span data-ttu-id="ca607-140">![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span><span class="sxs-lookup"><span data-stu-id="ca607-140">![Search results](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span></span>  
  
7.  <span data-ttu-id="ca607-141">单击搜索结果以查看相应的员工记录中的链接。</span><span class="sxs-lookup"><span data-stu-id="ca607-141">Click a link in the search result to view the respective employee record.</span></span>  
  
     <span data-ttu-id="ca607-142">![详细雇员记录](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span><span class="sxs-lookup"><span data-stu-id="ca607-142">![Detailed employee record](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ca607-143">总结</span><span class="sxs-lookup"><span data-stu-id="ca607-143">Summary</span></span>  
 <span data-ttu-id="ca607-144">在本教程中，您可以创建你想要从 SharePoint 门户网站访问的 Oracle E-business Suite 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="ca607-144">In this tutorial, you created a WCF service for the Oracle E-Business Suite artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="ca607-145">此外创建导入到 SharePoint 门户网站创建 Web 部件显示，并在 Oracle E-business Suite 中搜索数据的应用程序定义的 Oracle E-business Suite 项目。</span><span class="sxs-lookup"><span data-stu-id="ca607-145">You also created an application definition for the Oracle E-Business Suite artifacts that is imported into a SharePoint portal to create Web Parts to present and search data in Oracle E-Business Suite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca607-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca607-146">See Also</span></span>  
 [<span data-ttu-id="ca607-147">教程：从 SharePoint 站点上的 Oracle E-business Suite 的呈现数据</span><span class="sxs-lookup"><span data-stu-id="ca607-147">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)