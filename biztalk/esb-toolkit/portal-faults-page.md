---
title: 门户错误页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b11e3492-da1a-43f3-acf8-3775b5cbc2c5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 294ba24516cccbf6c15ada26d28f169a6eb45c98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294605"
---
# <a name="portal-faults-page"></a><span data-ttu-id="16626-102">门户错误页</span><span class="sxs-lookup"><span data-stu-id="16626-102">Portal Faults Page</span></span>
<span data-ttu-id="16626-103">图 1 显示的错误页。</span><span class="sxs-lookup"><span data-stu-id="16626-103">Figure 1 shows the Faults page.</span></span> <span data-ttu-id="16626-104">此页显示的主要属性的每个错误，并且它提供排序和筛选功能，以支持的条件，例如错误类型和时间范围内的错误的详细的分析。</span><span class="sxs-lookup"><span data-stu-id="16626-104">This page displays the main properties of each fault, and it provides sorting and filtering capabilities that support detailed analysis of faults over a range of criteria, such as error type and time.</span></span> <span data-ttu-id="16626-105">每个错误的链接，可在错误消息查看器中查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="16626-105">A link for each fault allows you to view more details in the Fault Message Viewer.</span></span>  
  
 <span data-ttu-id="16626-106">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span><span class="sxs-lookup"><span data-stu-id="16626-106">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span></span>  
  
 <span data-ttu-id="16626-107">**图 1**</span><span class="sxs-lookup"><span data-stu-id="16626-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="16626-108">**ESB 管理门户的错误页上**</span><span class="sxs-lookup"><span data-stu-id="16626-108">**The Faults page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="16626-109">以下列表说明如何使用 ESB 管理门户错误页的功能：</span><span class="sxs-lookup"><span data-stu-id="16626-109">The following list explains how you can use the features of the ESB Management Portal Faults page:</span></span>  
  
-   <span data-ttu-id="16626-110">若要筛选的页中显示的错误的列表，请使用下拉列表和列表上方的错误的文本框。</span><span class="sxs-lookup"><span data-stu-id="16626-110">To filter the list of faults displayed in the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="16626-111">你可以筛选中通过以下方式显示的行：</span><span class="sxs-lookup"><span data-stu-id="16626-111">You can filter the rows displayed in the following ways:</span></span>  
  
    -   <span data-ttu-id="16626-112">选择已安装的 BizTalk 应用程序中的任一**应用程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="16626-112">Select any one of the installed BizTalk applications in the **Application** drop-down list.</span></span>  
  
    -   <span data-ttu-id="16626-113">指定在其中通过选择将出现故障的时间段**小时、 天、 周、 月、 季度、 每年，** 或**所有**中**检索中最后一个记录**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="16626-113">Specify the period within which the fault occurred by selecting **hour, day, week, month, quarter, year,** or **all** in the **Retrieve records within last** drop-down list.</span></span>  
  
    -   <span data-ttu-id="16626-114">指定你想要在页面上显示的行数**记录每个页**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="16626-114">Specify how many rows you want to display on the page in the **Records Per Page** drop-down list.</span></span>  
  
    -   <span data-ttu-id="16626-115">键入的错误代码数字**错误代码**文本框。</span><span class="sxs-lookup"><span data-stu-id="16626-115">Type a fault code number in the **Fault Code** text box.</span></span>  
  
    -   <span data-ttu-id="16626-116">键入全部或部分中的错误类别名称**错误类别**文本框。</span><span class="sxs-lookup"><span data-stu-id="16626-116">Type all or part of the fault category name in the **Fault Category** text box.</span></span>  
  
    -   <span data-ttu-id="16626-117">键入全部或部分中的错误类型文本**错误类型**文本框。</span><span class="sxs-lookup"><span data-stu-id="16626-117">Type all or part of the error type text in the **Error Type** text box.</span></span>  
  
    -   <span data-ttu-id="16626-118">键入的最小值和/或最大错误严重级别的值 (如**警告、 错误、 严重，** 或**严重**) 中**Min 故障严重性**和**最大错误严重性**文本框。</span><span class="sxs-lookup"><span data-stu-id="16626-118">Type a value for the minimum and/or maximum fault severity (such as **Warning, Error, Severe,** or **Critical**) in the **Min Fault Severity** and **Max Fault Severity** text boxes.</span></span>  
  
-   <span data-ttu-id="16626-119">为一个或多个这些控件指定的值后，单击**应用筛选器**按钮以应用所有指定的条件。</span><span class="sxs-lookup"><span data-stu-id="16626-119">After you specify the values for one or more of these controls, click the **Apply Filters** button to apply all the specified criteria.</span></span>  
  
-   <span data-ttu-id="16626-120">单击列标题以显示该列内容，顺序的错误消息行，然后再次单击以按相反的顺序显示的列表。</span><span class="sxs-lookup"><span data-stu-id="16626-120">Click a column heading to display the fault message rows in the order of that column contents, and then click again to display the list in reverse order.</span></span>  
  
-   <span data-ttu-id="16626-121">若要显示在列表中，显示的错误的详细信息，也可以编辑和重新提交它包含的消息，单击任意位置中打开该错误的行中[门户错误消息查看器](../esb-toolkit/portal-fault-message-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="16626-121">To display more details of a fault shown in the list, or to edit and resubmit the message it contains, click anywhere in the row for that fault to open it in the [Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md).</span></span>