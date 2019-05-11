---
title: 如何定义业务活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5702d1530926bf4bd0c2ecdc97520f777be3701e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385367"
---
# <a name="how-to-define-a-business-activity"></a><span data-ttu-id="612cd-102">如何定义业务活动</span><span class="sxs-lookup"><span data-stu-id="612cd-102">How to Define a Business Activity</span></span>
<span data-ttu-id="612cd-103">若要指示您需要为报告收集的数据，必须定义 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="612cd-103">To indicate the data you need to collect for reports, you must define a BAM activity.</span></span> <span data-ttu-id="612cd-104">这包含一系列重要的里程碑和数据项您希望 BAM 跟踪。使用 BAM Excel 外接程序创建一个活动，如下面的过程中所示。</span><span class="sxs-lookup"><span data-stu-id="612cd-104">This contains a list of the important milestones and data items you want BAM to track. Use the BAM Excel add-in to create an activity as shown in the following procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612cd-105">活动部署后，可在活动执行的操作就会受到限制。</span><span class="sxs-lookup"><span data-stu-id="612cd-105">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="612cd-106">具体而言，除非你已准备好让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则您不能从活动中删除项目。</span><span class="sxs-lookup"><span data-stu-id="612cd-106">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="612cd-107">除非管理员进行备份，这可能导致查看中断和数据丢失的数据和还原。</span><span class="sxs-lookup"><span data-stu-id="612cd-107">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
### <a name="to-create-a-business-activity"></a><span data-ttu-id="612cd-108">若要创建业务活动</span><span class="sxs-lookup"><span data-stu-id="612cd-108">To create a business activity</span></span>  
  
1.  <span data-ttu-id="612cd-109">打开 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="612cd-109">Open Microsoft Excel.</span></span>  
  
2.  <span data-ttu-id="612cd-110">菜单在工具栏上，单击**BAM**菜单项，然后单击**BAM 活动**。</span><span class="sxs-lookup"><span data-stu-id="612cd-110">On the menu tool bar, click the **BAM** menu item, and click **BAM Activity**.</span></span>  
  
     <span data-ttu-id="612cd-111">**业务活动监视活动向导**出现。</span><span class="sxs-lookup"><span data-stu-id="612cd-111">The **Business Activity Monitoring Activity Wizard** appears.</span></span>  
  
3.  <span data-ttu-id="612cd-112">单击**新的活动**。</span><span class="sxs-lookup"><span data-stu-id="612cd-112">Click **New Activity**.</span></span>  
  
     <span data-ttu-id="612cd-113">**新的活动**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="612cd-113">The **New Activity** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="612cd-114">键入一个描述性名称的活动**活动名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="612cd-114">Type a descriptive name for the activity in the **Activity Name** text box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612cd-115">活动必须包含至少一个活动项。</span><span class="sxs-lookup"><span data-stu-id="612cd-115">An activity must contain at least one activity item.</span></span>  
  
#### <a name="to-create-a-new-item"></a><span data-ttu-id="612cd-116">若要创建新项</span><span class="sxs-lookup"><span data-stu-id="612cd-116">To create a new item</span></span>  
  
1. <span data-ttu-id="612cd-117">单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="612cd-117">Click **New Item**.</span></span>  
  
2. <span data-ttu-id="612cd-118">在中**新活动项**对话框中**新活动项**框中，键入活动项的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="612cd-118">In the **New Activity Item** dialog box, in the **New Activity Item** box, type a descriptive name for the activity item.</span></span>  
  
3. <span data-ttu-id="612cd-119">从**项类型**下拉列表菜单中，选择此项的类型。</span><span class="sxs-lookup"><span data-stu-id="612cd-119">From the **Item type** drop-down menu, select a type for this item.</span></span> <span data-ttu-id="612cd-120">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="612cd-120">Possible values include:</span></span>  
  
   |<span data-ttu-id="612cd-121">项类型</span><span class="sxs-lookup"><span data-stu-id="612cd-121">Item type</span></span>|<span data-ttu-id="612cd-122">Description</span><span class="sxs-lookup"><span data-stu-id="612cd-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="612cd-123">业务里程碑</span><span class="sxs-lookup"><span data-stu-id="612cd-123">Business Milestone</span></span>|<span data-ttu-id="612cd-124">日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="612cd-124">A date/time value.</span></span> <span data-ttu-id="612cd-125">例如，采购订单的批准日期。</span><span class="sxs-lookup"><span data-stu-id="612cd-125">For example, an approval date for a purchase order.</span></span>|  
   |<span data-ttu-id="612cd-126">业务数据 – Text</span><span class="sxs-lookup"><span data-stu-id="612cd-126">Business Data – Text</span></span>|<span data-ttu-id="612cd-127">包含任何字母数字字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="612cd-127">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="612cd-128">例如，发运到：城市、 省/市/自治区和邮政编码的代码。</span><span class="sxs-lookup"><span data-stu-id="612cd-128">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
   |<span data-ttu-id="612cd-129">业务数据 – Integer</span><span class="sxs-lookup"><span data-stu-id="612cd-129">Business Data – Integer</span></span>|<span data-ttu-id="612cd-130">一个整数值。</span><span class="sxs-lookup"><span data-stu-id="612cd-130">A whole number value.</span></span> <span data-ttu-id="612cd-131">例如，购买的总数。</span><span class="sxs-lookup"><span data-stu-id="612cd-131">For example, the total number of purchases.</span></span>|  
   |<span data-ttu-id="612cd-132">业务数据 – Decimal</span><span class="sxs-lookup"><span data-stu-id="612cd-132">Business Data – Decimal</span></span>|<span data-ttu-id="612cd-133">一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="612cd-133">A decimal value.</span></span> <span data-ttu-id="612cd-134">有关示例的美元总金额的采购订单。</span><span class="sxs-lookup"><span data-stu-id="612cd-134">For example the total dollar amount of the PO.</span></span>|  
  
    <span data-ttu-id="612cd-135">如果您选择的项类型"业务数据 – Text"，则必须对字符串输入的最大字符数**的最大长度**框。</span><span class="sxs-lookup"><span data-stu-id="612cd-135">If you select the item type "Business Data – Text", you must enter the maximum number of characters for the string in the **Maximum length** box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="612cd-136">有关创建这些项的详细信息，请参阅"合作伙伴管理和业务活动监视"Microsoft BizTalk Server 教程中。</span><span class="sxs-lookup"><span data-stu-id="612cd-136">For more information about creating these items, see "Partner Management and Business Activity Monitoring" in the Microsoft BizTalk Server tutorial.</span></span>  
  
4. <span data-ttu-id="612cd-137">重复步骤 1 至 3，将添加到此活动所需的所有项。</span><span class="sxs-lookup"><span data-stu-id="612cd-137">Repeat steps 1 through 3 to add as many items as needed to this activity.</span></span>  
  
5. <span data-ttu-id="612cd-138">完成业务活动监视活动向导后，业务活动监视视图向导将自动启动。</span><span class="sxs-lookup"><span data-stu-id="612cd-138">After you complete the Business Activity Monitoring Activity Wizard, the Business Activity Monitoring View Wizard starts automatically.</span></span>  
  
   <span data-ttu-id="612cd-139">有关使用此向导的详细信息，请参阅[定义 BAM 视图](../core/defining-a-bam-view.md)。</span><span class="sxs-lookup"><span data-stu-id="612cd-139">For more information about using this wizard, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612cd-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="612cd-140">See Also</span></span>  
 <span data-ttu-id="612cd-141">[定义 BAM 视图](../core/defining-a-bam-view.md) </span><span class="sxs-lookup"><span data-stu-id="612cd-141">[Defining a BAM View](../core/defining-a-bam-view.md) </span></span>  
 [<span data-ttu-id="612cd-142">在 Excel 中定义业务活动和视图</span><span class="sxs-lookup"><span data-stu-id="612cd-142">Defining Business Activities and Views in Excel</span></span>](../core/defining-business-activities-and-views-in-excel.md)