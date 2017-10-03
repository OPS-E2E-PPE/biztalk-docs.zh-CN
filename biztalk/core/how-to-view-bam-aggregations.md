---
title: "如何查看 BAM 聚合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], viewing aggregations
- viewing, aggregations [BAM]
ms.assetid: aa697f16-ac47-46f9-98a5-a951961d0413
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b1bc81ac4cc85cdb2f9d02903b9c9ba0f3ef7c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-bam-aggregations"></a><span data-ttu-id="b4cef-102">如何查看 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="b4cef-102">How to View BAM Aggregations</span></span>
<span data-ttu-id="b4cef-103">BAM 聚合是由业务分析员在 Excel 中使用 Excel 外接程序定义的。</span><span class="sxs-lookup"><span data-stu-id="b4cef-103">BAM aggregations are defined by the business analyst in Excel using the Excel add-in.</span></span>  
  
### <a name="to-view-your-bam-aggregations"></a><span data-ttu-id="b4cef-104">查看您的 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="b4cef-104">To view your BAM aggregations</span></span>  
  
1.  <span data-ttu-id="b4cef-105">在运行的计算机上[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; 单击**启动**，指向**所有程序**，右键单击**Internet Explorer**，然后单击**以运行管理员**。</span><span class="sxs-lookup"><span data-stu-id="b4cef-105">On Computers running [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span> <span data-ttu-id="b4cef-106">在**用户帐户控制**对话框中，单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="b4cef-106">In the **User Account Control** dialog box, click **Continue**.</span></span> <span data-ttu-id="b4cef-107">在 Internet Explorer 地址栏中，键入`http://<server>/BAM/`，其中*\<服务器 >*是运行 BAM 门户的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="b4cef-107">In the Internet Explorer address bar, type `http://<server>/BAM/`, where *\<server>* is the name of the computer that is running the BAM portal.</span></span>  
  
     <span data-ttu-id="b4cef-108">--或者--</span><span class="sxs-lookup"><span data-stu-id="b4cef-108">-- or --</span></span>  
  
     <span data-ttu-id="b4cef-109">单击**启动**，单击**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。</span><span class="sxs-lookup"><span data-stu-id="b4cef-109">Click **Start**, click **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2.  <span data-ttu-id="b4cef-110">从**MyViews**导航窗格中，单击一个视图，以展开的视图以显示任务列表。</span><span class="sxs-lookup"><span data-stu-id="b4cef-110">From the **MyViews** navigation pane, click a view to expand the view to show the task list.</span></span>  
  
3.  <span data-ttu-id="b4cef-111">单击**聚合**任务以展开的列表定义聚合。</span><span class="sxs-lookup"><span data-stu-id="b4cef-111">Click the **Aggregations** task to expand the list of defined aggregations.</span></span>  
  
4.  <span data-ttu-id="b4cef-112">单击列出加载 BAM 门户内容的帧中的聚合的聚合。</span><span class="sxs-lookup"><span data-stu-id="b4cef-112">Click an aggregation listed to load the aggregation in the content frame of the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4cef-113">如果没有显示任何视图，则是因为视图尚未创建（此任务通常由业务分析员执行），或尚未向用户授予权限（此任务通常由管理员执行）。</span><span class="sxs-lookup"><span data-stu-id="b4cef-113">If there are no views shown, then either views have not been created, a task typically performed by a business analyst, or permissions have not been granted to the user, a task typically performed by an administrator.</span></span>  
  
 <span data-ttu-id="b4cef-114">有关如何使用实时数据工作簿的详细信息，请参阅[查看实时 BAM 数据](../core/viewing-live-bam-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b4cef-114">For more information about what you can do with the live data workbooks, see [Viewing Live BAM Data](../core/viewing-live-bam-data.md).</span></span>  
  
 <span data-ttu-id="b4cef-115">下图显示了预先计算的 BAM 聚合。</span><span class="sxs-lookup"><span data-stu-id="b4cef-115">The following figure shows pre-calculated BAM aggregations.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="b4cef-116">预先计算的 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="b4cef-116">Pre-calculated BAM aggregations</span></span>