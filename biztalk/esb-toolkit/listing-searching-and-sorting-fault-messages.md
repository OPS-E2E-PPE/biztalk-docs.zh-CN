---
title: 列出、 搜索和排序错误消息 |Microsoft Docs
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
ms.openlocfilehash: 0c68d5411bc7f9837a1e1f41892b2741d0b56a3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261498"
---
# <a name="listing-searching-and-sorting-fault-messages"></a><span data-ttu-id="8e27e-102">列出、 搜索和排序故障消息</span><span class="sxs-lookup"><span data-stu-id="8e27e-102">Listing, Searching, and Sorting Fault Messages</span></span>
<span data-ttu-id="8e27e-103">ESB 管理门户的主页上可用于获取 Microsoft BizTalk Server 内执行的应用程序的状态的总体视图。</span><span class="sxs-lookup"><span data-stu-id="8e27e-103">You can use the Home page of the ESB Management Portal to obtain an overall view of the status of the applications executing within Microsoft BizTalk Server.</span></span> <span data-ttu-id="8e27e-104">可以使用的错误页错误消息，根据一系列条件的查询。</span><span class="sxs-lookup"><span data-stu-id="8e27e-104">The Faults page can be used to query for fault messages, based on a range of criteria.</span></span>  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a><span data-ttu-id="8e27e-105">若要查看当前的 BizTalk Server 应用程序的状态的概述</span><span class="sxs-lookup"><span data-stu-id="8e27e-105">To see an overview of the status of current BizTalk Server applications</span></span>  
  
1.  <span data-ttu-id="8e27e-106">打开[门户主页上](../esb-toolkit/portal-home-page.md)。</span><span class="sxs-lookup"><span data-stu-id="8e27e-106">Open the [Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="8e27e-107">此页显示的应用程序的总体状态、 错误的摘要、 通用描述、 发现和集成 (UDDI) 注册和显示的错误类型和应用程序细分的图表的最近的请求。</span><span class="sxs-lookup"><span data-stu-id="8e27e-107">This page displays the overall application state, a summary of faults, recent requests for Universal Description, Discovery, and Integration (UDDI) registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
2.  <span data-ttu-id="8e27e-108">若要选择你想要查看的信息的应用程序，请单击**选择应用程序**链接上方的第一个图表，然后选择或清除复选框将显示已安装 BizTalk Server 应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="8e27e-108">To select the applications for which you want to view information, click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed BizTalk Server applications that appears.</span></span>  
  
3.  <span data-ttu-id="8e27e-109">若要更改的期限为其在门户中显示的信息，请选择**小时、 天、 周、 月、 季度、 年**或**所有**的第一个图表上方的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="8e27e-109">To change the period for which the portal displays information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="8e27e-110">若要更改默认设置应用程序和显示时间的列表所用的主页上，编辑设置上[门户我的设置网页](../esb-toolkit/portal-my-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="8e27e-110">To change the default settings used on the Home page for the list of applications and the display period, edit the settings on the [Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span>  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a><span data-ttu-id="8e27e-111">若要列出，搜索以搜索和排序故障 ESB 管理门户中的消息</span><span class="sxs-lookup"><span data-stu-id="8e27e-111">To list, search for, and sort fault messages in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="8e27e-112">打开[容错设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="8e27e-112">Open the [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span> <span data-ttu-id="8e27e-113">此页显示被截断的每个错误的属性列表，并由一系列条件支持的错误进行的分析。</span><span class="sxs-lookup"><span data-stu-id="8e27e-113">This page displays a truncated list of properties for each fault and supports analysis of faults by a range of criteria.</span></span>  
  
2.  <span data-ttu-id="8e27e-114">若要筛选的错误页上显示的列表，请使用下拉列表和列表上方的错误的文本框。</span><span class="sxs-lookup"><span data-stu-id="8e27e-114">To filter the list of faults displayed on the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="8e27e-115">您可以筛选的行显示的应用程序、 时间、 错误代码编号、 错误类别名称、 错误类型文本和最小/最大故障严重性。</span><span class="sxs-lookup"><span data-stu-id="8e27e-115">You can filter the rows displayed by application, period, fault code number, fault category name, error type text, and minimum/maximum fault severity.</span></span> <span data-ttu-id="8e27e-116">保留的任何控件为空以检索所有消息而不考虑它们的值为此条件。</span><span class="sxs-lookup"><span data-stu-id="8e27e-116">Leave any of the controls empty to retrieve all messages irrespective of their value for this criterion.</span></span>  
  
3.  <span data-ttu-id="8e27e-117">单击**将应用筛选器**若要查看匹配的错误的列表。</span><span class="sxs-lookup"><span data-stu-id="8e27e-117">Click **Apply Filters** to see the list of matching faults.</span></span> <span data-ttu-id="8e27e-118">请注意，筛选非常大的容错数据库上可能需要几秒钟来显示结果。</span><span class="sxs-lookup"><span data-stu-id="8e27e-118">Note that filtering on very large fault databases may take a few seconds to display results.</span></span>  
  
4.  <span data-ttu-id="8e27e-119">若要在页中显示更多或更少的行，选择相应的值**记录每个页面**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e27e-119">To display more or fewer rows in the page, select the appropriate value in the **Records Per Page** drop-down list.</span></span>  
  
5.  <span data-ttu-id="8e27e-120">若要排序的错误消息的列表，请单击列标题。</span><span class="sxs-lookup"><span data-stu-id="8e27e-120">To sort the list of fault messages, click a column heading.</span></span> <span data-ttu-id="8e27e-121">若要以相反顺序的行进行排序，请单击同一个列标题。</span><span class="sxs-lookup"><span data-stu-id="8e27e-121">To sort the rows in reverse order, click the same column heading again.</span></span>  
  
6.  <span data-ttu-id="8e27e-122">单击**导出到 Excel**若要下载可以在 Microsoft Excel 中查看的格式的错误消息的完整列表。</span><span class="sxs-lookup"><span data-stu-id="8e27e-122">Click **Export To Excel** to download the complete list of fault messages in a format that you can view in Microsoft Excel.</span></span>