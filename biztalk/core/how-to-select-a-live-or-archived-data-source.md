---
title: 如何选择实时或存档的数据源 |Microsoft Docs
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
ms.openlocfilehash: e5917c4488e047a1956fde66a659754c659f23d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383951"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="717fe-102">如何选择实时或存档的数据源</span><span class="sxs-lookup"><span data-stu-id="717fe-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="717fe-103">使用 biztalktracking 可以访问存档和实时数据。</span><span class="sxs-lookup"><span data-stu-id="717fe-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="717fe-104">从主选择实时或存档的数据源**BizTalk Server 管理**节点 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="717fe-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="717fe-105">默认源是从 BizTalk 管理数据库中检索到的实时数据。</span><span class="sxs-lookup"><span data-stu-id="717fe-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="717fe-106">如果您选择使用存档的数据，必须选择相应服务器和数据库/s 可处理的。</span><span class="sxs-lookup"><span data-stu-id="717fe-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  

-   <span data-ttu-id="717fe-107">存档的数据：分析已存档的数据，可以在业务中和在系统上检查趋势，因为您可以根据需要回溯。</span><span class="sxs-lookup"><span data-stu-id="717fe-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="717fe-108">如果选择存档的数据，还必须选择相应的 SQL 服务器和包含已存档的数据的 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="717fe-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  

     <span data-ttu-id="717fe-109">通过选择指定存档的数据**连接到现有跟踪数据库...**.</span><span class="sxs-lookup"><span data-stu-id="717fe-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  

-   <span data-ttu-id="717fe-110">实时数据：分析实时数据，可以监视业务流程和管道，以便确定并解决开发或过渡环境中的问题。</span><span class="sxs-lookup"><span data-stu-id="717fe-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="717fe-111">监视实时数据还可以在系统中，如挂起消息的原因更正问题。</span><span class="sxs-lookup"><span data-stu-id="717fe-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  

     <span data-ttu-id="717fe-112">通过选择指定实时数据**连接到现有组...**.</span><span class="sxs-lookup"><span data-stu-id="717fe-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="717fe-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="717fe-113">Prerequisites</span></span>  
 <span data-ttu-id="717fe-114">您必须为要执行此过程的 BizTalk Server Operators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="717fe-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  

### <a name="to-select-live-data"></a><span data-ttu-id="717fe-115">选择实时数据</span><span class="sxs-lookup"><span data-stu-id="717fe-115">To select live data</span></span>  

1. <span data-ttu-id="717fe-116">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="717fe-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="717fe-117">单击主**BizTalk Server 管理**节点。</span><span class="sxs-lookup"><span data-stu-id="717fe-117">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="717fe-118">单击**连接到现有组...**</span><span class="sxs-lookup"><span data-stu-id="717fe-118">Click **Connect to an existing group…**</span></span>  

4. <span data-ttu-id="717fe-119">在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="717fe-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="717fe-120">在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。</span><span class="sxs-lookup"><span data-stu-id="717fe-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="717fe-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="717fe-121">Click **OK**.</span></span>  

### <a name="to-select-archived-data"></a><span data-ttu-id="717fe-122">若要选择存档的数据</span><span class="sxs-lookup"><span data-stu-id="717fe-122">To select archived data</span></span>  

1. <span data-ttu-id="717fe-123">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="717fe-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="717fe-124">单击主**BizTalk Server 管理**节点。</span><span class="sxs-lookup"><span data-stu-id="717fe-124">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="717fe-125">单击**连接到现有跟踪数据库...**</span><span class="sxs-lookup"><span data-stu-id="717fe-125">Click **Connect to an existing tracking database…**</span></span>  

4. <span data-ttu-id="717fe-126">在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="717fe-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="717fe-127">在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。</span><span class="sxs-lookup"><span data-stu-id="717fe-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="717fe-128">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="717fe-128">Click **OK**.</span></span>
