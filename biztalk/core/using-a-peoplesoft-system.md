---
title: 使用 PeopleSoft 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b7f98086c5e2be4e236a5691e4ff5633ac5f45b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399944"
---
# <a name="using-a-peoplesoft-system"></a><span data-ttu-id="7c8d2-102">使用 PeopleSoft 系统</span><span class="sxs-lookup"><span data-stu-id="7c8d2-102">Using a PeopleSoft System</span></span>
<span data-ttu-id="7c8d2-103">使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="7c8d2-104">此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配合使用的一组八个业务线 (LOB) 适配器之一。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7c8d2-105">PeopleSoft 实验室工作分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-105">The PeopleSoft lab work is divided into two parts.</span></span> <span data-ttu-id="7c8d2-106">第一个实验室 (实验室 1)，可使用 PeopleSoft 系统，而无需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何 Microsoft 产品 （可能是 Internet Explorer 中，但你可以使用任何浏览器）。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-106">This first lab (Lab 1) allows you to use the PeopleSoft system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products (except perhaps Internet Explorer, but you can use any browser).</span></span> <span data-ttu-id="7c8d2-107">在此实验中，您将连接到 PeopleSoft 系统以找到并修改简单的数据记录。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-107">In this lab, you will connect to the PeopleSoft system to locate and modify a simple data record.</span></span>  
  
 <span data-ttu-id="7c8d2-108">在第二个实验室 (实验室 2) 中，将创建 BizTalk 项目和业务流程。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="7c8d2-109">创建应用程序后，会将其部署，并使用它来通过使用 PeopleSoft 适配器连接到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-109">After you create the application, you will deploy it and use it to connect to a PeopleSoft system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="7c8d2-110">目标是通过使用适配器通过 BizTalk 应用程序访问数据。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7c8d2-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="7c8d2-111">Prerequisites</span></span>  
 <span data-ttu-id="7c8d2-112">若要执行此实验室的过程，需要一个浏览器和 Internet 连接，以及 PeopleSoft 系统上的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-112">To perform the procedures for this lab, you need a browser and an Internet connection, along with a user account on a PeopleSoft system.</span></span> <span data-ttu-id="7c8d2-113">您需要知道要浏览到 PeopleSoft 系统 Web 访问的位置。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-113">You need to know the location to browse to for gaining Web access to your PeopleSoft system.</span></span> <span data-ttu-id="7c8d2-114">不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何其他 Microsoft 技术。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any other Microsoft technologies.</span></span>  
  
## <a name="lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="7c8d2-115">实验室 1-使用 PeopleSoft 系统</span><span class="sxs-lookup"><span data-stu-id="7c8d2-115">Lab 1 - Using a PeopleSoft System</span></span>  
 <span data-ttu-id="7c8d2-116">在此实验室中，你将使用 PeopleSoft 系统而无需使用的任何组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-116">In this lab, you will use the PeopleSoft system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7c8d2-117">目标是测试与 PeopleSoft 以确保第二个实验室可以正常工作的连接。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-117">The goal is to test your connectivity to PeopleSoft to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="7c8d2-118">最初连接到 PeopleSoft 系统通过其 Web 界面，您可以使用 Internet Explorer 等浏览器登录。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-118">Initially you connect to the PeopleSoft system through its Web interface that allows you to log on by using a browser such as Internet Explorer.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="7c8d2-119">实验室 1-使用 PeopleSoft 系统的过程</span><span class="sxs-lookup"><span data-stu-id="7c8d2-119">Procedures for Lab 1 - Using a PeopleSoft System</span></span>  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a><span data-ttu-id="7c8d2-120">若要使用浏览器登录到 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="7c8d2-120">To log on to PeopleSoft by using a browser</span></span>  
  
-   <span data-ttu-id="7c8d2-121">通过浏览到 PeopleSoft 登录页登录到 PeopleSoft 系统。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-121">Log on to the PeopleSoft system by browsing to a PeopleSoft logon page.</span></span> <span data-ttu-id="7c8d2-122">输入你**用户 ID**并**密码**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-122">Enter your **User ID** and **Password** and then click **Sign In**.</span></span>  
  
     <span data-ttu-id="7c8d2-123">![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")</span><span class="sxs-lookup"><span data-stu-id="7c8d2-123">![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")</span></span>  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a><span data-ttu-id="7c8d2-124">若要找到并修改 PeopleSoft 数据</span><span class="sxs-lookup"><span data-stu-id="7c8d2-124">To locate and modify PeopleSoft data</span></span>  
  
1.  <span data-ttu-id="7c8d2-125">成功登录后，在页后，可以通过选择其布局，看到的内容进行个性化设置您。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-125">A successful logon places you at the page to personalize the content you see by choosing its layout.</span></span> <span data-ttu-id="7c8d2-126">向下滚动并展开**设置财务状况/供应链**，单击**常见定义**，单击**位置**，然后单击**位置**电子邮件了。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-126">Scroll down and expand **Set Up Financials/Supply Chain**, click **Common Definitions**, click **Location**, and then click **Location** again.</span></span> <span data-ttu-id="7c8d2-127">这将进入**位置**搜索界面。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-127">This brings you to the **Location** search interface.</span></span>  
  
     <span data-ttu-id="7c8d2-128">![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")</span><span class="sxs-lookup"><span data-stu-id="7c8d2-128">![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")</span></span>  
  
2.  <span data-ttu-id="7c8d2-129">若要开始搜索，请设置**SetID**到 **=** ，将**位置代码**到**开头**，输入  ，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-129">To begin the search, set **SetID** to **=**, set **Location Code** to **begins with**, enter **A**, and then click **Search**.</span></span> <span data-ttu-id="7c8d2-130">这将显示的城市名称开头中的一个**搜索结果**接口的部分。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-130">This displays cities whose names start with A in the **Search Results** section of the interface.</span></span>  
  
     <span data-ttu-id="7c8d2-131">![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")</span><span class="sxs-lookup"><span data-stu-id="7c8d2-131">![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")</span></span>  
  
3.  <span data-ttu-id="7c8d2-132">单击其中一个要获取其详细信息的位置。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-132">Click one of the locations to get its detail information.</span></span> <span data-ttu-id="7c8d2-133">例如，在下图中，用户单击**AUS01**中的链接**位置代码**列。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-133">For example, in the figure below, the user clicked the **AUS01** link in the **Location Code** column.</span></span>  
  
4.  <span data-ttu-id="7c8d2-134">为一个字段中输入一些新数据 (如**地址 2**字段)，单击**保存**左下角。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-134">Enter some new data into one of the fields (such as the **Address 2** field) and click **Save** in the lower-left corner.</span></span> <span data-ttu-id="7c8d2-135">这会将新输入的数据保存到记录。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-135">This saves the newly entered data into the record.</span></span>  
  
     <span data-ttu-id="7c8d2-136">![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")</span><span class="sxs-lookup"><span data-stu-id="7c8d2-136">![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")</span></span>  
  
5.  <span data-ttu-id="7c8d2-137">若要验证此更改的成功，重复步骤 2 中的过程，再次查找同一记录并观察对记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-137">To verify the success of this change, repeat the process from step 2, find this same record again, and observe the changes made to the record.</span></span>  
  
6.  <span data-ttu-id="7c8d2-138">在窗口的右上方部分，单击**注销**以结束 PeopleSoft 会话。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-138">In the upper-right portion of the window, click **Sign out** to end your PeopleSoft session.</span></span>  
  
     <span data-ttu-id="7c8d2-139">![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")</span><span class="sxs-lookup"><span data-stu-id="7c8d2-139">![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c8d2-140">在下一步的实验室中有使用 PeopleSoft 适配器检索您修改的位置记录 (AUS01) 的信息的说明。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-140">In the next lab there are instructions for using the PeopleSoft adapter to retrieve the information for the location record (AUS01) that you modified.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7c8d2-141">总结</span><span class="sxs-lookup"><span data-stu-id="7c8d2-141">Summary</span></span>  
 <span data-ttu-id="7c8d2-142">在此实验室中您登录到 PeopleSoft 系统通过浏览器。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-142">In this lab you logged on to the PeopleSoft system through a browser.</span></span> <span data-ttu-id="7c8d2-143">连接之后，您搜索了数据，然后操作并更新记录的地址字段。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-143">After you were connected, you searched for data, and then manipulated and updated a record's address field.</span></span> <span data-ttu-id="7c8d2-144">后提交更改，您可以查看修改后的数据来验证在浏览器中正确执行的更改。</span><span class="sxs-lookup"><span data-stu-id="7c8d2-144">After committing the change, you could view the modified data in the browser to verify that the change executed properly.</span></span>