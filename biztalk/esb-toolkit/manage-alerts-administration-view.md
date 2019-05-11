---
title: 管理警报 （管理视图） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27f8bf7d-15b7-448d-8c13-e4969b90d021
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71c73788b50154aa49e1773f8c3dc072a81c36a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261453"
---
# <a name="manage-alerts-administration-view"></a><span data-ttu-id="74918-102">管理警报 （管理视图）</span><span class="sxs-lookup"><span data-stu-id="74918-102">Manage Alerts (Administration View)</span></span>
<span data-ttu-id="74918-103">图 1 显示管理视图，管理员可以使用来查看所有警报和及其活动的摘要的列表中的通知页。</span><span class="sxs-lookup"><span data-stu-id="74918-103">Figure 1 shows the Alerts page in administration view, which administrators can use to view a list of all alerts and a summary of their activity.</span></span> <span data-ttu-id="74918-104">表显示每个警报的行。</span><span class="sxs-lookup"><span data-stu-id="74918-104">A table displays a row for each alert.</span></span> <span data-ttu-id="74918-105">每行显示警报的名称、 创建者的姓名、 警报 （例如，在最后一个小时、 天或月警报激活的数量） 的常规统计信息的链接警报的订阅服务器上，若要查看列表，并包含一系列 cli 的操作列的计数若要对警报执行操作的 ckable 图标。</span><span class="sxs-lookup"><span data-stu-id="74918-105">Each row shows the alert name, the name of the creator, general statistics for the alert (such as number of alert activations within the last hour, day, or month), a count of subscribers for the alerts with a link to view a list, and an Actions column containing a set of clickable icons to perform actions on the alert.</span></span>  
  
 <span data-ttu-id="74918-106">![管理警报页](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="74918-106">![Manage Alerts Page](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span></span>  
  
 <span data-ttu-id="74918-107">**图 1**</span><span class="sxs-lookup"><span data-stu-id="74918-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="74918-108">**ESB 管理门户管理警报 （管理视图） 页**</span><span class="sxs-lookup"><span data-stu-id="74918-108">**The ESB Management Portal Manage Alerts (Administration view) page**</span></span>  
  
 <span data-ttu-id="74918-109">以下列表说明了如何使用 ESB 管理门户管理警报页的功能：</span><span class="sxs-lookup"><span data-stu-id="74918-109">The following list explains how you can use the features of the ESB Management Portal Manage Alerts page:</span></span>  
  
-   <span data-ttu-id="74918-110">单击**创建警报**顶部的创建新的警报页的链接。</span><span class="sxs-lookup"><span data-stu-id="74918-110">Click the **Create Alert** link at the top of the page to create a new alert.</span></span>  
  
-   <span data-ttu-id="74918-111">单击**导出到 Excel**链接以将警报的列表导出为 Microsoft Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="74918-111">Click the **Export To Excel** link to export the list of alerts as a Microsoft Excel spreadsheet.</span></span>  
  
-   <span data-ttu-id="74918-112">单击 +**查看订户**行以显示用于警报的订阅服务器列表中的链接。</span><span class="sxs-lookup"><span data-stu-id="74918-112">Click the + **View Subscribers** link in a row to show a list of subscribers for the alert.</span></span> <span data-ttu-id="74918-113">在行中，展开该列表并允许管理员从警报中删除订阅服务器上每个操作列中显示一个删除图标。</span><span class="sxs-lookup"><span data-stu-id="74918-113">The list expands within the row, and a delete icon appears in the Actions column for each one that allows administrators to remove a subscriber from the alert.</span></span> <span data-ttu-id="74918-114">同时，该链接将更改到-**隐藏订户**，允许您折叠的订阅服务器列表。</span><span class="sxs-lookup"><span data-stu-id="74918-114">At the same time, the link changes to - **Hide Subscribers**, allowing you to collapse the list of subscribers.</span></span>  
  
-   <span data-ttu-id="74918-115">单击该行中的警报执行的任务的操作列中的图标。</span><span class="sxs-lookup"><span data-stu-id="74918-115">Click an icon in the Actions column to perform a task for the alerts in that row.</span></span> <span data-ttu-id="74918-116">（按它们出现的顺序） 图标和任务如下所示：</span><span class="sxs-lookup"><span data-stu-id="74918-116">The icons (in the order they appear) and the tasks are the following:</span></span>  
  
    -   <span data-ttu-id="74918-117">**查看警报详细信息。**</span><span class="sxs-lookup"><span data-stu-id="74918-117">**View alert details.**</span></span> <span data-ttu-id="74918-118">此图标显示所选警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="74918-118">This icon displays details of the selected alert.</span></span>  
  
    -   <span data-ttu-id="74918-119">**查看历史记录**。</span><span class="sxs-lookup"><span data-stu-id="74918-119">**View history**.</span></span> <span data-ttu-id="74918-120">此图标显示包含所选警报的所有激活的表。</span><span class="sxs-lookup"><span data-stu-id="74918-120">This icon displays a table containing all the activations for the selected alert.</span></span>  
  
    -   <span data-ttu-id="74918-121">**添加订阅者**。</span><span class="sxs-lookup"><span data-stu-id="74918-121">**Add subscriber**.</span></span> <span data-ttu-id="74918-122">此图标允许管理员将订阅服务器添加到所选警报。</span><span class="sxs-lookup"><span data-stu-id="74918-122">This icon allows administrators to add a subscriber to the selected alert.</span></span>  
  
    -   <span data-ttu-id="74918-123">**编辑警报**。</span><span class="sxs-lookup"><span data-stu-id="74918-123">**Edit alert**.</span></span> <span data-ttu-id="74918-124">此链接允许管理员编辑警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="74918-124">This link allows administrators to edit the alert details.</span></span>  
  
    -   <span data-ttu-id="74918-125">**删除警报**。</span><span class="sxs-lookup"><span data-stu-id="74918-125">**Delete alert**.</span></span> <span data-ttu-id="74918-126">此链接中删除的警报和所有关联的订阅。</span><span class="sxs-lookup"><span data-stu-id="74918-126">This link deletes the alert and all associated subscriptions.</span></span>