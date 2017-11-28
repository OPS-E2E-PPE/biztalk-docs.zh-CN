---
title: "门户警报页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba854c269db4a1d7eabb021a974fa9614abb7690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="portal-alerts-page"></a><span data-ttu-id="3b161-102">“门户警报”页</span><span class="sxs-lookup"><span data-stu-id="3b161-102">Portal Alerts Page</span></span>
<span data-ttu-id="3b161-103">图 1 显示警报页，其中包含两个部分：</span><span class="sxs-lookup"><span data-stu-id="3b161-103">Figure 1 shows the Alerts page, which contains two sections:</span></span>  
  
-   <span data-ttu-id="3b161-104">主要部分显示用于创建新的警报和现有警报的列表的链接。</span><span class="sxs-lookup"><span data-stu-id="3b161-104">The main section displays a link to create a new alert and a list of existing alerts.</span></span> <span data-ttu-id="3b161-105">每个警报都允许您对警报订阅的相应链接。</span><span class="sxs-lookup"><span data-stu-id="3b161-105">Each alert has a corresponding link that allows you to subscribe to the alert.</span></span> <span data-ttu-id="3b161-106">您也可以单击操作列查看警报的详细信息、 创建新订阅的警报，并删除警报中的图标。</span><span class="sxs-lookup"><span data-stu-id="3b161-106">You can also click the icons in the Action column to view details of the alert, create a new subscription for the alert, and delete the alert.</span></span>  
  
-   <span data-ttu-id="3b161-107">**我的订阅**部分显示已在门户内定义的订阅的列表。</span><span class="sxs-lookup"><span data-stu-id="3b161-107">The **My Subscriptions** section displays a list of subscriptions you have defined within the portal.</span></span> <span data-ttu-id="3b161-108">你可以编辑和取消订阅你现有的订阅，此列表中使用的链接。</span><span class="sxs-lookup"><span data-stu-id="3b161-108">You can edit and unsubscribe your existing subscriptions using the links in this list.</span></span>  
  
 <span data-ttu-id="3b161-109">![门户警报页](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8 PortalAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="3b161-109">![Portal Alerts Page](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span></span>  
  
 <span data-ttu-id="3b161-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="3b161-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="3b161-111">**ESB 管理门户通知页**</span><span class="sxs-lookup"><span data-stu-id="3b161-111">**The ESB Management Portal Alerts page**</span></span>  
  
 <span data-ttu-id="3b161-112">ESB 警报服务将生成警报基于条件指定的匹配中的异常值，如到达 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="3b161-112">The ESB Alert Service generates alerts based on criteria you specify that match the values in exceptions as they arrive at the ESB Management Portal.</span></span> <span data-ttu-id="3b161-113">你可以匹配，并比较的一系列引发的异常来准确地控制哪些警报将匹配每个可能的异常类型的字段。</span><span class="sxs-lookup"><span data-stu-id="3b161-113">You can match and compare a range of fields in an exception to control accurately which alerts will match each possible type of exception.</span></span> <span data-ttu-id="3b161-114">门户还可以创建映射到不同类型的警报定义的订阅。</span><span class="sxs-lookup"><span data-stu-id="3b161-114">The portal also allows you to create subscriptions that map to the different types of alerts you define.</span></span> <span data-ttu-id="3b161-115">当出现匹配的警报时，这些订阅可以通知用户。</span><span class="sxs-lookup"><span data-stu-id="3b161-115">These subscriptions can notify users when the matching alert occurs.</span></span>  
  
 <span data-ttu-id="3b161-116">以下列表说明如何使用 ESB 管理门户通知页的功能：</span><span class="sxs-lookup"><span data-stu-id="3b161-116">The following list explains how you can use the features of the ESB Management Portal Alerts page:</span></span>  
  
-   <span data-ttu-id="3b161-117">若要创建新的警报，请单击**创建警报**页后，可以打开添加警报页顶部的链接。</span><span class="sxs-lookup"><span data-stu-id="3b161-117">To create a new alert, click the **Create Alert** link at the top of the page to open the Add Alert page.</span></span>  
  
-   <span data-ttu-id="3b161-118">若要查看或编辑现有警报，请单击操作列中页的主要部分警报中的放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="3b161-118">To view or edit an existing alert, click the magnifying glass icon in the Action column for the alert in the main section of the page.</span></span> <span data-ttu-id="3b161-119">这将打开[警报查看器页面](../esb-toolkit/alert-viewer-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3b161-119">This opens the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md).</span></span>  
  
-   <span data-ttu-id="3b161-120">若要订阅的现有警报，请单击新建订阅图标以打开警报旁边的操作列[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="3b161-120">To subscribe to an existing alert, click the new subscription icon the Action column next to the alert to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="3b161-121">如果打开此页以管理员身份上使用选项**管理员**选项卡菜单 (而不是从**警报**选项卡)，可以单击交叉标记图标旁边的任何警报到列表中的操作列删除警报和任何链接的订阅。</span><span class="sxs-lookup"><span data-stu-id="3b161-121">If you opened this page as an administrator using the options on the **Admin** tab menu (instead of from the **Alerts** tab), you can click the cross mark icon the Action column next to any of the alerts in the list to delete the alert and any linked subscriptions.</span></span>  
  
-   <span data-ttu-id="3b161-122">若要编辑现有订阅，请单击**编辑**旁边的列表中该订阅链接**我的订阅**一部分页后，可以打开[添加警报订阅并编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="3b161-122">To edit an existing subscription, click the **Edit** link next to that subscription in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="3b161-123">若要删除现有订阅，请单击**取消订阅**旁边的列表中该订阅链接**我的订阅**页的部分。</span><span class="sxs-lookup"><span data-stu-id="3b161-123">To remove an existing subscription, click the **Unsubscribe** link next to that subscription in the list in the **My Subscriptions** section of the page.</span></span>  
  
-   <span data-ttu-id="3b161-124">若要导出到 Microsoft Excel 的警报的整个列表，请单击**导出到 Excel**。</span><span class="sxs-lookup"><span data-stu-id="3b161-124">To export the entire list of alerts to Microsoft Excel, click **Export to Excel**.</span></span>