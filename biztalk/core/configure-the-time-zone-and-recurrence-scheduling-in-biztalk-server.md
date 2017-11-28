---
title: "配置的时区和重复计划在 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: "5"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 918d12e2dc96723327f4d0b0d2b0f0d435d6e42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a><span data-ttu-id="93f15-102">配置的时区和 BizTalk Server 中的重复执行计划</span><span class="sxs-lookup"><span data-stu-id="93f15-102">Configure the time zone and recurrence scheduling in BizTalk Server</span></span>
<span data-ttu-id="93f15-103">时区上并配置重复计划你接收中的位置[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93f15-103">Set the timezone and configure a recurrence schedule on your receive locations in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="93f15-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**上的高级计划功能接收位置包含一些选项。</span><span class="sxs-lookup"><span data-stu-id="93f15-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the advanced scheduling feature on receive locations includes some options.</span></span> <span data-ttu-id="93f15-105">使用高级的计划选项，设置时区，并且还设置重复执行计划。</span><span class="sxs-lookup"><span data-stu-id="93f15-105">Using the advanced scheduling options, set the time zone, and also set a recurrence schedule.</span></span>

<span data-ttu-id="93f15-106">本主题演示如何配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="93f15-106">This topic shows you how to configure these features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93f15-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="93f15-107">Prerequisites</span></span>
<span data-ttu-id="93f15-108">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93f15-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="time-zone"></a><span data-ttu-id="93f15-109">时区</span><span class="sxs-lookup"><span data-stu-id="93f15-109">Time zone</span></span>

<span data-ttu-id="93f15-110">**计划**接收位置的属性包括**时区**属性。</span><span class="sxs-lookup"><span data-stu-id="93f15-110">The **Schedule** properties of a receive location includes a **Time Zone** property.</span></span> <span data-ttu-id="93f15-111">设置时，而不是本地计算机上的时区使用你在接收位置中选择的时区。</span><span class="sxs-lookup"><span data-stu-id="93f15-111">When set, the time zone you choose in the receive location is used instead of the time zone on the local computer.</span></span> 

<span data-ttu-id="93f15-112">所有日期和时间在**计划**属性是特定于你选择的时区。</span><span class="sxs-lookup"><span data-stu-id="93f15-112">All dates and times in the **Schedule** properties are specific to the time zone you choose.</span></span> <span data-ttu-id="93f15-113">任何现有计划迁移到承载 BizTalk 管理数据库 (BizTalkMgmtDb) 的服务器的时区。</span><span class="sxs-lookup"><span data-stu-id="93f15-113">Any existing schedules are migrated to the time zone of the server hosting the BizTalk Management database (BizTalkMgmtDb).</span></span> 

<span data-ttu-id="93f15-114">你还可以调整为夏令时 (DST)。</span><span class="sxs-lookup"><span data-stu-id="93f15-114">You can also adjust for daylight saving time (DST).</span></span> <span data-ttu-id="93f15-115">选中后，计划将自动调整为你选择的时区的夏时制。</span><span class="sxs-lookup"><span data-stu-id="93f15-115">When checked, the schedule automatically adjusts to the daylight saving time of the time zone you choose.</span></span> <span data-ttu-id="93f15-116">如果组件，此选项可对计划没有任何影响：</span><span class="sxs-lookup"><span data-stu-id="93f15-116">This option has no impact on the schedule if:</span></span>

* <span data-ttu-id="93f15-117">指定的时区没有夏时制</span><span class="sxs-lookup"><span data-stu-id="93f15-117">The specified time zone does not have a daylight saving time</span></span>
* <span data-ttu-id="93f15-118">夏时制未观察到在你选择的时区</span><span class="sxs-lookup"><span data-stu-id="93f15-118">Daylight saving time is not observed in the time zone you choose</span></span>

## <a name="enable-recurrence-schedule"></a><span data-ttu-id="93f15-119">启用重复执行计划</span><span class="sxs-lookup"><span data-stu-id="93f15-119">Enable recurrence schedule</span></span>
1. <span data-ttu-id="93f15-120">在**BizTalk Server 管理**控制台中，右键单击其中一个你接收位置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="93f15-120">In the **BizTalk Server Administration** console, right-click one of your receive locations, and select **Properties**.</span></span> 
2. <span data-ttu-id="93f15-121">上**计划**页上，选择**启用服务窗口**。</span><span class="sxs-lookup"><span data-stu-id="93f15-121">On the **Scheduling** page, select **Enable service window**.</span></span> <span data-ttu-id="93f15-122">**开始时间**和**停止时间**设置允许运行计划的初始时间：</span><span class="sxs-lookup"><span data-stu-id="93f15-122">The **Start Time** and **Stop time** set the initial time the schedule is allowed to run:</span></span>

    ![启用的服务时段接收端口](../core/media/enable-service-windows-for-receive-port.PNG)

3. <span data-ttu-id="93f15-124">显示的其他计划选项：</span><span class="sxs-lookup"><span data-stu-id="93f15-124">The additional scheduling options are displayed:</span></span>

    ![有关高级计划接收端口](../core/media/advanced-scheduling-for-receive-port.PNG)

4. <span data-ttu-id="93f15-126">**重复**属性运行每个天、 周或月你选择的接收端口：</span><span class="sxs-lookup"><span data-stu-id="93f15-126">The **Recurrence** property runs the receive port every day, week, or month that you choose:</span></span> 

    1. <span data-ttu-id="93f15-127">使用**每日**重复运行接收端口每个*x*数天上, 启动**从**日期选择，并仅在**服务时段**你选择：</span><span class="sxs-lookup"><span data-stu-id="93f15-127">Use the **Daily** recurrence to run the receive port every *x* number of days, starting on the **From** date you choose, and only within the **service window** you choose:</span></span>

        ![每日计划](../core/media/daily-shcedule.png)

    2. <span data-ttu-id="93f15-129">使用**每周**重复上一周内，就能仅在特定的一天运行接收端口**服务窗口**你选择：</span><span class="sxs-lookup"><span data-stu-id="93f15-129">Use the **Weekly** recurrence to run the receive port on a specific day within a week, and only within the **service window** you choose:</span></span> 

        ![每周计划](../core/media/weekly-shcedule.png)

    3. <span data-ttu-id="93f15-131">使用**每月**定期在每月计划上运行的接收端口。</span><span class="sxs-lookup"><span data-stu-id="93f15-131">Use the **Monthly** recurrence to run the receive port on a monthly schedule.</span></span> <span data-ttu-id="93f15-132">**天**和**上**选项才可用。</span><span class="sxs-lookup"><span data-stu-id="93f15-132">The **Days** and **On** options are available.</span></span> 
    
        <span data-ttu-id="93f15-133">使用**天**重复周期内的特定日期运行接收端口**月**你选择：</span><span class="sxs-lookup"><span data-stu-id="93f15-133">Use the **Days** recurrence to run the receive port on specific dates within the **months** you choose:</span></span> 

        ![每月计划](../core/media/monthly-shcedule.PNG)

        <span data-ttu-id="93f15-135">使用**上**重复执行的特定天的月份上运行的接收端口：</span><span class="sxs-lookup"><span data-stu-id="93f15-135">Use the **On** recurrence to run the receive port on on specific days of the month:</span></span>

        ![每月按计划](../core/media/monthly-on-shcedule.PNG)

5. <span data-ttu-id="93f15-137">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="93f15-137">Select **OK** to save your changes.</span></span> 

## <a name="see-also"></a><span data-ttu-id="93f15-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93f15-138">See also</span></span>
[<span data-ttu-id="93f15-139">配置功能包</span><span class="sxs-lookup"><span data-stu-id="93f15-139">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)