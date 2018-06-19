---
title: 管理警报 （管理视图） |Microsoft 文档
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
ms.openlocfilehash: bc5472e96414fe5141de27630ebe3c810d2df28c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294437"
---
# <a name="manage-alerts-administration-view"></a><span data-ttu-id="b45a2-102">管理警报 （管理视图）</span><span class="sxs-lookup"><span data-stu-id="b45a2-102">Manage Alerts (Administration View)</span></span>
<span data-ttu-id="b45a2-103">图 1 显示管理视图，管理员可以使用它来查看所有警报和其活动的摘要的列表中的通知页。</span><span class="sxs-lookup"><span data-stu-id="b45a2-103">Figure 1 shows the Alerts page in administration view, which administrators can use to view a list of all alerts and a summary of their activity.</span></span> <span data-ttu-id="b45a2-104">一个表显示对于每个警报的行。</span><span class="sxs-lookup"><span data-stu-id="b45a2-104">A table displays a row for each alert.</span></span> <span data-ttu-id="b45a2-105">每行都显示警报的名称、 创建者的姓名、 （如警报激活数内最后一个小时、 天或月），该警报的常规统计信息的链接的警报的订阅服务器上，若要查看列表和一个操作列，包含一套 cli 的计数ckable 图标，以对警报执行操作。</span><span class="sxs-lookup"><span data-stu-id="b45a2-105">Each row shows the alert name, the name of the creator, general statistics for the alert (such as number of alert activations within the last hour, day, or month), a count of subscribers for the alerts with a link to view a list, and an Actions column containing a set of clickable icons to perform actions on the alert.</span></span>  
  
 <span data-ttu-id="b45a2-106">![管理警报页](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8 ManageAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="b45a2-106">![Manage Alerts Page](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span></span>  
  
 <span data-ttu-id="b45a2-107">**图 1**</span><span class="sxs-lookup"><span data-stu-id="b45a2-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="b45a2-108">**ESB 管理门户管理通知 （管理视图） 页**</span><span class="sxs-lookup"><span data-stu-id="b45a2-108">**The ESB Management Portal Manage Alerts (Administration view) page**</span></span>  
  
 <span data-ttu-id="b45a2-109">以下列表说明如何使用 ESB 管理门户管理通知页的功能：</span><span class="sxs-lookup"><span data-stu-id="b45a2-109">The following list explains how you can use the features of the ESB Management Portal Manage Alerts page:</span></span>  
  
-   <span data-ttu-id="b45a2-110">单击**创建警报**页后，可以创建新的警报顶部的链接。</span><span class="sxs-lookup"><span data-stu-id="b45a2-110">Click the **Create Alert** link at the top of the page to create a new alert.</span></span>  
  
-   <span data-ttu-id="b45a2-111">单击**导出到 Excel**链接以将警报的列表导出为 Microsoft Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="b45a2-111">Click the **Export To Excel** link to export the list of alerts as a Microsoft Excel spreadsheet.</span></span>  
  
-   <span data-ttu-id="b45a2-112">单击 +**查看订户**行显示用于警报的订阅服务器列表中的链接。</span><span class="sxs-lookup"><span data-stu-id="b45a2-112">Click the + **View Subscribers** link in a row to show a list of subscribers for the alert.</span></span> <span data-ttu-id="b45a2-113">在行中，展开该列表和一个删除图标将出现在为每个，使管理员能够从警报中删除订阅服务器操作列。</span><span class="sxs-lookup"><span data-stu-id="b45a2-113">The list expands within the row, and a delete icon appears in the Actions column for each one that allows administrators to remove a subscriber from the alert.</span></span> <span data-ttu-id="b45a2-114">同时，该链接将更改到-**隐藏的订阅服务器**，并可折叠的订阅服务器列表。</span><span class="sxs-lookup"><span data-stu-id="b45a2-114">At the same time, the link changes to - **Hide Subscribers**, allowing you to collapse the list of subscribers.</span></span>  
  
-   <span data-ttu-id="b45a2-115">单击操作列以该行中的警报执行某项任务中的图标。</span><span class="sxs-lookup"><span data-stu-id="b45a2-115">Click an icon in the Actions column to perform a task for the alerts in that row.</span></span> <span data-ttu-id="b45a2-116">（按它们出现的顺序） 的图标和任务如下所示：</span><span class="sxs-lookup"><span data-stu-id="b45a2-116">The icons (in the order they appear) and the tasks are the following:</span></span>  
  
    -   <span data-ttu-id="b45a2-117">**查看警报详细信息。**</span><span class="sxs-lookup"><span data-stu-id="b45a2-117">**View alert details.**</span></span> <span data-ttu-id="b45a2-118">此图标显示所选警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b45a2-118">This icon displays details of the selected alert.</span></span>  
  
    -   <span data-ttu-id="b45a2-119">**查看历史记录**。</span><span class="sxs-lookup"><span data-stu-id="b45a2-119">**View history**.</span></span> <span data-ttu-id="b45a2-120">此图标显示包含所选警报的所有激活的表。</span><span class="sxs-lookup"><span data-stu-id="b45a2-120">This icon displays a table containing all the activations for the selected alert.</span></span>  
  
    -   <span data-ttu-id="b45a2-121">**将订户添加**。</span><span class="sxs-lookup"><span data-stu-id="b45a2-121">**Add subscriber**.</span></span> <span data-ttu-id="b45a2-122">此图标允许管理员将订户添加到所选警报。</span><span class="sxs-lookup"><span data-stu-id="b45a2-122">This icon allows administrators to add a subscriber to the selected alert.</span></span>  
  
    -   <span data-ttu-id="b45a2-123">**编辑警报**。</span><span class="sxs-lookup"><span data-stu-id="b45a2-123">**Edit alert**.</span></span> <span data-ttu-id="b45a2-124">此链接允许管理员编辑警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b45a2-124">This link allows administrators to edit the alert details.</span></span>  
  
    -   <span data-ttu-id="b45a2-125">**删除警报**。</span><span class="sxs-lookup"><span data-stu-id="b45a2-125">**Delete alert**.</span></span> <span data-ttu-id="b45a2-126">此链接删除的警报和所有关联的订阅。</span><span class="sxs-lookup"><span data-stu-id="b45a2-126">This link deletes the alert and all associated subscriptions.</span></span>