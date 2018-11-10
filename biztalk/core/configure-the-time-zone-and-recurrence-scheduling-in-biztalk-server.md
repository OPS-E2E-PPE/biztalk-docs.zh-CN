---
title: 配置时区和重复周期在 BizTalk Server 中计划 |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe12e4fe81705d178520f02591f8179e47606f6c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753285"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a><span data-ttu-id="d1df2-102">配置时区和重复执行计划在 BizTalk Server 中</span><span class="sxs-lookup"><span data-stu-id="d1df2-102">Configure the time zone and recurrence scheduling in BizTalk Server</span></span>
<span data-ttu-id="d1df2-103">将时区设置和配置重复计划在应用中接收位置[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1df2-103">Set the timezone and configure a recurrence schedule on your receive locations in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="d1df2-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 上的高级计划功能接收位置包括一些选项。</span><span class="sxs-lookup"><span data-stu-id="d1df2-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the advanced scheduling feature on receive locations includes some options.</span></span> <span data-ttu-id="d1df2-105">使用高级计划选项，设置时区，并且还设置重复执行计划。</span><span class="sxs-lookup"><span data-stu-id="d1df2-105">Using the advanced scheduling options, set the time zone, and also set a recurrence schedule.</span></span>

<span data-ttu-id="d1df2-106">本主题演示如何配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="d1df2-106">This topic shows you how to configure these features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1df2-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="d1df2-107">Prerequisites</span></span>
<span data-ttu-id="d1df2-108">安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1df2-108">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="time-zone"></a><span data-ttu-id="d1df2-109">时区</span><span class="sxs-lookup"><span data-stu-id="d1df2-109">Time zone</span></span>

<span data-ttu-id="d1df2-110">**计划**接收位置的属性包括**时区**属性。</span><span class="sxs-lookup"><span data-stu-id="d1df2-110">The **Schedule** properties of a receive location includes a **Time Zone** property.</span></span> <span data-ttu-id="d1df2-111">设置时，而不是本地计算机上的时区使用接收位置中选择的时区。</span><span class="sxs-lookup"><span data-stu-id="d1df2-111">When set, the time zone you choose in the receive location is used instead of the time zone on the local computer.</span></span> 

<span data-ttu-id="d1df2-112">所有日期和时间中的**计划**属性是特定于您选择的时间区域。</span><span class="sxs-lookup"><span data-stu-id="d1df2-112">All dates and times in the **Schedule** properties are specific to the time zone you choose.</span></span> <span data-ttu-id="d1df2-113">任何现有计划将迁移到 BizTalk 管理数据库 (BizTalkMgmtDb) 的宿主服务器的时区。</span><span class="sxs-lookup"><span data-stu-id="d1df2-113">Any existing schedules are migrated to the time zone of the server hosting the BizTalk Management database (BizTalkMgmtDb).</span></span> 

<span data-ttu-id="d1df2-114">您还可以调整为夏令时 (DST)。</span><span class="sxs-lookup"><span data-stu-id="d1df2-114">You can also adjust for daylight saving time (DST).</span></span> <span data-ttu-id="d1df2-115">选中后，计划将自动调整为夏时制的时间区域选择。</span><span class="sxs-lookup"><span data-stu-id="d1df2-115">When checked, the schedule automatically adjusts to the daylight saving time of the time zone you choose.</span></span> <span data-ttu-id="d1df2-116">此选项没有任何影响计划如果：</span><span class="sxs-lookup"><span data-stu-id="d1df2-116">This option has no impact on the schedule if:</span></span>

* <span data-ttu-id="d1df2-117">指定的时区不具有夏时制</span><span class="sxs-lookup"><span data-stu-id="d1df2-117">The specified time zone does not have a daylight saving time</span></span>
* <span data-ttu-id="d1df2-118">在您选择的时间区域中未观察到夏时制</span><span class="sxs-lookup"><span data-stu-id="d1df2-118">Daylight saving time is not observed in the time zone you choose</span></span>

## <a name="enable-recurrence-schedule"></a><span data-ttu-id="d1df2-119">启用重复计划</span><span class="sxs-lookup"><span data-stu-id="d1df2-119">Enable recurrence schedule</span></span>
1. <span data-ttu-id="d1df2-120">在中**BizTalk Server 管理**控制台中，右键单击其中一个将接收位置，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="d1df2-120">In the **BizTalk Server Administration** console, right-click one of your receive locations, and select **Properties**.</span></span> 
2. <span data-ttu-id="d1df2-121">上**计划**页上，选择**启用服务时段**。</span><span class="sxs-lookup"><span data-stu-id="d1df2-121">On the **Scheduling** page, select **Enable service window**.</span></span> <span data-ttu-id="d1df2-122">**开始时间**并**停止时间**设置计划允许运行的初始时间：</span><span class="sxs-lookup"><span data-stu-id="d1df2-122">The **Start Time** and **Stop time** set the initial time the schedule is allowed to run:</span></span>

    ![启用服务 Windows 为接收端口](../core/media/enable-service-windows-for-receive-port.PNG)

3. <span data-ttu-id="d1df2-124">将显示其他计划选项：</span><span class="sxs-lookup"><span data-stu-id="d1df2-124">The additional scheduling options are displayed:</span></span>

    ![高级计划的接收端口](../core/media/advanced-scheduling-for-receive-port.PNG)

4. <span data-ttu-id="d1df2-126">**重复周期**属性在运行每个天、 周或月所选的接收端口：</span><span class="sxs-lookup"><span data-stu-id="d1df2-126">The **Recurrence** property runs the receive port every day, week, or month that you choose:</span></span> 

    1. <span data-ttu-id="d1df2-127">使用**每日**定期运行的接收端口每*x*数天，在启动**从**日期选择，并仅在**服务时段**你选择：</span><span class="sxs-lookup"><span data-stu-id="d1df2-127">Use the **Daily** recurrence to run the receive port every *x* number of days, starting on the **From** date you choose, and only within the **service window** you choose:</span></span>

        ![每日计划](../core/media/daily-schedule.png)

    2. <span data-ttu-id="d1df2-129">使用**每周**重复一周中并仅在特定的一天中运行的接收端口**服务时段**你选择：</span><span class="sxs-lookup"><span data-stu-id="d1df2-129">Use the **Weekly** recurrence to run the receive port on a specific day within a week, and only within the **service window** you choose:</span></span> 

        ![每周计划](../core/media/weekly-schedule.png)

    3. <span data-ttu-id="d1df2-131">使用**每月**重复周期每月计划上运行的接收端口。</span><span class="sxs-lookup"><span data-stu-id="d1df2-131">Use the **Monthly** recurrence to run the receive port on a monthly schedule.</span></span> <span data-ttu-id="d1df2-132">**天**并**上**选项才可用。</span><span class="sxs-lookup"><span data-stu-id="d1df2-132">The **Days** and **On** options are available.</span></span> 
    
        <span data-ttu-id="d1df2-133">使用**天**重复周期在特定的日期内运行的接收端口**月**你选择：</span><span class="sxs-lookup"><span data-stu-id="d1df2-133">Use the **Days** recurrence to run the receive port on specific dates within the **months** you choose:</span></span> 

        ![每月计划](../core/media/monthly-schedule.PNG)

        <span data-ttu-id="d1df2-135">使用**上**重复周期的每月特定天运行的接收端口：</span><span class="sxs-lookup"><span data-stu-id="d1df2-135">Use the **On** recurrence to run the receive port on specific days of the month:</span></span>

        ![每月按计划](../core/media/monthly-on-schedule.PNG)

5. <span data-ttu-id="d1df2-137">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="d1df2-137">Select **OK** to save your changes.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d1df2-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1df2-138">See also</span></span>
[<span data-ttu-id="d1df2-139">配置功能包</span><span class="sxs-lookup"><span data-stu-id="d1df2-139">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
