---
title: 警报订阅中添加和编辑订阅页面 |Microsoft 文档
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
ms.openlocfilehash: 49bed9959b51439f21d625795a69804fd41d77ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290037"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a><span data-ttu-id="a52b4-102">警报订阅中添加和编辑订阅页面</span><span class="sxs-lookup"><span data-stu-id="a52b4-102">Add Alert Subscription and Edit Subscription Pages</span></span>
<span data-ttu-id="a52b4-103">添加警报订阅和编辑订阅页很相似。</span><span class="sxs-lookup"><span data-stu-id="a52b4-103">The Add Alert Subscription and Edit Subscription pages are similar.</span></span> <span data-ttu-id="a52b4-104">它们不同，因为编辑订阅页显示订阅服务器 ID （Microsoft Windows 当前门户用户的帐户），并具有一组不同的按钮。</span><span class="sxs-lookup"><span data-stu-id="a52b4-104">They differ in that the Edit Subscription page shows the subscriber ID (the Microsoft Windows account of the current portal user), and has a different set of buttons.</span></span> <span data-ttu-id="a52b4-105">图 1 显示的添加警报订阅和编辑订阅页。</span><span class="sxs-lookup"><span data-stu-id="a52b4-105">Figure 1 shows the Add Alert Subscription and Edit Subscription pages.</span></span>  
  
 <span data-ttu-id="a52b4-106">![添加警报编辑订阅](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8 AddAlertEditSubscription")</span><span class="sxs-lookup"><span data-stu-id="a52b4-106">![Add Alert Edit Subscription](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span></span>  
  
 <span data-ttu-id="a52b4-107">**图 1**</span><span class="sxs-lookup"><span data-stu-id="a52b4-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="a52b4-108">**ESB 管理门户添加警报订阅和编辑订阅页**</span><span class="sxs-lookup"><span data-stu-id="a52b4-108">**The ESB Management Portal Add Alert Subscription and Edit Subscription pages**</span></span>  
  
 <span data-ttu-id="a52b4-109">添加警报订阅和编辑订阅页允许你指定并修改以下：</span><span class="sxs-lookup"><span data-stu-id="a52b4-109">The Add Alert Subscription and Edit Subscription pages allow you to specify and modify the following:</span></span>  
  
-   <span data-ttu-id="a52b4-110">要使用的订阅 （而不是你的 Microsoft Windows 帐户电子邮件地址） 的自定义电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="a52b4-110">A custom e-mail address to use for the subscription (instead of your Microsoft Windows account e-mail address)</span></span>  
  
-   <span data-ttu-id="a52b4-111">如果将接受警报通知的时间段</span><span class="sxs-lookup"><span data-stu-id="a52b4-111">The time period when you will accept alert notifications</span></span>  
  
-   <span data-ttu-id="a52b4-112">如假期的事件"买卖"期</span><span class="sxs-lookup"><span data-stu-id="a52b4-112">A "black-out" period for events such as vacations</span></span>  
  
-   <span data-ttu-id="a52b4-113">通过该门户不会发送重复警报间隔</span><span class="sxs-lookup"><span data-stu-id="a52b4-113">The interval over which the portal will not send duplicate alerts</span></span>  
  
 <span data-ttu-id="a52b4-114">你可以执行以下操作的添加警报订阅和编辑订阅页上：</span><span class="sxs-lookup"><span data-stu-id="a52b4-114">You can do the following on the Add Alert Subscription and Edit Subscription pages:</span></span>  
  
-   <span data-ttu-id="a52b4-115">选中的复选框旁边**自定义电子邮件**文本框中，如果你想要使用标准 Windows 帐户在电子邮件地址，不同的订阅的电子邮件地址，然后在文本框中键入首选电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a52b4-115">Select the check box next to the **Custom Email** text box if you want to use an e-mail address for the subscription that is different to your standard Windows account e-mail address, and then type the preferred e-mail address in the text box.</span></span>  
  
-   <span data-ttu-id="a52b4-116">选择顶部的复选框**计划**部分如果你想要指定当门户应将警报发送到你，，然后指定期的开始和结束时间的段**开始时间**和**结束时间**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a52b4-116">Select the check box at the top of the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **End Time** drop-down lists.</span></span> <span data-ttu-id="a52b4-117">发生此期之外的警报排队，并在指定时段内传递。</span><span class="sxs-lookup"><span data-stu-id="a52b4-117">Alerts occurring outside this period are queued and delivered during the specified period.</span></span>  
  
-   <span data-ttu-id="a52b4-118">键入的开始日期和结束日期**黑色超时期限**是否存在一段时间，当你将无法接收和处理的警报。</span><span class="sxs-lookup"><span data-stu-id="a52b4-118">Type the start date and end date for a **Black-out Period** if there is a period when you will be unable to receive and act on alerts.</span></span> <span data-ttu-id="a52b4-119">用于在两个日期的格式为 mm/dd/yyyy。</span><span class="sxs-lookup"><span data-stu-id="a52b4-119">Use the format mm/dd/yyyy for the two dates.</span></span>  
  
-   <span data-ttu-id="a52b4-120">选择**间隔**中**分钟**和相同警报的多个实例发生时发送只有一个的比较引发警报门户将过程。</span><span class="sxs-lookup"><span data-stu-id="a52b4-120">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="a52b4-121">这可以防止创建大量的相同警报消息快速出现错误。</span><span class="sxs-lookup"><span data-stu-id="a52b4-121">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
-   <span data-ttu-id="a52b4-122">单击**保存**按钮以创建或更新订阅。</span><span class="sxs-lookup"><span data-stu-id="a52b4-122">Click the **Save** button to create or update the subscription.</span></span>  
  
-   <span data-ttu-id="a52b4-123">单击**删除**按钮 （仅适用于编辑订阅页） 以删除所选的订阅。</span><span class="sxs-lookup"><span data-stu-id="a52b4-123">Click the **Delete** button (available only on the Edit Subscription page) to delete the selected subscription.</span></span>  
  
-   <span data-ttu-id="a52b4-124">单击**取消**按钮以返回到[警报查看器页面](../esb-toolkit/alert-viewer-page.md)而不创建或修改订阅。</span><span class="sxs-lookup"><span data-stu-id="a52b4-124">Click the **Cancel** button to go back to the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md) without creating or modifying the subscription.</span></span>