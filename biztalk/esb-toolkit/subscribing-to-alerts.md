---
title: "警报订阅 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfa46b63-c1c7-47cd-86b0-557fd322dc8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02ef5f136002f5afca6e062362b92d25a20baa99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="subscribing-to-alerts"></a><span data-ttu-id="8d44f-102">订阅警报</span><span class="sxs-lookup"><span data-stu-id="8d44f-102">Subscribing to Alerts</span></span>
### <a name="to-subscribe-to-an-alert"></a><span data-ttu-id="8d44f-103">若要订阅警报</span><span class="sxs-lookup"><span data-stu-id="8d44f-103">To subscribe to an alert</span></span>  
  
1.  <span data-ttu-id="8d44f-104">打开[门户警报页面](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，并且你对这些警报的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="8d44f-104">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="8d44f-105">在操作列中，单击**AddSubscriber**为现有的警报图标。</span><span class="sxs-lookup"><span data-stu-id="8d44f-105">In the Action column, click the **AddSubscriber** icon for an existing alert.</span></span> <span data-ttu-id="8d44f-106">这将打开[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="8d44f-106">This opens the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="8d44f-107">门户将警报通知发送到与用于访问门户的帐户关联的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d44f-107">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="8d44f-108">如果你想要使用不同的电子邮件地址，选中的复选框旁边**自定义电子邮件**文本框中，然后键入在文本框中的首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d44f-108">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="8d44f-109">选择中的复选框**计划**部分如果你想要指定当门户应将警报发送到你，，然后指定期的开始和结束时间的段**开始时间**和**EndTime**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8d44f-109">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="8d44f-110">如果有一段时间，当你将无法接收和处理警报时，输入中的开始和结束日期**黑色超时期限**框。</span><span class="sxs-lookup"><span data-stu-id="8d44f-110">If there is a period when you will be unable to receive and act upon alerts, type the start and end dates in the **Black-out Period** boxes.</span></span>  
  
6.  <span data-ttu-id="8d44f-111">选择**间隔**中**分钟**和相同警报的多个实例发生时发送只有一个的比较引发警报门户将过程。</span><span class="sxs-lookup"><span data-stu-id="8d44f-111">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="8d44f-112">这可以防止创建大量的相同警报消息快速出现错误。</span><span class="sxs-lookup"><span data-stu-id="8d44f-112">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="8d44f-113">单击**保存**按钮以创建新的订阅。</span><span class="sxs-lookup"><span data-stu-id="8d44f-113">Click the **Save** button to create the new subscription.</span></span>  
  
### <a name="to-edit-an-existing-alert-subscription"></a><span data-ttu-id="8d44f-114">若要编辑现有的警报订阅</span><span class="sxs-lookup"><span data-stu-id="8d44f-114">To edit an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="8d44f-115">打开[门户警报页面](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，并且你对这些警报的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="8d44f-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="8d44f-116">单击**编辑**你想要修改的列表中的订阅旁边的链接**我的订阅**一部分页后，可以打开[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="8d44f-116">Click the **Edit** link next to the subscription you want to modify in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="8d44f-117">门户将警报通知发送到与用于访问门户的帐户关联的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d44f-117">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="8d44f-118">如果你想要使用不同的电子邮件地址，选中的复选框旁边**自定义电子邮件**文本框中，然后键入在文本框中的首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d44f-118">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="8d44f-119">选择中的复选框**计划**部分如果你想要指定当门户应将警报发送到你，，然后指定期的开始和结束时间的段**开始时间**和**EndTime**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8d44f-119">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="8d44f-120">键入的开始和结束日期**黑色超时期限**是否存在一段时间，当你将无法接收和对警报进行操作。</span><span class="sxs-lookup"><span data-stu-id="8d44f-120">Type the start and end dates for a **Black-out Period** if there is a period when you will be unable to receive and act upon alerts.</span></span>  
  
6.  <span data-ttu-id="8d44f-121">选择**间隔**中**分钟**在该门户将比较引发的警报和相同警报的多个实例出现时将发送只有一个期间。</span><span class="sxs-lookup"><span data-stu-id="8d44f-121">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and will send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="8d44f-122">这可以防止创建大量的相同警报消息快速出现错误。</span><span class="sxs-lookup"><span data-stu-id="8d44f-122">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="8d44f-123">单击**保存**按钮可更新订阅。</span><span class="sxs-lookup"><span data-stu-id="8d44f-123">Click the **Save** button to update the subscription.</span></span>  
  
### <a name="to-delete-an-existing-alert-subscription"></a><span data-ttu-id="8d44f-124">若要删除现有的警报订阅</span><span class="sxs-lookup"><span data-stu-id="8d44f-124">To delete an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="8d44f-125">打开[门户警报页面](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，并且你对这些警报的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="8d44f-125">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="8d44f-126">单击**删除**你想要删除的列表中的订阅旁边的链接**我的订阅**页的部分。</span><span class="sxs-lookup"><span data-stu-id="8d44f-126">Click the **Delete** link next to the subscription you want to delete in the list in the **My Subscriptions** section of the page.</span></span>