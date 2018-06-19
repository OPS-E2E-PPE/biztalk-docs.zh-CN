---
title: 列出、 搜索和排序错误消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294637"
---
# <a name="listing-searching-and-sorting-fault-messages"></a><span data-ttu-id="88e86-102">列出、 搜索和排序错误消息</span><span class="sxs-lookup"><span data-stu-id="88e86-102">Listing, Searching, and Sorting Fault Messages</span></span>
<span data-ttu-id="88e86-103">ESB 管理门户主页上可用于获取在 Microsoft BizTalk Server 中执行的应用程序的状态的总体视图。</span><span class="sxs-lookup"><span data-stu-id="88e86-103">You can use the Home page of the ESB Management Portal to obtain an overall view of the status of the applications executing within Microsoft BizTalk Server.</span></span> <span data-ttu-id="88e86-104">可以使用的错误页的错误消息，基于对一系列的条件的查询。</span><span class="sxs-lookup"><span data-stu-id="88e86-104">The Faults page can be used to query for fault messages, based on a range of criteria.</span></span>  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a><span data-ttu-id="88e86-105">若要查看当前的 BizTalk Server 应用程序的状态的概述</span><span class="sxs-lookup"><span data-stu-id="88e86-105">To see an overview of the status of current BizTalk Server applications</span></span>  
  
1.  <span data-ttu-id="88e86-106">打开[门户主页上](../esb-toolkit/portal-home-page.md)。</span><span class="sxs-lookup"><span data-stu-id="88e86-106">Open the [Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="88e86-107">此页显示整个应用程序状态、 错误的摘要、 通用、 描述、 发现和集成 (UDDI) 注册和显示的错误以及按应用程序类型和细分的图表的最近的请求。</span><span class="sxs-lookup"><span data-stu-id="88e86-107">This page displays the overall application state, a summary of faults, recent requests for Universal Description, Discovery, and Integration (UDDI) registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
2.  <span data-ttu-id="88e86-108">若要选择你想要查看的信息的应用程序，请单击**选择应用程序**链接上方的第一个图表，然后选择或清除复选框中显示的已安装 BizTalk Server 应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="88e86-108">To select the applications for which you want to view information, click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed BizTalk Server applications that appears.</span></span>  
  
3.  <span data-ttu-id="88e86-109">若要更改时间为其门户显示的信息，请选择**小时、 天、 周、 月、 季度、 每年，** 或**所有**第二个图表上方的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="88e86-109">To change the period for which the portal displays information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="88e86-110">若要更改默认设置用于在主页上的应用程序和显示时间的列表，请编辑设置上[门户我设置页](../esb-toolkit/portal-my-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="88e86-110">To change the default settings used on the Home page for the list of applications and the display period, edit the settings on the [Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span>  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a><span data-ttu-id="88e86-111">若要列出，搜索和排序错误 ESB 管理门户中的消息</span><span class="sxs-lookup"><span data-stu-id="88e86-111">To list, search for, and sort fault messages in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="88e86-112">打开[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="88e86-112">Open the [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span> <span data-ttu-id="88e86-113">此页面显示截断的每个错误的属性的列表，并由一系列条件支持的故障分析。</span><span class="sxs-lookup"><span data-stu-id="88e86-113">This page displays a truncated list of properties for each fault and supports analysis of faults by a range of criteria.</span></span>  
  
2.  <span data-ttu-id="88e86-114">若要筛选的页面上显示的错误的列表，请使用下拉列表和列表上方的错误的文本框。</span><span class="sxs-lookup"><span data-stu-id="88e86-114">To filter the list of faults displayed on the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="88e86-115">你可以筛选显示的应用程序、 段、 错误代码编号、 错误类别名称、 错误键入文本，和最小/最大错误严重级别的行。</span><span class="sxs-lookup"><span data-stu-id="88e86-115">You can filter the rows displayed by application, period, fault code number, fault category name, error type text, and minimum/maximum fault severity.</span></span> <span data-ttu-id="88e86-116">任何控件留空以检索而不考虑其值为此条件的所有消息。</span><span class="sxs-lookup"><span data-stu-id="88e86-116">Leave any of the controls empty to retrieve all messages irrespective of their value for this criterion.</span></span>  
  
3.  <span data-ttu-id="88e86-117">单击**应用筛选器**以查看匹配的错误的列表。</span><span class="sxs-lookup"><span data-stu-id="88e86-117">Click **Apply Filters** to see the list of matching faults.</span></span> <span data-ttu-id="88e86-118">请注意，筛选非常大的容错的数据库可能需要几秒钟才会显示结果。</span><span class="sxs-lookup"><span data-stu-id="88e86-118">Note that filtering on very large fault databases may take a few seconds to display results.</span></span>  
  
4.  <span data-ttu-id="88e86-119">若要在页中显示更多或更少的行，选择相应的值**记录每个页**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="88e86-119">To display more or fewer rows in the page, select the appropriate value in the **Records Per Page** drop-down list.</span></span>  
  
5.  <span data-ttu-id="88e86-120">若要排序的错误消息的列表，请单击列标题。</span><span class="sxs-lookup"><span data-stu-id="88e86-120">To sort the list of fault messages, click a column heading.</span></span> <span data-ttu-id="88e86-121">若要以相反顺序对行进行排序，请单击相同的列标题。</span><span class="sxs-lookup"><span data-stu-id="88e86-121">To sort the rows in reverse order, click the same column heading again.</span></span>  
  
6.  <span data-ttu-id="88e86-122">单击**导出到 Excel**下载可以在 Microsoft Excel 中查看的格式的错误消息的完整列表。</span><span class="sxs-lookup"><span data-stu-id="88e86-122">Click **Export To Excel** to download the complete list of fault messages in a format that you can view in Microsoft Excel.</span></span>