---
title: "创建、 查看和删除错误消息警报 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55894eca1baa8ca6616c67f623a87e8015a2f32f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a><span data-ttu-id="9d2dd-102">创建、 查看和删除错误消息警报</span><span class="sxs-lookup"><span data-stu-id="9d2dd-102">Creating, Viewing, and Deleting Fault Message Alerts</span></span>
<span data-ttu-id="9d2dd-103">ESB 管理门户可以在门户中，错误消息到达时生成警报基于警报中指定条件的消息中的值的比较。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-103">The ESB Management Portal can generate alerts when fault messages arrive at the portal, based on a comparison of values in the message with criteria specified for the alert.</span></span> <span data-ttu-id="9d2dd-104">门户还可以维护一份通知链接到单个警报和用户，并后它会主动发出警报，它会通知这些用户。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-104">The portal can also maintain a list of notifications linked to individual alerts and users, and it will notify these users when it proactively raises alerts.</span></span>  
  
### <a name="to-create-and-configure-a-new-alert"></a><span data-ttu-id="9d2dd-105">若要创建和配置新的警报</span><span class="sxs-lookup"><span data-stu-id="9d2dd-105">To create and configure a new alert</span></span>  
  
1.  <span data-ttu-id="9d2dd-106">打开[门户警报页面](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，并且你对这些警报的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-106">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="9d2dd-107">单击**创建警报**链接以打开[添加警报页](../esb-toolkit/add-alert-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-107">Click the **Create Alert** link to open the [Add Alert Page](../esb-toolkit/add-alert-page.md).</span></span>  
  
3.  <span data-ttu-id="9d2dd-108">在**输入警报名称**文本框中，键入新警报的名称。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-108">In the **Enter Alert Name** text box, type a name for the new alert.</span></span>  
  
4.  <span data-ttu-id="9d2dd-109">在**条件**部分的添加警报页，选择一个字段 (如**应用程序**，**错误类型**，或**故障严重性**) 中**条件**下拉列表; 选择一种比较类型 (如 +、 =、 ！ =、 > =、 < =、 或**如**) 中**运算符**下拉列表; 并键入或选择从第三个的列表或文本框中的值 (名为**值**)。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-109">In the **Conditions** section of the Add Alert page, select a field (such as **Application**, **Error Type**, or **Fault Severity**) in the **Criteria** drop-down list; select a comparison type (such as +, =, !=, >=, <=, or **like**) in the **Operator** drop-down list; and type or select a value from the third list or text box (named **Value**).</span></span> <span data-ttu-id="9d2dd-110">当你选择**条件**值，页面将发生变化以显示一个文本框或匹配的值的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-110">As you select a **Criteria** value, the page changes to display either a text box or a drop-down list for the matching value.</span></span> <span data-ttu-id="9d2dd-111">所有条件将都结合使用**AND**运算符。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-111">All conditions are combined using the **AND** operator.</span></span>  
  
5.  <span data-ttu-id="9d2dd-112">单击**添加**要添加到列表中，这种情况的链接，然后重复上述步骤以在需要时添加更多条件。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-112">Click the **Add** link to add this condition to the list, and then repeat the previous step to add more conditions if required.</span></span>  
  
6.  <span data-ttu-id="9d2dd-113">单击**保存**按钮以创建新的警报具有指定的名称和条件。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-113">Click the **Save** button to create a new alert with the specified name and conditions.</span></span>  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a><span data-ttu-id="9d2dd-114">若要查看现有警报详细信息，或删除现有警报</span><span class="sxs-lookup"><span data-stu-id="9d2dd-114">To view details of an existing alert or delete an existing alert</span></span>  
  
1.  <span data-ttu-id="9d2dd-115">打开[门户警报页](../esb-toolkit/portal-alerts-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span>  
  
2.  <span data-ttu-id="9d2dd-116">若要删除警报，请单击**删除警报**现有警报的操作列中的图标。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-116">To delete an alert, click the **Delete Alert** icon in the Action column of an existing alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d2dd-117">非管理用户可以删除警报他们是所有者，并为其当前有任何订户。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-117">Non-administrative users can delete only alerts for which they are an owner, and for which there are currently no subscribers.</span></span> <span data-ttu-id="9d2dd-118">你必须登录到门户以管理员身份中删除其他警报。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-118">You must log on to the portal as an administrator to delete other alerts.</span></span>  
  
3.  <span data-ttu-id="9d2dd-119">若要查看的警报的详细信息，请单击**视图**现有警报的操作列中的图标。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-119">To view details of an alert, click the **View** icon in the Action column of an existing alert.</span></span> <span data-ttu-id="9d2dd-120">这将打开警报查看器页。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-120">This opens the Alert Viewer page.</span></span>  
  
4.  <span data-ttu-id="9d2dd-121">单击**导出到 Excel**下载可以在 Microsoft Excel 中查看的格式中的警报的完整列表。</span><span class="sxs-lookup"><span data-stu-id="9d2dd-121">Click **Export To Excel** to download the complete list of alerts in a format that you can view in Microsoft Excel.</span></span>