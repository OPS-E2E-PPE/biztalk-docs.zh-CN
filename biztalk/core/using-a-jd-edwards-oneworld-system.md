---
title: 使用 JD Edwards OneWorld 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fb7bdef551f0ceb66e8eea5ea1fe073bd0bca72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399926"
---
# <a name="using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="ecb09-102">使用 JD Edwards OneWorld 系统</span><span class="sxs-lookup"><span data-stu-id="ecb09-102">Using a JD Edwards OneWorld System</span></span>
<span data-ttu-id="ecb09-103">JD Edwards OneWorld 系统是从可访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统通过使用 JD Edwards OneWorld 适配器。</span><span class="sxs-lookup"><span data-stu-id="ecb09-103">The JD Edwards OneWorld system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="ecb09-104">此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配合使用的一组八个业务线 (LOB) 适配器之一。</span><span class="sxs-lookup"><span data-stu-id="ecb09-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ecb09-105">JD Edwards OneWorld 实验室工作分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="ecb09-105">The JD Edwards OneWorld lab work is divided into two parts.</span></span> <span data-ttu-id="ecb09-106">第一个实验室 (实验室 1)，可使用 JD Edwards OneWorld 系统，而无需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何 Microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="ecb09-106">This first lab (Lab 1) allows you to use the JD Edwards OneWorld system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products.</span></span> <span data-ttu-id="ecb09-107">您将使用 JD Edwards OneWorld 客户端工具连接到 JD Edwards OneWorld 数据库并找到基于地址的特定记录。</span><span class="sxs-lookup"><span data-stu-id="ecb09-107">You will use the JD Edwards OneWorld Client tool to connect to a JD Edwards OneWorld database and locate a specific record based upon address.</span></span>  
  
 <span data-ttu-id="ecb09-108">在第二个实验室 (实验室 2) 中，将创建 BizTalk 项目和业务流程。</span><span class="sxs-lookup"><span data-stu-id="ecb09-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="ecb09-109">创建应用程序后，会将其部署，并使用它来通过使用 JD Edwards OneWorld 适配器连接到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="ecb09-109">After you create the application, you will deploy it and use it to connect to a JD Edwards OneWorld system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="ecb09-110">目标是通过使用适配器通过 BizTalk 应用程序访问数据。</span><span class="sxs-lookup"><span data-stu-id="ecb09-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecb09-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="ecb09-111">Prerequisites</span></span>  
 <span data-ttu-id="ecb09-112">若要执行此实验室的过程，需要安装 JD Edwards OneWorld 客户端软件，且其最新的更新。</span><span class="sxs-lookup"><span data-stu-id="ecb09-112">To perform the procedures for this lab, you need to install the JD Edwards OneWorld client software and its latest update.</span></span> <span data-ttu-id="ecb09-113">若要使用任何客户端软件工具将需要 JD Edwards OneWorld 数据库、 网络连接到该数据库，并在该系统上的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ecb09-113">To use any of the client software tools you will need a JD Edwards OneWorld database, network connectivity to that database, and a user account on that system.</span></span> <span data-ttu-id="ecb09-114">不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]完成此实验。</span><span class="sxs-lookup"><span data-stu-id="ecb09-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to complete this lab.</span></span>  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="ecb09-115">实验室 1-使用 JD Edwards OneWorld 系统</span><span class="sxs-lookup"><span data-stu-id="ecb09-115">Lab 1 - Using a JD Edwards OneWorld System</span></span>  
 <span data-ttu-id="ecb09-116">在此实验室中，你将使用 JD Edwards OneWorld 系统而无需使用的任何组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ecb09-116">In this lab, you will use the JD Edwards OneWorld system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ecb09-117">目标是测试与 JD Edwards OneWorld 的连接，以确保第二个实验室可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="ecb09-117">The goals are to test your connectivity to JD Edwards OneWorld and to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="ecb09-118">将使用 JD Edwards OneWorld SQL Plus 工具创建和操作 JD Edwards OneWorld 数据库中的数据表。</span><span class="sxs-lookup"><span data-stu-id="ecb09-118">You will use the JD Edwards OneWorld SQL Plus tool to create and manipulate a data table in a JD Edwards OneWorld database.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="ecb09-119">实验室 1-使用 JD Edwards OneWorld 系统的过程</span><span class="sxs-lookup"><span data-stu-id="ecb09-119">Procedures for Lab 1 - Using a JD Edwards OneWorld System</span></span>  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a><span data-ttu-id="ecb09-120">若要使用浏览器登录到 JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="ecb09-120">To log on to JD Edwards OneWorld by using a browser</span></span>  
  
-   <span data-ttu-id="ecb09-121">通过单击 JD Edwards OneWorld 图标登录到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="ecb09-121">Log on to the JD Edwards OneWorld system by clicking the JD Edwards OneWorld icon.</span></span> <span data-ttu-id="ecb09-122">输入你**用户 ID**，**密码**，并**环境**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ecb09-122">Enter your **User ID**, **Password**, and **Environment**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ecb09-123">![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")</span><span class="sxs-lookup"><span data-stu-id="ecb09-123">![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")</span></span>  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a><span data-ttu-id="ecb09-124">若要查找和查看 JD Edwards OneWorld 数据</span><span class="sxs-lookup"><span data-stu-id="ecb09-124">To locate and view JD Edwards OneWorld data</span></span>  
  
1.  <span data-ttu-id="ecb09-125">成功登录后，您在**JD Edwards OneWorld Explorer**。</span><span class="sxs-lookup"><span data-stu-id="ecb09-125">A successful logon places you at the **JD Edwards OneWorld Explorer**.</span></span>  
  
     <span data-ttu-id="ecb09-126">![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")</span><span class="sxs-lookup"><span data-stu-id="ecb09-126">![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")</span></span>  
  
2.  <span data-ttu-id="ecb09-127">展开**主目录**，然后**Foundation 系统**，然后**通讯簿**，然后**每天处理**。</span><span class="sxs-lookup"><span data-stu-id="ecb09-127">Expand **Master Directory**, then **Foundation Systems**, then **Address Book**, and then **Daily Processing**.</span></span>  
  
     <span data-ttu-id="ecb09-128">![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")</span><span class="sxs-lookup"><span data-stu-id="ecb09-128">![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")</span></span>  
  
3.  <span data-ttu-id="ecb09-129">在右侧窗口中，双击**Address Book Revisions**。</span><span class="sxs-lookup"><span data-stu-id="ecb09-129">In the right-hand window, double-click **Address Book Revisions**.</span></span>  
  
     <span data-ttu-id="ecb09-130">![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")</span><span class="sxs-lookup"><span data-stu-id="ecb09-130">![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")</span></span>  
  
4.  <span data-ttu-id="ecb09-131">有关**Alpha 名称**，输入`Ga`，选择**显示地址**复选框，然后依次**查找**工具栏上。</span><span class="sxs-lookup"><span data-stu-id="ecb09-131">For **Alpha Name**, enter `Ga`, select the **Display Address** check box, and then click **Find** on the toolbar.</span></span>  
  
     <span data-ttu-id="ecb09-132">![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")</span><span class="sxs-lookup"><span data-stu-id="ecb09-132">![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")</span></span>  
  
     <span data-ttu-id="ecb09-133">在中**Address Book Revisions-[Work With Addresses]** 对话框中，两条记录显示为一个搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ecb09-133">In the **Address Book Revisions - [Work With Addresses]** dialog box, two records are displayed as a result of the search.</span></span>  
  
     <span data-ttu-id="ecb09-134">![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")</span><span class="sxs-lookup"><span data-stu-id="ecb09-134">![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")</span></span>  
  
     <span data-ttu-id="ecb09-135">查找数据的一种替代方法是清除**Alpha 名称**字段中，单击上方的文本框中**地址号码**列中，并输入`500`。</span><span class="sxs-lookup"><span data-stu-id="ecb09-135">An alternative method of locating data is to clear the **Alpha Name** field, click in the text box above the **Address Number** column, and enter `500`.</span></span> <span data-ttu-id="ecb09-136">单击**查找**上工具栏以显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ecb09-136">Click **Find** on the toolbar to display the search results.</span></span>  
  
     <span data-ttu-id="ecb09-137">![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")</span><span class="sxs-lookup"><span data-stu-id="ecb09-137">![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")</span></span>  
  
     <span data-ttu-id="ecb09-138">在实验室 2 中，将使用 JD Edwards OneWorld 适配器来检索的信息说明**地址号码**的`500`。</span><span class="sxs-lookup"><span data-stu-id="ecb09-138">In Lab 2, there will be instructions for using the JD Edwards OneWorld adapter to retrieve the information for an **Address Number** of `500`.</span></span>  
  
5.  <span data-ttu-id="ecb09-139">上**文件**菜单上，单击**退出**以退出 JE Edwards OneWorld 客户端会话。</span><span class="sxs-lookup"><span data-stu-id="ecb09-139">On the **File** menu, click **Exit** to exit the JE Edwards OneWorld Client session.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ecb09-140">总结</span><span class="sxs-lookup"><span data-stu-id="ecb09-140">Summary</span></span>  
 <span data-ttu-id="ecb09-141">在此实验中，您将使用 JD Edwards OneWorld 客户端工具登录到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="ecb09-141">In this lab, you used the JD Edwards OneWorld Client tool to log on to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="ecb09-142">连接之后，您搜索特定的数据，并查看返回的数据记录。</span><span class="sxs-lookup"><span data-stu-id="ecb09-142">After you were connected, you searched for specific data and viewed the data records returned.</span></span>