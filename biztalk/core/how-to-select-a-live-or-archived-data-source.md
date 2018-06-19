---
title: 如何选择实时或已存档的数据源 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7172a822a71e2b0d7dc621e6c1e11b055b723bd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255285"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="22edf-102">如何选择实时或已存档的数据源</span><span class="sxs-lookup"><span data-stu-id="22edf-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="22edf-103">使用 BizTalktracking 可以访问存档和实时数据。</span><span class="sxs-lookup"><span data-stu-id="22edf-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="22edf-104">从 main 选择实时或已存档的数据源**BizTalk Server 管理**节点 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="22edf-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="22edf-105">默认情况下将采用实时数据源，即从 BizTalk 管理数据库中检索数据。</span><span class="sxs-lookup"><span data-stu-id="22edf-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="22edf-106">如果选择使用存档的数据，则必须选择要使用的相应服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="22edf-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  
  
-   <span data-ttu-id="22edf-107">存档的数据：通过分析存档的数据，可以检查在业务和系统方面的趋势，因为您可以根据需要以前任意时候发生的事件进行查看。</span><span class="sxs-lookup"><span data-stu-id="22edf-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="22edf-108">若要选择存档的数据，则还必须选择包含存档数据的相应 SQL Server 和 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="22edf-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  
  
     <span data-ttu-id="22edf-109">已存档的数据所指定的选择**连接到现有的跟踪数据库...**.</span><span class="sxs-lookup"><span data-stu-id="22edf-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  
  
-   <span data-ttu-id="22edf-110">实时数据：通过分析实时数据，可以监视业务流程和管道，以便确定并解决开发或过渡环境中的问题。</span><span class="sxs-lookup"><span data-stu-id="22edf-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="22edf-111">通过监视实时数据，还可以解决系统中的问题，例如，消息为何挂起等。</span><span class="sxs-lookup"><span data-stu-id="22edf-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  
  
     <span data-ttu-id="22edf-112">实时数据所指定的选择**连接到现有组...**.</span><span class="sxs-lookup"><span data-stu-id="22edf-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="22edf-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="22edf-113">Prerequisites</span></span>  
 <span data-ttu-id="22edf-114">必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="22edf-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-select-live-data"></a><span data-ttu-id="22edf-115">选择实时数据</span><span class="sxs-lookup"><span data-stu-id="22edf-115">To select live data</span></span>  
  
1.  <span data-ttu-id="22edf-116">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="22edf-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="22edf-117">单击主**BizTalk Server 管理**节点。</span><span class="sxs-lookup"><span data-stu-id="22edf-117">Click the main  **BizTalk Server Administration** node.</span></span>  
  
3.  <span data-ttu-id="22edf-118">单击**连接到现有组...**</span><span class="sxs-lookup"><span data-stu-id="22edf-118">Click **Connect to an existing group…**</span></span>  
  
4.  <span data-ttu-id="22edf-119">在**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="22edf-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  
  
5.  <span data-ttu-id="22edf-120">在**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。</span><span class="sxs-lookup"><span data-stu-id="22edf-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  
  
6.  <span data-ttu-id="22edf-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="22edf-121">Click **OK**.</span></span>  
  
### <a name="to-select-archived-data"></a><span data-ttu-id="22edf-122">选择存档的数据</span><span class="sxs-lookup"><span data-stu-id="22edf-122">To select archived data</span></span>  
  
1.  <span data-ttu-id="22edf-123">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="22edf-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="22edf-124">单击主**BizTalk Server 管理**节点。</span><span class="sxs-lookup"><span data-stu-id="22edf-124">Click the main  **BizTalk Server Administration** node.</span></span>  
  
3.  <span data-ttu-id="22edf-125">单击**连接到现有的跟踪数据库...**</span><span class="sxs-lookup"><span data-stu-id="22edf-125">Click **Connect to an existing tracking database…**</span></span>  
  
4.  <span data-ttu-id="22edf-126">在**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="22edf-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  
  
5.  <span data-ttu-id="22edf-127">在**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。</span><span class="sxs-lookup"><span data-stu-id="22edf-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  
  
6.  <span data-ttu-id="22edf-128">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="22edf-128">Click **OK**.</span></span>