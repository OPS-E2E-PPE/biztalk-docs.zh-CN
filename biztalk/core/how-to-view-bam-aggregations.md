---
title: 如何查看 BAM 聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], viewing aggregations
- viewing, aggregations [BAM]
ms.assetid: aa697f16-ac47-46f9-98a5-a951961d0413
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e25825fbcb755179ce833a3c542e9554b99ac923
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383170"
---
# <a name="how-to-view-bam-aggregations"></a><span data-ttu-id="0fd34-102">如何查看 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="0fd34-102">How to View BAM Aggregations</span></span>
<span data-ttu-id="0fd34-103">BAM 聚合由业务分析员在 Excel 中使用的 Excel 外接程序定义。</span><span class="sxs-lookup"><span data-stu-id="0fd34-103">BAM aggregations are defined by the business analyst in Excel using the Excel add-in.</span></span>  
  
### <a name="to-view-your-bam-aggregations"></a><span data-ttu-id="0fd34-104">若要查看您的 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="0fd34-104">To view your BAM aggregations</span></span>  
  
1. <span data-ttu-id="0fd34-105">运行的计算机上[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; 单击**启动**，依次指向**所有程序**，右键单击**Internet Explorer**，然后单击**以运行管理员**。</span><span class="sxs-lookup"><span data-stu-id="0fd34-105">On Computers running [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span> <span data-ttu-id="0fd34-106">在中**用户帐户控制**对话框中，单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="0fd34-106">In the **User Account Control** dialog box, click **Continue**.</span></span> <span data-ttu-id="0fd34-107">在 Internet Explorer 地址栏中，键入`http://<server>/BAM/`，其中*\<服务器 >* 是正在运行 BAM 门户的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="0fd34-107">In the Internet Explorer address bar, type `http://<server>/BAM/`, where *\<server>* is the name of the computer that is running the BAM portal.</span></span>  
  
    <span data-ttu-id="0fd34-108">--或者--</span><span class="sxs-lookup"><span data-stu-id="0fd34-108">-- or --</span></span>  
  
    <span data-ttu-id="0fd34-109">单击**启动**，单击**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。</span><span class="sxs-lookup"><span data-stu-id="0fd34-109">Click **Start**, click **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="0fd34-110">从**我的视图**导航窗格中，单击某个视图展开视图以显示任务列表。</span><span class="sxs-lookup"><span data-stu-id="0fd34-110">From the **MyViews** navigation pane, click a view to expand the view to show the task list.</span></span>  
  
3. <span data-ttu-id="0fd34-111">单击**聚合**任务以展开的列表定义的聚合。</span><span class="sxs-lookup"><span data-stu-id="0fd34-111">Click the **Aggregations** task to expand the list of defined aggregations.</span></span>  
  
4. <span data-ttu-id="0fd34-112">单击列出要加载的 BAM 门户内容框架中聚合的聚合。</span><span class="sxs-lookup"><span data-stu-id="0fd34-112">Click an aggregation listed to load the aggregation in the content frame of the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fd34-113">如果不没有显示任何视图，然后是因为视图尚未创建，通常由业务分析员执行的任务，或已授予权限给用户，通常由管理员执行的任务。</span><span class="sxs-lookup"><span data-stu-id="0fd34-113">If there are no views shown, then either views have not been created, a task typically performed by a business analyst, or permissions have not been granted to the user, a task typically performed by an administrator.</span></span>  
  
 <span data-ttu-id="0fd34-114">使用实时数据工作簿可以执行的操作的详细信息，请参阅[查看实时 BAM 数据](../core/viewing-live-bam-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0fd34-114">For more information about what you can do with the live data workbooks, see [Viewing Live BAM Data](../core/viewing-live-bam-data.md).</span></span>  
  
 <span data-ttu-id="0fd34-115">下图显示了预先计算的 BAM 聚合。</span><span class="sxs-lookup"><span data-stu-id="0fd34-115">The following figure shows pre-calculated BAM aggregations.</span></span>  
  
 <span data-ttu-id="0fd34-116">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="0fd34-116">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
<span data-ttu-id="0fd34-117">预先计算的 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="0fd34-117">Pre-calculated BAM aggregations</span></span>