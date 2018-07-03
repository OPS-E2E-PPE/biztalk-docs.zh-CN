---
title: 将警报的订阅添加和编辑订阅页面 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b843bde8905d8b6803dda56a6370f70c934a610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013446"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a><span data-ttu-id="02253-102">将警报的订阅添加和编辑订阅页面</span><span class="sxs-lookup"><span data-stu-id="02253-102">Add Alert Subscription and Edit Subscription Pages</span></span>
<span data-ttu-id="02253-103">添加警报订阅和编辑订阅页的类似。</span><span class="sxs-lookup"><span data-stu-id="02253-103">The Add Alert Subscription and Edit Subscription pages are similar.</span></span> <span data-ttu-id="02253-104">它们不同，编辑订阅页显示的订阅者 ID （Microsoft Windows 的当前门户用户帐户），并且具有一组不同的按钮。</span><span class="sxs-lookup"><span data-stu-id="02253-104">They differ in that the Edit Subscription page shows the subscriber ID (the Microsoft Windows account of the current portal user), and has a different set of buttons.</span></span> <span data-ttu-id="02253-105">图 1 显示了添加警报订阅和编辑订阅页。</span><span class="sxs-lookup"><span data-stu-id="02253-105">Figure 1 shows the Add Alert Subscription and Edit Subscription pages.</span></span>  

 <span data-ttu-id="02253-106">![添加警报编辑订阅](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span><span class="sxs-lookup"><span data-stu-id="02253-106">![Add Alert Edit Subscription](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span></span>  

 <span data-ttu-id="02253-107">**图 1**</span><span class="sxs-lookup"><span data-stu-id="02253-107">**Figure 1**</span></span>  

 <span data-ttu-id="02253-108">**ESB 管理门户添加警报订阅和编辑订阅页**</span><span class="sxs-lookup"><span data-stu-id="02253-108">**The ESB Management Portal Add Alert Subscription and Edit Subscription pages**</span></span>  

 <span data-ttu-id="02253-109">添加警报订阅和编辑订阅页面允许您指定并修改以下：</span><span class="sxs-lookup"><span data-stu-id="02253-109">The Add Alert Subscription and Edit Subscription pages allow you to specify and modify the following:</span></span>  

- <span data-ttu-id="02253-110">要使用的订阅 （而不是 Microsoft Windows 帐户电子邮件地址） 的自定义电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="02253-110">A custom e-mail address to use for the subscription (instead of your Microsoft Windows account e-mail address)</span></span>  

- <span data-ttu-id="02253-111">如果将接受警报通知的时间段</span><span class="sxs-lookup"><span data-stu-id="02253-111">The time period when you will accept alert notifications</span></span>  

- <span data-ttu-id="02253-112">事件，例如休假"买卖"期</span><span class="sxs-lookup"><span data-stu-id="02253-112">A "black-out" period for events such as vacations</span></span>  

- <span data-ttu-id="02253-113">通过该门户不会发送重复警报间隔</span><span class="sxs-lookup"><span data-stu-id="02253-113">The interval over which the portal will not send duplicate alerts</span></span>  

  <span data-ttu-id="02253-114">您可以执行以下操作在添加警报订阅和编辑订阅页上：</span><span class="sxs-lookup"><span data-stu-id="02253-114">You can do the following on the Add Alert Subscription and Edit Subscription pages:</span></span>  

- <span data-ttu-id="02253-115">选中复选框旁边**自定义电子邮件**文本框如果想要使用标准 Windows 帐户在电子邮件地址，不同的订阅的电子邮件地址，然后在文本框中键入的首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="02253-115">Select the check box next to the **Custom Email** text box if you want to use an e-mail address for the subscription that is different to your standard Windows account e-mail address, and then type the preferred e-mail address in the text box.</span></span>  

- <span data-ttu-id="02253-116">选择顶部的复选框**计划**部分中如果你想要指定在段时在门户应将警报发送到你，，然后指定中时间段的开始和结束时间**开始时间**和**结束时间**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="02253-116">Select the check box at the top of the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **End Time** drop-down lists.</span></span> <span data-ttu-id="02253-117">超出此时间段发生的警报排队，并在指定时段内传送。</span><span class="sxs-lookup"><span data-stu-id="02253-117">Alerts occurring outside this period are queued and delivered during the specified period.</span></span>  

- <span data-ttu-id="02253-118">键入开始日期和结束日期**买卖期**是否存在时将不能接收和处理警报在一段。</span><span class="sxs-lookup"><span data-stu-id="02253-118">Type the start date and end date for a **Black-out Period** if there is a period when you will be unable to receive and act on alerts.</span></span> <span data-ttu-id="02253-119">使用两个日期，格式为 mm/dd/yyyy。</span><span class="sxs-lookup"><span data-stu-id="02253-119">Use the format mm/dd/yyyy for the two dates.</span></span>  

- <span data-ttu-id="02253-120">选择**间隔**中**分钟**和多个实例的同一个警报发生时发送只有一个的比较引发的警报在门户将过程。</span><span class="sxs-lookup"><span data-stu-id="02253-120">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="02253-121">这可以防止出现一次快速故障创建大量的相同警报消息。</span><span class="sxs-lookup"><span data-stu-id="02253-121">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  

- <span data-ttu-id="02253-122">单击**保存**按钮以创建或更新订阅。</span><span class="sxs-lookup"><span data-stu-id="02253-122">Click the **Save** button to create or update the subscription.</span></span>  

- <span data-ttu-id="02253-123">单击**删除**按钮 （仅适用于编辑订阅页） 以删除所选的订阅。</span><span class="sxs-lookup"><span data-stu-id="02253-123">Click the **Delete** button (available only on the Edit Subscription page) to delete the selected subscription.</span></span>  

- <span data-ttu-id="02253-124">单击**取消**按钮以返回到[警报查看器页](../esb-toolkit/alert-viewer-page.md)无需创建或修改订阅。</span><span class="sxs-lookup"><span data-stu-id="02253-124">Click the **Cancel** button to go back to the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md) without creating or modifying the subscription.</span></span>
