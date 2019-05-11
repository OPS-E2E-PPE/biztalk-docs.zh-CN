---
title: 订阅警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfa46b63-c1c7-47cd-86b0-557fd322dc8f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e402d37ba9e680b3cb41db6c935990a47569b484
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268993"
---
# <a name="subscribing-to-alerts"></a><span data-ttu-id="4f07b-102">订阅警报</span><span class="sxs-lookup"><span data-stu-id="4f07b-102">Subscribing to Alerts</span></span>
### <a name="to-subscribe-to-an-alert"></a><span data-ttu-id="4f07b-103">若要订阅警报</span><span class="sxs-lookup"><span data-stu-id="4f07b-103">To subscribe to an alert</span></span>  
  
1.  <span data-ttu-id="4f07b-104">打开[门户警报页](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，以及对这些警报在当前订阅。</span><span class="sxs-lookup"><span data-stu-id="4f07b-104">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="4f07b-105">在操作列中，单击**AddSubscriber**现有警报的图标。</span><span class="sxs-lookup"><span data-stu-id="4f07b-105">In the Action column, click the **AddSubscriber** icon for an existing alert.</span></span> <span data-ttu-id="4f07b-106">这将打开[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="4f07b-106">This opens the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="4f07b-107">在门户将警报通知发送到与用于访问门户的帐户关联的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4f07b-107">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="4f07b-108">如果你想要使用不同的电子邮件地址，选中的复选框旁边**自定义电子邮件**文本框中，并键入在文本框中的首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4f07b-108">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="4f07b-109">选择中的复选框**计划**部分中如果你想要指定在段时在门户应将警报发送到你，，然后指定中时间段的开始和结束时间**开始时间**并**EndTime**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4f07b-109">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="4f07b-110">如果当你将不能接收和操作警报一段，则输入中的开始和结束日期**买卖期**框。</span><span class="sxs-lookup"><span data-stu-id="4f07b-110">If there is a period when you will be unable to receive and act upon alerts, type the start and end dates in the **Black-out Period** boxes.</span></span>  
  
6.  <span data-ttu-id="4f07b-111">选择**间隔**中**分钟**和多个实例的同一个警报发生时发送只有一个的比较引发的警报在门户将过程。</span><span class="sxs-lookup"><span data-stu-id="4f07b-111">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="4f07b-112">这可以防止出现一次快速故障创建大量的相同警报消息。</span><span class="sxs-lookup"><span data-stu-id="4f07b-112">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="4f07b-113">单击**保存**按钮以创建新的订阅。</span><span class="sxs-lookup"><span data-stu-id="4f07b-113">Click the **Save** button to create the new subscription.</span></span>  
  
### <a name="to-edit-an-existing-alert-subscription"></a><span data-ttu-id="4f07b-114">若要编辑现有的警报订阅</span><span class="sxs-lookup"><span data-stu-id="4f07b-114">To edit an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="4f07b-115">打开[门户警报页](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，以及对这些警报在当前订阅。</span><span class="sxs-lookup"><span data-stu-id="4f07b-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="4f07b-116">单击**编辑**想要修改的列表中的订阅旁边的链接**我的订阅**部分中的页后，可以打开[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="4f07b-116">Click the **Edit** link next to the subscription you want to modify in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="4f07b-117">在门户将警报通知发送到与用于访问门户的帐户关联的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4f07b-117">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="4f07b-118">如果你想要使用不同的电子邮件地址，选中的复选框旁边**自定义电子邮件**文本框中，并键入在文本框中的首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4f07b-118">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="4f07b-119">选择中的复选框**计划**部分中如果你想要指定在段时在门户应将警报发送到你，，然后指定中时间段的开始和结束时间**开始时间**并**EndTime**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4f07b-119">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="4f07b-120">键入的开始和结束日期**买卖期**是否存在时将不能接收和操作警报一段。</span><span class="sxs-lookup"><span data-stu-id="4f07b-120">Type the start and end dates for a **Black-out Period** if there is a period when you will be unable to receive and act upon alerts.</span></span>  
  
6.  <span data-ttu-id="4f07b-121">选择**间隔**中**分钟**期间的门户将比较引发的警报和多个实例的同一个警报发生时发送只有一个。</span><span class="sxs-lookup"><span data-stu-id="4f07b-121">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and will send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="4f07b-122">这可以防止出现一次快速故障创建大量的相同警报消息。</span><span class="sxs-lookup"><span data-stu-id="4f07b-122">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="4f07b-123">单击**保存**按钮可更新订阅。</span><span class="sxs-lookup"><span data-stu-id="4f07b-123">Click the **Save** button to update the subscription.</span></span>  
  
### <a name="to-delete-an-existing-alert-subscription"></a><span data-ttu-id="4f07b-124">若要删除现有的警报订阅</span><span class="sxs-lookup"><span data-stu-id="4f07b-124">To delete an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="4f07b-125">打开[门户警报页](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，以及对这些警报在当前订阅。</span><span class="sxs-lookup"><span data-stu-id="4f07b-125">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="4f07b-126">单击**删除**想要删除的列表中的订阅旁边的链接**我的订阅**页部分。</span><span class="sxs-lookup"><span data-stu-id="4f07b-126">Click the **Delete** link next to the subscription you want to delete in the list in the **My Subscriptions** section of the page.</span></span>