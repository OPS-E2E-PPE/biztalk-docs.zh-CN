---
title: "使用 PeopleSoft 系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-peoplesoft-system"></a><span data-ttu-id="9c64b-102">使用 PeopleSoft 系统</span><span class="sxs-lookup"><span data-stu-id="9c64b-102">Using a PeopleSoft System</span></span>
<span data-ttu-id="9c64b-103">使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="9c64b-104">此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。</span><span class="sxs-lookup"><span data-stu-id="9c64b-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9c64b-105">PeopleSoft 实验室工作分为两部分。</span><span class="sxs-lookup"><span data-stu-id="9c64b-105">The PeopleSoft lab work is divided into two parts.</span></span> <span data-ttu-id="9c64b-106">在第一个实验室（实验室 1）中，您将在不使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或任何 Microsoft 产品（可能需要使用 Internet Explorer，但您可以使用任何浏览器）的情况下，使用 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-106">This first lab (Lab 1) allows you to use the PeopleSoft system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products (except perhaps Internet Explorer, but you can use any browser).</span></span> <span data-ttu-id="9c64b-107">在此实验室中，您将连接到 PeopleSoft 系统，以找到并修改简单的数据记录。</span><span class="sxs-lookup"><span data-stu-id="9c64b-107">In this lab, you will connect to the PeopleSoft system to locate and modify a simple data record.</span></span>  
  
 <span data-ttu-id="9c64b-108">在第二个实验室（实验室 2）中，您将创建 BizTalk 项目和业务流程。</span><span class="sxs-lookup"><span data-stu-id="9c64b-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="9c64b-109">创建应用程序之后，将对其进行部署和使用，以使用 PeopleSoft 适配器将其连接到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-109">After you create the application, you will deploy it and use it to connect to a PeopleSoft system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="9c64b-110">目标是使用适配器通过 BizTalk 应用程序来访问数据。</span><span class="sxs-lookup"><span data-stu-id="9c64b-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c64b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="9c64b-111">Prerequisites</span></span>  
 <span data-ttu-id="9c64b-112">为执行此实验室的过程，您需要浏览器和 Internet 连接，以及 PeopleSoft 系统的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9c64b-112">To perform the procedures for this lab, you need a browser and an Internet connection, along with a user account on a PeopleSoft system.</span></span> <span data-ttu-id="9c64b-113">您需要知道要浏览的位置，获取对 PeopleSoft 系统的网络访问权限。</span><span class="sxs-lookup"><span data-stu-id="9c64b-113">You need to know the location to browse to for gaining Web access to your PeopleSoft system.</span></span> <span data-ttu-id="9c64b-114">无需使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或其他任何 Microsoft 技术。</span><span class="sxs-lookup"><span data-stu-id="9c64b-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any other Microsoft technologies.</span></span>  
  
## <a name="lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="9c64b-115">实验室 1 - 使用 PeopleSoft 系统</span><span class="sxs-lookup"><span data-stu-id="9c64b-115">Lab 1 - Using a PeopleSoft System</span></span>  
 <span data-ttu-id="9c64b-116">在此实验室中，您将在不使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的任何组件的情况下，使用 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-116">In this lab, you will use the PeopleSoft system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9c64b-117">目标是测试与 PeopleSoft 的连接，以确保第二个实验室正常工作。</span><span class="sxs-lookup"><span data-stu-id="9c64b-117">The goal is to test your connectivity to PeopleSoft to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="9c64b-118">首先，通过其 Web 界面（允许您使用 Internet Explorer 等浏览器登录）连接到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-118">Initially you connect to the PeopleSoft system through its Web interface that allows you to log on by using a browser such as Internet Explorer.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="9c64b-119">实验室 1 的过程 - 使用 PeopleSoft 系统</span><span class="sxs-lookup"><span data-stu-id="9c64b-119">Procedures for Lab 1 - Using a PeopleSoft System</span></span>  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a><span data-ttu-id="9c64b-120">使用浏览器登录到 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="9c64b-120">To log on to PeopleSoft by using a browser</span></span>  
  
-   <span data-ttu-id="9c64b-121">浏览到 PeopleSoft 登录页，登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-121">Log on to the PeopleSoft system by browsing to a PeopleSoft logon page.</span></span> <span data-ttu-id="9c64b-122">输入你**用户 ID**和**密码**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="9c64b-122">Enter your **User ID** and **Password** and then click **Sign In**.</span></span>  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a><span data-ttu-id="9c64b-123">找到并修改 PeopleSoft 数据</span><span class="sxs-lookup"><span data-stu-id="9c64b-123">To locate and modify PeopleSoft data</span></span>  
  
1.  <span data-ttu-id="9c64b-124">登录成功后，您将转到一个页面，在该页中您可以通过选择布局对看到的内容进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="9c64b-124">A successful logon places you at the page to personalize the content you see by choosing its layout.</span></span> <span data-ttu-id="9c64b-125">向下滚动并展开**设置财务/供应链**，单击**通用定义**，单击**位置**，然后单击**位置**试。</span><span class="sxs-lookup"><span data-stu-id="9c64b-125">Scroll down and expand **Set Up Financials/Supply Chain**, click **Common Definitions**, click **Location**, and then click **Location** again.</span></span> <span data-ttu-id="9c64b-126">这将进入**位置**搜索接口。</span><span class="sxs-lookup"><span data-stu-id="9c64b-126">This brings you to the **Location** search interface.</span></span>  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  <span data-ttu-id="9c64b-127">若要开始搜索，设置**SetID**到 **=** ，将其设置**位置代码**到**开头**，输入，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="9c64b-127">To begin the search, set **SetID** to **=**, set **Location Code** to **begins with**, enter **A**, and then click **Search**.</span></span> <span data-ttu-id="9c64b-128">此时将显示其名称以在 A 开头的城市**搜索结果**接口的部分。</span><span class="sxs-lookup"><span data-stu-id="9c64b-128">This displays cities whose names start with A in the **Search Results** section of the interface.</span></span>  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  <span data-ttu-id="9c64b-129">单击任一位置以获取其详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c64b-129">Click one of the locations to get its detail information.</span></span> <span data-ttu-id="9c64b-130">例如，在下图中，用户单击**AUS01**中链接**位置代码**列。</span><span class="sxs-lookup"><span data-stu-id="9c64b-130">For example, in the figure below, the user clicked the **AUS01** link in the **Location Code** column.</span></span>  
  
4.  <span data-ttu-id="9c64b-131">输入一些新的数据的字段之一 (如**地址 2**字段)，然后单击**保存**的左下角。</span><span class="sxs-lookup"><span data-stu-id="9c64b-131">Enter some new data into one of the fields (such as the **Address 2** field) and click **Save** in the lower-left corner.</span></span> <span data-ttu-id="9c64b-132">会将新输入的数据保存到记录中。</span><span class="sxs-lookup"><span data-stu-id="9c64b-132">This saves the newly entered data into the record.</span></span>  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  <span data-ttu-id="9c64b-133">要验证此更改是否成功，可重复步骤 2 之后的步骤，再次查找同一记录，然后观察对记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9c64b-133">To verify the success of this change, repeat the process from step 2, find this same record again, and observe the changes made to the record.</span></span>  
  
6.  <span data-ttu-id="9c64b-134">在窗口右上角，单击**注销**以结束 PeopleSoft 会话。</span><span class="sxs-lookup"><span data-stu-id="9c64b-134">In the upper-right portion of the window, click **Sign out** to end your PeopleSoft session.</span></span>  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  <span data-ttu-id="9c64b-135">下一个实验室中为使用 PeopleSoft 适配器检索您修改的位置记录 (AUS01) 的信息提供了说明。</span><span class="sxs-lookup"><span data-stu-id="9c64b-135">In the next lab there are instructions for using the PeopleSoft adapter to retrieve the information for the location record (AUS01) that you modified.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="9c64b-136">摘要</span><span class="sxs-lookup"><span data-stu-id="9c64b-136">Summary</span></span>  
 <span data-ttu-id="9c64b-137">在本实验室中，您通过浏览器登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="9c64b-137">In this lab you logged on to the PeopleSoft system through a browser.</span></span> <span data-ttu-id="9c64b-138">连接之后，您搜索了数据，然后对记录的地址字段进行了操作和更新。</span><span class="sxs-lookup"><span data-stu-id="9c64b-138">After you were connected, you searched for data, and then manipulated and updated a record's address field.</span></span> <span data-ttu-id="9c64b-139">提交更改后，您可以在浏览器中查看修改的数据，以验证更改是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="9c64b-139">After committing the change, you could view the modified data in the browser to verify that the change executed properly.</span></span>