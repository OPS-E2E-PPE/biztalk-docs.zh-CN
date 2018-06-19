---
title: 使用博士 Edwards OneWorld 系统 |Microsoft 文档
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
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287469"
---
# <a name="using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="0b707-102">使用 JD Edwards OneWorld 系统</span><span class="sxs-lookup"><span data-stu-id="0b707-102">Using a JD Edwards OneWorld System</span></span>
<span data-ttu-id="0b707-103">可以使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统中访问 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="0b707-103">The JD Edwards OneWorld system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="0b707-104">此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。</span><span class="sxs-lookup"><span data-stu-id="0b707-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b707-105">JD Edwards OneWorld 实验室工作分为两部分。</span><span class="sxs-lookup"><span data-stu-id="0b707-105">The JD Edwards OneWorld lab work is divided into two parts.</span></span> <span data-ttu-id="0b707-106">第一个实验室（实验室 1）允许您使用 JD Edwards OneWorld 系统，而无需 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或任何 Microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="0b707-106">This first lab (Lab 1) allows you to use the JD Edwards OneWorld system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products.</span></span> <span data-ttu-id="0b707-107">您将使用 JD Edwards OneWorld 客户端工具连接到 JD Edwards OneWorld 数据库并根据地址查找特定的记录。</span><span class="sxs-lookup"><span data-stu-id="0b707-107">You will use the JD Edwards OneWorld Client tool to connect to a JD Edwards OneWorld database and locate a specific record based upon address.</span></span>  
  
 <span data-ttu-id="0b707-108">在第二个实验室（实验室 2）中，您将创建 BizTalk 项目和业务流程。</span><span class="sxs-lookup"><span data-stu-id="0b707-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="0b707-109">创建应用程序之后，将对其进行部署和使用，并通过 JD Edwards OneWorld 适配器连接到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="0b707-109">After you create the application, you will deploy it and use it to connect to a JD Edwards OneWorld system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="0b707-110">目标是使用适配器通过 BizTalk 应用程序来访问数据。</span><span class="sxs-lookup"><span data-stu-id="0b707-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0b707-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="0b707-111">Prerequisites</span></span>  
 <span data-ttu-id="0b707-112">为执行此实验室的过程，您需要安装 JD Edwards OneWorld 客户端软件及其最新更新。</span><span class="sxs-lookup"><span data-stu-id="0b707-112">To perform the procedures for this lab, you need to install the JD Edwards OneWorld client software and its latest update.</span></span> <span data-ttu-id="0b707-113">若要使用任意客户端软件工具，您需要 JD Edwards OneWorld 数据库、到该数据库的网络连接以及该系统上的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0b707-113">To use any of the client software tools you will need a JD Edwards OneWorld database, network connectivity to that database, and a user account on that system.</span></span> <span data-ttu-id="0b707-114">不需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 即可完成此实验。</span><span class="sxs-lookup"><span data-stu-id="0b707-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to complete this lab.</span></span>  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="0b707-115">实验室 1 - 使用 JD Edwards OneWorld 系统</span><span class="sxs-lookup"><span data-stu-id="0b707-115">Lab 1 - Using a JD Edwards OneWorld System</span></span>  
 <span data-ttu-id="0b707-116">在此实验室中，您将使用 JD Edwards OneWorld 系统，而无需使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的任何组件。</span><span class="sxs-lookup"><span data-stu-id="0b707-116">In this lab, you will use the JD Edwards OneWorld system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0b707-117">目标是测试与 JD Edwards OneWorld 的连接，以确保第二个实验室可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="0b707-117">The goals are to test your connectivity to JD Edwards OneWorld and to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="0b707-118">您将使用 JD Edwards OneWorld SQL Plus 工具创建并处理 JD Edwards OneWorld 数据库中的数据表。</span><span class="sxs-lookup"><span data-stu-id="0b707-118">You will use the JD Edwards OneWorld SQL Plus tool to create and manipulate a data table in a JD Edwards OneWorld database.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="0b707-119">实验室 1 的过程 - 使用 JD Edwards OneWorld 系统</span><span class="sxs-lookup"><span data-stu-id="0b707-119">Procedures for Lab 1 - Using a JD Edwards OneWorld System</span></span>  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a><span data-ttu-id="0b707-120">使用浏览器登录到 JD Edwards OneWorld 的步骤</span><span class="sxs-lookup"><span data-stu-id="0b707-120">To log on to JD Edwards OneWorld by using a browser</span></span>  
  
-   <span data-ttu-id="0b707-121">通过单击 JD Edwards OneWorld 图标登录到 JD Edwards OneWorld 系统。</span><span class="sxs-lookup"><span data-stu-id="0b707-121">Log on to the JD Edwards OneWorld system by clicking the JD Edwards OneWorld icon.</span></span> <span data-ttu-id="0b707-122">输入你**用户 ID**，**密码**，和**环境**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0b707-122">Enter your **User ID**, **Password**, and **Environment**, and then click **OK**.</span></span>  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a><span data-ttu-id="0b707-123">查找和查看 JD Edwards OneWorld 数据的步骤</span><span class="sxs-lookup"><span data-stu-id="0b707-123">To locate and view JD Edwards OneWorld data</span></span>  
  
1.  <span data-ttu-id="0b707-124">成功登录使用户在**博士 Edwards OneWorld 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="0b707-124">A successful logon places you at the **JD Edwards OneWorld Explorer**.</span></span>  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  <span data-ttu-id="0b707-125">展开**主路径**，然后**Foundation 系统**，然后**通讯簿**，，然后**每天处理**。</span><span class="sxs-lookup"><span data-stu-id="0b707-125">Expand **Master Directory**, then **Foundation Systems**, then **Address Book**, and then **Daily Processing**.</span></span>  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  <span data-ttu-id="0b707-126">在右侧的窗口中，双击**地址簿修订**。</span><span class="sxs-lookup"><span data-stu-id="0b707-126">In the right-hand window, double-click **Address Book Revisions**.</span></span>  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  <span data-ttu-id="0b707-127">有关**字母名称**，输入`Ga`，选择**显示地址**复选框，并依次**查找**工具栏上。</span><span class="sxs-lookup"><span data-stu-id="0b707-127">For **Alpha Name**, enter `Ga`, select the **Display Address** check box, and then click **Find** on the toolbar.</span></span>  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     <span data-ttu-id="0b707-128">在**地址簿修订版本-[工作与地址]** 对话框中，搜索结果显示两条记录。</span><span class="sxs-lookup"><span data-stu-id="0b707-128">In the **Address Book Revisions - [Work With Addresses]** dialog box, two records are displayed as a result of the search.</span></span>  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     <span data-ttu-id="0b707-129">查找数据的一种替代方法是清除**字母名称**字段中，在上面的文本框中单击**地址数**列，并输入`500`。</span><span class="sxs-lookup"><span data-stu-id="0b707-129">An alternative method of locating data is to clear the **Alpha Name** field, click in the text box above the **Address Number** column, and enter `500`.</span></span> <span data-ttu-id="0b707-130">单击**查找**在工具栏上，以显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="0b707-130">Click **Find** on the toolbar to display the search results.</span></span>  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     <span data-ttu-id="0b707-131">在实验室 2 中，将使用博士 Edwards OneWorld 适配器若要检索的信息的说明**地址数**的`500`。</span><span class="sxs-lookup"><span data-stu-id="0b707-131">In Lab 2, there will be instructions for using the JD Edwards OneWorld adapter to retrieve the information for an **Address Number** of `500`.</span></span>  
  
5.  <span data-ttu-id="0b707-132">上**文件**菜单上，单击**退出**退出 JE Edwards OneWorld 客户端会话。</span><span class="sxs-lookup"><span data-stu-id="0b707-132">On the **File** menu, click **Exit** to exit the JE Edwards OneWorld Client session.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="0b707-133">摘要</span><span class="sxs-lookup"><span data-stu-id="0b707-133">Summary</span></span>  
 <span data-ttu-id="0b707-134">在此实验室中，您使用了用于登录到 JD Edwards OneWorld 系统的 JD Edwards OneWorld 客户端工具。</span><span class="sxs-lookup"><span data-stu-id="0b707-134">In this lab, you used the JD Edwards OneWorld Client tool to log on to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="0b707-135">连接后，您对特定数据进行了搜索并查看了返回的数据记录。</span><span class="sxs-lookup"><span data-stu-id="0b707-135">After you were connected, you searched for specific data and viewed the data records returned.</span></span>